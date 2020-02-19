---
title: Introduzione ai componenti core
description: 'I componenti core sono stati introdotti per offrire componenti di base affidabili ed estensibili, basati sulle tecnologie e le best practice più recenti. '
translation-type: tm+mt
source-git-commit: fe8a121520000ffd56ae3347469590e89121eaf0

---


# Introduzione ai componenti core{#core-components-introduction}

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create. I componenti sono sempre stati un elemento fondamentale dell’esperienza AEM perché permettono agli autori di creare pagine in modo semplice e potente e agli sviluppatori di realizzare componenti in modo flessibile ed estensibile.

I componenti core sono stati introdotti per offrire componenti di base affidabili ed estensibili, basati sulle tecnologie e le best practice più recenti, in conformità con le linee guida sull’accessibilità e con lo standard WCAG 2.0 AA. I componenti core consentono di creare pagine in modo più flessibile e personalizzabile e possono essere estesi facilmente dagli sviluppatori per offrire funzionalità personalizzate.

## Provare i componenti core

Se vuoi iniziare subito a provare i componenti core, passa alla pagina della [libreria dei componenti](https://adobe.com/go/aem_cmp_library). La libreria dei componenti è una vetrina online in cui vengono proposte le versioni correnti della maggior parte dei componenti core, che ti permette di interagire con le varianti dei componenti e di visualizzare esempi di output HTML e JSON.

L’esercitazione [WKND](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) illustra inoltre come utilizzare i componenti core.

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
| [Localizzati](get-started/localization.md) | La risoluzione intelligente dei riferimenti consente ad alcuni componenti di trovare e rappresentare automaticamente i contenuti localizzati corrispondenti |

## Componenti disponibili {#available-components}

La versione corrente dei componenti core include i seguenti componenti.

* [Pannello a soffietto](components/accordion.md)
* [Breadcrumb](components/breadcrumb.md)
* [Pulsante](components/button.md)
* [Contenitore](components/container.md)
* [Carosello](components/carousel.md)
* [Frammento di contenuto](components/content-fragment-component.md)
* [Elenco di frammenti di contenuto](components/content-fragment-list.md)
* [Scarica](components/download.md)
* [Incorpora](components/embed.md)
* [Frammento esperienza](components/experience-fragment.md)
* [Pulsante modulo](components/forms/form-button.md)
* [Contenitore modulo](components/forms/form-container.md)
* [Nascosto per modulo](components/forms/form-hidden.md)
* [Opzioni modulo](components/forms/form-options.md)
* [Testo modulo](components/forms/form-text.md)
* [Immagine](components/image.md)
* [Navigazione lingua](components/language-navigation.md)
* [Elenco](components/list.md)
* [Navigazione](components/navigation.md)
* [Pagina](components/page.md)
* [Ricerca rapida](components/quick-search.md)
* [Separatore](components/separator.md)
* [Condivisione social media](components/sharing.md)
* [Schede](components/tabs.md)
* [Testo](components/text.md)
* [Titolo](components/title.md)

>[!NOTE]
>
>I componenti core non sono immediatamente disponibili per gli autori; [devono prima essere integrarti nell’ambiente dal team di sviluppo](get-started/using.md). Once integrated, they may be made available and pre-configured via the [template editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!CAUTION]
>
>Alcune versioni di singoli componenti core potrebbero essere compatibili solo con determinate versioni di AEM.
>
>Consulta la pagina della guida del componente specifico (mediante il collegamento incluso nell’elenco precedente) per informazioni sulla compatibilità, oppure fai riferimento al documento [Versioni dei componenti core](versions.md).

## Quando utilizzare i componenti core {#when-to-use-core-components}

Poiché i componenti core sono completamente nuovi e offrono molteplici vantaggi, si consiglia di utilizzarli nei nuovi progetti AEM. Per i progetti esistenti, la migrazione dei componenti dovrà essere eseguita nell’ambito di un’attività più ampia, ad esempio in occasione di un progetto di rebranding o riformattazione generale.

Per raccomandazioni d’uso specifiche, consulta [Quando utilizzare i componenti core?](developing/overview.md#when-to-use-the-core-components) nel documento [Sviluppo di componenti core](developing/overview.md).

## Panoramica - Sessione Gems {#gems-session-overview}

Per un’introduzione ai componenti core, alle funzionalità offerte e alla modalità di utilizzo in AEM, vedi la pagina della sessione Gems di AEM dedicata ai [componenti core di AEM](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) è una serie di approfondimenti tecnici offerti dagli esperti Adobe. Questa serie integra la documentazione di prodotto e di tutti gli altri canali tecnici, e consente agli sviluppatori di entrare in contatto e approfondire un argomento specifico.

## Sviluppo con i componenti core {#developing-core-components}

I componenti core forniscono componenti di base affidabili ed estensibili che implementano diversi pattern che consentono una facile personalizzazione, dal semplice stile al riutilizzo avanzato delle funzionalità. Per ulteriori informazioni, consulta la documentazione [sullo sviluppo dei componenti](developing/overview.md) core.

Inizia a sviluppare AEM Sites con i componenti core seguendo [l’esercitazione WKND.](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

Non dimenticare di avviare il tuo progetto AEM sfruttando l’archetipo [del progetto](developing/archetype/overview.md) AEM con i componenti core più recenti incorporati!

## Supporto per i componenti core {#core-components-support}

I componenti core sono parte integrante di AEM e sono supportati così come sono. Sono soggetti agli stessi termini e condizioni dei prodotti forniti con Quickstart.

Analogamente ad altre funzionalità di prodotto, la regola generale di fine vita è la seguente:

* La rimozione dei componenti è preceduta da un annuncio di obsolescenza.
* I componenti potrebbero quindi essere rimossi a partire dalla prima versione di AEM rilasciata dopo tale annuncio.

In questo modo i clienti hanno a disposizione almeno un ciclo di rilascio per passare alla nuova versione del componente prima della fine del supporto.

La versione di ogni componente indica chiaramente le versioni di AEM che supporta. Quando cessa il supporto per una versione di AEM, cessa anche il supporto dei componenti core per tale versione di AEM.

Per informazioni dettagliate sul supporto delle personalizzazioni dei componenti, consulta la pagina [Personalizzazione dei componenti core](developing/customizing.md) per la versione dei componenti core pertinente.

## Supporto dei componenti di base (“foundation”) {#foundation-component-support}

Poiché i componenti di base (“foundation”) sono stati utilizzati come base per lo sviluppo di tanti progetti in numerose versioni, continueranno a essere supportati nel prossimo futuro.

However, Adobe&#39;s development emphasis has shifted to the Core Components and new features will be added to them, whereas [nearly all Foundation Components have been deprecated with AEM 6.5](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) and only bug fixes will be made to the Foundation Components going forward.
