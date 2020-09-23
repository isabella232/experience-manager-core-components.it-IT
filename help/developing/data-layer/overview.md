---
title: Utilizzo del livello dati client del Adobe  con i componenti core
description: Utilizzo del livello dati client del Adobe  con i componenti core
translation-type: tm+mt
source-git-commit: 4a44a5f584efa736320556f6b4e2f4126d058a48
workflow-type: tm+mt
source-wordcount: '575'
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
>Per ulteriori dettagli tecnici sull&#39;integrazione del livello dati client del Adobe  con i componenti core, vedere il [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) file nell&#39;archivio Componenti di base.

## Installazione e attivazione {#installation-activation}

A partire dalla release 2.9.0 dei componenti core, il livello dati è distribuito con i componenti core come clientlib. Non è necessaria alcuna installazione.

Tuttavia, il livello dati non è attivato per impostazione predefinita. Per attivare il Livello dati è necessario creare una configurazione [](/help/developing/context-aware-configs.md) contestuale per tale livello:

1. Crea la struttura seguente sotto il `/conf` nodo:
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * Tipo di nodo: `nt:unstructured`
1. Aggiungete una proprietà booleana chiamata `enabled` e impostatela su `true`.
1. Aggiungi una `sling:configRef` proprietà al `jcr:content` nodo del sito `/content` (ad es. `/content/<mySite>/jcr:content`) e impostarla su `/conf/<mySite>`.

Una volta attivata questa opzione, potete verificare l’attivazione caricando una pagina del sito all’esterno dell’editor. Quando ispezionate la pagina vedrete che è stato caricato il Livello dati client del Adobe .

## Schemi di dati dei componenti core {#data-schemas}

Di seguito è riportato un elenco di schemi utilizzati dai componenti core con il livello dati.

### Schema elemento componente/contenitore {#item}

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

L&#39; [evento](#events) seguente è pertinente allo schema Componente/Elemento contenitore:

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

Gli [eventi](#events) seguenti sono pertinenti allo schema Contenitore:

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

L’ [evento](#events) seguente è relativo allo schema immagine:

* `cmp:click`

### Schema risorse {#asset}

Lo schema delle risorse viene utilizzato all’interno del componente [Immagine.](/help/components/image.md)

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

## Eventi {#events}

Esistono diversi eventi attivati dal livello dati.

* **`cmp:click`** - Facendo clic su un elemento selezionabile (un elemento con un `data-cmp-clickable` attributo) il livello dati attiva un `cmp:click` evento.
* **`cmp:show`** e **`cmp:hide`** - La manipolazione del pannello a soffietto (espandi/comprimi), del carosello (pulsanti Successivo/Precedente) e delle schede (selezione scheda) determina l&#39;attivazione del livello dati `cmp:show` e di un `cmp:hide` evento.
* **`cmp:loaded`** - Non appena il livello dati viene popolato con i componenti core sulla pagina, il livello dati attiva un `cmp:loaded` evento.

### Eventi attivati dal componente {#events-components}

Le tabelle seguenti elencano i componenti core standard che attivano gli eventi insieme a tali eventi.

| Componente | Eventi |
|---|---|
| [Navigazione](/help/components/navigation.md) | `cmp:click` |
| [Navigazione lingua](/help/components/language-navigation.md) | `cmp:click` |
| [Breadcrumb](/help/components/breadcrumb.md) | `cmp:click` |
| [Pulsante](/help/components/button.md) | `cmp:click` |
| [Carosello](/help/components/carousel.md) | `cmp:show` e `cmp:hide` |
| [Schede](/help/components/tabs.md) | `cmp:show` e `cmp:hide` |
| [Pannello a soffietto](/help/components/accordion.md) | `cmp:show` e `cmp:hide` |
