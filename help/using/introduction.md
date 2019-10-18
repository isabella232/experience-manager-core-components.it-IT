---
title: Introduzione ai componenti core
seo-title: Introduzione ai componenti core
description: 'I componenti core sono stati introdotti per offrire componenti di base affidabili ed estensibili, basati sulle tecnologie e le best practice più recenti. '
seo-description: 'I componenti core sono stati introdotti per offrire componenti di base affidabili ed estensibili, basati sulle tecnologie e le best practice più recenti. '
uuid: b815c7d1-fbb0-4480-bd23-42606ff8b1eb
contentOwner: User
content-type: reference
topic-tags: introduction
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: c44bb0d7-5d91-4659-878e-a0658fe29aa2
translation-type: tm+mt
source-git-commit: cbfc96bd215260e902f96c035a7889c968814e39

---


# Introduzione ai componenti core{#core-components-introduction}

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create. I componenti sono sempre stati un elemento fondamentale dell’esperienza AEM perché permettono agli autori di creare pagine in modo semplice e potente e agli sviluppatori di realizzare componenti in modo flessibile ed estensibile.

I componenti core sono stati introdotti per offrire componenti di base affidabili ed estensibili, basati sulle tecnologie e le best practice più recenti, in conformità con le linee guida sull’accessibilità e con lo standard WCAG 2.0 AA. I componenti core consentono di creare pagine in modo più flessibile e personalizzabile e possono essere estesi facilmente dagli sviluppatori per offrire funzionalità personalizzate.

## Provare i componenti core

Se vuoi iniziare subito a provare i componenti core, passa alla pagina della [libreria dei componenti](http://opensource.adobe.com/aem-core-wcm-components/library.html). La libreria dei componenti è una vetrina online in cui vengono proposte le versioni correnti della maggior parte dei componenti core, che ti permette di interagire con le varianti dei componenti e di visualizzare esempi di output HTML e JSON.

The [We.Retail reference site](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html) also illustrates how the core components can be used.

## Componenti core - Caratteristiche principali {#core-components-core-features}

I componenti core sono:

|  |  |
|--- |--- |
| Pre-configurabili | I modelli consentono di definirne le modalità d’uso da parte degli autori di pagine. |
| Versatili | Gli autori possono utilizzarli per creare la maggior parte dei contenuti. |
| Facili da usare | Gli autori possono utilizzarli per creare e gestire in modo efficiente i contenuti. |
| Pronti per la produzione | Oltre a essere già pronti all’uso, sono robusti, testati e garantiscono ottime prestazioni. |
| Accessibili | Sono conformi allo standard WCAG 2.0, forniscono etichette ARIA e supportano la navigazione da tastiera. |
| Facili da personalizzare con gli stili | I componenti implementano il sistema di stili e il markup è conforme alla denominazione CSS BEM. |
| SEO-friendly | L’output HTML è semantico e fornisce annotazioni di microdati schema.org. |
| Pronti per PWA/SPA/App | L’output JSON ottimizzato che li contraddistingue può essere utilizzato anche per il rendering sul lato client. |
| Estensibili | È possibile estendere qualsiasi elemento per soddisfare esigenze personalizzate senza partire da zero. |
| Open source | In caso di errori, è possibile proporre miglioramenti su GitHub (Licenza Apache). |
| Controllo delle versioni | I componenti core non generano errori nel tuo sito quando vengono apportati miglioramenti ad alcuni aspetti che potrebbero interessarti. |
| [Localizzati](localization.md) | Grazie alla risoluzione intelligente dei riferimenti alcuni componenti sono in grado di trovare ed eseguire automaticamente il rendering dei contenuti localizzati corrispondenti. |

## Componenti disponibili {#available-components}

La versione corrente dei componenti core include i seguenti componenti.

* [Pannello a soffietto](accordion.md)
* [Breadcrumb](breadcrumb.md)
* [Pulsante](button.md)
* [Contenitore](container.md)
* [Carosello](carousel.md)
* [Frammento di contenuto](content-fragment-component.md)
* [Elenco di frammenti di contenuto](content-fragment-list.md)
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
>I componenti core non sono immediatamente disponibili per gli autori; [devono prima essere integrarti nell’ambiente dal team di sviluppo](using.md). Once integrated, they may be made available and pre-configured via the [template editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) or in [design mode](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-designmode.html).

>[!CAUTION]
>
>Alcune versioni di singoli componenti core potrebbero essere compatibili solo con determinate versioni di AEM.
>
>Consulta la pagina della guida del componente specifico (mediante il collegamento incluso nell’elenco precedente) per informazioni sulla compatibilità, oppure fai riferimento al documento [Versioni dei componenti core](versions.md).

## Quando utilizzare i componenti core {#when-to-use-core-components}

Poiché i componenti core sono completamente nuovi e offrono molteplici vantaggi, si consiglia di utilizzarli nei nuovi progetti AEM. Per i progetti esistenti, la migrazione dei componenti dovrà essere eseguita nell’ambito di un’attività più ampia, ad esempio in occasione di un progetto di rebranding o riformattazione generale.

Per raccomandazioni d’uso specifiche, consulta [Quando utilizzare i componenti core?](developing.md) nel documento [Sviluppo di componenti core](developing.md).

## Panoramica - Sessione Gems {#gems-session-overview}

Per un’introduzione ai componenti core, alle funzionalità offerte e alla modalità di utilizzo in AEM, vedi la pagina della sessione Gems di AEM dedicata ai [componenti core di AEM](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) è una serie di approfondimenti tecnici offerti dagli esperti Adobe. Questa serie integra la documentazione di prodotto e di tutti gli altri canali tecnici, e consente agli sviluppatori di entrare in contatto e approfondire un argomento specifico.

## Sviluppo con i componenti core {#developing-core-components}

I componenti core forniscono componenti di base affidabili ed estensibili che implementano diversi pattern che consentono una facile personalizzazione, dal semplice stile al riutilizzo avanzato delle funzionalità. Per ulteriori informazioni, consulta la documentazione [sullo sviluppo dei componenti](developing.md) core.

Per iniziare a sviluppare un sito con AEM Sites e i componenti core, segui questa esercitazione passo passo.[](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

Non dimenticare di avviare il tuo progetto AEM sfruttando l’archetipo [del progetto](archetype.md) AEM con i componenti core più recenti incorporati!

## Supporto per i componenti core {#core-components-support}

I componenti core sono parte integrante di AEM e sono supportati così come sono. Sono soggetti agli stessi termini e condizioni dei prodotti forniti con Quickstart.

Analogamente ad altre funzionalità di prodotto, la regola generale di fine vita è la seguente:

* La rimozione dei componenti è preceduta da un annuncio di obsolescenza.
* I componenti potrebbero quindi essere rimossi a partire dalla prima versione di AEM rilasciata dopo tale annuncio.

In questo modo i clienti hanno a disposizione almeno un ciclo di rilascio per passare alla nuova versione del componente prima della fine del supporto.

La versione di ogni componente indica chiaramente le versioni di AEM che supporta. Quando cessa il supporto per una versione di AEM, cessa anche il supporto dei componenti core per tale versione di AEM.

Per informazioni dettagliate sul supporto delle personalizzazioni dei componenti, consulta la pagina [Personalizzazione dei componenti core](customizing.md) per la versione dei componenti core pertinente.

## Supporto dei componenti di base (“foundation”) {#foundation-component-support}

Poiché i componenti di base (“foundation”) sono stati utilizzati come base per lo sviluppo di tanti progetti in numerose versioni, continueranno a essere supportati nel prossimo futuro.

However, Adobe's development emphasis has shifted to the Core Components and new features will be added to them, whereas [nearly all Foundation Components have been deprecated with AEM 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) and only bug fixes will be made to the Foundation Components going forward.
