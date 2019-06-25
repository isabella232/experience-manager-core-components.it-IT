---
title: Introduzione ai componenti core
seo-title: Introduzione ai componenti core
description: 'Componenti core sono stati introdotti per fornire componenti base affidabili ed estensibili, basati sulla tecnologia più recente e sulle best practice. '
seo-description: 'Componenti core sono stati introdotti per fornire componenti base affidabili ed estensibili, basati sulla tecnologia più recente e sulle best practice. '
uuid: b 815 c 7 d 1-fbb 0-4480-bd 23-42606 ff 8 b 1 eb
contentOwner: Utente
content-type: riferimento
topic-tags: introduction
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: c 44 bb 0 d 7-5 d 91-4659-878 e-a 0658 fe 29 aa 2
translation-type: tm+mt
source-git-commit: 7130f4ae8add8c8dc3cdfcc4addd0621722b89f7

---


# Core Components Introduction{#core-components-introduction}

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create. I componenti sono sempre stati un elemento fondamentale dell&#39;esperienza AEM, rendendo la creazione di pagine semplice ma potente per l&#39;autore e lo sviluppo di componenti flessibili e estensibili per lo sviluppatore.

Componenti core sono stati introdotti per fornire componenti base affidabili ed estensibili, basati sulla tecnologia e sulle procedure ottimali più recenti e sul conformità alle linee guida sull&#39;accessibilità e conformi allo standard WCAG 2.0 AA. I componenti core rendono l&#39;authoring delle pagine più flessibile e personalizzabile, e estenderli a offrire funzionalità personalizzate è semplice per lo sviluppatore.

## Provate i componenti core

If you want to get started straight away trying out the Core Components, head over to the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library.html). La Libreria componenti è una vetrina online della versione corrente della maggior parte dei componenti core, che consente di interagire con varianti dei componenti e visualizzare l&#39;output di esempio HTML e JSON.

The [We.Retail reference site](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html) also illustrates how the core components can be used.

## Core Components - Core Features {#core-components-core-features}

I componenti core sono:

|  |  |
|--- |--- |
| Pre-configurabile | I modelli possono definire in che modo gli autori delle pagine possono utilizzarli. |
| Versatile | Gli autori possono creare più tipi di contenuto. |
| Semplice da utilizzare | Gli autori possono creare e gestire con efficienza i contenuti. |
| Produzione pronta | Utilizzabile out-of-the-box. Sono affidabili, ben testati ed eseguibili. |
| Accessibile | Essi rispettano lo standard WCAG 2.0, forniscono etichette AIR e supportano la navigazione mediante tastiera. |
| Facile da usare | I componenti implementano il sistema di stile e la marcatura segue la denominazione CSS BEM. |
| SEO | L&#39;output HTML è semantica e fornisce schema.org di annotazioni microdati. |
| PWA/SPA/App Ready | Il loro output JSON ottimizzato può essere utilizzato anche per il rendering sul lato client. |
| Estensibile | Per soddisfare esigenze personalizzate, ma senza partire da zero, tutto può essere esteso. |
| Open Source | Se non è così, contribuisci su github (Apache License). |
| Versione | I componenti core non interrompono il sito quando si migliorano gli elementi che potrebbero avere impatto. |

## Available Components {#available-components}

La versione corrente dei componenti core presenta i seguenti componenti.

* [Accordion](accordion.md)
* [Breadcrumb](breadcrumb.md)
* [Pulsante](button.md)
* [Contenitore](container.md)
* [Carosello](carousel.md)
* [Frammento di contenuto](content-fragment-component.md)
* [Elenco frammenti di contenuto](content-fragment-list.md)
* [Scarica](download.md)
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
>See the individual help page (linked to in the previous list) for the specific component for compatibility information or reference the [Core Components Versions](versions.md) document for more information.

## When to Use Core Components {#when-to-use-core-components}

Poiché i componenti core sono completamente nuovi e offrono più vantaggi, è consigliabile utilizzare i nuovi progetti AEM. Per i progetti esistenti, una migrazione deve far parte di un&#39;attività di progetto più grande, ad esempio un rebranding o un refactoring complessivo.

For specific use recommendations, see [When to Use the Core Components?](developing.md) nel documento [Sviluppo componenti](developing.md) core.

## Gems Session Overview {#gems-session-overview}

For an introduction to the Core Components, the features they offer, and how they are leveraged in AEM, check out the AEM Gems Session [AEM Core Components.](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) è una serie di approfondimenti tecnici offerti dagli esperti Adobe. Questa serie integra la documentazione di prodotto e tutti gli altri canali tecnici, consentendo agli sviluppatori di mettersi in contatto con un argomento specifico.

## WKND Developer Tutorial {#wknd-developer-tutorial}

Get started developing AEM Sites with Core Components by following [this step by step tutorial.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## Core Components Support {#core-components-support}

I componenti core sono parte integrante di AEM e sono supportati così come sono, con gli stessi termini e condizioni di questa distribuzione come parte della sezione Quickstart.

Come per le altre funzionalità del prodotto, la regola generale del ciclo di vita è:

* I componenti vengono inizialmente dichiarati obsoleti prima di essere rimossi
* Al primo vengono quindi rimossi dalla release AEM dopo l&#39;annuncio.

Questo offre ai clienti almeno un ciclo di rilascio per passare alla nuova versione del componente, prima di terminare il supporto.

La versione di ciascun componente indica chiaramente le versioni AEM supportate. Quando il supporto viene interrotto per una versione di AEM, questo supporta anche i componenti core per quella versione di AEM.

For details about the support of component customizations, see the [Customizing Core Components](customizing.md) page of the relevant Core Components Version.

## Foundation Component Support {#foundation-component-support}

Poiché i componenti Foundation sono serviti come base per lo sviluppo di progetti in molte versioni, continueranno a essere supportati nel prossimo futuro.

However, Adobe&#39;s development emphasis has shifted to the Core Components and new features will be added to them, whereas [nearly all Foundation Components have been deprecated with AEM 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) and only bug fixes will be made to the Foundation Components going forward.
