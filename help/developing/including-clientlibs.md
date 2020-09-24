---
title: Incluse le librerie client
description: Esistono diversi modi per includere le librerie client, a seconda del caso di utilizzo.
translation-type: tm+mt
source-git-commit: 24f718be2ba66113eda970c213c6ce4baec51752
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---


# Incluse le librerie client {#including-client-libraries}

Esistono diversi modi per includere le librerie [](/help/developing/archetype/uifrontend.md#clientlibs) client, a seconda del caso di utilizzo. Questo documento fornisce esempi e snippet [HTL di esempio](https://docs.adobe.com/content/help/it-IT/experience-manager-htl/using/overview.html) per ciascuno di essi.

## Utilizzo predefinito consigliato {#recommended-default-usage}

Se non hai il tempo di studiare le migliori situazioni, includi le librerie client inserendo le seguenti righe HTL nell’ `head` elemento della pagina:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Questo includerà sia il CSS che il JS nella pagina `head`, ma l&#39;aggiunta dell&#39; `defer` attributo al JS `script` include, in modo che i browser attendono che il DOM sia pronto prima di eseguire gli script, e quindi ottimizzando la velocità di caricamento della pagina.

## Utilizzo di base {#basic-usage}

La sintassi di base per includere sia JS che CSS di una categoria di libreria client, che genererà tutti `link` gli elementi CSS e/o JS `script` corrispondenti, è la seguente:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Per fare lo stesso per più categorie di libreria client contemporaneamente, è possibile trasmettere al `categories` parametro un array di stringhe:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## Solo CSS o JS {#css-js-only}

Spesso, si desidera inserire i CSS inclusi nell&#39; `head` elemento HTML, e il JS include appena prima della chiusura dell&#39; `body` elemento.
&#x200B;
Per `head`includere solo il CSS e non il JS, utilizzate `cssIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

Prima della `body` chiusura, per includere solo il file JS e non il file CSS, utilizzate `jsIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## Attributi {#attributes}

Per applicare gli attributi agli `link` elementi CSS e/o agli `script` elementi JS generati, sono possibili diversi parametri:

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

* `media`: stringa &#x200B; attributi JS `script` che possono essere passati a `jsAndCssIncludes` e `jsIncludes`:

* `async`: booleano
* `defer`: booleano
* `onload`: stringa
* `crossorigin`: stringa

## Indesign {#inlining}

In alcuni casi, per l’ottimizzazione o per e-mail o [AMP,](amp.md) potrebbe essere necessario allineare CSS o JS nell’output dell’HTML.
&#x200B;
Per agganciare il CSS, `cssInline` potete utilizzarlo, nel qual caso dovete scrivere l&#39; `style` elemento circostante:

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

Allo stesso modo, per agganciare il JS, `jsInline` può essere utilizzato, nel qual caso è necessario scrivere l&#39; `script` elemento circostante:

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```
