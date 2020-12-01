---
title: Personalizzazione dei componenti core
description: I componenti core implementano diversi pattern che consentono una facile personalizzazione, dallo stile semplice al riutilizzo avanzato delle funzionalità.
translation-type: tm+mt
source-git-commit: fe8a121520000ffd56ae3347469590e89121eaf0
workflow-type: tm+mt
source-wordcount: '1106'
ht-degree: 3%

---


# Personalizzazione dei componenti core{#customizing-core-components}

I [Componenti di base](overview.md) implementano diversi pattern che consentono una facile personalizzazione, dal semplice stile al riutilizzo avanzato delle funzionalità.

## Architettura flessibile {#flexible-architecture}

I componenti core sono stati progettati fin dall&#39;inizio per essere flessibili ed estensibili. Una panoramica della loro architettura mostra dove è possibile effettuare delle personalizzazioni.

![Architettura dei componenti core](/help/assets/screen_shot_2018-12-07at093742.png)

* [La ](/help/get-started/authoring.md#edit-and-design-dialogs) finestra di dialogo Progettazione definisce le operazioni che gli autori possono o non possono eseguire nella finestra di dialogo di modifica.
* [La ](/help/get-started/authoring.md#edit-and-design-dialogs) finestra di dialogo di modifica mostra solo agli autori le opzioni consentite.
* [Il ](#customizing-the-logic-of-a-core-component) modello Sling verifica e prepara il contenuto per la visualizzazione (modello).
* [Il risultato del ](#customizing-the-logic-of-a-core-component) modello Sling può essere serializzato su JSON per SPA casi di utilizzo.
* [HTL esegue il rendering ](#customizing-the-markup) HTMLserver-side per il tradizionale rendering lato server.
* [L&#39;](#customizing-the-markup) output HTML è semantico, accessibile, ottimizzato per i motori di ricerca e di facile stile.

E tutti i componenti core implementano il [Sistema di stile](#styling-the-components).

## AEM Project Archetype {#aem-project-archetype}

[AEM Project ](/help/developing/archetype/overview.md) Archetyspecifica un progetto Adobe Experience Manager minimo come punto di partenza per i vostri progetti, incluso un esempio di componente HTL personalizzato con SlingModels per la logica e la corretta implementazione dei componenti core con il pattern proxy consigliato.

## Pattern di personalizzazione {#customization-patterns}

### Personalizzazione delle finestre di dialogo {#customizing-dialogs}

Può essere utile personalizzare le opzioni di configurazione disponibili in una finestra di dialogo del componente principale, sia che si tratti della finestra di dialogo [Progettazione o della finestra di dialogo di modifica](/help/get-started/authoring.md).

Ogni finestra di dialogo ha una struttura di nodi coerente. È consigliabile che questa struttura venga replicata in un componente ereditario in modo che [Sling Resource Merger](https://docs.adobe.com/content/help/it-IT/experience-manager-64/developing/platform/sling-resource-merger.html) e [Nascondi condizioni](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html) possano essere utilizzate per nascondere, sostituire o riordinare le sezioni della finestra di dialogo originale. La struttura da replicare è definita come qualsiasi cosa fino al livello del nodo dell&#39;elemento tabulazione.

Per essere pienamente compatibile con qualsiasi modifica apportata a una finestra di dialogo sulla versione corrente, è molto importante che le strutture al di sotto del livello dell&#39;elemento tabulazione non vengano toccate (nascoste, aggiunte, sostituite, riordinate, ecc.). Al contrario, un elemento scheda dell&#39;elemento padre deve essere nascosto tramite la proprietà `sling:hideResource` (vedere [Proprietà fusione risorse Sling](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html)) e nuovi elementi di scheda aggiunti che contengono i campi di configurazione personalizzati. `sling:orderBefore` può essere utilizzato per riordinare gli elementi tabulazione, se necessario.

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

La business logic per i componenti core è implementata in Sling Models. Questa logica può essere estesa utilizzando un pattern di delega Sling.

Ad esempio, il componente core del titolo utilizza la proprietà `jcr:title` della risorsa richiesta per fornire il testo del titolo. Se non è definita alcuna proprietà `jcr:title`, viene implementato un fallback al titolo della pagina corrente. Modificare il comportamento in modo che il titolo della pagina corrente sia sempre visualizzato.

Poiché l&#39;implementazione dei modelli dei componenti core è privata, è necessario estenderli con un pattern di delega.

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

Per ulteriori dettagli sul modello di delega vedere l&#39;articolo Wiki sui componenti core di GitHub [Pattern di delega per i modelli Sling](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models).

### Personalizzazione del codice {#customizing-the-markup}

A volte lo stile avanzato richiede una diversa struttura di marcatura del componente.

Questo può essere fatto facilmente copiando i file HTL che devono essere modificati dal componente core al componente proxy.

Riprendendo l&#39;esempio del componente Breadcrumb di base, per personalizzare l&#39;output del codice, il file `breadcrumb.html` deve essere copiato nel componente specifico del sito che ha un `sling:resourceSuperTypes` che punta al componente Breadcrumb di base.

### Attribuzione dello stile ai componenti {#styling-the-components}

La prima forma di personalizzazione consiste nell&#39;applicare gli stili CSS.

Per semplificare questa procedura, i componenti core eseguono il rendering dei commenti semantici e seguono una convenzione di denominazione standard ispirata a [Bootstrap](https://getbootstrap.com/). Inoltre, per definire facilmente gli stili dei singoli componenti, ogni componente core è racchiuso in un elemento DIV con le classi &quot; `cmp`&quot; e &quot; `cmp-<name>`&quot;.

Ad esempio, guardando il file HTL del componente Breadcrumb v1 core: [breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html), la gerarchia degli elementi di output è `ol.breadcrumb > li.breadcrumb-item > a`. Per essere certi che una regola CSS influisca solo sulla classe di breadcrumb del componente, tutte le regole devono essere spaccate con il nome, come illustrato di seguito:

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

Inoltre, ciascuno dei componenti core utilizza la AEM [funzione Style System](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html) che consente agli autori dei modelli di definire nomi di classe CSS aggiuntivi che possono essere applicati al componente dagli autori delle pagine. Questo consente di definire per ciascun modello un elenco degli stili di componente consentiti e se uno di essi deve essere applicato per impostazione predefinita a tutti i componenti di tale tipo.

## Compatibilità di aggiornamento delle personalizzazioni {#upgrade-compatibility-of-customizations}

Sono possibili tre diversi tipi di upgrade:

* aggiornamento della versione di AEM
* aggiornamento dei componenti core a una nuova versione secondaria
* aggiornamento dei componenti core a una versione principale

In genere, l&#39;aggiornamento AEM a una nuova versione non influirà sui componenti core o sulle personalizzazioni eseguite, a condizione che le versioni dei componenti supportino anche la nuova versione AEM a cui viene eseguita la migrazione e che le personalizzazioni non utilizzino API [obsolete o rimosse](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/release-notes/deprecated-removed-features.html).

L&#39;aggiornamento dei componenti core senza passare a una versione principale più recente non dovrebbe influenzare le personalizzazioni, purché siano utilizzati i pattern di personalizzazione descritti in questa pagina.

Il passaggio a una nuova versione principale dei componenti core è compatibile solo per la struttura del contenuto, ma potrebbe essere necessario reimpostare le personalizzazioni. Per ogni versione di componente verranno pubblicati registri di modifiche chiare per evidenziare le modifiche che influirebbero sul tipo di personalizzazioni descritto in questa pagina.

## Supporto delle personalizzazioni {#support-of-customizations}

Come per qualsiasi componente AEM, è necessario conoscere una serie di aspetti relativi alle personalizzazioni:

1. **Non modificare mai direttamente il codice dei componenti core.**

   In questo modo non saranno completamente supportati e i futuri aggiornamenti dei componenti risulteranno dolorosi. Utilizzate, invece, i metodi di personalizzazione descritti in questa pagina.

1. **Il codice personalizzato è una vostra responsabilità.**

   Il nostro programma di supporto non copre il codice personalizzato, e i problemi segnalati che non possono essere riprodotti con i componenti di base della vaniglia che sono [utilizzati come documentato](/help/get-started/using.md) non saranno idonei.

1. **Funzionalità obsolete e rimosse.**

   Con l&#39;aggiornamento di ogni nuova versione AEM, accertati che tutte le API utilizzate siano ancora di attualità, controllando la pagina [Funzioni obsolete e rimosse](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/release-notes/deprecated-removed-features.html).

Vedere anche la sezione [Supporto componenti core](overview.md#core-component-support).

**Articolo successivo:**

* [Utilizzo dei componenti](/help/get-started/using.md)  di base: per iniziare a usare i componenti di base nel tuo progetto.
* [Linee guida](guidelines.md)  per i componenti - per apprendere i pattern di implementazione dei componenti core.
