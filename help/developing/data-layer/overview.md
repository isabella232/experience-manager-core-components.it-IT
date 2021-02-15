---
title: Utilizzo del livello dati client del Adobe  con i componenti core
description: Utilizzo del livello dati client del Adobe  con i componenti core
translation-type: tm+mt
source-git-commit: 57582c5c938e0f345b27785bd6fd6d5ed5454bd0
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 5%

---


# Utilizzo del livello dati client del Adobe  con i componenti core {#data-layer-core-components}

L&#39;obiettivo di  Client Data Layer del Adobe è quello di ridurre lo sforzo di strumentalizzare i siti Web fornendo un metodo standardizzato per esporre e accedere a qualsiasi tipo di dati per qualsiasi script.

Il livello dati client del Adobe  è agnostico della piattaforma, ma è completamente integrato nei componenti core per l&#39;utilizzo con AEM.

Come per i componenti core, il codice per  Client Data Layer è disponibile su GitHub con la relativa documentazione per lo sviluppo. Questo documento fornisce una panoramica di come i componenti core interagiscono con il livello dati, ma i dettagli tecnici completi sono differiti alla documentazione GitHub.

>[!TIP]
>
>Per ulteriori informazioni sul livello dati client del Adobe , [fare riferimento alle risorse presenti nel repository GitHub.](https://github.com/adobe/adobe-client-data-layer)
>
>Per ulteriori dettagli tecnici sull&#39;integrazione del livello dati client del Adobe  con i componenti core, vedere il file [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) nell&#39;archivio dei componenti core.

## Installazione e attivazione {#installation-activation}

A partire dalla release 2.9.0 dei componenti core, il livello dati è distribuito con i componenti core come libreria client AEM e non è necessaria alcuna installazione. Tutti i progetti generati dal [AEM Project Archetype v. 24+](/help/developing/archetype/overview.md) includono per impostazione predefinita un Data Layer attivato.

Per attivare manualmente il Livello dati è necessario creare una [configurazione sensibile al contesto](/help/developing/context-aware-configs.md) per tale configurazione:

1. Create la struttura seguente sotto la cartella `/conf/<mySite>`, dove `<mySite>` è il nome del progetto del sito:
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * Dove ogni nodo ha un `jcr:primaryType` impostato su `nt:unstructured`.
1. Aggiungete una proprietà booleana denominata `enabled` e impostatela su `true`.

   ![Posizione di DataLayerConfig nel sito di riferimento WKND](/help/assets/datalayer-contextaware-sling-config.png)

   *Posizione di DataLayerConfig nel sito di riferimento WKND*

1. Aggiungere una proprietà `sling:configRef` al nodo `jcr:content` del sito sotto `/content` (ad es. `/content/<mySite>/jcr:content`) e impostarlo su `/conf/<mySite>` dal passaggio precedente.

1. Una volta attivata questa opzione, è possibile verificare l&#39;attivazione caricando una pagina del sito all&#39;esterno dell&#39;editor, ad esempio utilizzando l&#39;opzione **Visualizza come pubblicato** nell&#39;editor.  Inspect l&#39;origine della pagina e il tag `<body>` devono includere un attributo `data-cmp-data-layer-enabled`

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

1. È inoltre possibile aprire gli strumenti di sviluppo del browser e nella console l&#39;oggetto JavaScript `adobeDataLayer` deve essere disponibile. Digita il comando seguente per ottenere lo stato Livello dati della pagina corrente:

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

Di seguito è riportato un elenco di schemi utilizzati dai componenti core con il livello dati.

### Schema componente/elemento contenitore {#item}

Lo schema Componente/Elemento contenitore è utilizzato nei seguenti componenti:

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

Il seguente [evento](#events) è pertinente allo schema Componente/Elemento contenitore:

* `cmp:click`

### Schema pagina {#page}

Lo schema Pagina è utilizzato dal componente seguente:

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

Al caricamento della pagina viene attivato un evento `cmp:show`. Questo evento viene inviato da JavaScript in linea immediatamente sotto il tag di apertura `<body>`, rendendolo il primo evento nella coda di eventi Livello dati.

### Schema contenitore {#container}

Lo schema Contenitore è utilizzato dai seguenti componenti:

* [Pannello a soffietto](/help/components/accordion.md)
* [Schede](/help/components/tabs.md)
* [Carosello](/help/components/carousel.md)

Lo schema Contenitore è definito come segue.

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

I seguenti eventi [](#events) sono pertinenti allo schema del contenitore:

* `cmp:click`
* `cmp:show`
* `cmp:hide`

### Schema immagini {#image}

Lo schema immagine è utilizzato dal componente seguente:

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

Il seguente [evento](#events) è relativo allo schema immagine:

* `cmp:click`

### Schema risorse {#asset}

Lo schema delle risorse viene utilizzato all&#39;interno del componente [Immagine.](/help/components/image.md)

Lo schema della risorsa è definito come segue.

```javascript
id: {
    repo:id             // asset UUID
    repo:path           // asset path
    @type               // asset resource type
    xdm:tags            // asset tags
    repo:modifyDate
}
```

Il seguente [evento](#events) è pertinente allo schema delle risorse:

* `cmp:click`

### Schema frammento di contenuto {#content-fragment}

Lo schema frammento di contenuto è utilizzato dal componente [Frammento di contenuto.](/help/components/content-fragment-component.md)

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

Lo schema utilizzato per l&#39;elemento Frammento di contenuto è il seguente.

```javascript
{
    xdm:title           // title
    xdm:text            // text
}
```

## Eventi componenti core {#events}

Esistono diversi eventi attivati da Componenti di base tramite il Livello dati. La procedura ottimale per interagire con il livello dati è [registrare un listener di eventi](https://github.com/adobe/adobe-client-data-layer/wiki#addeventlistener) e *then* eseguire un&#39;azione in base al tipo di evento e/o al componente che ha attivato l&#39;evento. In questo modo si evitano potenziali condizioni di gara con gli script asincroni.

Di seguito sono riportati gli eventi forniti dai componenti core AEM:

* **`cmp:click`** - Facendo clic su un elemento selezionabile (un elemento con un  `data-cmp-clickable` attributo) il livello dati attiva un  `cmp:click` evento.
* **`cmp:show`** e  **`cmp:hide`** - La manipolazione del pannello a soffietto (espansione/riduzione), del carosello (pulsanti successivo/precedente) e delle schede (selezione scheda) determina l&#39;attivazione del livello dati  `cmp:show` e di un  `cmp:hide` evento. Un evento `cmp:show` viene inviato anche al caricamento della pagina e dovrebbe essere il primo evento.
* **`cmp:loaded`** - Non appena il Livello dati viene popolato con i componenti core sulla pagina, il Livello dati attiva un  `cmp:loaded` evento.

### Eventi attivati dal componente {#events-components}

Le tabelle seguenti elencano i componenti core standard che attivano gli eventi insieme a tali eventi.

| Componente | Eventi |
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

Ogni evento Livello dati attivato da un componente core AEM includerà un payload con il seguente oggetto JSON:

```json
eventInfo: {
    path: '<component-path>'
}
```

Dove `<component-path>` è il percorso JSON del componente nel livello dati che ha attivato l&#39;evento.  Il valore, disponibile tramite `event.eventInfo.path`, è importante in quanto può essere utilizzato come parametro per `adobeDataLayer.getState(<component-path>)` che recupera lo stato corrente del componente che ha attivato l&#39;evento, consentendo al codice personalizzato di accedere a dati aggiuntivi e aggiungerlo al Livello dati.

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

Vuoi esplorare più in dettaglio il Livello dati e i Componenti di base? [Guardate questa esercitazione pratica](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/adobe-client-data-layer/data-layer-overview.html).

>[!TIP]
>
>Per scoprire ulteriormente la flessibilità del Livello dati, consulta le opzioni di integrazione, tra cui come abilitare il Livello dati per i componenti personalizzati.
