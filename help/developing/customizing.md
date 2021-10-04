---
title: Personalizzazione dei Componenti core
description: I Componenti core implementano diversi modelli che consentono una facile personalizzazione, dalla semplice assegnazione di uno stile al riutilizzo di funzionalità avanzate.
role: Architect, Developer, Admin
exl-id: ec4b918b-bc70-4d72-ba84-a24556aedb41
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 98%

---

# Personalizzazione dei Componenti core{#customizing-core-components}

I [Componenti core](overview.md) implementano diversi modelli che consentono una facile personalizzazione, dalla semplice assegnazione di uno stile al riutilizzo di funzionalità avanzate.

## Architettura flessibile {#flexible-architecture}

I Componenti core sono stati concepiti per essere flessibili ed estensibili. Una panoramica della loro architettura rivela dove è possibile effettuare personalizzazioni.

![Architettura dei Componenti core](/help/assets/screen_shot_2018-12-07at093742.png)

* [La finestra di dialogo per progettazione](/help/get-started/authoring.md#edit-and-design-dialogs) definisce le operazioni che gli autori possono o non possono eseguire nella finestra di dialogo per modifica.
* [La finestra di dialogo per modifica](/help/get-started/authoring.md#edit-and-design-dialogs) mostra agli autori solo le opzioni che possono utilizzare.
* [Il modello Sling](#customizing-the-logic-of-a-core-component) verifica e prepara il contenuto per la visualizzazione (modello).
* [Il risultato del modello Sling](#customizing-the-logic-of-a-core-component) può essere serializzato in output JSON per i casi d’uso SPA (Single Page App).
* [Gli script HTL eseguono il rendering del codice HTML](#customizing-the-markup) lato server per il rendering lato server tradizionale.
* [L’output HTML](#customizing-the-markup) è semantico, accessibile, ottimizzato per i motori di ricerca e di facile applicazione degli stili.

Tutti i Componenti core implementano il [Sistema di stili](#styling-the-components).

## Archetipo progetto AEM {#aem-project-archetype}

[L’Archetipo progetto AEM](/help/developing/archetype/overview.md) crea un progetto Adobe Experience Manager minimo come punto di partenza per i tuoi progetti, incluso un esempio di componente HTL personalizzato con i modelli Sling per la logica e la corretta implementazione dei Componenti core con il modello proxy consigliato.

## Modelli di personalizzazione {#customization-patterns}

### Personalizzazione delle finestre di dialogo {#customizing-dialogs}

Potrebbe risultare conveniente personalizzare le opzioni di configurazione disponibili nella finestra di dialogo di un Componente core, che si tratti della [finestra di dialogo per progettazione o della finestra di dialogo per modifica](/help/get-started/authoring.md).

Ogni finestra di dialogo ha una struttura di nodi coerente. Si consiglia di replicare questa struttura in un componente ereditante, in modo che le opzioni [Sling Resource Merger](https://helpx.adobe.com/it/experience-manager/6-4/sites/developing/using/sling-resource-merger.html) e [Nascondi condizioni](https://experienceleague.adobe.com/docs/experience-manager-65/developing/components/hide-conditions.html?lang=it) possano essere utilizzate per nascondere, sostituire o riordinare le sezioni della finestra di dialogo originale. La struttura da replicare è definita fino al livello del nodo dell’elemento Scheda.

Per essere pienamente compatibile con qualsiasi modifica apportata a una finestra di dialogo nella sua versione corrente, è molto importante che le strutture al di sotto del livello dell’elemento Scheda non vengano toccate (nascoste, aggiunte, sostituite, riordinate, ecc.). Al contrario, un elemento Scheda derivato dall’elemento padre deve essere nascosto tramite la proprietà `sling:hideResource` (vedi [Proprietà di Sling Resource Merger](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html?lang=it)) e devono essere aggiunti nuovi elementi Scheda contenenti i campi di configurazione personalizzati. La proprietà `sling:orderBefore` può essere utilizzata per riordinare gli elementi Scheda, se necessario.

La finestra di dialogo che segue illustra la struttura consigliata e come nascondere e sostituire una scheda ereditata come descritto in precedenza:

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

### Personalizzazione della logica di un Componente core {#customizing-the-logic-of-a-core-component}

La logica di business dei Componenti core è implementata nei modelli Sling. Questa logica può essere estesa utilizzando un modello di delega Sling.

Ad esempio, il componente core Titolo utilizza la proprietà `jcr:title` della risorsa richiesta per fornire il testo del titolo. Se la proprietà `jcr:title` non è definita, viene effettuato un regresso al titolo della pagina corrente. Noi vogliamo modificare questo comportamento, in modo che il titolo della pagina corrente sia sempre visualizzato.

Poiché l’implementazione dei modelli dei Componenti core è privata, è necessario estenderla con un modello di delega.

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

Per ulteriori dettagli sul modello di delega, vedi l’articolo Wiki sui Componenti core [Modello di delega per modelli Sling](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models) in GitHub.

### Personalizzazione del markup {#customizing-the-markup}

A volte gli stili avanzati richiedono una diversa struttura di markup del componente.

Ciò può essere fatto facilmente copiando i file HTL che devono essere modificati dal Componente core al [componente proxy.](guidelines.md#proxy-component-pattern)

Riprendendo l’esempio del componente core Breadcrumb, core, per personalizzare l’output di markup, il file `breadcrumb.html` deve essere copiato nel componente specifico del sito che ha la proprietà `sling:resourceSuperTypes` che punta al componente core Breadcrumb.

### Definizione degli stili dei componenti {#styling-the-components}

La prima forma di personalizzazione consiste nell’applicare gli stili CSS.

Per semplificare questa operazione, i Componenti core forniscono un markup semantico e seguono una convenzione di denominazione standard ispirata a [Bootstrap](https://getbootstrap.com/). Inoltre, per individuare e denominare gli stili dei singoli componenti, ciascun Componente core è racchiuso in un elemento DIV con le classi “`cmp`” e “`cmp-<name>`”.

Ad esempio, osservando il file HTL del componente core Breadcrumb v1: [breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html), notiamo che la gerarchia degli dell’output degli elementi è `ol.breadcrumb > li.breadcrumb-item > a`. Quindi, per fare in modo che una regola CSS influisca solo sulla classe di breadcrumb di quel componente, tutte le regole devono denominate come indicato di seguito:

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

Inoltre, ciascuno dei Componenti core utilizza la [funzionalità Sistema di stili](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html) di AEM che consente agli autori di modelli di definire nomi di classi CSS aggiuntivi che possono essere applicati al componente dagli autori delle pagine. Ciò consente di definire per ogni modello un elenco di stili di consentiti e se uno di questi deve essere applicato per impostazione predefinita a tutti i componenti di quel tipo.

## Compatibilità degli aggiornamenti delle personalizzazioni {#upgrade-compatibility-of-customizations}

Sono possibili tre diversi tipi di aggiornamento:

* Aggiornamento della versione di AEM
* Aggiornamento dei Componenti core a una nuova versione secondaria
* Aggiornamento dei Componenti core a una versione principale

In genere, l’aggiornamento di AEM a una nuova versione non influisce sui Componenti core o sulle personalizzazioni eseguite, purché le versioni dei componenti supportino anche la nuova versione di AEM a cui viene effettuata la migrazione e le personalizzazioni non utilizzino API che sono state dichiarate [obsolete oppure rimosse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html).

L’aggiornamento dei Componenti core senza passare a una versione principale più recente non dovrebbe influire sulle personalizzazioni, purché vengano utilizzati i modelli di personalizzazione descritti in questa pagina.

Il passaggio a una versione principale più recente dei Componenti core è compatibile solo per la struttura del contenuto, ma potrebbe essere necessario eseguire il refactoring delle personalizzazioni. Per ogni versione di un componente verranno pubblicati registri di modifica chiari per evidenziare le modifiche che avrebbero un impatto sul tipo di personalizzazioni descritte in questa pagina.

## Supporto delle personalizzazioni {#support-of-customizations}

Come per qualsiasi componente AEM, occorre essere consapevoli di alcune situazioni concernenti le personalizzazioni:

1. **Non modificare mai direttamente il codice dei Componenti core.**

   Questo li renderebbe del tutto non supportati e renderebbe estremamente complessi i futuri aggiornamenti dei componenti. Utilizza invece i metodi di personalizzazione descritti in questa pagina.

1. **Il codice personalizzato è di tua esclusiva responsabilità.**

   Il nostro programma di supporto non copre il codice personalizzato e i problemi segnalati, che non possono essere riprodotti con i Componenti core “vanilla” [utilizzati come da documentazione](/help/get-started/using.md), non sono idonei per il supporto.

1. **Attenzione alle funzionalità obsolete e rimosse.**

   Quando ti aggiorni a nuova versione di AEM, accertati che tutte le API utilizzate siano ancora attuali visitando la pagina [Funzioni obsolete e rimosse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html).

Vedi anche la sezione [Supporto dei componenti core](overview.md#core-component-support).

**Articolo successivo:**

* [Utilizzo dei componenti core](/help/get-started/using.md): scopri come utilizzare i Componenti core nel tuo progetto.
* [Linee guida per i componenti](guidelines.md): per scoprire i modelli di implementazione dei Componenti core.
