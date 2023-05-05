---
title: Versioni dei Componenti core
description: Le versioni dei Componenti core pubblicate possono contenere più di una versione degli stessi Componenti core. Questo documento spiega cosa s’intende per versioni e come comprendere la compatibilità con i Componenti core e AEM.
role: Architect, Developer, Admin, User
exl-id: 7d4dbe46-4013-4217-b815-cdb1462072c6
source-git-commit: 468078da4d31d7eedf9bd73cbcf2d71107bfe3f4
workflow-type: ht
source-wordcount: '2924'
ht-degree: 100%

---

# Versioni dei Componenti core {#core-components-versions}

La versione corrente dei Componenti core è la 2.22.4 ed è compatibile con le installazioni di [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=it) e [AEM on-premise](https://experienceleague.adobe.com/docs/experience-manager-65/user-guide/home.html?lang=it).

## Cronologia delle versioni e compatibilità {#release-history-and-compatibility}

I Componenti core sono progettati per essere flessibili e compatibili con tutte le versioni di AEM supportate. Per questo motivo, una versione dei componenti può contenere più versioni dello stesso componente.

Le tabelle seguenti illustrano la compatibilità delle versioni dei Componenti core insieme alle versioni dei Componenti inclusi in ciascuna versione.

### Cronologia e requisiti delle versioni {#release-history-requirements}

La tabella che segue, il cui contenuto è [disponibile su GitHub con tutti i dettagli della versione completa](https://github.com/adobe/aem-core-wcm-components/releases), offre una panoramica delle versioni dei Componenti core e della loro compatibilità con le versioni di AEM e Java.

| Versione | Descrizione | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service | Java | Data di pubblicazione |
|---|---|---|---|---|---|---|
| [2.22.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.4) | Questa è una versione patch che serve a risolvere un problema del [Componente Elenco Frammento di contenuto.](/help/components/content-fragment-list.md) | - | 6.5.14.0+ * | Continua | 8, 11 | 5 aprile 2023 |
| [2.22.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.2) | Questa è una versione di manutenzione che serve a risolvere due problemi introdotti nella versione 2.22.0 | - | 6.5.14.0+ * | Continua | 8, 11 | 31 marzo 2023 |
| [2.22.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.0) | Questa versione introduce una nuova versione del [Componente elenco](/help/components/list.md) insieme ai miglioramenti apportati al [Teaser](/help/components/teaser.md) e all’aggiornamento del [Visualizzatore PDF](/help/components/pdf-viewer.md) e del [Carosello](/help/components/carousel.md). | - | 6.5.14.0+ * | Continua | 8, 11 | 9 febbraio 2023 |
| [2.21.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.21.2) | Si tratta di una versione patch che risolve un problema relativo ai [Componenti teaser](/help/components/teaser.md) v1 e v2. | - | 6.5.13.0+ * | Continua | 8, 11 | 12 settembre 2022 |
| [2.21.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.21.0) | Questa versione include una serie di miglioramenti, tra cui la pubblicazione dell’API LinkHandler, miglioramenti al [Componente immagine](/help/components/image.md) e al [livello dei dati,](/help/developing/data-layer/overview.md) nonché ai componenti per più pannelli. | - | 6.5.13.0+ * | Continua | 8, 11 | 12 settembre 2022 |
| [2.20.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.8) | Questa versione risolve un problema di consegna di immagini SVG tramite AdaptiveImageServlet. | - | 6.5.13.0+ * | Continua | 8, 11 | 4 agosto 2022 |
| [2.20.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.6) | Questa versione patch risolve un problema relativo al nuovo [Componente Sommario.](/help/components/tableofcontents.md) | - | 6.5.13.0+ * | Continua | 8, 11 | 7 luglio 2022 |
| [2.20.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.4) | Questa versione patch risolve un problema relativo al nuovo [Componente Sommario.](/help/components/tableofcontents.md) | - | 6.5.13.0+ * | Continua | 8, 11 | 29 giugno 2022 |
| [2.20.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.2) | Questa è una versione patch che risolve un problema nel nuovo [servizio di consegna di risorse ottimizzate per il web](/help/developing/web-optimized-image-delivery.md) di AEMaaCS. | - | 6.5.13.0+ * | Continua | 8, 11 | 20 giugno 2022 |
| [2.20.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.0) | Questa versione introduce il nuovo [componente Sommario](/help/components/tableofcontents.md) e il supporto per il [servizio di consegna di risorse ottimizzate per il web](/help/developing/web-optimized-image-delivery.md) di AEMaaCS, e include alcune correzioni di bug. | - | 6.5.13.0+ * | Continua | 8, 11 | 9 giugno 2022 |
| [2.19.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.19.0) | Questa versione aggiunge una nuova versione al [componente Ricerca](/help/components/quick-search.md) e alcune funzioni al [componente Pulsante](/help/components/button.md). Contiene inoltre numerosi miglioramenti a livello di accessibilità e alcune correzioni di bug. | - | 6.5.10.0+ * | Continua | 8, 11 | 7 aprile 2022 |
| [2.18.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.8) | Questa versione risolve un problema per AEMaaCS. | - | 6.5.10.0+ * | Continua | 8, 11 | 17 marzo 2022 |
| [2.18.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.6) | Questa è una versione patch. | - | 6.5.10.0+ * | Continua | 8, 11 | 3 marzo 2022 |
| [2.18.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.0) | Questa versione principale dei componenti core vede l’introduzione di un nuovo gestore di collegamenti nelle nuove versioni di più componenti, insieme a numerosi miglioramenti a livello di accessibilità e correzioni di bug. | - | 6.5.10.0+ * | Continua | 8, 11 | 16 febbraio 2022 |
| [2.17.14](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | Questa è una versione patch. | 6.4.8.4+ * | 6.5.6.0+ * | Continua | 8, 11 | 13 dicembre 2021 |
| [2.17.12](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | Questa è una patch che risolve una regressione introdotta con la versione precedente. | 6.4.8.4+ * | 6.5.6.0+ * | Continua | 8, 11 | 1° ottobre 2021 |
| [2.17.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.10) | Questa patch migliora i componenti [Elenco](/help/components/list.md) e [Navigazione](/help/components/navigation.md) in modo da visualizzare l’URL esterno per le destinazioni di reindirizzamento; abilita l’ereditarietà delle immagini di pagina per la prossima v2 del componente [Teaser](/help/components/teaser.md); e contiene alcune correzioni di bug aggiuntivi. | 6.4.8.4+ * | 6.5.6.0+ * | Continua | 8, 11 | 31 agosto 2021 |
| [2.17.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.8) | Questa versione patch corregge una modifica non compatibile con le versioni precedenti introdotta in precedenza. | 6.4.8.4+ * | 6.5.6.0+ * | Continua | 8, 11 | 2 agosto 2021 |
| [2.17.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.6) | Questa versione patch aggiunge il supporto delle mappe del sito per le pagine e include vari miglioramenti a livello di accessibilità. | 6.4.8.4+ * | 6.5.6.0+ * | Continua | 8, 11 | 29 luglio 2021 |
| [2.17.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.2) | Questa versione della patch include una correzione per [Data Layer](/help/developing/data-layer/overview.md) che non funziona con AEMaaCS. | 6.4.8.4+ * | 6.5.6.0+ * | Continua | 8, 11 | 8 luglio 2021 |
| [2.17.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.0) | Questa versione include anteprime tecniche di molte nuove versioni dei componenti che supportano funzioni di gestione dei collegamenti e un’anteprima tecnica di una nuova funzione per le immagini del [componente Pagina.](/help/components/page.md) Sono incluse anche diverse correzioni di bug. | 6.4.8.4+ * | 6.5.6.0+ * | Continua | 8, 11 | 16 giugno 2021 |
| [2.16.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.4) | Questa è una versione di patch per risolvere un problema con la nuova gestione di collegamenti. | 6.4.8.1+ * | 6.5.5.0+ * | Continua | 8, 11 | 19 maggio 2021 |
| [2.16.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.2) | Anche questa è una versione di patch che principalmente risolve un problema con la nuova gestione dei collegamenti e con in più un miglioramento per il supporto di applicazioni multipagina per [PWA.](/help/components/page.md#pwa-support) | 6.4.8.1+ * | 6.5.5.0+ * | Continua | 8, 11 | 15 maggio 2021 |
| [2.16.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.0) | Questa versione si concentra sul miglioramento dell’accessibilità e sull’introduzione di una nuova gestione di collegamenti per i componenti esistenti. | 6.4.8.1+ * | 6.5.5.0+ * | Continua | 8, 11 | 22 aprile 2021 |
| [2.15.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.2) | Versione di patch che principalmente risolve alcuni problemi di compatibilità di [Data Layer](/help/developing/data-layer/overview.md) con le versioni precedenti e il problema dei test IT che non riescono in alcune situazioni. | 6.4.8.1+ * | 6.5.5.0+ * | Continua | 8, 11 | 16 marzo 2021 |
| [2.15.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.0) | Questa versione include il supporto per le [PWA (Progressive Web App) nel componente Pagina](/help/components/page.md#pwa-support) e per la versione 2.0.0 di [Adobe Data Layer.](/help/developing/data-layer/overview.md) | 6.4.8.1+ * | 6.5.5.0+ * | Continua | 8, 11 | 23 febbraio 2021 |
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | Questa versione include nuove opzioni per il [componente Incorpora](/help/components/embed.md) e introduce la funzione Brand Slug a livello di [pagina](/help/components/page.md) oltre a risolvere molti altri problemi. | 6.4.8.1+ * | 6.5.5.0+ * | Continua | 8, 11 | 9 febbraio 2021 |
| [2.13.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.2) | Versione di patch per risolvere un problema dell’editor Rich Text con AEMaaCS | 6.4.8.1+ * | 6.5.5.0+ * | Continua | 8, 11 | 16 dicembre 2020 |
| [2.13.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.0) | Questa versione include nuove funzioni Dynamic Media per il [componente Immagine.](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | Continua | 8, 11 | 4 dicembre 2020 |
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | Versione di patch correlata alla versione 2.12.0 con correzioni minori. | 6.4.8.1+ * | 6.5.5.0+ * | Continua | 8, 11 | 11 novembre 2020 |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | Versione di patch correlata alla versione 2.12.0 che corregge un bug importante nel [componente Immagine.](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | Continua | 8, 11 | 5 novembre 2020 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | Questa versione introduce [un nuovo gestore di moduli POST;](/help/components/forms/form-container.md#post-data) la possibilità di includere tag di metadati, JavaScript e CSS personalizzati tramite la [configurazione basata sul contesto;](/help/developing/including-clientlibs.md#context-aware-loading) nonché una `DataLayerBuilder` utilità per [semplificare l’integrazione di Data Layer nei componenti personalizzati.](/help/developing/data-layer/integrations.md#enabling-custom-components) | 6.4.8.1+ * | 6.5.5.0+ * | Continua | 8, 11 | 29 ottobre 2020 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | Questa versione introduce il supporto [AMP.](/help/developing/amp.md) | 6.4.8.1+ * | 6.5.5.0+ * | Continua | 8, 11 | 20 luglio 2020 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | Questa versione introduce il [componente Visualizzatore PDF.](/help/components/pdf-viewer.md) | 6.4.8.1+ | 6.5.5.0+ | Continua | 8, 11 | 17 giugno 2020 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | Questa versione abilita l’integrazione con [Adobe Client Data Layer](/help/developing/data-layer/overview.md) e introduce il [componente Barra di avanzamento.](/help/components/progress-bar.md) | 6.4.8.0+ | 6.5.4.0+ | Continua | 8, 11 | 29 maggio 2020 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | Questa versione si concentra sulle correzioni con piccoli miglioramenti. | 6.4.4.0+ | 6.5.0.0+ | Continua | 8, 11 | 5 dicembre 2019 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | Questa versione introduce il nuovo [componente Incorpora.](/help/components/embed.md) | 6.4.4.0+ | 6.5.0.0+ | Continua | 8, 11 | 25 settembre 2019 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | Questa versione introduce il nuovo [componente Frammento esperienza.](/help/components/experience-fragment.md) | 6.4.4.0+ | 6.5.0.0+ | Continua | 8, 11 | 6 settembre 2019 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | Questa versione introduce i nuovi componenti [Pannello a soffietto,](/help/components/accordion.md) [Pulsante,](/help/components/button.md) [Contenitore,](/help/components/container.md) e [Scarica.](/help/components/download.md) | 6.4.2.0+ | 6.5.0.0+ | Continua | 8, 11 | 25 giugno 2019 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | Questa versione introduce il [componente Elenco di frammenti di contenuto.](/help/components/content-fragment-list.md) | 6.4.2.0+ | 6.5.0.0+ | Continua | 8, 11 | 7 maggio 2019 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | Questa versione si concentra sui miglioramenti apportati alla [Libreria dei componenti,](https://aemcomponents.dev) ma contiene anche alcuni miglioramenti funzionali del [componente Separatore.](/help/components/separator.md) | 6.4.2.0+ | 6.5.0.0+ | Continua | 8 | 14 marzo 2019 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | Questa versione si concentra sulla [Libreria dei componenti](https://aemcomponents.dev) e sull’introduzione del nuovo [componente Separatore,](/help/components/separator.md) ma contiene anche alcuni miglioramenti funzionali del [componente Immagine.](/help/components/image.md) | 6.4.2.0+ | - | - | 8 | 11 febbraio 2019 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | Questa versione contiene principalmente correzioni di bug, ma anche alcuni miglioramenti funzionali del [componente Carosello.](/help/components/carousel.md) | 6.4.2.0+ | - | - | 8 | 27 novembre 2018 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | Questa versione introduce il [componente Schede](/help/components/tabs.md) e il [componente Carosello](/help/components/carousel.md), ma apporta anche miglioramenti al [componente Immagine](/help/components/image.md), al [componente Pagina](/help/components/page.md), al [componente Titolo](/help/components/title.md) e alla funzione di tracciamento. | 6.4.2.0+ | - | - | 8 | 16 ottobre 2018 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | Questa versione introduce il [componente Teaser](/help/components/teaser.md) oltre a miglioramenti del [componente Immagine](/help/components/image.md) e a numerose correzioni di bug. | 6.4.2.0+ | - | - | 8 | 13 luglio 2018 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | Versione di correzione di bug. | 6.4.0.0+ | - | - | 8 | 12 giugno 2018 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | Questa versione apporta miglioramenti interni, correzioni di bug e piccoli miglioramenti, tra cui il supporto della funzione di riflessione del [componente Immagine.](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 11 aprile 2018 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | Questa versione si concentra principalmente su miglioramenti interni, correzioni di bug e alcuni miglioramenti minori al [componente Immagine,](/help/components/image.md) al [componente Pagina,](/help/components/page.md) e al [componente Frammento di contenuto.](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 7 marzo 2018 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | Questa versione introduce il [componente Navigazione,](/help/components/navigation.md) il [componente Navigazione lingua](/help/components/language-navigation.md) e il [componente Ricerca rapida](/help/components/quick-search.md) e implementa il [Sistema di stili](/help/get-started/authoring.md#component-styling) per tutti i componenti. | 6.4.0.0+ | - | - | 8 | 16 gennaio 2018 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | Questa versione implementa l’esportazione JSON per tutti i componenti e introduce il [componente Frammento di contenuto.](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 10 ottobre 2017 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | Questa versione apporta diverse correzioni al [componente Immagine.](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 4 agosto 2017 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | Questa versione apporta correzioni al [componente Pagina,](/help/components/page.md) al [componente Immagine](/help/components/image.md) e vari miglioramenti e correzioni globali. | 6.4.0.0+ | - | - | 8 | 26 aprile 2017 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | Questa versione apporta correzioni alla gestione delle immagini GIF animate nel [componente Immagine.](/help/components/image.md) | 6.4.0.0+ | - | - | 7 | 22 marzo 2017 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | Versione iniziale dei Componenti core. | 6.4.0.0+ | - | - | 7 | 20 marzo 2017 |

>[!NOTE]
>
>(*) A partire dalla versione 2.11.0, è richiesto `org.apache.sling.models.impl` versione 1.4.12 o successiva (a causa di [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)). Ciò sarà previsto per AEM 6.4 e 6.5 in un futuro Service Pack. Fino ad allora, il bundle Sling Models è incluso nel pacchetto `core.wcm.components.all`.

>[!TIP]
>
>Come per AEM, Adobe consiglia agli sviluppatori di utilizzare le [versioni più recenti dei Componenti core](https://github.com/adobe/aem-core-wcm-components/releases/latest) compatibili con la versione di AEM in esecuzione per beneficiare delle correzioni e delle funzionalità più aggiornate.

### Versioni dei componenti {#component-versions-and-releases}

La tabella che segue riporta in dettaglio le versioni dei singoli componenti contenuti in ciascuna versione dei Componenti core.

|  | Versione 1.0.0 - 1.0.6 | Versione 1.1.0 | Versione 2.0.0 - 2.0.8 | Versione 2.1.0 | Versione 2.2.0-2.2.0 | Versione 2.3.0-2.3.2 | Versione 2.4.0 | Versione 2.5.0 | Versione 2.6.0 | Versione 2.7.0-2.8.0 | Versione 2.9.0 - 2.17.14 | Versione 2.18.0 | Versione 2.19.0 | Versione 2.20.0-2.21.2 | Versione 2.22.0+ |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **[Pagina](components/page.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 |
| **[Titolo](components/title.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 |
| **[Immagine](components/image.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 |
| **[Elenco](components/list.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3, v4 |
| **[Breadcrumb](components/breadcrumb.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 |
| **[Condivisione sui social media](components/sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, obsoleto | v1, obsoleto | v1, obsoleto | v1, obsoleto |
| **[Contenitore modulo](components/forms/form-container.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Testo modulo](components/forms/form-text.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Opzioni modulo](components/forms/form-options.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Campo nascosto modulo](components/forms/form-hidden.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Pulsante modulo](components/forms/form-button.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Frammento di contenuto](components/content-fragment-component.md)** |  | Sandbox | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Navigazione](components/navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Navigazione lingua](components/language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Ricerca rapida](components/quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 |
| **[Teaser](components/teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Schede](components/tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Carosello](components/carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Separatore](components/separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Elenco di frammenti di contenuto](components/content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Pannello a soffietto](components/accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Pulsante](components/button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Contenitore](components/container.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Scarica](components/download.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Frammento esperienza](components/experience-fragment.md)** |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Incorpora](components/embed.md)** |  |  |  |  |  |  |  |  |  | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Barra di avanzamento](components/progress-bar.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[Visualizzatore PDF](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[Sommario](components/tableofcontents.md)** |  |  |  |  |  |  |  |  |  |  |  |  |  | v1 | v1 |

## Versioni {#versions-and-releases}

I Componenti core sono distribuiti tramite GitHub. Ciò consente ad Adobe di aggiungere più rapidamente funzionalità ai componenti e consente anche l’input della community al di fuori del ciclo di rilascio di AEM.

I Componenti core vengono resi disponibili nelle specifiche versioni di AEM con cui sono compatibili. Ciò significa che una versione di AEM può supportare più versioni dei Componenti core.

### Versioni {#versions}

La principale iterazione dei Componenti core è costituita dalle **versioni**. Ciascun componente ha una versione. Le versioni sono indicate con una **v** seguita da un numero intero positivo diverso da zero, ad esempio v1 e v2. I numeri di versione vengono incrementate solo in caso di modifiche non sono compatibili con le versioni precedenti, come di solito avviene per l’introduzione di nuove funzioni e funzionalità.

Gli sviluppatori e gli amministratori possono riconoscere le versioni dei Componenti core in base al numero inserito nei percorsi dei tipi di risorse e nei nomi completi delle classi Java relative alle loro implementazioni. Questo numero rappresenta una versione principale, secondo quanto definito dalle [linee guida per il controllo delle versioni semantiche](https://semver.org/).

Per ulteriori dettagli sulle versioni dei componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](developing/guidelines.md).

### Indicazione estesa delle versioni {#releases}

I Componenti core vengono resi disponibili tramite le **versioni** e [rappresentano gli artefatti effettivamente pubblicati e disponibili su GitHub.](https://github.com/adobe/aem-core-wcm-components/releases) Le versioni estese sono identificate con un numero decimale di formato `X.Y.Z` e raccolgono tutti i Componenti core come singolo pacchetto erogabile.

* **Versioni principali** introduce componenti completamente nuovi, miglioramenti alla versione esistente dei componenti e correzioni di bug standard. Ciò viene rappresentato da un incremento nel componente `X` del numero di versione.
* **Versioni minori** introducono nuovi componenti, nuove funzionalità alle versioni esistenti dei componenti e correzioni di bug. Ciò viene rappresentato da un incremento nel componente `Y` del numero di versione.
* **Le versioni patch** contengono solo correzioni di bug. Ciò viene rappresentato da un incremento nel componente `Z` del numero di versione.

>[!NOTE]
>
>Le versioni possono contenere più versioni dello stesso componente.
>
>La stessa versione di un componente può apparire in più versioni.

## Supporto dei Componenti core {#core-components-support}

I Componenti core sono parte integrante di AEM e sono supportati in quanto tali, soggetti agli stessi termini e condizioni dei prodotti forniti con Quickstart.

Analogamente ad altre funzionalità di prodotto, la regola generale di fine vita è la seguente:

* La rimozione dei componenti è preceduta da un annuncio di obsolescenza.
* I componenti potrebbero quindi essere rimossi a partire dalla prima versione di AEM rilasciata dopo tale annuncio.

In questo modo i clienti hanno il tempo per passare alla nuova versione del componente prima della fine del supporto.

La versione di ogni componente indica chiaramente le versioni di AEM supportate. Quando cessa il supporto per una versione di AEM, cessa anche il supporto dei Componenti core per quella versione di AEM.

Per informazioni dettagliate sul supporto delle personalizzazioni dei componenti, consulta la pagina [Personalizzazione dei componenti core](developing/customizing.md) per la versione dei Componenti core pertinente.

## Supporto dei Componenti di base {#foundation-component-support}

L’enfasi sullo sviluppo di Adobe si è spostata sui Componenti core e nuove funzioni continueranno a essere aggiunte.

[Quasi tutti i Componenti di base sono stati dichiarati obsoleti con AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/siteandpage/default-components-foundation.html?lang=it) e solo le correzioni di bug principali verranno prese in considerazione per i Componenti di base in futuro.
