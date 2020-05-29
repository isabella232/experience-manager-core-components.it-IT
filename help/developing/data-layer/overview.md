---
title: Utilizzo del livello dati client Adobe con i componenti core
description: Utilizzo del livello dati client Adobe con i componenti core
translation-type: tm+mt
source-git-commit: 539a4250c954ac830731a9ecf010e129b2cf9c3a
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 3%

---


# Utilizzo del livello dati client Adobe con i componenti core {#data-layer-core-components}

L&#39;obiettivo di Adobe Client Data Layer è quello di ridurre lo sforzo di utilizzare i siti Web fornendo un metodo standardizzato per esporre e accedere a qualsiasi tipo di dati per qualsiasi script.

Adobe Client Data Layer è agnostico della piattaforma, ma è completamente integrato nei componenti core per l’utilizzo con AEM.

Come per i componenti core, il codice per Adobe Client Data Layer è disponibile su GitHub con la relativa documentazione per gli sviluppatori. Questo documento fornisce una panoramica di come i componenti core interagiscono con il livello dati, ma i dettagli tecnici completi sono differiti alla documentazione GitHub.

>[!TIP]
>
>Per ulteriori informazioni su Adobe Client Data Layer, [fare riferimento alle risorse presenti nell&#39;archivio GitHub.](https://github.com/adobe/adobe-client-data-layer)
>
>Per ulteriori informazioni tecniche sull&#39;integrazione del livello dati client Adobe con i componenti core, vedere il [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) file nell&#39;archivio Componenti principali.


## Installazione e attivazione {#installation-activation}

A partire dalla release 2.9.0 dei componenti core, il livello dati è distribuito con i componenti core come clientlib. Non è necessaria alcuna installazione.

Tuttavia, il livello dati non è attivato per impostazione predefinita. Per attivare il livello dati

1. Crea la struttura seguente sotto il `/conf` nodo:
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
1. Aggiungete una proprietà booleana chiamata `enabled` e impostatela su `true`.
1. Aggiungi una `sling:configRef` proprietà al `jcr:content` nodo del sito `/content` (ad es. `/content/<mySite>/jcr:content`) e impostarla su `/conf/<mySite>`.

Una volta attivata questa opzione, potete verificare l’attivazione caricando una pagina del sito all’esterno dell’editor. Quando ispezionate la pagina vedrete che è caricato il Livello dati client Adobe.

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

```
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


### Schema pagina {#page}

Lo schema Pagina è utilizzato dal componente seguente:

* [Pagina](/help/components/page.md)

Lo schema Pagina è definito come segue.

```
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

```
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

### Schema immagini {#image}

Lo schema immagine è utilizzato dal componente seguente:

* [Immagine](/help/components/image.md)

Lo schema immagine è definito come segue.

```
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

### Schema risorse {#asset}

Lo schema delle risorse viene utilizzato all’interno del componente [Immagine.](/help/components/image.md)

Lo schema della risorsa è definito come segue.

```
id: {
    repo:id             // asset UUID
    repo:path           // asset path
    @type               // asset resource type
    xdm:tags            // asset tags
    repo:modifyDate
}
```

