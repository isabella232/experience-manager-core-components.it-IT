---
title: Versioni dei componenti core
seo-title: Versioni dei componenti core
description: I componenti core sono pubblicati come versioni che possono contenere più versioni degli stessi componenti core. Questo documento spiega cosa sono le versioni e come comprendere la compatibilità con i componenti core e AEM.
seo-description: I componenti core sono pubblicati come versioni che possono contenere più versioni degli stessi componenti core. Questo documento spiega cosa sono le versioni e come comprendere la compatibilità con i componenti core e AEM.
uuid: a916a923-8c5e-456a-84b5-b5228e21434
contentOwner: Utente
content-type: riferimento
topic-tags: introduzione
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS
discoiquuid: a3a98b2f-65bf-4493-82ad-01717938fdbc
translation-type: tm+mt
source-git-commit: d748bf211ec36d12cac016ca9bf707f24db1ce48

---


# Versioni dei componenti core{#core-components-versions}

La versione corrente dei componenti core è 2.7.0 ed è compatibile con AEM 6.5. È stato rilasciato a settembre 2019 come un aggiornamento importante per la release 2.0.0. La release 2.0.0 ha introdotto nuovi componenti insieme agli aggiornamenti v2 dei componenti esistenti.

Per ulteriori informazioni, consulta la sezione Cronologia [rilascio e compatibilità](#versions-and-releases) di questo documento.

È inoltre possibile consultare la Libreria [](http://opensource.adobe.com/aem-core-wcm-components/library.html)componenti, che presenta la versione corrente dei componenti core e ne illustra l’utilizzo.

## Versioni e release {#versions-and-releases}

I componenti core sono distribuiti tramite GitHub. Questo consente ad Adobe di aggiungere funzionalità più rapidamente ai componenti e di consentire l'input da parte della community al di fuori del ciclo di rilascio di AEM.

I componenti core sono disponibili con versioni AEM definite con cui sono compatibili. Ciò significa che una versione di AEM può supportare più versioni o rilasci dei componenti core. Ciò offre maggiore flessibilità rispetto ai precedenti componenti di base, che erano legati a una versione specifica di AEM.

### Versioni {#versions}

L'iterazione principale dei componenti core è costituita dalle **versioni**. Ogni componente ha una versione. Le versioni sono indicate con **v** aggiunto con un numero intero positivo diverso da zero, ad esempio v1 e v2. Le versioni vengono incrementate solo per le modifiche che non sono compatibili con le versioni precedenti, come avviene normalmente per l'introduzione di nuove funzioni e funzionalità.

Gli sviluppatori e gli amministratori possono riconoscere le versioni dei componenti core da un numero nei percorsi del tipo di risorsa e nei nomi completi delle classi Java delle loro implementazioni. Questo numero di versione rappresenta una versione principale, come definito dalle linee guida relative alle versioni [semantiche](https://semver.org/).

Per ulteriori informazioni sulle versioni dei componenti core, consulta la documentazione per [gli sviluppatori sui componenti](guidelines.md)core.

### Releases {#releases}

I componenti core sono disponibili tramite **le versioni** e [rappresentano gli artifact effettivamente pubblicati disponibili su GitHub](https://github.com/adobe/aem-core-wcm-components/releases). Releases are denoted with a decimal number of the format X.Y.Z and collect all core components together as a deliverable package.

* **Major releases can introduce new versions of existing components along with entirely new components as well as standard bug fixes.** This is represented by an increment in the X component of the release number.
* **Important releases can introduce new functionality to existing versions of components along with bug fixes.** This is represented by an increment in the Y component of the release number.
* **Minor releases contain only bug fixes.** È rappresentato da un incremento nel componente Z del numero di rilascio.

>[!NOTE]
>
>Releases can contain multiple versions of the same component.
>
>The same version of a component can appear in multiple releases.

## Release History and Compatibility {#release-history-and-compatibility}

The Core Components were first released with AEM 6.3 and are designed to be flexible and compatible with all supported AEM versions. Because of this a release of the components can contain multiple versions of the same component.

The following tables illustrate the compatibility of the releases of the Core Components along with which component versions are contained in which releases.

### Release History &amp; Supported AEM Versions {#release-history-supported-aem-versions}

The following table, the contents of which are [available on GitHub with full release details](https://github.com/adobe/aem-core-wcm-components/releases), gives an overview of the releases of the Core Components and their compatibility with AEM releases and Java versions.

| Release | Descrizione | AEM 6.3 | AEM 6.4 | AEM 6.5 | Java | Data di rilascio |
|---|---|---|---|---|---|---|
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | Questa versione ha introdotto il nuovo componente Incorpora | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | 8, 11 | 25 settembre 2019 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | Questa versione ha introdotto il nuovo componente Frammento esperienza | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | 8, 11 | 6 settembre 2019 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | Questa versione ha introdotto i nuovi componenti Accordion, Button, Container e Download. | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 | 25 giugno 2019 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | Questa versione ha introdotto il componente Elenco frammenti di contenuto | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 | 7 maggio 2019 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | Questa versione è stata dedicata ai miglioramenti apportati alla libreria di componenti, ma contiene anche alcune funzioni migliorate per il componente Separatore | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8 | 14 marzo 2019 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | Questa versione è incentrata sulla libreria dei componenti e sull’introduzione del nuovo componente separatore, ma contiene anche alcuni miglioramenti a livello di funzioni per il componente Immagine | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 11 febbraio 2019 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | Questa release è stata dedicata principalmente alle correzioni dei bug, ma contiene anche alcuni miglioramenti delle funzioni per il componente Carosello | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 27 novembre 2018 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | Sono stati introdotti componenti per schede e carosello, miglioramenti a immagini, pagine e titoli e funzionalità di tracciamento migliorate | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 16 ottobre 2018 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | È stato introdotto il componente teaser, sono stati apportati miglioramenti ai componenti immagine e sono stati corretti numerosi bug | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 13 luglio 2018 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | Rilascio di Bugfix | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 12 giugno 2018 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | Sono stati apportati ulteriori miglioramenti, correzioni di bug e piccoli miglioramenti, tra cui il supporto della riflessione delle immagini. | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 11 aprile 2018 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | Principalmente miglioramenti implementati, correzioni di bug e alcuni miglioramenti secondari dei componenti Immagine, Pagina e Frammento di contenuto | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 7 marzo 2018 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | Sono stati introdotti i componenti Navigazione, Navigazione lingua e Ricerca rapida. Sistema di stile implementato per tutti i componenti. | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 16 January 2018 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | Implementation of JSON export on all components, introduction of the Content Fragment component | 6.3.1.0 | 6.4.0.0+ | - | 8 | 10 October 2017 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | Several fixes for the Image component | 6.3.0.0+ | 6.4.0.0+ | - | 8 | 4 August 2017 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | Fixes of Page Component, Image Component, various global fixes and improvements | 6.3.0.0+ | 6.4.0.0+ | - | 8 | 26 April 2017 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | Fixes for animated GIF images in Image component | 6.3.0.0+ | 6.4.0.0+ | - | 7 | 22 March 2017 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | Initial release of Core Components | 6.3.0.0+ | 6.4.0.0+ | - | 7 | 20 March 2017 |

>[!NOTE]
>
>As with AEM, Adobe recommends that developers use the latest release and versions of the Core Components available that is compatible with the version of AEM that they are running in order to benefit from the most up-to-date fixes and features.[](https://github.com/adobe/aem-core-wcm-components/releases/latest)

### Component Versions &amp; Releases {#component-versions-and-releases}

The following table details which versions of which components are contained in which releases of the Core Components.

|  | Release 1.0.0 - 1.0.6 | Release 1.1.0 | Release 2.0.0 - 2.0.8 | Release 2.1.0 | Release 2.2.0-2.2.0 | Release 2.3.0-2.3.2 | Release 2.4.0 | Release 2.5.0 | Release 2.6.0 | Release 2.7.0+ |
|---|---|---|---|---|---|---|---|---|---|---|
| **[Page](page.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Titolo](title.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Immagine](image.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Elenco](list.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Breadcrumb](breadcrumb.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Condivisione social media](sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Contenitore modulo](form-container.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Testo modulo](form-text.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Opzioni modulo](form-options.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Nascosto per modulo](form-hidden.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Pulsante modulo](form-button.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Frammento di contenuto](content-fragment-component.md)** |  | Sandbox | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Navigazione](navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Navigazione lingua](language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Ricerca rapida](quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Teaser](teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Schede](tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Carosello](carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Separatore](separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[Elenco di frammenti di contenuto](content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[Accordion](accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Pulsante](button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Contenitore](separator.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Scarica](separator.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Frammento esperienza](separator.md)** |  |  |  |  |  |  |  |  | v1 | v1 |
| **[Embed](separator.md)** |  |  |  |  |  |  |  |  |  | v1 |

## Documentazione {#documentation}

[L’authoring con i componenti](authoring.md) core descrive l’utilizzo dei componenti core e le funzioni esposte agli autori dei contenuti e agli autori di modelli. Ogni componente è documentato in dettaglio.

[Libreria](http://opensource.adobe.com/aem-core-wcm-components/library.html) componenti è una vetrina della versione corrente della maggior parte dei componenti core, che illustra come possono essere utilizzati.

[Lo sviluppo di componenti](developing.md) di base descrive le funzionalità tecniche dei componenti di base, come utilizzarli nei progetti, come personalizzare e procedure ottimali.

[Introduzione](introduction.md) ai componenti core offre una panoramica della compatibilità dei componenti core tra versioni, casi di utilizzo e supporto.

[L’esercitazione](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) WKND è un’introduzione dettagliata allo sviluppo per AEM, compreso l’utilizzo dei componenti core.
