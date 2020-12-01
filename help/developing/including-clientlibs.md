---
title: Incluse le librerie client
description: Esistono diversi modi per includere le librerie client, a seconda del caso di utilizzo.
translation-type: tm+mt
source-git-commit: afce571ada011c38c83830628f09a9e268658965
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 3%

---


# Incluse le librerie client {#including-client-libraries}

Esistono diversi modi per includere [librerie client](/help/developing/archetype/uifrontend.md#clientlibs) a seconda del caso d&#39;uso. In questo documento sono riportati esempi e frammenti [HTL](https://docs.adobe.com/content/help/it-IT/experience-manager-htl/using/overview.html) di esempio per ciascuno di essi.

## Utilizzo predefinito consigliato {#recommended-default-usage}

Se non hai il tempo di esaminare le soluzioni migliori per la tua situazione, includi le librerie client inserendo le seguenti righe HTL all&#39;interno dell&#39;elemento della pagina `head`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Questo includerà sia il CSS che il JS nella pagina `head`, ma l&#39;aggiunta dell&#39;attributo `defer` al JS `script` include, in modo che i browser attendono che il DOM sia pronto prima di eseguire gli script, ottimizzando quindi la velocità di caricamento della pagina.

## Uso di base {#basic-usage}

La sintassi di base per includere sia JS che CSS di una categoria di libreria client, che genererà tutti gli elementi CSS `link` e/o JS `script` corrispondenti, è la seguente:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Per fare lo stesso per più categorie di libreria client contemporaneamente, è possibile trasmettere un array di stringhe al parametro `categories`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## Solo CSS o JS {#css-js-only}

Spesso, si desidera inserire il CSS include nell&#39;elemento HTML `head`, e il JS include appena prima della chiusura dell&#39;elemento `body`.

In `head`, per includere solo il CSS e non il JS, utilizzare `cssIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

Prima della chiusura di `body`, per includere solo il file JS e non il file CSS, utilizzate `jsIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## Attributi {#attributes}

Per applicare gli attributi agli elementi CSS `link` generati e/o agli elementi JS `script`, sono possibili diversi parametri:

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

* `media`: stringa  `script` attributi JS a cui è possibile passare  `jsAndCssIncludes` e  `jsIncludes`:
* `async`: booleano
* `defer`: booleano
* `onload`: stringa
* `crossorigin`: stringa

## Inclinazione {#inlining}

In alcuni casi, per l&#39;ottimizzazione o per le e-mail o per [AMP,](amp.md) potrebbe essere necessario inline il CSS o JS nell&#39;output dell&#39;HTML.

Per allineare il CSS, è possibile utilizzare `cssInline`, nel qual caso è necessario scrivere l&#39;elemento `style` circostante:

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

Allo stesso modo, per agganciare il JS, è possibile utilizzare `jsInline`, nel qual caso è necessario scrivere l&#39;elemento `script` circostante:

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

## Caricamento di CSS e JavaScript in base al contesto {#context-aware-loading}

Il [componente Pagina](/help/components/page.md) supporta anche il caricamento di tag CSS, JavaScript o meta definiti dagli sviluppatori in base al contesto.

A questo scopo, è necessario creare una risorsa [sensibile al contesto](context-aware-configs.md) per `com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig` utilizzando la seguente struttura:

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

[Per ulteriori informazioni, consultare la documentazione tecnica relativa al componente Pagina.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page#loading-of-context-aware-cssjs)
