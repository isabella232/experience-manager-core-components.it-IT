---
title: Introduzione ai componenti core
seo-title: Introduzione ai componenti core
description: 'I componenti core sono stati introdotti per fornire componenti di base affidabili ed estensibili, basati sulle tecnologie e sulle best practice più recenti. '
seo-description: 'I componenti core sono stati introdotti per fornire componenti di base affidabili ed estensibili, basati sulle tecnologie e sulle best practice più recenti. '
uuid: b815c7d1-fbb0-4480-bd23-42606ff8b1eb
contentOwner: Utente
content-type: riferimento
topic-tags: introduzione
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: c44bb0d7-5d91-4659-878e-a0658fe29aa2
translation-type: tm+mt
source-git-commit: b6fbef1cff2908533df6573cd3a92266857ba93f

---


# Introduzione ai componenti core{#core-components-introduction}

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create. I componenti sono sempre stati un elemento fondamentale dell’esperienza AEM, rendendo la creazione di pagine semplice ma potente per l’autore e lo sviluppo di componenti flessibili ed estensibili per lo sviluppatore.

I componenti core sono stati introdotti per fornire componenti di base solidi ed estensibili, basati sulle tecnologie e sulle best practice più recenti, e conformi alle linee guida sull'accessibilità e conformi allo standard WCAG 2.0 AA. I componenti core rendono l’authoring delle pagine più flessibile e personalizzabile, e l’estensione per offrire funzionalità personalizzate è semplice per lo sviluppatore.

## Prova i componenti core

Per iniziare subito a provare i componenti core, visita la libreria [dei](http://opensource.adobe.com/aem-core-wcm-components/library.html)componenti. La libreria dei componenti è una vetrina online della versione corrente della maggior parte dei componenti core, che consente di interagire con le varianti dei componenti e di visualizzare un esempio di output HTML e JSON.

The [We.Retail reference site](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html) also illustrates how the core components can be used.

## Componenti di base - Funzioni di base {#core-components-core-features}

I componenti core sono:

|  |  |
|--- |--- |
| Preconfigurabile | I modelli possono definire il modo in cui gli autori delle pagine possono utilizzarli. |
| Versatile | Gli autori possono creare la maggior parte del tipo di contenuto. |
| Facile da usare | Gli autori possono creare e gestire in modo efficiente i contenuti. |
| Pronto per la produzione | Utilizzabile out-of-the-box! Sono robusti, ben testati e ottimi risultati. |
| Accessibile | Rispetta lo standard WCAG 2.0, fornisce etichette ARIA e supporta la navigazione tramite tastiera. |
| Facilità di stile | I componenti implementano il Sistema di stile e la marcatura segue la denominazione BEM CSS. |
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

Per un'introduzione ai componenti core, alle funzioni che offrono e alla modalità di utilizzo in AEM, consultate i componenti core di AEM Gems Session [AEM.](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) è una serie di approfondimenti tecnici offerti dagli esperti Adobe. Questa serie integra la documentazione del prodotto e tutti gli altri canali tecnici, consentendo agli sviluppatori di mettersi in contatto e approfondire un argomento specifico.

## Esercitazione per sviluppatori WKND {#wknd-developer-tutorial}

Inizia a sviluppare AEM Sites con i componenti core seguendo [questa esercitazione passo.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## Supporto dei componenti core {#core-components-support}

I componenti core sono parte integrante di AEM e sono supportati così come lo sono, secondo gli stessi termini e condizioni come se fossero stati consegnati come parte del Quickstart.

Come per altre caratteristiche del prodotto, la regola generale della fine del ciclo di vita è:

* I componenti vengono dichiarati obsoleti prima di essere rimossi
* Subito dopo l’annuncio, questi vengono rimossi dalla versione di AEM.

Questo consente ai clienti di passare alla nuova versione del componente almeno un ciclo di rilascio prima del termine del supporto.

La versione di ciascun componente indica chiaramente le versioni AEM supportate. Quando il supporto per una versione di AEM cessa, viene utilizzato anche il supporto dei componenti core per tale versione di AEM.

Per informazioni dettagliate sul supporto delle personalizzazioni dei componenti, consultate la pagina [Personalizzazione dei componenti](customizing.md) core della versione dei componenti core pertinente.

## Supporto dei componenti di base {#foundation-component-support}

Poiché i componenti di base sono stati alla base di così tanto sviluppo di progetti in molte versioni, continueranno ad essere sostenuti nel prossimo futuro.

Tuttavia, l'enfasi di sviluppo di Adobe si è spostata sui componenti core e le nuove funzioni verranno aggiunte a tali componenti, mentre [quasi tutti i componenti di base sono stati dichiarati obsoleti con AEM 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) e solo le correzioni di bug verranno apportate ai componenti di base in futuro.
