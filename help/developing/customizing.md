---
title: Personalizzazione dei componenti core
description: I componenti core implementano diversi pattern che consentono una facile personalizzazione, dal semplice stile al riutilizzo avanzato delle funzionalità.
role: Architetto, Sviluppatore, Amministratore
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '1109'
ht-degree: 3%

---


# Personalizzazione dei componenti core{#customizing-core-components}

I [Componenti core](overview.md) implementano diversi pattern che consentono una facile personalizzazione, dal semplice stile al riutilizzo avanzato delle funzionalità.

## Architettura flessibile {#flexible-architecture}

I componenti core sono stati progettati fin dall’inizio per essere flessibili ed estensibili. Una panoramica della loro architettura mostra dove è possibile effettuare personalizzazioni.

![Architettura dei componenti core](/help/assets/screen_shot_2018-12-07at093742.png)

* [La finestra di ](/help/get-started/authoring.md#edit-and-design-dialogs) dialogo Progettazione definisce le operazioni che gli autori possono o non possono eseguire nella finestra di dialogo di modifica.
* [La ](/help/get-started/authoring.md#edit-and-design-dialogs) finestra di dialogo di modifica mostra agli autori solo le opzioni che possono utilizzare.
* [Il ](#customizing-the-logic-of-a-core-component) modello Sling verifica e prepara il contenuto per la visualizzazione (modello).
* [Il risultato del ](#customizing-the-logic-of-a-core-component) modello Sling può essere serializzato in JSON per SPA casi d’uso.
* [HTL esegue il rendering ](#customizing-the-markup) HTML lato server per il rendering lato server tradizionale.
* [L&#39;](#customizing-the-markup) output HTML è semantico, accessibile, ottimizzato per i motori di ricerca e di facile stile.

E tutti i componenti core implementano il [Sistema di stili](#styling-the-components).

## AEM Project Archetype {#aem-project-archetype}

[AEM Project ](/help/developing/archetype/overview.md) Archetypecrealizza un progetto Adobe Experience Manager minimo come punto di partenza per i tuoi progetti, incluso un esempio di componente HTL personalizzato con SlingModels per la logica e la corretta implementazione dei componenti core con il modello proxy consigliato.

## Pattern di personalizzazione {#customization-patterns}

### Personalizzazione delle finestre di dialogo {#customizing-dialogs}

Puoi personalizzare le opzioni di configurazione disponibili nella finestra di dialogo di un componente core, che si tratti della finestra di dialogo di progettazione o della finestra di dialogo di modifica](/help/get-started/authoring.md).[

Ogni finestra di dialogo ha una struttura del nodo coerente. Si consiglia di replicare questa struttura in un componente ereditante in modo che le sezioni [Sling Resource Merger](https://docs.adobe.com/content/help/it-IT/experience-manager-64/developing/platform/sling-resource-merger.html) e [Nascondi condizioni](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html) possano essere utilizzate per nascondere, sostituire o riordinare la finestra di dialogo originale. La struttura da replicare è definita come qualsiasi cosa fino al livello del nodo dell&#39;elemento tabulazione.

Per essere pienamente compatibile con qualsiasi modifica apportata a una finestra di dialogo sulla sua versione corrente, è molto importante che le strutture al di sotto del livello dell’elemento di tabulazione non vengano toccate (nascoste, aggiunte, sostituite, riordinate, ecc.). Al contrario, un elemento tab del padre deve essere nascosto tramite la proprietà `sling:hideResource` (consulta [Proprietà Sling Resource Merger](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html)) e nuovi elementi tab aggiunti che contengono i campi di configurazione personalizzati. `sling:orderBefore` può essere utilizzato per riordinare gli elementi tabulazione, se necessario.

La finestra di dialogo seguente illustra la struttura di dialogo consigliata e come nascondere e sostituire una scheda ereditata come descritto in precedenza:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0"
          xmlns:jcr="https://www.jcp.org/jcr/1.0"
          xmlns:nt="https://www.jcp.org/jcr/nt/1.0"
          xmlns:granite="https://www.adobe.com/jcr/granite/1.0"
          jcr:primaryType="nt:unstructured">
    <content jcr:primaryType="nt:unstructured">
        <items jcr:primaryType="nt:unstructured">
            <tabs jcr:primaryType="nt:unstructured">
                <items jcr:primaryType="nt:unstructured">
                        <originalTab
                                jcr:primaryType="nt:unstructured"
                                sling:hideResource="true"/>
                        </originalTab>
                        <myTab
                               jcr:primaryType="nt:unstructured"
                               jcr:title="My Tab"
                               sling:resourceType="granite/ui/components/coral/foundation/container"/>
                               <!-- myTab content -->
                        </myTab>
                </items>
            </basic>
        </items>
    </content>
</jcr:root>
```

### Personalizzazione della logica di un componente core {#customizing-the-logic-of-a-core-component}

La logica di business per i componenti core è implementata in Sling Models. Questa logica può essere estesa utilizzando un pattern di delega Sling.

Ad esempio, il componente core titolo utilizza la proprietà `jcr:title` della risorsa richiesta per fornire il testo del titolo. Se non è definita alcuna proprietà `jcr:title` , viene implementato un fallback al titolo della pagina corrente. Desideriamo modificare il comportamento in modo che il titolo della pagina corrente sia sempre visualizzato.

Poiché l’implementazione dei modelli dei componenti core è privata, è necessario estenderla con un pattern di delega.

```java
@Model(adaptables = SlingHttpServletRequest.class,
       adapters = Title.class,
       resourceType = "myproject/components/pageHeadline")
public class PageHeadline implements Title {
    @ScriptVariable private Page currentPage;
    @Self @Via(type = ResourceSuperType.class)
    private Title title;
    @Override public String getText() {
        return currentPage.getTitle();
    }
    @Override public String getType() {
        return title.getType();
    }
}
```

Per ulteriori dettagli sul pattern di delega consulta l’articolo Wiki sui componenti core GitHub [Pattern di delega per modelli Sling](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models).

### Personalizzazione del markup {#customizing-the-markup}

A volte lo stile avanzato richiede una diversa struttura di marcatura del componente.

Questo può essere facilmente fatto copiando i file HTL che devono essere modificati dal componente core al componente proxy.

Riprendendo l’esempio del componente Breadcrumb core, per personalizzare l’output di markup, il file `breadcrumb.html` deve essere copiato nel componente specifico del sito che ha un `sling:resourceSuperTypes` che punta al componente Breadcrumb core.

### Stile dei componenti {#styling-the-components}

La prima forma di personalizzazione consiste nell’applicare gli stili CSS.

Per semplificarlo, i componenti core eseguono il rendering del markup semantico e seguono una convenzione di denominazione standard ispirata a [Bootstrap](https://getbootstrap.com/). Inoltre, per eseguire facilmente il targeting e lo spazio dei nomi degli stili per i singoli componenti, ogni componente core è racchiuso in un elemento DIV con le classi &quot; `cmp`&quot; e &quot; `cmp-<name>`&quot;.

Ad esempio, guardando il file HTL del componente Breadcrumb di base v1 : [breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html), la gerarchia degli elementi di output è `ol.breadcrumb > li.breadcrumb-item > a`. Quindi, per fare in modo che una regola CSS influisca solo sulla classe di breadcrumb di quel componente, tutte le regole devono essere precedute dal nome come mostrato di seguito:

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

Inoltre, ciascuno dei componenti core sfrutta la AEM [funzionalità Sistema di stili](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html) che consente agli autori di modelli di definire nomi di classe CSS aggiuntivi che possono essere applicati al componente dagli autori di pagine. Questo consente di definire per ogni modello un elenco di stili di componenti consentiti e se uno di questi deve essere applicato per impostazione predefinita a tutti i componenti di quel tipo.

## Compatibilità di aggiornamento delle personalizzazioni {#upgrade-compatibility-of-customizations}

Sono possibili tre diversi tipi di upgrade:

* aggiornamento della versione di AEM
* aggiornamento dei componenti core a una nuova versione secondaria
* aggiornamento dei componenti core a una versione principale

In genere, l’aggiornamento AEM a una nuova versione non influisce sui componenti core o sulle personalizzazioni eseguite, purché le versioni dei componenti supportino anche la nuova versione AEM in cui viene effettuata la migrazione e le personalizzazioni non utilizzano API che sono state [obsolete o rimosse](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/release-notes/deprecated-removed-features.html).

L’aggiornamento dei componenti core senza passare a una versione principale più recente non dovrebbe influenzare le personalizzazioni, purché vengano utilizzati i pattern di personalizzazione descritti in questa pagina.

Il passaggio a una versione principale più recente dei componenti core è compatibile solo per la struttura dei contenuti, ma potrebbe essere necessario eseguire il refactoring delle personalizzazioni. Per ogni versione di un componente verranno pubblicati registri di modifica chiari per evidenziare le modifiche che avrebbero un impatto sul tipo di personalizzazioni descritte in questa pagina.

## Supporto delle personalizzazioni {#support-of-customizations}

Come per qualsiasi componente AEM, è necessario tenere presenti una serie di elementi relativi alle personalizzazioni:

1. **Non modificare mai direttamente il codice dei componenti core.**

   Questo li renderebbe del tutto non supportati e renderebbe dolorosi gli aggiornamenti futuri dei componenti. Utilizza invece i metodi di personalizzazione descritti in questa pagina.

1. **Il codice personalizzato è di tua responsabilità.**

   Il nostro programma di supporto non copre il codice personalizzato e i problemi segnalati che non possono essere riprodotti con i componenti core di vaniglia che sono [utilizzati come documentato](/help/get-started/using.md) non sono qualificati.

1. **Funzionalità obsolete e rimosse.**

   Con ogni nuova versione di AEM in fase di aggiornamento, assicurati che tutte le API utilizzate siano ancora attuali tenendo d&#39;occhio la pagina [Funzioni obsolete e rimosse](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/release-notes/deprecated-removed-features.html) .

Consulta anche la sezione [Supporto componenti core](overview.md#core-component-support) .

**Articolo successivo:**

* [Utilizzo dei componenti core](/help/get-started/using.md) : scopri come utilizzare i componenti core nel tuo progetto.
* [Linee guida per i componenti](guidelines.md) : per scoprire i pattern di implementazione dei componenti core.
