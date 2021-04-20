---
title: Utilizzo di Adobe Client Data Layer con i componenti core
description: Utilizzo di Adobe Client Data Layer con i componenti core
feature: Core Components, Adobe Client Data Layer
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 5%

---


# Utilizzo di Adobe Client Data Layer con i componenti core {#data-layer-core-components}

L’obiettivo di Adobe Client Data Layer è ridurre lo sforzo di strumenti sui siti web fornendo un metodo standardizzato per esporre e accedere a qualsiasi tipo di dati per qualsiasi script.

Adobe Client Data Layer è indipendente dalla piattaforma, ma è completamente integrato nei componenti core per l’utilizzo con AEM.

Come i componenti core, il codice per Adobe Client Data Layer è disponibile su GitHub insieme alla relativa documentazione per gli sviluppatori. Questo documento fornisce una panoramica dell’interazione dei componenti core con Data Layer, ma i dettagli tecnici completi vengono differiti alla documentazione GitHub.

>[!TIP]
>
>Per ulteriori informazioni su Adobe Client Data Layer, [fai riferimento alle risorse nel relativo archivio GitHub.](https://github.com/adobe/adobe-client-data-layer)
>
>Per ulteriori dettagli tecnici sull’integrazione di Adobe Client Data Layer con i componenti core, consulta il file [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) nell’archivio dei componenti core.

## Installazione e attivazione {#installation-activation}

A partire dalla versione 2.9.0 dei componenti core, il livello dati è distribuito con i componenti core come libreria client AEM e non è necessaria alcuna installazione. Tutti i progetti generati da [AEM Project Archetype v. 24+](/help/developing/archetype/overview.md) includono un Data Layer attivato per impostazione predefinita.

Per attivare manualmente il Livello dati è necessario creare una [configurazione consapevole del contesto](/help/developing/context-aware-configs.md) per tale configurazione:

1. Crea la seguente struttura sotto la cartella `/conf/<mySite>` , dove `<mySite>` è il nome del progetto del sito:
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * Dove ogni nodo ha un `jcr:primaryType` impostato su `nt:unstructured`.
1. Aggiungi una proprietà booleana denominata `enabled` e impostala su `true`.

   ![Posizione di DataLayerConfig nel sito di riferimento WKND](/help/assets/datalayer-contextaware-sling-config.png)

   *Posizione di DataLayerConfig nel sito di riferimento WKND*

1. Aggiungi una proprietà `sling:configRef` al nodo `jcr:content` del sito sotto `/content` (ad esempio `/content/<mySite>/jcr:content`) e impostalo su `/conf/<mySite>` dal passaggio precedente.

1. Una volta abilitata, puoi verificare l’attivazione caricando una pagina del sito all’esterno dell’editor, ad esempio utilizzando l’opzione **Visualizza come pubblicato** nell’editor. Inspect la sorgente della pagina e il tag `<body>` devono includere un attributo `data-cmp-data-layer-enabled`

   ```html
   <body class="page basicpage" id="page-id" data-cmp-data-layer-enabled>
       <script>
         window.adobeDataLayer = window.adobeDataLayer || [];
         adobeDataLayer.push({
             page: JSON.parse("{\x22page\u002D6c5d4b9fdd\x22:{\x22xdm:language\x22:\x22en\x22,\x22repo:path\x22:\x22\/content\/wknd\/language\u002Dmasters\/en.html\x22,\x22xdm:tags\x22:[],\x22xdm:template\x22:\x22\/conf\/wknd\/settings\/wcm\/templates\/landing\u002Dpage\u002Dtemplate\x22,\x22@type\x22:\x22wknd\/components\/page\x22,\x22dc:description\x22:\x22WKND is a collective of outdoors, music, crafts, adventure sports, and travel enthusiasts that want to share our experiences, connections, and expertise with the world.\x22,\x22dc:title\x22:\x22WKND Adventures and Travel\x22,\x22repo:modifyDate\x22:\x222020\u002D09\u002D29T07:50:13Z\x22}}"),
             event:'cmp:show',
             eventInfo: {
                 path: 'page.page\u002D6c5d4b9fdd'
             }
         });
       </script>
   ```

1. Puoi anche aprire gli strumenti di sviluppo del browser e nella console l’ `adobeDataLayer` oggetto JavaScript dovrebbe essere disponibile. Immetti il seguente comando per ottenere lo stato del livello dati della pagina corrente:

   ```javascript
   window.adobeDataLayer.getState();
   ```

## Componenti supportati {#supported-components}

I seguenti componenti supportano il livello dati.

* [Pannello a soffietto](/help/components/accordion.md)
* [Breadcrumb](/help/components/breadcrumb.md)
* [Pulsante](/help/components/button.md)
* [Carosello](/help/components/carousel.md)
* [Frammento di contenuto](/help/components/content-fragment-component.md)
* [Immagine](/help/components/image.md)
* [Navigazione lingua](/help/components/language-navigation.md)
* [Elenco](/help/components/list.md)
* [Navigazione](/help/components/navigation.md)
* [Pagina](/help/components/page.md)
* [Barra di avanzamento](/help/components/progress-bar.md)
* [Schede](/help/components/tabs.md)
* [Teaser](/help/components/teaser.md)
* [Testo](/help/components/text.md)
* [Titolo](/help/components/title.md)

Fare riferimento anche agli eventi [attivati dai componenti.](#events-components)

## Schemi di dati dei componenti core {#data-schemas}

Di seguito è riportato un elenco di schemi utilizzati dai componenti core con Data Layer.

### Schema elemento componente/contenitore {#item}

Lo schema Componente/Elemento contenitore viene utilizzato nei seguenti componenti:

* [Breadcrumb](/help/components/breadcrumb.md)
* [Pulsante](/help/components/button.md)
* [Navigazione lingua](/help/components/language-navigation.md)
* [Elenco](/help/components/list.md)
* [Navigazione](/help/components/navigation.md)
* [Teaser](/help/components/teaser.md)
* [Testo](/help/components/text.md)
* [Titolo](/help/components/title.md)

Lo schema Componente/Elemento contenitore è definito come segue.

```javascript
id: {                   // component ID
    @type               // resource type
    repo:modifyDate     // last modified date
    dc:title            // title
    dc:description      // description
    xdm:text            // text
    xdm:linkURL         // link URL
    parentId            // parent component ID
}
```

Il seguente [evento](#events) è pertinente allo schema Componente/Elemento contenitore :

* `cmp:click`

### Schema pagina {#page}

Lo schema Pagina viene utilizzato dal componente seguente:

* [Pagina](/help/components/page.md)

Lo schema Pagina è definito come segue.

```javascript
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    xdm:tags            // page tags
    repo:path           // page path
    xdm:template        // page template
    xdm:language        // page language
}
```

Un evento `cmp:show` viene attivato al caricamento della pagina. Questo evento viene inviato da JavaScript in linea immediatamente sotto il tag di apertura `<body>` , rendendolo il primo evento nella coda degli eventi Livello dati .

### Schema contenitore {#container}

Lo schema Contenitore viene utilizzato dai seguenti componenti:

* [Pannello a soffietto](/help/components/accordion.md)
* [Schede](/help/components/tabs.md)
* [Carosello](/help/components/carousel.md)

Lo schema del contenitore è definito come segue.

```javascript
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    shownItems          // array of the displayed item IDs
}
```

I seguenti [eventi](#events) sono pertinenti allo schema del contenitore:

* `cmp:click`
* `cmp:show`
* `cmp:hide`

### Schema immagine {#image}

Lo schema immagine viene utilizzato dal componente seguente:

* [Immagine](/help/components/image.md)

Lo schema immagine è definito come segue.

```javascript
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    image               // asset detail (see below section)
}
```

Il seguente [evento](#events) è pertinente allo schema immagine:

* `cmp:click`

### Schema risorse {#asset}

Lo schema Risorsa viene utilizzato all&#39;interno del componente [Immagine.](/help/components/image.md)

Lo schema delle risorse è definito come segue.

```javascript
id: {
    repo:id             // asset UUID
    repo:path           // asset path
    @type               // asset resource type
    xdm:tags            // asset tags
    repo:modifyDate
}
```

Il seguente [evento](#events) è pertinente allo schema Risorsa:

* `cmp:click`

### Schema frammento di contenuto {#content-fragment}

Lo schema Frammento di contenuto viene utilizzato dal componente [Frammento di contenuto.](/help/components/content-fragment-component.md)

Lo schema Frammento di contenuto è definito come segue.

```javascript
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    elements            // array of the Content Fragment elements
}
```

Lo schema utilizzato per l’elemento Frammento di contenuto è il seguente.

```javascript
{
    xdm:title           // title
    xdm:text            // text
}
```

## Eventi dei componenti core {#events}

Esistono diversi eventi che i componenti core attivano tramite il livello dati. La best practice per interagire con il Livello dati è quella di [registrare un listener di eventi](https://github.com/adobe/adobe-client-data-layer/wiki#addeventlistener) e *then* eseguire un&#39;azione in base al tipo di evento e/o al componente che ha attivato l&#39;evento. In questo modo si evitano potenziali condizioni di corsa con script asincroni.

Di seguito sono riportati gli eventi predefiniti forniti dai componenti core AEM:

* **`cmp:click`** - Facendo clic su un elemento cliccabile (un elemento con un  `data-cmp-clickable` attributo) il livello dati attiva un  `cmp:click` evento.
* **`cmp:show`** e  **`cmp:hide`** - La manipolazione del pannello a soffietto (espandi/comprimi), del carosello (pulsanti successivo/precedente) e delle schede (selezione scheda) determina l’attivazione del livello dati  `cmp:show` e di un  `cmp:hide` evento rispettivamente. Anche un evento `cmp:show` viene inviato al caricamento della pagina e deve essere il primo evento.
* **`cmp:loaded`** - Non appena il Livello dati viene popolato con i Componenti core nella pagina, il Livello dati attiva un  `cmp:loaded` evento.

### Eventi attivati dal componente {#events-components}

Nelle tabelle seguenti sono elencati i componenti core standard che attivano gli eventi insieme a tali eventi.

| Componente | Evento/i |
|---|---|
| [Pannello a soffietto](/help/components/accordion.md) | `cmp:show` e `cmp:hide` |
| [Pulsante](/help/components/button.md) | `cmp:click` |
| [Breadcrumb](/help/components/breadcrumb.md) | `cmp:click` |
| [Carosello](/help/components/carousel.md) | `cmp:show` e `cmp:hide` |
| [Navigazione lingua](/help/components/language-navigation.md) | `cmp:click` |
| [Navigazione](/help/components/navigation.md) | `cmp:click` |
| [Pagina](/help/components/page.md) | `cmp:show` |
| [Schede](/help/components/tabs.md) | `cmp:show` e `cmp:hide` |
| [Teaser](/help/components/teaser.md) | `cmp:click` |

### Informazioni percorso evento {#event-path-info}

Ogni evento Livello dati attivato da un componente di base AEM includerà un payload con il seguente oggetto JSON:

```json
eventInfo: {
    path: '<component-path>'
}
```

Dove `<component-path>` è il percorso JSON del componente nel Livello dati che ha attivato l’evento.  Il valore, disponibile tramite `event.eventInfo.path`, è importante in quanto può essere utilizzato come parametro per `adobeDataLayer.getState(<component-path>)` che recupera lo stato corrente del componente che ha attivato l’evento, consentendo al codice personalizzato di accedere ai dati aggiuntivi e aggiungerlo al livello dati.

Esempio:

```javascript
function logEventObject(event) {
    if(event.hasOwnProperty("eventInfo") && event.eventInfo.hasOwnProperty("path")) {
        var dataObject = window.adobeDataLayer.getState(event.eventInfo.path);
        console.debug("The component that triggered this event: ");
        console.log(dataObject);
    }
}

window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push(function (dl) {
     dl.addEventListener("cmp:show", logEventObject);
});
```

## Esercitazione

Vuoi esplorare più dettagliatamente i livelli dati e i componenti core? [Guarda questo tutorial](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/adobe-client-data-layer/data-layer-overview.html) pratico.

>[!TIP]
>
>Per esplorare ulteriormente la flessibilità di Data Layer, controlla le opzioni di integrazione, tra cui come abilitare Data Layer per i componenti personalizzati.
