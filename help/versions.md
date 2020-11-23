---
title: Versioni dei componenti core
description: I componenti core sono pubblicati come versioni che possono contenere più versioni degli stessi componenti core. In questo documento vengono illustrati i rilasci e le versioni e viene illustrato come comprendere la compatibilità con i componenti core e i AEM.
translation-type: tm+mt
source-git-commit: 2f3d2499e9f6c88453b633c20e49703eac25eff4
workflow-type: tm+mt
source-wordcount: '1870'
ht-degree: 22%

---


# Versioni dei componenti core {#core-components-versions}

La versione corrente dei componenti core è 2.12.1 ed è compatibile con [AEM come Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) e [locale AEM](https://docs.adobe.com/content/help/en/experience-manager-65/user-guide/home.html) installazioni. È stato rilasciato nel novembre 2020 come patch release per 2.12.0. La release 2.12.0 ha introdotto diverse nuove funzioni per moduli, metadati e livello dati.

## Cronologia rilascio e compatibilità {#release-history-and-compatibility}

I componenti core sono progettati per essere flessibili e compatibili con tutte le versioni AEM supportate. Di conseguenza, una versione dei componenti può contenere più versioni dello stesso componente.

Le tabelle seguenti illustrano la compatibilità delle versioni dei componenti core insieme alle versioni dei componenti in cui sono contenute le versioni.

### Cronologia e requisiti di rilascio {#release-history-requirements}

La seguente tabella, il cui contenuto è [disponibile su GitHub con i dettagli](https://github.com/adobe/aem-core-wcm-components/releases)sulla versione completa, fornisce una panoramica delle versioni dei componenti core e della loro compatibilità con AEM versioni e versioni Java.

| Release | Descrizione | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service | Java | Data di rilascio |
|---|---|---|---|---|---|---|
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | Questa era una patch release per 2.12.0 con correzioni secondarie. | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 11 novembre 2020 |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | Questa è una patch release per 2.12.0 che risolve un bug principale nel componente [immagine.](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 5 novembre 2020 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | Questa versione ha introdotto [un nuovo gestore di moduli POST;](/help/components/forms/form-container.md#post-data) la possibilità di includere [tag CSS, Javascript e metadati personalizzati mediante la configurazione in base al contesto;](/help/developing/including-clientlibs.md#context-aware-loading) e un&#39; `DataLayerBuilder` utility per [semplificare l&#39;integrazione del livello dati nei componenti personalizzati.](/help/developing/data-layer/integrations.md#enabling-custom-components) | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 29 ottobre 2020 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | Questa versione ha introdotto il supporto [AMP.](/help/developing/amp.md) | 6.4.8.1+ * | 6.5.5.0+ * | Continuo | 8, 11 | 20 luglio 2020 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | Questa versione ha introdotto il componente Visualizzatore [PDF.](/help/components/pdf-viewer.md) | 6.4.8.1+ | 6.5.5.0+ | Continuo | 8, 11 | 17 giugno 2020 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | Questa release ha consentito l’integrazione con il [Livello](/help/developing/data-layer/overview.md) dati client Adobe e ha introdotto il componente Barra di [avanzamento.](/help/components/progress-bar.md) | 6.4.8.0+ | 6.5.4.0+ | Continuo | 8, 11 | 29 maggio 2020 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | Questa release era incentrata sulle correzioni con piccoli miglioramenti. | 6.4.4.0+ | 6.5.0.0+ | Continuo | 8, 11 | 5 dicembre 2019 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | In questa versione è stato introdotto il nuovo componente [Incorpora.](/help/components/embed.md) | 6.4.4.0+ | 6.5.0.0+ | Continuo | 8, 11 | 25 settembre 2019 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | Questa versione ha introdotto il nuovo componente Frammento [esperienza.](/help/components/experience-fragment.md) | 6.4.4.0+ | 6.5.0.0+ | Continuo | 8, 11 | 6 settembre 2019 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | Questa versione ha introdotto i nuovi componenti [Accordion,](/help/components/accordion.md) [Button,](/help/components/button.md) [Container,](/help/components/container.md) [Download.](/help/components/download.md) | 6.4.2.0+ | 6.5.0.0+ | Continuo | 8, 11 | 25 giugno 2019 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | In questa versione è stato introdotto il componente Elenco frammenti di [contenuto.](/help/components/content-fragment-list.md) | 6.4.2.0+ | 6.5.0.0+ | Continuo | 8, 11 | 7 maggio 2019 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | Questa versione è stata dedicata ai miglioramenti apportati alla libreria di [componenti,](https://aemcomponents.dev) ma contiene anche alcuni miglioramenti delle funzioni per il componente [Separatore.](/help/components/separator.md) | 6.4.2.0+ | 6.5.0.0+ | Continuo | 8 | 14 marzo 2019 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | Questa release era dedicata alla libreria [di](https://aemcomponents.dev) componenti e all’introduzione del nuovo componente [Separatore,](/help/components/separator.md) ma contiene anche alcuni miglioramenti a livello di funzioni per il componente [immagine.](/help/components/image.md) | 6.4.2.0+ | - | - | 8 | 11 febbraio 2019 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | Questa versione è stata dedicata principalmente alle correzioni dei bug, ma contiene anche alcuni miglioramenti delle funzioni per il componente [Carosello.](/help/components/carousel.md) | 6.4.2.0+ | - | - | 8 | 27 novembre 2018 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | Questa release ha introdotto il componente [](/help/components/tabs.md) Tabs e il componente [](/help/components/carousel.md) Carosello, nonché miglioramenti al componente [Immagine,](/help/components/image.md) Componente [pagina,](/help/components/page.md) Componente [](/help/components/title.md) titolo e al tracciamento migliorato. | 6.4.2.0+ | - | - | 8 | 16 ottobre 2018 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | Questa versione ha introdotto il componente [](/help/components/teaser.md) Teaser insieme a miglioramenti al componente [](/help/components/image.md) immagine e a numerose correzioni di bug. | 6.4.2.0+ | - | - | 8 | 13 luglio 2018 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | Questa era una release di bug. | 6.4.0.0+ | - | - | 8 | 12 giugno 2018 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | Questa versione ha apportato miglioramenti implementati, correzioni di bug e piccoli miglioramenti, tra cui il supporto della riflessione delle immagini nel componente [Immagine.](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 11 aprile 2018 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | Questa release si è concentrata principalmente su miglioramenti implementati sotto la soglia di protezione, correzioni di bug, più alcuni miglioramenti secondari al componente [immagine,](/help/components/image.md) componente [pagina,](/help/components/page.md) e componente frammento di [contenuto.](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 7 marzo 2018 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | In questa versione sono stati introdotti il componente di [navigazione,](/help/components/navigation.md) il componente di navigazione della [lingua,](/help/components/language-navigation.md) il componente [di ricerca](/help/components/quick-search.md) rapida e il sistema [di](/help/get-started/authoring.md#component-styling) stile per tutti i componenti. | 6.4.0.0+ | - | - | 8 | 16 gennaio 2018 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | Questa versione implementa l’esportazione JSON su tutti i componenti e introduce il componente frammento di [contenuto.](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 10 ottobre 2017 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | Questa versione aggiunge diverse correzioni al componente [Immagine.](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 4 agosto 2017 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | Questa versione aggiunge correzioni per il componente [Pagina,](/help/components/page.md) il componente [Immagine,](/help/components/image.md) e vari miglioramenti e correzioni globali. | 6.4.0.0+ | - | - | 8 | 26 aprile 2017 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | Questa versione aggiunge correzioni per le immagini GIF animate nel componente [Immagine.](/help/components/image.md) | 6.4.0.0+ | - | - | 7 | 22 marzo 2017 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | Versione iniziale dei componenti core. | 6.4.0.0+ | - | - | 7 | 20 marzo 2017 |

>[!NOTE]
>
>(*) A partire dalla versione 2.11.0, è necessaria `org.apache.sling.models.impl` la versione 1.4.12 o successiva (a causa di [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)). Questo verrà fornito per AEM 6.4 e 6.5 in un futuro Service Pack. Fino ad allora, il bundle Sling Models è incluso nel `core.wcm.components.all` pacchetto.

>[!TIP]
>
>Come per AEM,  Adobe consiglia agli sviluppatori di utilizzare la versione [più recente e le versioni dei componenti](https://github.com/adobe/aem-core-wcm-components/releases/latest) core disponibili, compatibili con la versione di AEM in esecuzione, al fine di beneficiare delle correzioni e delle funzionalità più aggiornate.

### Versioni e rilasci di componenti {#component-versions-and-releases}

Nella tabella seguente sono illustrate le versioni dei componenti in cui sono contenuti i rilasci dei componenti core.

|  | Release 1.0.0 - 1.0.6 | Release 1.1.0 | Release 2.0.0 - 2.0.8 | Release 2.1.0 | Release 2.2.0-2.2.0 | Release 2.3.0-2.3.2 | Release 2.4.0 | Release 2.5.0 | Release 2.6.0 | Release 2.7.0-2.8.0 | Release 2.9.0+ |
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

## Versioni e release {#versions-and-releases}

I componenti core sono distribuiti tramite GitHub. Questo consente  Adobe di aggiungere più rapidamente funzionalità ai componenti e di consentire l&#39;input della community al di fuori del ciclo di rilascio AEM.

I componenti core sono disponibili con versioni AEM definite con cui sono compatibili. Ciò significa che una AEM versione può supportare più versioni o release dei componenti core. Ciò offre maggiore flessibilità rispetto ai componenti di base precedenti, che erano legati a una specifica versione di AEM.

### Versioni {#versions}

L&#39;iterazione principale dei componenti core è costituita dalle **versioni**. Ogni componente ha una versione. Le versioni sono indicate con **v** aggiunto con un numero intero positivo diverso da zero, ad esempio v1 e v2. Le versioni vengono incrementate solo per le modifiche che non sono compatibili con le versioni precedenti, come avviene normalmente per l&#39;introduzione di nuove funzioni e funzionalità.

Gli sviluppatori e gli amministratori possono riconoscere le versioni dei componenti core da un numero nei percorsi del tipo di risorsa e nei nomi completi delle classi Java delle loro implementazioni. Questo numero di versione rappresenta una versione principale, come definito dalle linee guida relative alle versioni [semantiche](https://semver.org/).

Per ulteriori informazioni sulle versioni dei componenti core, consulta la documentazione per [gli sviluppatori sui componenti](developing/guidelines.md)core.

### Rilasci {#releases}

I componenti core sono disponibili tramite **le versioni** e [rappresentano gli artifact effettivamente pubblicati disponibili su GitHub](https://github.com/adobe/aem-core-wcm-components/releases). Le release sono indicate con un numero decimale del formato X.Y.Z e raccolgono tutti i componenti core come pacchetto finale.

* **Le versioni** principali possono introdurre nuove versioni dei componenti esistenti, insieme a componenti completamente nuovi e correzioni di bug standard. È rappresentato da un incremento nel componente X del numero di rilascio.
* **Le versioni** importanti possono introdurre nuove funzionalità alle versioni esistenti dei componenti e correzioni di bug. È rappresentato da un incremento nel componente Y del numero di rilascio.
* **Le versioni** secondarie contengono solo correzioni di bug. È rappresentato da un incremento nel componente Z del numero di rilascio.

>[!NOTE]
>
>Le release possono contenere più versioni dello stesso componente.
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

## Supporto dei componenti di base (“foundation”) {#foundation-component-support}

 Adobe  l&#39;enfasi sullo sviluppo si è spostata sui componenti core e le nuove funzioni continueranno ad essere aggiunte.

[Quasi tutti i componenti di Foundation sono stati dichiarati obsoleti con AEM 6.5](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) e solo le correzioni di bug principali verranno prese in considerazione per i componenti di Foundation in futuro.
