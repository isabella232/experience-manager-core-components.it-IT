---
title: Introduzione ai componenti core
seo-title: Introduzione ai componenti core
description: 'Core Components were introduced to provide robust and extensible base components, built on the latest technology and best practices. '
seo-description: 'Core Components were introduced to provide robust and extensible base components, built on the latest technology and best practices. '
uuid: b815c7d1-fbb0-4480-bd23-42606ff8b1eb
contentOwner: Utente
content-type: riferimento
topic-tags: introduzione
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: c44bb0d7-5d91-4659-878e-a0658fe29aa2
translation-type: tm+mt
source-git-commit: bf1993085c4cd95121cb6d78be8c52934802b645

---


# Core Components Introduction{#core-components-introduction}

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create. Components have always been a fundamental element of the AEM experience, making page creation simple but powerful for the author and the development of components flexible and extensible for the developer.

Core Components were introduced to provide robust and extensible base components, built on the latest technology and best practices, and adhering to accessibility guidelines and are compliant with the WCAG 2.0 AA standard. I componenti core rendono l’authoring delle pagine più flessibile e personalizzabile, e l’estensione per offrire funzionalità personalizzate è semplice per lo sviluppatore.

## Prova i componenti core

Per iniziare subito a provare i componenti core, visita la libreria [dei](http://opensource.adobe.com/aem-core-wcm-components/library.html)componenti. La libreria dei componenti è una vetrina online della versione corrente della maggior parte dei componenti core, che consente di interagire con le varianti dei componenti e di visualizzare un esempio di output HTML e JSON.

The [We.Retail reference site](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html) also illustrates how the core components can be used.

## Componenti di base - Funzioni di base {#core-components-core-features}

I componenti core sono:

|  |  |
|--- |--- |
| Preconfigurabile | I modelli possono definire il modo in cui gli autori delle pagine possono utilizzarli. |
| Versatile | Authors can create most kind of content with them. |
| Easy-to-Use | Authors can efficiently create and manage content with them. |
| Production-Ready | Usable out-of-the-box! They are robust, well-tested, and perform well. |
| Accessible | They comply WCAG 2.0 standard, provide ARIA labels, and support keyboard navigation. |
| Easy to Style | I componenti implementano il Sistema di stile e la marcatura segue la denominazione BEM CSS. |
| SEO | L'output HTML è semantico e fornisce annotazioni di microdati schema.org. |
| PWA/SPA/App Ready | L'output JSON ottimizzato può essere utilizzato anche per il rendering sul lato client. |
| Estensibile | Per soddisfare esigenze personalizzate ma senza partire da zero, tutto può essere esteso. |
| Open Source | Se qualcosa non è come dovrebbe essere, contribuire miglioramenti su GitHub (Apache License). |
| Versione | I componenti core non interromperanno il sito quando si migliorano gli elementi che potrebbero avere un impatto sull'utente. |
| [Localizzato](localization.md) | La risoluzione SmartReference consente ad alcuni componenti di trovare ed eseguire automaticamente il rendering dei contenuti localizzati corrispondenti |

## Componenti disponibili {#available-components}

La versione corrente di Core Components include i seguenti componenti.

* [Accordion](accordion.md)
* [Breadcrumb](breadcrumb.md)
* [Pulsante](button.md)
* [Contenitore](container.md)
* [Carosello](carousel.md)
* [Frammento di contenuto](content-fragment-component.md)
* [Elenco frammenti di contenuto](content-fragment-list.md)
* [Scarica](download.md)
* [Incorpora](embed.md)
* [Frammento esperienza](experience-fragment.md)
* [Pulsante modulo](form-button.md)
* [Contenitore modulo](form-container.md)
* [Nascosto per modulo](form-hidden.md)
* [Opzioni modulo](form-options.md)
* [Testo modulo](form-text.md)
* [Immagine](image.md)
* [Navigazione lingua](language-navigation.md)
* [Elenco](list.md)
* [Navigazione](navigation.md)
* [Pagina](page.md)
* [Ricerca rapida](quick-search.md)
* [Separatore](separator.md)
* [Condivisione social media](sharing.md)
* [Schede](tabs.md)
* [Testo](text.md)
* [Titolo](title.md)

>[!NOTE]
>
>Core Components are not immediately available to authors, the [development team must first integrate them to your environment](using.md). Once integrated, they may be made available and pre-configured via the [template editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) or in [design mode](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-designmode.html).

>[!CAUTION]
>
>Alcune versioni di singoli componenti core possono essere compatibili solo con determinate versioni di AEM.
>
>Per informazioni sulla compatibilità, consultate la singola pagina della guida (collegata all’elenco precedente) per il componente specifico oppure fate riferimento al documento Versioni [dei componenti](versions.md) core per ulteriori informazioni.

## Quando utilizzare i componenti core {#when-to-use-core-components}

Poiché i componenti core sono completamente nuovi e offrono molteplici vantaggi, si consiglia di utilizzarli nei nuovi progetti AEM. Per i progetti esistenti, una migrazione dovrebbe essere parte di un progetto più ampio, ad esempio un rifacimento o un refactoring complessivo.

Per consigli d'uso specifici, consultate [Quando utilizzare i componenti core?](developing.md) nel documento [Sviluppo di componenti](developing.md) core.

## Panoramica della sessione Gems {#gems-session-overview}

For an introduction to the Core Components, the features they offer, and how they are leveraged in AEM, check out the AEM Gems Session AEM Core Components.[](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager is a series of technical deep dives delivered by Adobe experts. ](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) This series complements the product documentation and of all the other technical channels, allowing developers to get in touch and go deep on a specific topic.

## WKND Developer Tutorial {#wknd-developer-tutorial}

Get started developing AEM Sites with Core Components by following this step by step tutorial.[](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## Core Components Support {#core-components-support}

Core Components are an integral part of AEM and supported as is, under the same terms and conditions as if they were delivered as part of the Quickstart.

Like other product features, the general rule of end-of-life is:

* Components are first announced to be deprecated before being removed
* At the earliest they are then removed from the AEM release following the announcement.

This gives customers at least one release cycle to move to the new version of the component, before support ends.

La versione di ciascun componente indica chiaramente le versioni AEM supportate. When support ceases for a version of AEM, then so does the support of the Core Components for that version of AEM.

For details about the support of component customizations, see the Customizing Core Components page of the relevant Core Components Version.[](customizing.md)

## Foundation Component Support {#foundation-component-support}

Poiché i componenti di base sono stati alla base di così tanto sviluppo di progetti in molte versioni, continueranno ad essere sostenuti nel prossimo futuro.

Tuttavia, l'enfasi di sviluppo di Adobe si è spostata sui componenti core e le nuove funzioni verranno aggiunte a tali componenti, mentre [quasi tutti i componenti di base sono stati dichiarati obsoleti con AEM 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) e solo le correzioni di bug verranno apportate ai componenti di base in futuro.
