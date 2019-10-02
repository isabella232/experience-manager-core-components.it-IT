---
title: Embed Component
seo-title: Embed Component
description: The Embed Component enables embedding external content in an AEM content page.
seo-description: Il componente Incorpora consente di incorporare contenuto esterno in una pagina di contenuto AEM.
content-type: riferimento
topic-tags: core-components
translation-type: tm+mt
source-git-commit: 97f1461b57079806f9f96d325d9b763538e32127

---


# Incorpora componente{#embed-component}

Il componente Incorpora componenti core consente di incorporare contenuto esterno in una pagina di contenuto AEM.

## Utilizzo {#usage}

Il componente core Incorpora componente permette all’autore del contenuto di definire il contenuto esterno selezionato da incorporare in una pagina di contenuto AEM. In addition, there is an option to define free-form HTML to be embedded as well.

* Le proprietà del componente possono essere definite nella finestra di dialogo [di](#configure-dialog)configurazione.
* I valori predefiniti per il componente quando lo si aggiunge a una pagina possono essere definiti nella finestra di dialogo [](#design-dialog)della progettazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Incorpora è v1, introdotto con la release 2.7.0 dei componenti core a settembre 2019, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Incorpora e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](http://opensource.adobe.com/aem-core-wcm-components/library/embed.html)componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Embed [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire la risorsa esterna da incorporare nella pagina. Scegliete innanzitutto il tipo di risorsa da incorporare: **URL**, **incorporabile** o **HTML**.

### URL {#url}

L’incorporamento più semplice è l’URL. È sufficiente incollare l’URL della risorsa da incorporare nel campo **URL** . Il componente tenterà di accedere alla risorsa e, se può essere rappresentato da uno dei processori, visualizzerà un messaggio di conferma sotto il campo **URL** . In caso contrario, il campo verrà contrassegnato come errore.

Il componente Incorpora viene fornito con processori per i seguenti tipi di risorse:

* Risorse conformi allo standard [](https://oembed.com/) oEmbed, inclusi Facebook Post, Instagram, SoundCloud, Twitter e YouTube
* Pinterest

Gli sviluppatori possono aggiungere altri processori URL [seguendo la documentazione per gli sviluppatori del componente Incorpora.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![](assets/screen-shot-2019-09-25-10.08.29.png)

### Contenuto incorporabile {#embeddable}

Le variabili da incorporare consentono una maggiore personalizzazione della risorsa incorporata, che può essere parametrizzata e includere informazioni aggiuntive. Un autore può scegliere tra file da incorporare affidabili preconfigurati e i componenti vengono forniti con un out-of-the-box YouTube incorporato.

The **Embeddable** field defines the type of processor you want to use. Nel caso di YouTube embedable potete quindi definire:

* **Video ID - The unique video ID from YouTube of the resource you want to embed**
* **Width - The width of the embedded video**
* **Height - The height of the embedded video**

Other embeddables would offer similar fields and can be defined by a developer by following the developer documentation of the Embed Component.[](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![](assets/screen-shot-2019-09-25-10.15.00.png)

>[!NOTE]
>Embeddables must be enabled at the template level via the [Design Dialog](#design-dialog) to be available to the page author.

### HTML {#html}

You can add free-form HTML to your page using the Embed Component.

![](assets/screen-shot-2019-09-25-10.20.00.png)

>[!NOTE]
>Any unsafe tags such as scripts will be filtered from the entered HTML and will not be rendered on the resulting page.

## Design Dialog {#design-dialog}

The design dialog allows the template author to define the options available to the content author who uses the Embed Component and the defaults set when placing the Embed Component.

![](assets/screen-shot-2019-09-25-10.25.28.png)

* **Disable URL - Disables the URL option for the content author when selected******
* **Disable Embeddables - Disables the Embeddable option for the content author when selected, regardless of which embeddable processors are allowed.******
* **Disable HTML - Disables the HTML option for the content author when selected.******
* **Allowed Embeddables - Multislect that defines which embeddable processors are available to the content author, provided that the Embeddable option is active.******
