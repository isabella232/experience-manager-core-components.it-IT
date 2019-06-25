---
title: Versioni componenti principali
seo-title: Versioni componenti principali
description: I componenti core vengono pubblicati come rilasci che possono contenere più versioni degli stessi componenti core. Questo documento descrive le release e le versioni disponibili e come comprendere la compatibilità con Componenti core e AEM.
seo-description: I componenti core vengono pubblicati come rilasci che possono contenere più versioni degli stessi componenti core. Questo documento descrive le release e le versioni disponibili e come comprendere la compatibilità con Componenti core e AEM.
uuid: a 916 a 923-8 c 5 e -456 a -84 b 5-b 52228 e 21434
contentOwner: Utente
content-type: riferimento
topic-tags: introduction
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: a 3 a 98 b 2 f -65 bf -4493-82 ad -01717938 fdbc
translation-type: tm+mt
source-git-commit: 144494c03ffed068b403d80f62fdfddc73a53748

---


# Core Components Versions{#core-components-versions}

La versione corrente dei componenti core è 2.4.0 ed è compatibile con AEM 6.5. È stato rilasciato a maggio 2019 come aggiornamento secondario alla versione 2.0.0. La release 2.0.0 ha introdotto nuovi componenti con aggiornamenti v 2 dei componenti esistenti.

See the section [Release History and Compatibility](#versions-and-releases) of this document for more information.

You can also check out the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library.html), which showcases the current release of the Core Components and gives examples of their usage.

## Versions and Releases {#versions-and-releases}

I componenti core sono distribuiti tramite github. Questo consente ad Adobe di aggiungere più rapidamente funzionalità ai componenti e consente anche di inserire la community all&#39;esterno del processo di pubblicazione AEM.

I componenti core vengono resi disponibili con le versioni AEM definite e compatibili. Ciò significa che una versione AEM potrebbe supportare più versioni o rilasci dei componenti core. Questo offre maggiore flessibilità rispetto agli ex componenti di base, collegati a una versione specifica di AEM.

### Versioni {#versions}

The major iteration of the Core Components are the **versions**. Ogni componente ha una versione. Versions are denoted with **v** appended with a nonzero, positive integer such as v1 and v2. Le versioni vengono incrementate solo per le modifiche non compatibili con retrocompatibilità, normalmente utilizzate per l&#39;introduzione di nuove funzioni e funzionalità.

Sviluppatori e amministratori possono riconoscere le versioni dei componenti core da un numero nei percorsi di tipo resource type e nei nomi di classe Java completi delle rispettive implementazioni. This version number represents a major version as defined by [semantic versioning guidelines](https://semver.org/).

For more details about core component versions, see the [developer documentation of the Core Components](guidelines.md).

### Releases {#releases}

The core components are made available through **releases** and [represent the actual published artifacts available on GitHub](https://github.com/adobe/aem-core-wcm-components/releases). Le versioni sono denotate di un numero decimale del formato X.Y.Z e raccolgono tutti i componenti core come pacchetto reattivo.

* **Le versioni** principali possono introdurre nuove versioni dei componenti esistenti con componenti completamente nuovi e correzioni di bug standard. Questo è rappresentato da un incremento nel componente X del numero di rilascio.

* **Le release** importanti possono introdurre nuove funzionalità alle versioni esistenti dei componenti e correzioni di bug. Questo è rappresentato da un incremento nel componente Y del numero di release.

* **Le release secondarie** contengono solo correzioni di bug. Questo è rappresentato da un incremento nel componente Z del numero di release.

>[!NOTE]
>
>Le release possono contenere più versioni dello stesso componente.
>
>La stessa versione di un componente può essere visualizzata in più rilasci.

## Release History and Compatibility {#release-history-and-compatibility}

I componenti core sono stati rilasciati per la prima volta con AEM 6.3 e sono progettati per essere flessibili e compatibili con tutte le versioni AEM supportate. Poiché questa release dei componenti può contenere più versioni dello stesso componente.

Le tabelle seguenti illustrano la compatibilità delle versioni dei componenti core con le versioni dei componenti in cui vengono rilasciate le versioni.

### Release History &amp; Supported AEM Versions {#release-history-supported-aem-versions}

The following table, the contents of which are [available on GitHub with full release details](https://github.com/adobe/aem-core-wcm-components/releases), gives an overview of the releases of the Core Components and their compatibility with AEM releases and Java versions.

| Rilascio | Descrizione | AEM 6.3 | AEM 6.4 | AEM 6.5 | Java |
|---|---|---|---|---|---|
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | Questa versione ha introdotto il componente Elenco frammenti di contenuto | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | Questa release è incentrata su miglioramenti alla libreria dei componenti, ma contiene anche alcuni miglioramenti delle funzioni per il componente Separatore | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | Questa release si concentra sulla libreria dei componenti e introduce il nuovo componente separatore, ma contiene anche alcuni miglioramenti delle funzioni per il componente Immagine | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | Questa release si concentra principalmente sulle correzioni dei bug, ma contiene anche alcuni miglioramenti delle funzioni per il componente Carosello | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | Componenti Schede e Carosello introdotti, miglioramenti all&#39;immagine, componenti di pagina e titolo e tracciamento migliorato | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | Miglioramenti apportati al componente Teaser, miglioramenti al componente Immagine e numerose correzioni di bug | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | Release Bugfix | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | Miglioramenti a livello individuale, correzioni di bug e piccoli miglioramenti, compreso il supporto dell&#39;immagine capovolta. | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | Miglioramenti nella maggior parte dei casi, correzioni di bug, più piccoli miglioramenti ai componenti Immagine, Pagina e Frammenti di contenuto | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | Sono stati introdotti i componenti Navigazione, Navigazione lingua e Ricerca rapida. Sistema di stile implementato per tutti i componenti. | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | Implementazione dell&#39;esportazione JSON su tutti i componenti, introduzione al componente Frammento di contenuto | 6.3.1.0 | 6.4.0.0+ | - | 8 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | Diverse correzioni per il componente Immagine | 6.3.0.0+ | 6.4.0.0+ | - | 8 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | Correzioni di componente Pagina, Componente Immagine, correzioni e miglioramenti globali | 6.3.0.0+ | 6.4.0.0+ | - | 8 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | Correzioni per le immagini GIF animate nel componente Immagine | 6.3.0.0+ | 6.4.0.0+ | - | 7 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | Versione iniziale dei componenti core | 6.3.0.0+ | 6.4.0.0+ | - | 7 |

>[!NOTE]
>
>As with AEM, Adobe recommends that developers use the [latest release and versions of the Core Components](https://github.com/adobe/aem-core-wcm-components/releases/latest) available that is compatible with the version of AEM that they are running in order to benefit from the most up-to-date fixes and features.

### Component Versions &amp; Releases {#component-versions-and-releases}

La tabella seguente elenca le versioni dei componenti in cui sono inclusi i componenti core.

|  | Rilascio 1.0.0 - 1.0.6 | Release 1.1.0 | Rilascio 2.0.0 - 2.0.8 | Release 2.1.0 | Release 2.2.-2.2.0 | 2.3.0 |
|---|---|---|---|---|---|---|
| **[Pagina](page.md)** | v1 | v1 | v 1, v 2 | v 1, v 2 | v 1, v 2 | v 1, v 2 |
| **[Titolo](title.md)** | v1 | v1 | v 1, v 2 | v 1, v 2 | v 1, v 2 | v 1, v 2 |
| **[Immagine](image.md)** | v1 | v1 | v 1, v 2 | v 1, v 2 | v 1, v 2 | v 1, v 2 |
| **[Elenco](list.md)** | v1 | v1 | v 1, v 2 | v 1, v 2 | v 1, v 2 | v 1, v 2 |
| **[Breadcrumb](breadcrumb.md)** | v1 | v1 | v 1, v 2 | v 1, v 2 | v 1, v 2 | v 1, v 2 |
| **[Condivisione social media](sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Contenitore modulo](form-container.md)** | v1 | v1 | v 1, v 2 | v 1, v 2 | v 1, v 2 | v 1, v 2 |
| **[Testo modulo](form-text.md)** | v1 | v1 | v 1, v 2 | v 1, v 2 | v 1, v 2 | v 1, v 2 |
| **[Opzioni modulo](form-options.md)** | v1 | v1 | v 1, v 2 | v 1, v 2 | v 1, v 2 | v 1, v 2 |
| **[Nascosto per modulo](form-hidden.md)** | v1 | v1 | v 1, v 2 | v 1, v 2 | v 1, v 2 | v 1, v 2 |
| **[Pulsante modulo](form-button.md)** | v1 | v1 | v 1, v 2 | v 1, v 2 | v 1, v 2 | v 1, v 2 |
| **[Frammento di contenuto](content-fragment-component.md)** |  | Sandbox | v1 | v1 | v1 | v1 |
| **[Navigazione](navigation.md)** |  |  | v1 | v1 | v1 | v1 |
| **[Navigazione lingua](language-navigation.md)** |  |  | v1 | v1 | v1 | v1 |
| **[Ricerca rapida](quick-search.md)** |  |  | v1 | v1 | v1 | v1 |
| **[Teaser](teaser.md)** |  |  |  | v1 | v1 | v1 |
| **[Schede](tabs.md)** |  |  |  |  | v1 | v1 |
| **[Carosello](carousel.md)** |  |  |  |  | v1 | v1 |
| **[Separatore](separator.md)** |  |  |  |  |  | v1 |

## Documentazione {#documentation}

[L&#39;authoring con Componenti core](authoring.md) descrive l&#39;utilizzo dei componenti core e delle funzioni esposte agli autori di contenuto e agli autori dei modelli. Ogni componente è documentato in dettaglio.

[Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library.html) è una rappresentazione della versione corrente della maggior parte dei componenti core, illustrando come utilizzarli.

[Sviluppo di componenti](developing.md) core descrive le capacità tecniche dei componenti core, come usarli nei progetti, come personalizzare e best practice.

[L&#39;Introduzione ai componenti core](introduction.md) offre una panoramica della compatibilità dei componenti core tra versioni, casi d&#39;uso e supporto.
