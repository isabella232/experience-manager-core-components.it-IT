---
title: Incorpora componente
seo-title: Incorpora componente
description: Il componente Incorpora consente di incorporare contenuto esterno in una pagina di contenuto AEM.
seo-description: Il componente Incorpora consente di incorporare contenuto esterno in una pagina di contenuto AEM.
content-type: riferimento
topic-tags: core-components
translation-type: tm+mt
source-git-commit: 6882a0d8247328c403dc11a25ed9d079aefede69

---


# Incorpora componente{#embed-component}

Il componente Incorpora componenti core consente di incorporare contenuto esterno in una pagina di contenuto AEM.

## Utilizzo {#usage}

Il componente core Incorpora componente permette all’autore del contenuto di definire il contenuto esterno selezionato da incorporare in una pagina di contenuto AEM. È inoltre disponibile un’opzione per definire anche l’HTML a forma libera da incorporare.

* The components's properties can be defined in the [configure dialog](#configure-dialog).
* Defaults for the component when adding it to a page can be defined in the design dialog.[](#design-dialog)

## Version and Compatibility {#version-and-compatibility}

The current version of the Embed Component is v1, which was introduced with release 2.7.0 of the Core Components in September 2019, and is described in this document.

The following table details all supported versions of the component, the AEM versions with which the versions of the component is compatible, and links to documentation for previous versions.

| Component Version | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

For more information about Core Component versions and releases, see the document Core Components Versions.[](versions.md)

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

### Incorporabile {#embeddable}

Le variabili da incorporare consentono una maggiore personalizzazione della risorsa incorporata, che può essere parametrizzata e includere informazioni aggiuntive. Un autore può scegliere tra file incorporati attendibili preconfigurati e il componente viene fornito con un processore Youtube out-of-the-box.

Il campo **Incorporabile** definisce il tipo di processore da utilizzare. Nel caso del processore YouTube è possibile definire:

* **ID** video - ID video univoco da YouTube della risorsa da incorporare
* **Width** - The width of the embedded video
* **Height** - The height of the embedded video

Other processors would offer similar fields and can be defined by a developer by following the developer documentation of the Embed Component.[](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![](assets/screen-shot-2019-09-25-10.15.00.png)

>[!NOTE]
>Embedded processors must be enabled at the template level via the [Design Dialog](#design-dialog) to be avaialble to the page author.

### HTML {#html}

You can add free-form HTML to your page using the Embed Component.

![](assets/screen-shot-2019-09-25-10.20.00.png)

>[!NOTE]
>Any unsafe tags such as scripts will be filtered from the entered HTML and will not be rendered on the resulting page.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all'autore del modello di definire le opzioni disponibili per l'autore del contenuto che utilizza il componente Incorpora e le impostazioni predefinite impostate al momento del posizionamento del componente Incorpora.

![](assets/screen-shot-2019-09-25-10.25.28.png)

* **Disattiva URL** - Disattiva l'opzione **URL** per l'autore del contenuto selezionato
* **Disattiva incorporabili** - Disattiva l'opzione **Incorporabile** per l'autore del contenuto selezionato, indipendentemente dai processori incorporabili consentiti.
* **Disattiva HTML** - Disattiva l'opzione **HTML** per l'autore del contenuto selezionato.
* **Embeddables consentiti** - Multisello che definisce quali processori incorporabili sono disponibili per l'autore del contenuto, a condizione che sia attiva l'opzione **Incorporabile** .
