---
title: Sviluppo di componenti core
seo-title: Sviluppo di componenti core
description: I componenti core offrono componenti base affidabili ed estensibili che offrono funzionalità ricche di funzioni, prestazioni continue, controllo delle versioni dei componenti, implementazione moderna, marcatura lean e esportazione JSON dei contenuti.
seo-description: I componenti core offrono componenti base affidabili ed estensibili che offrono funzionalità ricche di funzioni, prestazioni continue, controllo delle versioni dei componenti, implementazione moderna, marcatura lean e esportazione JSON dei contenuti.
uuid: 68569 da 2-9 bc 8-4 e 20-9 a 71-e 5816 ace 51 ce
contentOwner: Utente
content-type: riferimento
topic-tags: sviluppo
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: 157 a 2 ec 3-9 fca -4 fad -977 a-d 93013 eeb 218
translation-type: tm+mt
source-git-commit: bea783936100abe899f9b60e4a09522514755db2

---


# Developing Core Components{#developing-core-components}

## Panoramica {#overview}

I componenti core forniscono componenti base affidabili ed estensibili e le relative evidenziazioni sono:

* Funzionalità avanzate
   * [Opzioni](authoring.md) di configurazione flessibili per contenere molti casi d&#39;uso
   * [Funzionalità preconfigurabili](authoring.md#pre-configuring-core-components) per definire quali funzioni sono disponibili per gli autori delle pagine
* Distribuzione continua
   * Miglioramenti frequenti alle funzionalità incrementali
   * Availability of the [source code on GitHub](https://github.com/adobe/aem-core-wcm-components) to allow the developer community to give feedback and contribute
   * Installation through a [separately released content package](https://github.com/adobe/aem-core-wcm-components/releases) for component upgrades to be done independently from AEM upgrades
* [Controllo delle versioni dei componenti](guidelines.md#component-versioning)
   * [Garantire la compatibilità all&#39;interno di una versione](#upgrade-of-core-components), ma consentire l&#39;evoluzione dei componenti
   * Consente la coesistere di più versioni di un componente nello stesso ambiente
* Implementazione moderna
   * Markup defined in [HTML Template Language](https://helpx.adobe.com/experience-manager/htl/using/overview.html) (HTL)
   * Content model logic implemented with [Sling Models](https://sling.apache.org/documentation/bundles/models.html)
* Marcatura lean
   * Following [Block Element Modifier](https://getbem.com/) (BEM) notation as of Release 2.0.0
      * Prior release follow [Bootstrap](https://getbootstrap.com/css/) naming conventions
   * Built around [accessibility guidelines](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)
   * Può essere utilizzato per siti reattivi e mobili
* Funzionalità per serializzare come JSON il modello di contenuto per i casi di utilizzo headless CMS
* Accessibile
   * Compliant with the [WCAG 2.0 AA standard](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

>[!CAUTION]
>
>Core Components require AEM 6.3 or later and Java 8 and and require the use of [editable templates](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)
>
>I componenti core non funzionano con l&#39;interfaccia classica né con i modelli statici.

## Gems Session Overview {#gems-session-overview}

For an introduction to the Core Components, the features they offer, and how they are leveraged in AEM, check out the AEM Gems Session [AEM Core Components.](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) è una serie di approfondimenti tecnici offerti dagli esperti Adobe. Questa serie integra la documentazione di prodotto e tutti gli altri canali tecnici, consentendo agli sviluppatori di mettersi in contatto con un argomento specifico.

## WKND Developer Tutorial {#wknd-developer-tutorial}

Get started developing AEM Sites with Core Components by following [this step-by-step tutorial.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## Delivered over GitHub {#delivered-over-github}

I componenti core vengono sviluppati e consegnati tramite github.

CODICE SU GITHUB

Potete trovare il codice di questa pagina su github

* [Apri progetto aem-core-wcm-components su github](https://github.com/adobe/aem-core-wcm-components)
* Download the project as [a ZIP file](https://github.com/adobe/aem-core-wcm-components/archive/master.zip)

See the [Using Core Components](using.md) documentation page to learn how to get started using them in your project.

La disponibilità dei componenti core su github consentirà di effettuare aggiornamenti frequenti e di ascoltare i commenti della community di sviluppatori AEM. Inoltre, questa funzione dovrebbe aiutare clienti e partner a seguire pattern simili durante la creazione di componenti personalizzati.

>[!NOTE]
>
>To keep up-to-date on the latest changes to the core components, you can watch the [Core Components repository](https://github.com/adobe/aem-core-wcm-components) on GitHub.

## Libreria componenti

Check out the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library.html), which showcases the current release of the Core Components and gives examples of their usage.

### Sample Content Run-Mode {#sample-content-run-mode}

The Core Components are visible in the Quickstart when the sample content is present, because the [We.Retail reference site](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) uses them. However, when running in production (in `nosamplecontent` runmode, without sample content enabled), the core components won&#39;t be present anymore and must be installed on the AEM instances by the development and/or operations team.

>[!NOTE]
>
>In production environments, always run the Quickstart in `nosamplecontent` runmode. To use the Core Components in `nosamplecontent` runmode, follow the instructions of the [Using Core Components](using.md) documentation page.

## Technical Capabilities {#technical-capabilities}

La tabella seguente fornisce una panoramica delle differenze tra componenti core e componenti di base.

For details about their authoring capabilities and options to pre-configurable them, [refer to the authoring page about them](authoring.md).

| **Funzionalità** | **Componente core** | **Componente Foundation** |
|-----|---|---|
| Implementazione logica | Java POJOs with [Sling Models](https://sling.apache.org/documentation/bundles/models.html) annotations | Codice JSP |
| Definizione di marcatura | [Sintassi HTL](https://helpx.adobe.com/experience-manager/htl/user-guide.html) (HTML Template Language) | Codice JSP |
| Pulizia XSS | Automatizzato per HTL | Più manuale |
| Denominazione delle classi CSS | Standardized naming convention based on [Block Element Modifier](https://getbem.com/) (BEM) notation (as of release 2.0.0) | Schemi personalizzati |
| Definizione finestra di dialogo | [Coral 3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Interfaccia Coral 2 + Classic |
| Output JSON | [Sling Models Exporter con serializzazione Jackson](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | Servlet Sling predefinito |
| Gestione versioni | [Per il modello e l&#39;HTL](guidelines.md) | Nessuno |
| Test | Test unità + Test integrazione | Test integrazione |
| Consegna | [Tramite github pubblico](https://github.com/adobe/aem-core-wcm-components) | Tramite Avvio rapido |
| Licenza | [Licenza Apache](https://www.apache.org/licenses/LICENSE-2.0) | Proprietario di Adobe |
| Contributo | Tramite richiesta di pull | Non possibile |
| Accessibilità | Fully compliant with the [WCAG 2.0 AA standard](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) | Only partially compliant with the [WCAG 2.0 AA standard](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) |

## Component List {#component-list}

Nella tabella seguente sono elencati i componenti core disponibili, che collegano all&#39;API e indicano quali componenti di base sostituiscono.

| Componente core | Descrizione | Sostituiti i componenti Foundation |
|---|---|---|
| [Pagina](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page) | Pagina reattiva con editor modelli | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [Breadcrumb](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb) | Navigazione gerarchica delle pagine | `/libs/foundation/components/breadcrumb` |
| [Titolo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v2/title) | Titolo H 1-H 6 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [Testo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | Testo RTF | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [Immagine](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v2/image) | Caricamento intelligente e lazy di dimensioni di rappresentazione ottimali | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [Elenco](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list) | Elenco di pagine | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [Condivisione social media](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/sharing/v1/sharing) | Widget di condivisione Facebook e Pinterest | `-` |
| [Contenitore modulo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v2/container) | Sistema paragrafo modulo reattivo | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [Testo modulo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v2/text) | Campo di immissione testo | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [Opzioni modulo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v2/options) | Campo di immissione più opzioni | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [Nascosto per modulo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v2/hidden) | Campo di immissione nascosto | `/libs/foundation/components/form/hidden` |
| [Pulsante modulo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v2/button) | Pulsante Invia o personalizzato | `/libs/foundation/components/form/submit` |
| [Navigazione](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/navigation/v1/navigation) | Componente di navigazione del sito che elenca la gerarchia di pagine nidificata | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [Navigazione lingua](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation) | Una lingua e un commutatore per paese che elenca la struttura globale del linguaggio | `-` |
| [Ricerca rapida](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/search/v1/search) | Componente ricerca che visualizza i risultati come suggerimenti interni in un menu a discesa | `/libs/foundation/components/search` |
| [Teaser](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser) | Consente all&#39;autore del contenuto di creare facilmente un teaser con un&#39;immagine, un titolo o un testo RTF e il collegamento a un altro contenuto o ad altre azioni | `-` |
| [Schede](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs) | Consente all&#39;autore del contenuto di organizzare il contenuto della pagina all&#39;interno di più schede | `-` |
| [Carosello](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel) | Consente all&#39;autore del contenuto di organizzare il contenuto in un carosello di diapositive | `/libs/foundation/components/carousel` |
| [Frammento di contenuto](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragment/v1/contentfragment) | Consente la visualizzazione di un frammento di contenuto | `-` |
| [Elenco frammenti di contenuto](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragmentlist/v1/contentfragmentlist) | Consente la visualizzazione di un elenco di frammenti di contenuto | `-` |
| [Separatore](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/separator/v1/separator) | Separa il contenuto di una pagina | `-` |
| [Accordion](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/accordion/v1/accordion) | Organizzare i pannelli dei contenuti in un pannello accordion comprimibile | `-` |
| [Contenitore](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/container/v1/container) | Organizzare i componenti all&#39;interno di un contenitore | `-` |
| [Pulsante](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/button/v1/button) | Creare un pulsante su una pagina | `-` |
| [Scarica](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/download/v1/download) | Aggiungere una risorsa scaricabile a una pagina | `-` |

### Upcoming components {#upcoming-components}

Stiamo lavorando attivamente sui seguenti componenti core. They haven&#39;t been released yet, but can be previewed in the [development branch](https://github.com/adobe/aem-core-wcm-components/tree/development):

* Incorpora
* Finestra modale

## Upgrade of Core Components {#upgrade-of-core-components}

Un vantaggio dei componenti su versione è che consente di separare la migrazione a una nuova versione AEM dalla migrazione alle nuove versioni dei componenti. Inoltre, se sono disponibili nuove versioni dei componenti, consente la singola migrazione di ciascun componente alla nuova versione.

Le migrazioni a una nuova versione AEM non influenzeranno l&#39;utilizzo dei componenti core, a condizione che le loro versioni supportino anche la nuova versione AEM alla quale viene trasferito. Customizations made to the Core Components should not be affected either, as long as they don&#39;t use APIs that have been [deprecated or removed](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html).

Le migrazioni a nuove versioni dei componenti core non influenzeranno l&#39;utilizzo del componente, ma le nuove funzioni potrebbero essere introdotte agli autori delle pagine, che potrebbero richiedere alcune configurazioni da parte di un editor modelli, nel caso in cui il comportamento predefinito non sia desiderato. Customizations however might need to be adapted, for more details see the [Customizing Core Components](customizing.md#upgrade-compatibility-of-customizations) page.

## When to Use the Core Components? {#when-to-use-the-core-components}

Poiché i componenti core sono completamente nuovi e offrono più vantaggi, è consigliabile utilizzare i nuovi progetti AEM. Per i progetti esistenti, una migrazione deve far parte di un&#39;attività di progetto più grande, ad esempio un rebranding o un refactoring complessivo.

Di conseguenza, Adobe fornisce le raccomandazioni seguenti:

* **Nuovi progetti**
I nuovi progetti devono sempre tentare di utilizzare componenti core. If Core Components cannot be used directly or [extended](customizing.md) to satisfy project requirements, then create a custom component following the component architecture set forth in core components. Except where not otherwise possible, avoid using the [foundation components](developing.md).
* **La raccomandazione Progetti**
esistenti continua a utilizzare i componenti [di base](developing.md), a meno che sia pianificato un sito o una funzione di reimpostazione del componente.\
   As they are very widely used by most existing projects, the foundation components [will continue to be supported.](developing.md)
* **Nuovi componenti
personalizzati** Valuta se un componente [di base esistente può essere personalizzato](customizing.md).\
   If not, recommendation is to build a new custom component following the [Component Guidelines](guidelines.md).
* **Componenti
personalizzati esistenti** Se i componenti funzionano come previsto, conservali così come sono.\
   In caso contrario, fai riferimento a «Nuovi componenti personalizzati» sopra.

## Migrazione ai componenti core

Qualsiasi nuovo progetto deve essere implementato con Componenti core. Tuttavia, in genere i progetti esistenti saranno caratterizzati da ampie implementazioni dei componenti di base.

Un lavoro più ampio su un progetto esistente (ad esempio un rebranding o un refactoring complessivo) offre spesso la possibilità di passare ai componenti core. Per semplificare questa migrazione, Adobe ha fornito una serie di strumenti di migrazione per incoraggiare l&#39;adozione dei componenti core e della tecnologia AEM più recente.

[Gli strumenti di modernizzazione di AEM](http://opensource.adobe.com/aem-modernize-tools/) consentono la conversione semplice di:

* Modelli statici a modelli modificabili
* Configurazione delle configurazioni ai criteri
* Componenti di base ai componenti core
* Interfaccia classica nell&#39;interfaccia touch

For further information about the usage of these tools, [see their documentation](http://opensource.adobe.com/aem-modernize-tools/).

>[!NOTE]
>
>Gli strumenti di modernizzazione AEM sono sforzi della community e non sono supportati o controllati da Adobe.

## Core Component Support {#core-component-support}

I componenti core sono parte integrante di AEM e sono supportati così come sono, con gli stessi termini e condizioni di questa distribuzione come parte della sezione Quickstart.

Come per le altre funzionalità del prodotto AEM, la regola generale è: I componenti vengono inizialmente dichiarati obsoleti e il primo viene rimosso per la seguente release AEM. Questo offre ai clienti almeno un processo di rilascio per passare alla nuova versione del componente, prima di rilasciare il supporto.

La versione di ciascun componente indica chiaramente le versioni AEM supportate. Quando il supporto viene interrotto per una versione di AEM, questo supporta anche i componenti core per quella versione di AEM.

For details about the support of component customizations, see the [Customizing Core Components](customizing.md) page.

## Foundation Component Support {#foundation-component-support}

Poiché i componenti di base sono stati gestiti come base per lo sviluppo di progetti in molte versioni AEM, continueranno a essere supportati nel prossimo futuro.

However, Adobe&#39;s development emphasis has shifted to the Core Components and new features will be added to them, whereas [nearly all Foundation Components have been deprecated with AEM 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) and only bug fixes will be made to the Foundation Components going forward.

**Leggi avanti:**

* [Utilizzo dei componenti](using.md) core: diventa disponibile con componenti core nel tuo progetto.
* [Linee guida sui componenti](guidelines.md) - per apprendere i pattern di implementazione dei componenti core.
