---
title: Versioni dei componenti core
seo-title: Versioni dei componenti core
description: I componenti core sono pubblicati come versioni che possono contenere più versioni degli stessi componenti core. Questo documento spiega cosa sono le versioni e come comprendere la compatibilità con i componenti core e AEM.
seo-description: I componenti core sono pubblicati come versioni che possono contenere più versioni degli stessi componenti core. Questo documento spiega cosa sono le versioni e come comprendere la compatibilità con i componenti core e AEM.
uuid: a916a923-8c5e-456a-84b5-b5228e21434
contentOwner: Utente
content-type: riferimento
topic-tags: introduzione
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: a3a98b2f-65bf-4493-82ad-01717938fdbc
translation-type: tm+mt
source-git-commit: 6882a0d8247328c403dc11a25ed9d079aefede69

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

Gli sviluppatori e gli amministratori possono riconoscere le versioni dei componenti core da un numero nei percorsi del tipo di risorsa e nei nomi completi delle classi Java delle loro implementazioni. This version number represents a major version as defined by semantic versioning guidelines.[](https://semver.org/)

For more details about core component versions, see the developer documentation of the Core Components.[](guidelines.md)

### Releases {#releases}

The core components are made available through releases and represent the actual published artifacts available on GitHub. ****[](https://github.com/adobe/aem-core-wcm-components/releases) Releases are denoted with a decimal number of the format X.Y.Z and collect all core components together as a deliverable package.

* **Major releases can introduce new versions of existing components along with entirely new components as well as standard bug fixes.** This is represented by an increment in the X component of the release number.
* **Important releases can introduce new functionality to existing versions of components along with bug fixes.** This is represented by an increment in the Y component of the release number.
* **Minor releases contain only bug fixes.** This is represented by an increment in the Z component of the release number.

>[!NOTE]
>
>Releases can contain multiple versions of the same component.
>
>La stessa versione di un componente può essere visualizzata in più versioni.

## Release History and Compatibility {#release-history-and-compatibility}

The Core Components were first released with AEM 6.3 and are designed to be flexible and compatible with all supported AEM versions. Di conseguenza, una versione dei componenti può contenere più versioni dello stesso componente.

Le tabelle seguenti illustrano la compatibilità delle versioni dei componenti core insieme alle versioni dei componenti contenute nelle varie versioni.

### Cronologia delle versioni e versioni AEM supportate {#release-history-supported-aem-versions}

La seguente tabella, il cui contenuto è [disponibile su GitHub con i dettagli](https://github.com/adobe/aem-core-wcm-components/releases)sulla versione completa, fornisce una panoramica delle versioni dei componenti core e della loro compatibilità con le versioni di AEM e Java.

| Release | Descrizione | AEM 6.3 | AEM 6.4 | AEM 6.5 | Java | Data di rilascio |
|---|---|---|---|---|---|---|
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | Questa versione ha introdotto il nuovo componente Incorpora | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 | 25 settembre 2019 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | Questa versione ha introdotto il nuovo componente Frammento esperienza | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 | 6 settembre 2019 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | Questa versione ha introdotto i nuovi componenti Accordion, Button, Container e Download. | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 | 25 giugno 2019 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | Questa versione ha introdotto il componente Elenco frammenti di contenuto | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 | 7 maggio 2019 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | Questa versione è stata dedicata ai miglioramenti apportati alla libreria di componenti, ma contiene anche alcune funzioni migliorate per il componente Separatore | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8 | 14 marzo 2019 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | Questa versione è incentrata sulla libreria dei componenti e sull’introduzione del nuovo componente separatore, ma contiene anche alcuni miglioramenti a livello di funzioni per il componente Immagine | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 11 febbraio 2019 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | Questa release è stata dedicata principalmente alle correzioni dei bug, ma contiene anche alcuni miglioramenti delle funzioni per il componente Carosello | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 27 novembre 2018 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | Sono stati introdotti componenti per schede e carosello, miglioramenti a immagini, pagine e titoli e funzionalità di tracciamento migliorate | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 16 ottobre 2018 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | È stato introdotto il componente teaser, sono stati apportati miglioramenti ai componenti immagine e sono stati corretti numerosi bug | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 13 July 2018 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | Bugfix release | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 12 June 2018 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | Sono stati apportati ulteriori miglioramenti, correzioni di bug e piccoli miglioramenti, tra cui il supporto della riflessione delle immagini. | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 11 aprile 2018 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | Mostly under-the-hood improvements, bug fixes, plus some minor improvements to the Image, Page, and Content Fragment Components | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 7 March 2018 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | Sono stati introdotti i componenti Navigazione, Navigazione lingua e Ricerca rapida. Style system implemented for all components. | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 16 January 2018 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | Implementation of JSON export on all components, introduction of the Content Fragment component | 6.3.1.0 | 6.4.0.0+ | - | 8 | 10 ottobre 2017 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | Diverse correzioni per il componente Immagine | 6.3.0.0+ | 6.4.0.0+ | - | 8 | 4 agosto 2017 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | Correzioni di componente pagina, componente immagine, varie correzioni e miglioramenti globali | 6.3.0.0+ | 6.4.0.0+ | - | 8 | 26 aprile 2017 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | Correzioni per immagini GIF animate nel componente Immagine | 6.3.0.0+ | 6.4.0.0+ | - | 7 | 22 marzo 2017 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | Versione iniziale dei componenti core | 6.3.0.0+ | 6.4.0.0+ | - | 7 | 20 marzo 2017 |

>[!NOTE]
>
>Come con AEM, Adobe consiglia agli sviluppatori di utilizzare la versione [più recente e le versioni dei componenti](https://github.com/adobe/aem-core-wcm-components/releases/latest) core disponibili, compatibili con la versione di AEM in esecuzione, al fine di trarre vantaggio dalle correzioni e dalle funzionalità più aggiornate.

### Versioni e release componenti {#component-versions-and-releases}

Nella tabella seguente sono illustrate le versioni dei componenti in cui sono contenuti i rilasci dei componenti core.

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
| **[Elenco frammenti di contenuto](content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[Accordion](accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Pulsante](button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Contenitore](separator.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Scarica](separator.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Frammento esperienza](separator.md)** |  |  |  |  |  |  |  |  | v1 | v1 |
| **[Incorpora](separator.md)** |  |  |  |  |  |  |  |  |  | v1 |

## Documentazione {#documentation}

[L’authoring con i componenti](authoring.md) core descrive l’utilizzo dei componenti core e le funzioni esposte agli autori dei contenuti e agli autori di modelli. Ogni componente è documentato in dettaglio.

[Libreria](http://opensource.adobe.com/aem-core-wcm-components/library.html) componenti è una vetrina della versione corrente della maggior parte dei componenti core, che illustra come possono essere utilizzati.

[Lo sviluppo di componenti](developing.md) di base descrive le funzionalità tecniche dei componenti di base, come utilizzarli nei progetti, come personalizzare e procedure ottimali.

[Introduzione](introduction.md) ai componenti core offre una panoramica della compatibilità dei componenti core tra versioni, casi di utilizzo e supporto.

[L’esercitazione](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) WKND è un’introduzione dettagliata allo sviluppo per AEM, compreso l’utilizzo dei componenti core.
