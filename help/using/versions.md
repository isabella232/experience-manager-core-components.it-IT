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
source-git-commit: 63e75079e41d3091ca57bfc3129e700675bf4939

---


# Versioni componenti principali{#core-components-versions}

La versione corrente dei componenti core è 2.6.0 ed è compatibile con AEM 6.5. È stato rilasciato a settembre 2019 come importante aggiornamento alla release 2.0.0. La release 2.0.0 ha introdotto nuovi componenti con aggiornamenti v 2 dei componenti esistenti.

Per ulteriori informazioni, consulta la sezione [Cronologia rilascio e Compatibilità](#versions-and-releases) del documento.

Potete anche controllare la [Libreria](http://opensource.adobe.com/aem-core-wcm-components/library.html)componenti, che mostra la versione corrente dei componenti core e ne fornisce esempi di utilizzo.

## Versioni e rilasci {#versions-and-releases}

I componenti core sono distribuiti tramite github. Questo consente ad Adobe di aggiungere più rapidamente funzionalità ai componenti e consente anche di inserire la community all'esterno del processo di pubblicazione AEM.

I componenti core vengono resi disponibili con le versioni AEM definite e compatibili. Ciò significa che una versione AEM potrebbe supportare più versioni o rilasci dei componenti core. Questo offre maggiore flessibilità rispetto agli ex componenti di base, collegati a una versione specifica di AEM.

### Versioni {#versions}

L'iterazione principale dei componenti core è **la versione**. Ogni componente ha una versione. Le versioni sono contrassegnate **da v** con un numero intero positivo, ad esempio v 1 e v 2. Le versioni vengono incrementate solo per le modifiche non compatibili con retrocompatibilità, normalmente utilizzate per l'introduzione di nuove funzioni e funzionalità.

Sviluppatori e amministratori possono riconoscere le versioni dei componenti core da un numero nei percorsi di tipo resource type e nei nomi di classe Java completi delle rispettive implementazioni. Questo numero di versione rappresenta una versione principale come definito dalle [linee guida semantici delle versioni](https://semver.org/).

Per ulteriori dettagli sulle versioni dei componenti di base, consulta la [documentazione per sviluppatori dei componenti core](guidelines.md).

### Rilasci {#releases}

I componenti core sono disponibili attraverso **le release** e [rappresentano gli artefatti pubblicati effettivi disponibili su github](https://github.com/adobe/aem-core-wcm-components/releases). Le versioni sono denotate di un numero decimale del formato X.Y.Z e raccolgono tutti i componenti core come pacchetto reattivo.

* **Le versioni** principali possono introdurre nuove versioni dei componenti esistenti con componenti completamente nuovi e correzioni di bug standard. Questo è rappresentato da un incremento nel componente X del numero di rilascio.
* **Le release** importanti possono introdurre nuove funzionalità alle versioni esistenti dei componenti e correzioni di bug. Questo è rappresentato da un incremento nel componente Y del numero di release.
* **Le release secondarie** contengono solo correzioni di bug. Questo è rappresentato da un incremento nel componente Z del numero di release.

>[!NOTE]
>
>Le release possono contenere più versioni dello stesso componente.
>
>La stessa versione di un componente può essere visualizzata in più rilasci.

## Cronologia rilascio e Compatibilità {#release-history-and-compatibility}

I componenti core sono stati rilasciati per la prima volta con AEM 6.3 e sono progettati per essere flessibili e compatibili con tutte le versioni AEM supportate. Poiché questa release dei componenti può contenere più versioni dello stesso componente.

Le tabelle seguenti illustrano la compatibilità delle versioni dei componenti core con le versioni dei componenti in cui vengono rilasciate le versioni.

### Cronologia rilascio e Versioni AEM supportate {#release-history-supported-aem-versions}

La tabella seguente, il cui contenuto è [disponibile su github con i dettagli sulla versione completa](https://github.com/adobe/aem-core-wcm-components/releases), fornisce una panoramica delle versioni dei componenti core e la loro compatibilità con le release AEM e le versioni Java.

| Rilascio | Descrizione | AEM 6.3 | AEM 6.4 | AEM 6.5 | Java | Data di rilascio |
|---|---|---|---|---|---|---|
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | Questa versione ha introdotto il nuovo componente Frammento esperienza | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 | Settembre 2019 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | Questa versione ha introdotto i nuovi componenti Accordion, Button, Container e Download. | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 | 25 giugno 2019 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | Questa versione ha introdotto il componente Elenco frammenti di contenuto | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 | 7 maggio 2019 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | Questa release è incentrata su miglioramenti alla libreria dei componenti, ma contiene anche alcuni miglioramenti delle funzioni per il componente Separatore | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8 | 14 marzo 2019 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | Questa release si concentra sulla libreria dei componenti e introduce il nuovo componente separatore, ma contiene anche alcuni miglioramenti delle funzioni per il componente Immagine | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 11 febbraio 2019 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | Questa release si concentra principalmente sulle correzioni dei bug, ma contiene anche alcuni miglioramenti delle funzioni per il componente Carosello | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 27 novembre 2018 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | Componenti Schede e Carosello introdotti, miglioramenti all'immagine, componenti di pagina e titolo e tracciamento migliorato | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 16 ottobre 2018 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | Miglioramenti apportati al componente Teaser, miglioramenti al componente Immagine e numerose correzioni di bug | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 13 luglio 2018 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | Release Bugfix | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 12 giugno 2018 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | Miglioramenti a livello individuale, correzioni di bug e piccoli miglioramenti, compreso il supporto dell'immagine capovolta. | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 11 aprile 2018 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | Miglioramenti nella maggior parte dei casi, correzioni di bug, più piccoli miglioramenti ai componenti Immagine, Pagina e Frammenti di contenuto | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 7 marzo 2018 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | Sono stati introdotti i componenti Navigazione, Navigazione lingua e Ricerca rapida. Sistema di stile implementato per tutti i componenti. | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 16 gennaio 2018 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | Implementazione dell'esportazione JSON su tutti i componenti, introduzione al componente Frammento di contenuto | 6.3.1.0 | 6.4.0.0+ | - | 8 | 10 ottobre 2017 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | Diverse correzioni per il componente Immagine | 6.3.0.0+ | 6.4.0.0+ | - | 8 | 4 agosto 2017 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | Correzioni di componente Pagina, Componente Immagine, correzioni e miglioramenti globali | 6.3.0.0+ | 6.4.0.0+ | - | 8 | 26 aprile 2017 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | Correzioni per le immagini GIF animate nel componente Immagine | 6.3.0.0+ | 6.4.0.0+ | - | 7 | 22 marzo 2017 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | Versione iniziale dei componenti core | 6.3.0.0+ | 6.4.0.0+ | - | 7 | 20 marzo 2017 |

>[!NOTE]
>
>Come con AEM, Adobe consiglia agli sviluppatori di utilizzare la [versione più recente e le versioni dei componenti](https://github.com/adobe/aem-core-wcm-components/releases/latest) core disponibili, compatibile con la versione di AEM in esecuzione per trarre vantaggio dalle correzioni e funzioni più aggiornate.

### Versioni e versioni dei componenti {#component-versions-and-releases}

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

[L'authoring con Componenti core](authoring.md) descrive l'utilizzo dei componenti core e delle funzioni esposte agli autori di contenuto e agli autori dei modelli. Ogni componente è documentato in dettaglio.

[Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library.html) è una rappresentazione della versione corrente della maggior parte dei componenti core, illustrando come utilizzarli.

[Sviluppo di componenti](developing.md) core descrive le capacità tecniche dei componenti core, come usarli nei progetti, come personalizzare e best practice.

[L'Introduzione ai componenti core](introduction.md) offre una panoramica della compatibilità dei componenti core tra versioni, casi d'uso e supporto.
