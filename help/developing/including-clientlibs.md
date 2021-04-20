---
title: Inclusione delle librerie client
description: Esistono diversi modi per includere le librerie client a seconda del caso d’uso.
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 3%

---


# Inclusione delle librerie client {#including-client-libraries}

Esistono diversi modi per includere [librerie client](/help/developing/archetype/uifrontend.md#clientlibs) a seconda del caso d’uso. Questo documento fornisce esempi e esempi [snippet HTL](https://docs.adobe.com/content/help/it-IT/experience-manager-htl/using/overview.html) per ciascuno di essi.

## Utilizzo predefinito consigliato {#recommended-default-usage}

Se non hai il tempo di indagare le migliori situazioni, includi le librerie client inserendo le seguenti righe HTL all’interno dell’elemento della pagina `head`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Questo includerà sia il CSS che il JS nella pagina `head`, ma l’aggiunta dell’attributo `defer` al JS `script` include, in modo che i browser attendano che il DOM sia pronto prima di eseguire gli script, ottimizzando quindi la velocità di caricamento della pagina.

## Uso di base {#basic-usage}

La sintassi di base per includere sia JS che CSS di una categoria di libreria client, che genererà tutti gli elementi CSS `link` e/o JS `script` corrispondenti, è la seguente:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Per fare lo stesso per più categorie di librerie client contemporaneamente, è possibile trasmettere un array di stringhe al parametro `categories` :

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## Solo CSS o JS {#css-js-only}

Spesso si desidera inserire gli inclusioni CSS nell&#39;elemento HTML `head` e JS include poco prima della chiusura dell&#39;elemento `body` .

In `head`, per includere solo il CSS e non il JS, utilizza `cssIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

Prima della chiusura `body` , per includere solo JS e non il CSS, utilizza `jsIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## Attributi {#attributes}

Per applicare gli attributi agli elementi CSS `link` e/o agli elementi JS `script` generati, sono possibili diversi parametri:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base',
    media='print',
    async=true,
    defer=true,
    onload='console.log(\'loaded: \' + this.src)',
    crossorigin='anonymous'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Attributi CSS `link` che possono essere passati a `jsAndCssIncludes` e `cssIncludes`:

* `media`: stringa  `script` attributi JS che possono essere passati a  `jsAndCssIncludes` e  `jsIncludes`:
* `async`: booleano
* `defer`: booleano
* `onload`: stringa
* `crossorigin`: stringa

## Struttura {#inlining}

In alcuni casi, per l’ottimizzazione, o per e-mail o [AMP,](amp.md) potrebbe essere necessario inline il CSS o JS nell’output dell’HTML.

Per inline il CSS, è possibile utilizzare `cssInline`, nel qual caso è necessario scrivere l’elemento `style` circostante:

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

Allo stesso modo, per inline il JS, è possibile utilizzare `jsInline`, nel qual caso è necessario scrivere l&#39;elemento `script` circostante:

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

## Caricamento di CSS e JavaScript in base al contesto {#context-aware-loading}

Il [componente pagina](/help/components/page.md) supporta anche il caricamento di tag CSS, JavaScript o meta definiti dagli sviluppatori in base al contesto.

Questo viene fatto creando una [risorsa consapevole del contesto](context-aware-configs.md) per `com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig` utilizzando la seguente struttura:

```text
com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig
    - prefixPath="/some/path"
    + item01
        - element=["link"|"script"|"meta"]
        - location=["header"|"footer"]
        + attributes
            - attributeName01="attributeValue01"
            - attributeName02="attributeValue02"
            ...
    + item02
        ...
    ...
```

[Per ulteriori informazioni, consulta la documentazione tecnica relativa al componente Pagina .](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page#loading-of-context-aware-cssjs)
