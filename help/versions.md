---
title: Versioni dei componenti core
description: I componenti core vengono pubblicati come versioni che possono contenere più di una versione degli stessi componenti core. Questo documento spiega cosa sono le versioni e le versioni e come comprendere la compatibilità con i componenti core e le AEM.
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 7d4dbe46-4013-4217-b815-cdb1462072c6
source-git-commit: 85904d334091f1b9345023a84e8f12abeeb54692
workflow-type: tm+mt
source-wordcount: '2174'
ht-degree: 21%

---

# Versioni dei componenti core {#core-components-versions}

La versione corrente dei componenti core è 2.17.2 ed è compatibile con le installazioni [AEM come Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) e [on-premise AEM](https://docs.adobe.com/content/help/en/experience-manager-65/user-guide/home.html).

## Cronologia delle versioni e compatibilità {#release-history-and-compatibility}

I componenti core sono progettati per essere flessibili e compatibili con tutte le versioni AEM supportate. Per questo motivo una versione dei componenti può contenere più versioni dello stesso componente.

Le tabelle seguenti illustrano la compatibilità delle versioni dei componenti core insieme alle versioni dei componenti in cui sono contenute le versioni.

### Cronologia e requisiti delle versioni {#release-history-requirements}

La tabella seguente, i cui contenuti sono [disponibili su GitHub con dettagli sulla versione completa](https://github.com/adobe/aem-core-wcm-components/releases), offre una panoramica delle versioni dei componenti core e della loro compatibilità con le versioni AEM e Java.

| Versione | Descrizione | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service | Java | Data di rilascio |
|---|---|---|---|---|---|---|
| [2.17.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.2) | Questa versione della patch include una correzione per il [Livello dati](/help/developing/data-layer/overview.md) che non funziona con AEMaaCS. | 6.4.8.4+ * | 6.5.6.0+ * | Continuo | 8, 11 | 2 luglio 2021 |
| [2.17.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.0) | Questa versione include anteprime tecniche di molte nuove versioni dei componenti che supportano le funzioni del gestore di collegamenti e un&#39;anteprima tecnica di una funzione immagine in primo piano per il [componente Pagina .](/help/components/page.md) Sono incluse anche diverse correzioni di bug. | 6.4.8.4+ * | 6.5.6.0+ * | Continuo | 8, 11 | 16 giugno 2021 |
| [2.16.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.4) | Questa è una release di patch per risolvere un problema con il nuovo gestore di collegamenti. | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 19 maggio 2021 |
| [2.16.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.2) | Questa era una release di patch principalmente risolve un problema con il nuovo Link Handler e aggiunto un miglioramento per supportare applicazioni multipagina per [PWA.](/help/components/page.md#pwa-support) | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 15 maggio 2021 |
| [2.16.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.0) | Questa versione si è concentrata sui miglioramenti dell’accessibilità e sull’introduzione di un nuovo gestore di collegamenti ai componenti esistenti. | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 22 aprile 2021 |
| [2.15.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.2) | Questa era una patch release principalmente risolvere problemi con [Livello dati](/help/developing/data-layer/overview.md) compatibilità con le versioni precedenti e i test IT non riescono in alcune situazioni. | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 16 marzo 2021 |
| [2.15.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.0) | Questa versione include il supporto per [app web progressive (PWA) nel componente pagina](/help/components/page.md#pwa-support) e supporta la versione 2.0.0 del [livello dati Adobe.](/help/developing/data-layer/overview.md) | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 23 febbraio 2021 |
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | Questa versione include nuove opzioni per il [componente da incorporare](/help/components/embed.md) e introduce la funzione Brand Slug a livello di [pagina](/help/components/page.md) e risolve molti problemi. | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 9 febbraio 2021 |
| [2.13.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.2) | Questa era una versione della patch per risolvere un problema con l’editor Rich Text quando veniva utilizzata su AEMaaCS | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 16 dicembre 2020 |
| [2.13.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.0) | Questa versione include nuove funzioni Dynamic Media per il [componente immagine.](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 4 dicembre 2020 |
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | Questa era una patch per 2.12.0 che includeva correzioni minori. | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 11 novembre 2020 |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | Questa era una versione della patch per 2.12.0 che risolve un bug principale nel [componente immagine.](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 5 novembre 2020 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | Questa versione introduce [un nuovo gestore di moduli POST;](/help/components/forms/form-container.md#post-data) la possibilità di includere tag CSS, Javascript e metadati personalizzati [tramite la configurazione in base al contesto;](/help/developing/including-clientlibs.md#context-aware-loading) e un&#39;utilità `DataLayerBuilder` per [semplificare l&#39;integrazione dei livelli dati nei componenti personalizzati.](/help/developing/data-layer/integrations.md#enabling-custom-components) | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 29 ottobre 2020 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | Questa versione introduce il supporto [AMP.](/help/developing/amp.md) | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 20 luglio 2020 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | Questa versione ha introdotto il componente [visualizzatore PDF.](/help/components/pdf-viewer.md) | 6.4.8.1+ | 6.5.5.0+ | Continuo | 8, 11 | 17 giugno 2020 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | Questa versione ha abilitato l&#39;integrazione con [Adobe Client Data Layer](/help/developing/data-layer/overview.md) e ha introdotto il componente [Barra di avanzamento .](/help/components/progress-bar.md) | 6.4.8.0+ | 6.5.4.0+ | Continuo | 8, 11 | 29 maggio 2020 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | Questa versione si è concentrata sulle correzioni con piccoli miglioramenti. | 6.4.4.0+ | 6.5.0.0+ | Continuo | 8, 11 | 5 dicembre 2019 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | Questa versione ha introdotto il nuovo [componente da incorporare.](/help/components/embed.md) | 6.4.4.0+ | 6.5.0.0+ | Continuo | 8, 11 | 25 settembre 2019 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | Questa versione ha introdotto il nuovo [componente Frammento esperienza.](/help/components/experience-fragment.md) | 6.4.4.0+ | 6.5.0.0+ | Continuo | 8, 11 | 6 settembre 2019 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | Questa versione introduce i nuovi componenti [Pannello a soffietto,](/help/components/accordion.md) [Pulsante,](/help/components/button.md) [Contenitore,](/help/components/container.md) e [Download.](/help/components/download.md) | 6.4.2.0+ | 6.5.0.0+ | Continuo | 8, 11 | 25 giugno 2019 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | Questa versione ha introdotto il [componente Elenco frammenti di contenuto.](/help/components/content-fragment-list.md) | 6.4.2.0+ | 6.5.0.0+ | Continuo | 8, 11 | 7 maggio 2019 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | Questa versione si concentra sui miglioramenti apportati alla [Libreria componenti,](https://aemcomponents.dev) ma contiene anche alcuni miglioramenti delle funzioni per il [Componente separatore.](/help/components/separator.md) | 6.4.2.0+ | 6.5.0.0+ | Continuo | 8 | 14 marzo 2019 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | Questa versione si è concentrata sulla [Libreria dei componenti](https://aemcomponents.dev) e sull&#39;introduzione del nuovo [Componente separatore,](/help/components/separator.md), ma contiene anche alcuni miglioramenti delle funzioni per il [Componente immagine.](/help/components/image.md) | 6.4.2.0+ | - | - | 8 | 11 febbraio 2019 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | Questa versione è incentrata principalmente sulle correzioni di bug, ma contiene anche alcuni miglioramenti delle funzioni per il [componente Carosello.](/help/components/carousel.md) | 6.4.2.0+ | - | - | 8 | 27 novembre 2018 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | Questa versione ha introdotto i [componenti scheda](/help/components/tabs.md) e il [componente carosello](/help/components/carousel.md), nonché miglioramenti al [componente immagine,](/help/components/image.md) [Componente pagina,](/help/components/page.md) e [Componente titolo](/help/components/title.md) e al tracciamento migliorato. | 6.4.2.0+ | - | - | 8 | 16 ottobre 2018 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | Questa versione ha introdotto il [componente teaser](/help/components/teaser.md) insieme a miglioramenti al [componente immagine](/help/components/image.md) e a numerose correzioni di bug. | 6.4.2.0+ | - | - | 8 | 13 luglio 2018 |
| [2,0,8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | Questa era una versione di bugfix. | 6.4.0.0+ | - | - | 8 | 12 giugno 2018 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | Questa versione ha aggiunto miglioramenti, correzioni di bug e piccoli miglioramenti, tra cui il supporto della funzione di capovolgimento dell&#39;immagine nel [componente immagine.](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 11 aprile 2018 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | Questa versione si è concentrata principalmente su miglioramenti secondari, correzioni di bug e alcuni miglioramenti minori al componente [immagine,](/help/components/image.md) [Componente pagina,](/help/components/page.md) e [Componente frammento di contenuto.](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 7 marzo 2018 |
| [2,0,0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | Questa versione ha introdotto il [componente di navigazione,](/help/components/navigation.md) [componente di navigazione lingua,](/help/components/language-navigation.md) e il [componente di ricerca rapida](/help/components/quick-search.md) e implementato il [sistema di stile](/help/get-started/authoring.md#component-styling) per tutti i componenti. | 6.4.0.0+ | - | - | 8 | 16 gennaio 2018 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | Questa versione implementa l’esportazione JSON su tutti i componenti e introduce il [componente Frammento di contenuto.](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 10 ottobre 2017 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | Questa versione aggiunge diverse correzioni per il [componente immagine.](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 4 agosto 2017 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | Questa versione aggiunge correzioni per [Componente pagina,](/help/components/page.md) [Componente immagine,](/help/components/image.md) e vari miglioramenti e correzioni globali. | 6.4.0.0+ | - | - | 8 | 26 aprile 2017 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | Questa versione aggiunge correzioni per le immagini GIF animate in [Componente immagine.](/help/components/image.md) | 6.4.0.0+ | - | - | 7 | 22 marzo 2017 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | Versione iniziale dei componenti core. | 6.4.0.0+ | - | - | 7 | 20 marzo 2017 |

>[!NOTE]
>
>(*) A partire dalla versione 2.11.0, è richiesto `org.apache.sling.models.impl` versione 1.4.12 o successiva (a causa di [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)). Questo sarà previsto per AEM 6.4 e 6.5 in un futuro Service Pack. Fino ad allora, il bundle Sling Models è incluso nel pacchetto `core.wcm.components.all`.

>[!TIP]
>
>Come per AEM, Adobe consiglia agli sviluppatori di utilizzare la [versione più recente e le versioni dei componenti core](https://github.com/adobe/aem-core-wcm-components/releases/latest) disponibili, compatibili con la versione di AEM in esecuzione per beneficiare delle correzioni e delle funzionalità più aggiornate.

### Versioni e versioni dei componenti {#component-versions-and-releases}

Nella tabella seguente sono descritte le versioni dei componenti contenuti nelle versioni dei componenti core.

|  | Versione 1.0.0 - 1.0.6 | Versione 1.1.0 | Versione 2.0.0 - 2.0.8 | Versione 2.1.0 | Versione 2.2.0-2.2.0 | Versione 2.3.0-2.3.2 | Versione 2.4.0 | Versione 2.5.0 | Versione 2.6.0 | Versione 2.7.0-2.8.0 | Versione 2.9.0+ |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **[Pagina](components/page.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Titolo](components/title.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Immagine](components/image.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Elenco](components/list.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Breadcrumb](components/breadcrumb.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Condivisione social media](components/sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Contenitore modulo](components/forms/form-container.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Testo modulo](components/forms/form-text.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Opzioni modulo](components/forms/form-options.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Nascosto per modulo](components/forms/form-hidden.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Pulsante modulo](components/forms/form-button.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Frammento di contenuto](components/content-fragment-component.md)** |  | Sandbox | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 |
| **[Navigazione](components/navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Navigazione lingua](components/language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Ricerca rapida](components/quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Teaser](components/teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Schede](components/tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Carosello](components/carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Separatore](components/separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Elenco di frammenti di contenuto](components/content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[Pannello a soffietto](components/accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[Pulsante](components/button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[Contenitore](components/container.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[Scarica](components/download.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[Frammento esperienza](components/experience-fragment.md)** |  |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Incorpora](components/embed.md)** |  |  |  |  |  |  |  |  |  | v1 | v1 |
| **[Barra di avanzamento](components/progress-bar.md)** |  |  |  |  |  |  |  |  |  |  | v1 |
| **[Visualizzatore PDF](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 |

## Versioni e versioni {#versions-and-releases}

I componenti core sono distribuiti tramite GitHub. Questo consente ad Adobe di aggiungere più rapidamente funzionalità ai componenti e anche di consentire l’input della community al di fuori del ciclo di rilascio AEM.

I componenti core sono disponibili con versioni AEM definite con cui sono compatibili. Ciò significa che una versione AEM può supportare più versioni o versioni dei componenti core. Ciò offre maggiore flessibilità rispetto ai precedenti componenti di base, che erano legati a una versione specifica di AEM.

### Versioni {#versions}

L&#39;iterazione principale dei componenti core è costituita dalle **versioni**. Ogni componente ha una versione. Le versioni sono identificate con **v** aggiunto con un numero intero positivo diverso da zero, ad esempio v1 e v2. Le versioni vengono incrementate solo per le modifiche che non sono compatibili con le versioni precedenti, come di solito avviene per l’introduzione di nuove funzioni e funzionalità.

Gli sviluppatori e gli amministratori possono riconoscere le versioni dei componenti core in base a un numero nei percorsi dei tipi di risorse e nei nomi delle classi Java completi delle loro implementazioni. Questo numero di versione rappresenta una versione principale definita dalle [linee guida per il controllo delle versioni semantiche](https://semver.org/).

Per ulteriori dettagli sulle versioni dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](developing/guidelines.md).

### Versioni {#releases}

I componenti core sono resi disponibili tramite **versioni** e [rappresentano gli artefatti effettivamente pubblicati disponibili su GitHub](https://github.com/adobe/aem-core-wcm-components/releases). Le versioni sono identificate con un numero decimale del formato X.Y.Z e raccolgono tutti i componenti core come pacchetto finale.

* **Le** versioni principali possono introdurre nuove versioni dei componenti esistenti, insieme a componenti completamente nuovi e correzioni di bug standard. Questo è rappresentato da un incremento nel componente X del numero di rilascio.
* **Versioni importanti** possono introdurre nuove funzionalità alle versioni esistenti dei componenti e correzioni di bug. È rappresentato da un incremento nel componente Y del numero di rilascio.
* **Le** versioni minori contengono solo correzioni di bug. Questo è rappresentato da un incremento del componente Z del numero di rilascio.

>[!NOTE]
>
>Le versioni possono contenere più versioni dello stesso componente.
>
>La stessa versione di un componente può essere visualizzata in più versioni.

## Supporto per i componenti core {#core-components-support}

I componenti core sono parte integrante di AEM e sono supportati così come sono. Sono soggetti agli stessi termini e condizioni dei prodotti forniti con Quickstart.

Analogamente ad altre funzionalità di prodotto, la regola generale di fine vita è la seguente:

* La rimozione dei componenti è preceduta da un annuncio di obsolescenza.
* I componenti potrebbero quindi essere rimossi a partire dalla prima versione di AEM rilasciata dopo tale annuncio.

In questo modo i clienti hanno a disposizione almeno un ciclo di rilascio per passare alla nuova versione del componente prima della fine del supporto.

La versione di ogni componente indica chiaramente le versioni di AEM che supporta. Quando cessa il supporto per una versione di AEM, cessa anche il supporto dei componenti core per tale versione di AEM.

Per informazioni dettagliate sul supporto delle personalizzazioni dei componenti, consulta la pagina [Personalizzazione dei componenti core](developing/customizing.md) per la versione dei componenti core pertinente.

## Supporto dei componenti di base (“foundation”)  {#foundation-component-support}

L’enfasi sullo sviluppo di Adobe si è spostata sui componenti core e le nuove funzioni continueranno ad essere aggiunte.

[Quasi tutti i componenti di base sono stati dichiarati obsoleti con AEM 6.5](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) e solo le correzioni di bug principali verranno prese in considerazione per i componenti di base in futuro.
