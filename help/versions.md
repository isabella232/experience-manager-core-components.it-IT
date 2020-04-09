---
title: Versioni dei componenti core
description: I componenti core sono pubblicati come versioni che possono contenere più versioni degli stessi componenti core. Questo documento spiega cosa sono le versioni e come comprendere la compatibilità con i componenti core e AEM.
translation-type: tm+mt
source-git-commit: 6c0dcfbe4af6aeb3bfa69bdbb43edaab273207be

---


# Versioni dei componenti core {#core-components-versions}

La versione corrente dei componenti core è 2.8.0 ed è compatibile con [AEM come servizio](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) cloud e con le installazioni [locali di AEM](https://docs.adobe.com/content/help/en/experience-manager-65/user-guide/home.html) . È stato rilasciato nel dicembre 2019 come un aggiornamento importante per la release 2.0.0. La release 2.0.0 ha introdotto nuovi componenti insieme agli aggiornamenti v2 dei componenti esistenti.

## Cronologia rilascio e compatibilità {#release-history-and-compatibility}

I componenti core sono stati rilasciati inizialmente con AEM 6.3 e sono progettati per essere flessibili e compatibili con tutte le versioni AEM supportate. Di conseguenza, una versione dei componenti può contenere più versioni dello stesso componente.

Le tabelle seguenti illustrano la compatibilità delle versioni dei componenti core insieme alle versioni dei componenti in cui sono contenute le versioni.

### Cronologia e requisiti di rilascio {#release-history-requirements}

La seguente tabella, il cui contenuto è [disponibile su GitHub con i dettagli](https://github.com/adobe/aem-core-wcm-components/releases)sulla versione completa, fornisce una panoramica delle versioni dei componenti core e della loro compatibilità con le versioni di AEM e Java.

| Versione | Descrizione | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service | Java | Data di rilascio |
|---|---|---|---|---|---|---|---|
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | Questa release era incentrata sulle correzioni con piccoli miglioramenti. | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | Continuo | 8, 11 | 5 dicembre 2019 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | Questa versione ha introdotto il nuovo componente Incorpora | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | Continuo | 8, 11 | 25 settembre 2019 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | Questa versione ha introdotto il nuovo componente Frammento esperienza | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | Continuo | 8, 11 | 6 settembre 2019 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | Con questa release sono stati introdotti i nuovi componenti Accordion, Button, Container e Download. | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | Continuo | 8, 11 | 25 giugno 2019 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | Questa versione ha introdotto il componente Elenco frammenti di contenuto | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | Continuo | 8, 11 | 7 maggio 2019 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | Questa versione è stata dedicata ai miglioramenti apportati alla libreria di componenti, ma contiene anche alcuni miglioramenti delle funzioni per il componente Separatore | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | Continuo | 8 | 14 marzo 2019 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | Questa versione è incentrata sulla libreria dei componenti e sull’introduzione del nuovo componente separatore, ma contiene anche alcuni miglioramenti a livello di funzioni per il componente Immagine | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 11 febbraio 2019 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | Questa release è stata dedicata principalmente alle correzioni dei bug, ma contiene anche alcuni miglioramenti delle funzioni per il componente Carosello | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 27 novembre 2018 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | Sono stati introdotti componenti per schede e carosello, miglioramenti a immagini, pagine e titoli e funzionalità di tracciamento migliorate | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 16 ottobre 2018 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | È stato introdotto il componente teaser, sono stati apportati miglioramenti ai componenti immagine e sono stati corretti numerosi bug | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 13 luglio 2018 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | Rilascio di Bugfix | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 12 giugno 2018 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | Sono stati apportati ulteriori miglioramenti, correzioni di bug e piccoli miglioramenti, tra cui il supporto della riflessione delle immagini. | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 11 aprile 2018 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | Principalmente miglioramenti implementati, correzioni di bug e alcuni miglioramenti secondari dei componenti Immagine, Pagina e Frammento di contenuto | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 7 marzo 2018 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | Sono stati introdotti i componenti Navigazione, Navigazione lingua e Ricerca rapida. Sistema di stile implementato per tutti i componenti. | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 16 gennaio 2018 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | Implementazione dell’esportazione JSON su tutti i componenti, introduzione del componente Frammento di contenuto | 6.3.1.0 | 6.4.0.0+ | - | - | 8 | 10 ottobre 2017 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | Diverse correzioni per il componente Immagine | 6.3.0.0+ | 6.4.0.0+ | - | - | 8 | 4 agosto 2017 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | Correzioni di componente pagina, componente immagine, varie correzioni e miglioramenti globali | 6.3.0.0+ | 6.4.0.0+ | - | - | 8 | 26 aprile 2017 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | Correzioni per immagini GIF animate nel componente Immagine | 6.3.0.0+ | 6.4.0.0+ | - | - | 7 | 22 marzo 2017 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | Versione iniziale dei componenti core | 6.3.0.0+ | 6.4.0.0+ | - | - | 7 | 20 marzo 2017 |

>[!NOTE]
>
>Come con AEM, Adobe consiglia agli sviluppatori di utilizzare la versione [più recente e le versioni dei componenti](https://github.com/adobe/aem-core-wcm-components/releases/latest) core disponibili, compatibili con la versione di AEM in esecuzione, al fine di trarre vantaggio dalle correzioni e dalle funzionalità più aggiornate.

### Versioni e rilasci di componenti {#component-versions-and-releases}

Nella tabella seguente sono illustrate le versioni dei componenti in cui sono contenuti i rilasci dei componenti core.

|  | Release 1.0.0 - 1.0.6 | Release 1.1.0 | Release 2.0.0 - 2.0.8 | Release 2.1.0 | Release 2.2.0-2.2.0 | Release 2.3.0-2.3.2 | Release 2.4.0 | Release 2.5.0 | Release 2.6.0 | Release 2.7.0+ |
|---|---|---|---|---|---|---|---|---|---|---|
| **[Pagina](components/page.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Titolo](components/title.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Immagine](components/image.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Elenco](components/list.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Breadcrumb](components/breadcrumb.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Condivisione social media](components/sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Contenitore modulo](components/forms/form-container.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Testo modulo](components/forms/form-text.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Opzioni modulo](components/forms/form-options.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Nascosto per modulo](components/forms/form-hidden.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Pulsante modulo](components/forms/form-button.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Frammento di contenuto](components/content-fragment-component.md)** |  | Sandbox | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Navigazione](components/navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Navigazione lingua](components/language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Ricerca rapida](components/quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Teaser](components/teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Schede](components/tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Carosello](components/carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Separatore](components/separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[Elenco di frammenti di contenuto](components/content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[Pannello a soffietto](components/accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Pulsante](components/button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Contenitore](components/container.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Scarica](components/download.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Frammento esperienza](components/experience-fragment.md)** |  |  |  |  |  |  |  |  | v1 | v1 |
| **[Incorpora](components/embed.md)** |  |  |  |  |  |  |  |  |  | v1 |

## Versioni e release {#versions-and-releases}

I componenti core sono distribuiti tramite GitHub. Questo consente ad Adobe di aggiungere funzionalità più rapidamente ai componenti e di consentire l&#39;input da parte della community al di fuori del ciclo di rilascio di AEM.

I componenti core sono disponibili con versioni AEM definite con cui sono compatibili. Ciò significa che una versione di AEM può supportare più versioni o rilasci dei componenti core. Ciò offre maggiore flessibilità rispetto ai precedenti componenti di base, che erano legati a una versione specifica di AEM.

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

Poiché i componenti di base (“foundation”) sono stati utilizzati come base per lo sviluppo di tanti progetti in numerose versioni, continueranno a essere supportati nel prossimo futuro.

However, Adobe&#39;s development emphasis has shifted to the Core Components and new features will be added to them, whereas [nearly all Foundation Components have been deprecated with AEM 6.5](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) and only bug fixes will be made to the Foundation Components going forward.
