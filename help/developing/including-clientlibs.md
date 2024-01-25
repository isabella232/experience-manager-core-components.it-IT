---
title: Inclusione delle librerie client
description: Esistono diversi modi per includere le librerie client a seconda del caso d’uso.
role: Architect, Developer, Admin
exl-id: 84e7c178-247b-42a2-99bf-6d1699ecee14
source-git-commit: 39a5dee1666fa2645e0579fdfac0400f7fcbdc27
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 100%

---

# Inclusione delle librerie client {#including-client-libraries}

Esistono diversi modi per includere le [librerie client](/help/developing/archetype/front-end.md#clientlibs) a seconda del caso d’uso. Questo documento fornisce esempi e [snippet HTL](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=it) per ciascuno di essi.

## Utilizzo predefinito consigliato {#recommended-default-usage}

Se non hai tempo di capire qual è la cosa migliore nella tua situazione, includi le librerie client inserendo le seguenti righe HTL nell’elemento `head` della pagina:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

In questo modo, includerai sia CSS che JS nell’elemento `head` della pagina, ma aggiungendo anche l’attributo `defer` agli `script` JS inclusi, farai in modo che i browser attendano che il DOM (Document Object Model) sia pronto prima di eseguire gli script, ottimizzando quindi la velocità di caricamento della pagina.

## Utilizzo di base {#basic-usage}

La sintassi di base per includere sia JS che CSS di una categoria di librerie client, che genererà tutti gli elementi `link` CSS e/o `script` JS corrispondenti, è la seguente:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Per fare lo stesso con più categorie di librerie client contemporaneamente, è possibile fornire un array di stringhe al parametro `categories`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## Solo CSS o JS {#css-js-only}

Spesso occorre inserire le inclusioni CSS nell’elemento `head` HTML e le inclusioni JS subito prima della chiusura dell’elemento `body`.

Per includere nell’elemento `head` solo CSS e non JS, utilizza `cssIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

Per includere nell’elemento `body` solo JS e non CSS, utilizza `jsIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## Attributi {#attributes}

Per applicare gli attributi agli elementi `link` CSS e/o agli elementi `script` JS generati, è possibile utilizzare diversi parametri:

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

Attributi `link` CSS che possono essere forniti a `jsAndCssIncludes` e `cssIncludes`:

* `media`: stringa Attributi `script` JS che possono essere forniti a `jsAndCssIncludes` e `jsIncludes`:
* `async`: booleano
* `defer`: booleano
* `onload`: stringa
* `crossorigin`: stringa

## Allineamento {#inlining}

In alcuni casi, per l’ottimizzazione, le e-mail o le [AMP,](amp.md) potrebbe essere necessario allineare CSS o JS nell’output HTML.

Per allineare CSS, si può utilizzare `cssInline`, nel qual caso è necessario scrivere l’elemento `style` circostante:

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

Allo stesso modo, per allineare JS, si può utilizzare `jsInline`, nel qual caso è necessario scrivere l’elemento `script` circostante:

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

## Caricamento di CSS e JavaScript in base al contesto {#context-aware-loading}

Il [componente Pagina](/help/components/page.md) supporta anche il caricamento di tag CSS, JavaScript o meta in base al contesto definiti dagli sviluppatori.

Ciò avviene attraverso la creazione di una [risorsa in base contesto](context-aware-configs.md) per `com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig`, utilizzando la seguente struttura:

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

[Per ulteriori informazioni, vedila documentazione tecnica relativa al componente Pagina.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page#loading-of-context-aware-cssjs)
