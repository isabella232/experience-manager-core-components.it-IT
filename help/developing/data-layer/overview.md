---
title: Utilizzo di Adobe Client Data Layer con i Componenti core
description: Utilizzo di Adobe Client Data Layer con i Componenti core
feature: Core Components, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: 55c984d3-deb7-4eda-a81d-7768791d2b46
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: ht
source-wordcount: '972'
ht-degree: 100%

---

# Utilizzo di Adobe Client Data Layer con i Componenti core {#data-layer-core-components}

L’obiettivo di Adobe Client Data Layer è semplificare l’organizzazione di siti web fornendo un metodo standardizzato per visualizzare e accedere a qualsiasi tipo di dati per qualsiasi script.

Adobe Client Data Layer è indipendente dalla piattaforma, ma è completamente integrato nei Componenti core per l’utilizzo con AEM.

Come i Componenti core, il codice di Adobe Client Data Layer è disponibile su GitHub, insieme alla relativa documentazione per gli sviluppatori. Questo documento fornisce una panoramica dell’interazione dei Componenti core con Data Layer, ma per tutti i dettagli tecnici completi si rimanda alla documentazione su GitHub.

>[!TIP]
>
>Per ulteriori informazioni su Adobe Client Data Layer, [vedi le risorse contenuto nel relativo archivio su GitHub.](https://github.com/adobe/adobe-client-data-layer)
>
>Per ulteriori dettagli tecnici sull’integrazione di Adobe Client Data Layer con i Componenti core, vedi il file [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) nell’archivio dei Componenti core.

## Installazione e attivazione {#installation-activation}

A partire dalla versione 2.9.0 dei Componenti core, Data Layer viene distribuito con i Componenti core come libreria client di AEM e non è necessaria alcuna installazione. Tutti i progetti generati da [Archetipo progetto AEM v. 24+](/help/developing/archetype/overview.md) includono Data Layer attivato per impostazione predefinita.

Per attivare manualmente Data Layer è necessario creare una specifica [configurazione in base al contesto](/help/developing/context-aware-configs.md):

1. Crea la seguente struttura sotto la cartella `/conf/<mySite>`, dove `<mySite>` è il nome del progetto del sito:
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * Dove ogni nodo ha una proprietà `jcr:primaryType` impostata su `nt:unstructured`.
1. Aggiungi una proprietà booleana denominata `enabled` e impostala su `true`.

   ![Posizione di DataLayerConfig nel sito di riferimento WKND](/help/assets/datalayer-contextaware-sling-config.png)

   *Posizione di DataLayerConfig nel sito di riferimento WKND*

1. Aggiungi una proprietà `sling:configRef` al nodo `jcr:content` del sito sotto `/content` (ad esempio `/content/<mySite>/jcr:content`) e impostala su `/conf/<mySite>` come da passaggio precedente.

1. Una volta abilitata, ne puoi verificare l’attivazione caricando una pagina del sito fuori dall’editor, ad esempio utilizzando l’opzione **Visualizza come pubblicato** nell’editor. Verifica che la sorgente della pagina e il tag `<body>` includano un attributo `data-cmp-data-layer-enabled`

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

1. Puoi anche aprire gli strumenti di sviluppo del browser e nella console dovrebbe essere disponibile l’oggetto JavaScript `adobeDataLayer`. Immetti il seguente comando per ottenere lo stato di Data Layer nella pagina corrente:

   ```javascript
   window.adobeDataLayer.getState();
   ```

## Componenti supportati {#supported-components}

I seguenti componenti supportano Data Layer.

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

Vedi anche [eventi attivati dai componenti.](#events-components)

## Schemi di dati dei Componenti core {#data-schemas}

Di seguito è riportato un elenco di schemi utilizzati dai Componenti core con Data Layer.

### Schema Componente/Contenitore {#item}

Lo schema Componente/Contenitore viene utilizzato nei seguenti componenti:

* [Breadcrumb](/help/components/breadcrumb.md)
* [Pulsante](/help/components/button.md)
* [Navigazione lingua](/help/components/language-navigation.md)
* [Elenco](/help/components/list.md)
* [Navigazione](/help/components/navigation.md)
* [Teaser](/help/components/teaser.md)
* [Testo](/help/components/text.md)
* [Titolo](/help/components/title.md)

Lo schema Componente/Contenitore è definito come segue.

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

Il seguente [evento](#events) è pertinente allo schema Componente/Contenitore:

* `cmp:click`

### Schema Pagina {#page}

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

Un evento `cmp:show` viene attivato al caricamento della pagina. Questo evento viene inviato da JavaScript in linea immediatamente sotto il tag di apertura `<body>`, rendendolo il primo evento nella coda eventi di Data Layer.

### Schema Contenitore {#container}

Lo schema Contenitore viene utilizzato dai seguenti componenti:

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

I seguenti [eventi](#events) sono pertinenti allo schema Contenitore:

* `cmp:click`
* `cmp:show`
* `cmp:hide`

### Schema Immagine {#image}

Lo schema Immagine viene utilizzato dal componente seguente:

* [Immagine](/help/components/image.md)

Lo schema Immagine è definito come segue.

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

Il seguente [evento](#events) è pertinente allo schema Immagine:

* `cmp:click`

### Schema Risorsa {#asset}

Lo schema Risorsa viene utilizzato all’interno del [componente Immagine.](/help/components/image.md)

Lo schema Risorsa è definito come segue.

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

### Schema Frammento di contenuto {#content-fragment}

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

## Eventi dei Componenti core {#events}

I Componenti core attivano diversi eventi tramite Data Layer. La best practice per interagire con Data Layer è [registrare un listener di eventi](https://github.com/adobe/adobe-client-data-layer/wiki#addeventlistener), *quindi* eseguire un’azione in base al tipo di evento e/o al componente che ha attivato l’evento. In questo modo, si evitano potenziali condizioni di contesa con script asincroni.

Di seguito sono riportati gli eventi predefiniti forniti dai Componenti core di AEM:

* **`cmp:click`** - Facendo clic su un elemento cliccabile (un elemento che ha l’attributo `data-cmp-clickable`), Data Layer attiva un evento `cmp:click`.
* **`cmp:show`** e **`cmp:hide`** - La manipolazione di Pannello a soffietto (espandi/comprimi), Carosello (pulsanti avanti/indietro) e Schede (selezione scheda) induce Data Layer ad attivare gli eventi `cmp:show` e `cmp:hide`, rispettivamente. Al caricamento della pagina, viene inviato anche un evento `cmp:show`, che deve essere il primo evento.
* **`cmp:loaded`** - Non appena Data Layer viene popolato con i Componenti core nella pagina, attiva un evento `cmp:loaded`.

### Eventi attivati dal componente {#events-components}

Le tabelle che seguono riportano i Componenti core standard che attivano altri eventi insieme a quelli indicati sopra.

| Componente | Evento o eventi |
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

### Informazioni sul percorso dell’evento {#event-path-info}

Ogni evento di Data Layer attivato da un Componente core di AEM includerà un carico utile con il seguente oggetto JSON:

```json
eventInfo: {
    path: '<component-path>'
}
```

Dove `<component-path>` è il percorso JSON del componente in Data Layer che ha attivato l’evento.  Il valore, disponibile tramite `event.eventInfo.path`, è importante in quanto può essere utilizzato come parametro per `adobeDataLayer.getState(<component-path>)` che recupera lo stato corrente del componente che ha attivato l’evento, consentendo al codice personalizzato di accedere a dati aggiuntivi e aggiungerli a Data Layer.

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

Vuoi esplorare più dettagliatamente Data Layer e Componenti core? [Guarda questa esercitazione pratica](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/integrations/adobe-client-data-layer/data-layer-overview.html?lang=it).

>[!TIP]
>
>Per saperne di più sulla flessibilità di Data Layer, vedi le opzioni di integrazione, tra cui come abilitare Data Layer per i tuoi componenti personalizzati.
