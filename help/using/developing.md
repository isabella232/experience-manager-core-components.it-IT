---
title: Sviluppo di componenti core
seo-title: Sviluppo di componenti core
description: I componenti core forniscono componenti di base affidabili ed estensibili che offrono funzionalità avanzate, distribuzione continua, controllo delle versioni dei componenti, implementazione moderna, marcatura snella ed esportazione JSON di contenuti.
seo-description: I componenti core forniscono componenti di base affidabili ed estensibili che offrono funzionalità avanzate, distribuzione continua, controllo delle versioni dei componenti, implementazione moderna, marcatura snella ed esportazione JSON di contenuti.
uuid: 68569da2-9bc8-4e20-9a71-e5816ace51ce
contentOwner: Utente
content-type: riferimento
topic-tags: development
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 157a2ec3-9fca-4fad-977a-d93013eeb218
translation-type: tm+mt
source-git-commit: 63e75079e41d3091ca57bfc3129e700675bf4939

---


# Sviluppo di componenti core{#developing-core-components}

## Panoramica {#overview}

I componenti core forniscono componenti di base affidabili ed estensibili e i loro elementi di rilievo sono:

* Funzionalità avanzate
   * [Opzioni](authoring.md) di configurazione flessibili per molti casi di utilizzo
   * [Funzionalità](authoring.md#pre-configuring-core-components) preconfigurabili per definire quali funzioni sono disponibili per gli autori delle pagine
* Consegna continua
   * Miglioramenti frequenti delle funzionalità incrementali
   * Disponibilità del codice [sorgente su GitHub](https://github.com/adobe/aem-core-wcm-components) per consentire alla comunità di sviluppatori di fornire feedback e contribuire
   * Installazione tramite un pacchetto [di contenuti rilasciato](https://github.com/adobe/aem-core-wcm-components/releases) separatamente per gli aggiornamenti dei componenti da eseguire indipendentemente dagli aggiornamenti di AEM
* [Versione componente](guidelines.md#component-versioning)
   * [Garantire la compatibilità all'interno di una versione](#upgrade-of-core-components), ma consentire ai componenti di evolversi
   * Consentire la coesistenza di più versioni di un componente nello stesso ambiente
* Implementazione moderna
   * Markup definito in [HTML Template Language](https://helpx.adobe.com/experience-manager/htl/using/overview.html) (HTL)
   * Logica del modello di contenuto implementata con i modelli [Sling](https://sling.apache.org/documentation/bundles/models.html)
* Marcatura iniziale
   * Seguente notazione del modificatore [elemento](https://getbem.com/) blocco (BEM) a partire dalla release 2.0.0
      * Le versioni precedenti seguono le convenzioni di denominazione di [Bootstrap](https://getbootstrap.com/css/)
   * Built around [accessibility guidelines](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)
   * Utilizzabile per siti reattivi e mobili
* Possibilità di serializzare come JSON il modello di contenuto per i casi di utilizzo headless CMS
* Accessibile
   * Conforme allo standard [WCAG 2.0 AA](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

>[!CAUTION]
>
>I componenti core richiedono AEM 6.3 o versione successiva e Java 8 e richiedono l’uso di modelli [modificabili](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)
>
>I componenti core non funzionano né con l’interfaccia classica né con i modelli statici.

## Panoramica della sessione Gems {#gems-session-overview}

Per un'introduzione ai componenti core, alle funzioni che offrono e alla modalità di utilizzo in AEM, consultate i componenti core di AEM Gems Session [AEM.](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) è una serie di approfondimenti tecnici offerti dagli esperti Adobe. Questa serie integra la documentazione del prodotto e tutti gli altri canali tecnici, consentendo agli sviluppatori di mettersi in contatto e approfondire un argomento specifico.

## Esercitazione per sviluppatori WKND {#wknd-developer-tutorial}

Inizia a sviluppare AEM Sites con i componenti core seguendo [questa esercitazione passo-passo.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## Consegnato su GitHub {#delivered-over-github}

I componenti core sono sviluppati e forniti tramite GitHub.

CODICE SU GITHUB

Puoi trovare il codice di questa pagina su GitHub

* [Open aem-core-wcm-components project on GitHub](https://github.com/adobe/aem-core-wcm-components)
* Scarica il progetto come [file ZIP](https://github.com/adobe/aem-core-wcm-components/archive/master.zip)

Consultate la pagina della documentazione [Utilizzo dei componenti](using.md) core per apprendere come iniziare a utilizzarli nel progetto.

Disporre dei componenti core su GitHub consentirà di effettuare aggiornamenti frequenti e di ascoltare i commenti della comunità di sviluppatori AEM. Inoltre, questo dovrebbe aiutare clienti e partner a seguire pattern simili durante la creazione di componenti personalizzati.

>[!NOTE]
>
>Per essere aggiornati sulle ultime modifiche apportate ai componenti core, puoi vedere l’archivio [Componenti](https://github.com/adobe/aem-core-wcm-components) principali su GitHub.

## Libreria dei componenti

Consulta la Libreria [](http://opensource.adobe.com/aem-core-wcm-components/library.html)componenti, che presenta la versione corrente dei componenti core e ne illustra l’utilizzo.

### Esempio di modalità esecuzione contenuto {#sample-content-run-mode}

I componenti core sono visibili in Avvio rapido quando è presente il contenuto di esempio, in quanto vengono utilizzati dal sito [di riferimento](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) We.Retail. Tuttavia, in fase di produzione (in `nosamplecontent` modalità di esecuzione, senza che sia abilitato il contenuto di esempio), i componenti core non saranno più presenti e dovranno essere installati nelle istanze di AEM dal team di sviluppo e/o dalle operazioni.

>[!NOTE]
>
>Negli ambienti di produzione, esegui sempre il Quickstart in `nosamplecontent` modalità di esecuzione. Per utilizzare i componenti core in `nosamplecontent` modalità di esecuzione, segui le istruzioni della pagina della documentazione [Uso dei componenti](using.md) core.

## Funzionalità tecniche {#technical-capabilities}

La tabella seguente fornisce una panoramica delle differenze tra i componenti core e i componenti di base.

Per informazioni dettagliate sulle funzionalità di authoring e sulle opzioni per la preconfigurazione, [consultare la pagina dedicata](authoring.md)all’authoring.

| **Funzionalità** | **Componente core** | **Componente Foundation** |
|-----|---|---|
| Implementazione logica | Java POJO con annotazioni [Sling Models](https://sling.apache.org/documentation/bundles/models.html) | Codice JSP |
| Definizione di markup | [Sintassi HTML Template Language](https://helpx.adobe.com/experience-manager/htl/user-guide.html) (HTL) | Codice JSP |
| Scarico XSS | Automatizzato da HTL | Principalmente manuale |
| Denominazione delle classi CSS | Convenzione di denominazione standard basata sulla notazione [del modificatore](https://getbem.com/) di elementi di blocco (BEM) (dalla release 2.0.0) | Schemi personalizzati |
| Definizione finestra di dialogo | [Corallo 3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Corallo 2 + Interfaccia classica |
| Uscita JSON | [Sling Models Exporter con serializzazione Jackson](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | Servlet Sling predefinito |
| Gestione versioni | [Per il modello e l'HTL](guidelines.md) | Nessuno |
| Test | Test di unità + test di integrazione | Test di integrazione |
| Consegna | [Tramite GitHub pubblico](https://github.com/adobe/aem-core-wcm-components) | Via Quickstart |
| Licenza | [Licenza Apache](https://www.apache.org/licenses/LICENSE-2.0) | Proprietà Adobe |
| Contributo | Tramite richiesta pull | Impossibile |
| Accessibilità | Completamente conforme allo standard [WCAG 2.0 AA](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) | Solo parzialmente conforme allo standard [WCAG 2.0 AA](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) |

## Elenco componenti {#component-list}

Nella tabella seguente sono elencati i componenti core disponibili, che si collegano all'API e indicano quali componenti di base sostituire.

| Componente core | Descrizione | Componenti di base sostituiti |
|---|---|---|
| [Pagina](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page) | Pagina reattiva che utilizza l’editor modelli | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [Breadcrumb](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb) | Navigazione gerarchica delle pagine | `/libs/foundation/components/breadcrumb` |
| [Titolo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v2/title) | Titolo H1-H6 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [Testo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | RTF | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [Immagine](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v2/image) | Caricamento intelligente e pigro delle dimensioni di rappresentazione ottimali | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [Elenco](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list) | Elenco di pagine | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [Condivisione social media](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/sharing/v1/sharing) | widget di condivisione Facebook e Pinterest | `-` |
| [Contenitore modulo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v2/container) | Sistema paragrafo modulo reattivo | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [Testo modulo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v2/text) | Campo di immissione testo | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [Opzioni modulo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v2/options) | Campo di immissione opzioni multiple | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [Nascosto per modulo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v2/hidden) | Campo di input nascosto | `/libs/foundation/components/form/hidden` |
| [Pulsante modulo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v2/button) | Pulsante Invia o personalizzato | `/libs/foundation/components/form/submit` |
| [Navigazione](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/navigation/v1/navigation) | Un componente di navigazione del sito che elenca la gerarchia di pagine nidificata | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [Navigazione lingua](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation) | Uno switcher di lingua e Paese che elenca la struttura globale della lingua | `-` |
| [Ricerca rapida](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/search/v1/search) | Componente di ricerca che visualizza i risultati come suggerimenti inseriti in un menu a discesa | `/libs/foundation/components/search` |
| [Teaser](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser) | Consente all’autore del contenuto di creare facilmente un teaser per l’ulteriore contenuto utilizzando un’immagine, un titolo o un RTF e collegando altri contenuti o altre azioni | `-` |
| [Schede](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs) | Consente all’autore del contenuto di organizzare il contenuto della pagina all’interno di più schede | `-` |
| [Carosello](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel) | Consente all’autore del contenuto di organizzare il contenuto in un carosello rotante di diapositive | `/libs/foundation/components/carousel` |
| [Frammento di contenuto](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragment/v1/contentfragment) | Consente la visualizzazione di un frammento di contenuto | `-` |
| [Elenco frammenti di contenuto](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragmentlist/v1/contentfragmentlist) | Consente di visualizzare un elenco dei frammenti di contenuto | `-` |
| [Separatore](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/separator/v1/separator) | Separa il contenuto di una pagina | `-` |
| [Accordion](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/accordion/v1/accordion) | Organizzare i pannelli dei contenuti in un ambiente comprimibile | `-` |
| [Contenitore](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/container/v1/container) | Organizzare i componenti all’interno di un contenitore | `-` |
| [Pulsante](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/button/v1/button) | Creare un pulsante su una pagina | `-` |
| [Scarica](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/download/v1/download) | Aggiunta di una risorsa scaricabile a una pagina | `-` |
| [Frammento esperienza](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/experience-fragment/v1/experience-fragment) | Aggiunta di un frammento esperienza a una pagina | `/libs/cq/experience-fragments/editor/components/experiencefragment` |

### Componenti in arrivo {#upcoming-components}

Per una panoramica della roadmap di Componente principale in arrivo, vedi il wiki di [progetto su GitHub](https://github.com/adobe/aem-core-wcm-components/wiki/home).

## Aggiornamento dei componenti core {#upgrade-of-core-components}

Un vantaggio dei componenti con versione è rappresentato dal fatto che consente di separare la migrazione a una nuova versione di AEM dalla migrazione alle nuove versioni dei componenti. Inoltre, se sono disponibili nuove versioni di componenti, è possibile migrare singolarmente ogni componente alla nuova versione.

Le migrazioni a una nuova versione di AEM non avranno alcun impatto sul funzionamento dei componenti core, a condizione che le loro versioni supportino anche la nuova versione di AEM in cui viene eseguita la migrazione. Le personalizzazioni effettuate sui componenti core non devono essere influenzate, a condizione che non utilizzino API che sono state [obsolete o rimosse](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html).

Le migrazioni a nuove versioni dei componenti core non influiranno neanche sul funzionamento del componente, ma potrebbero essere introdotte nuove funzionalità agli autori di pagine, che potrebbero richiedere alcune configurazioni da parte di un editor modelli, nel caso in cui il comportamento predefinito non sia desiderato. Potrebbe tuttavia essere necessario adattare le personalizzazioni, per ulteriori dettagli consultate la pagina [Personalizzazione dei componenti](customizing.md#upgrade-compatibility-of-customizations) core.

## Quando utilizzare i componenti core? {#when-to-use-the-core-components}

Poiché i componenti core sono completamente nuovi e offrono molteplici vantaggi, si consiglia di utilizzarli nei nuovi progetti AEM. Per i progetti esistenti, una migrazione dovrebbe essere parte di un progetto più ampio, ad esempio un rifacimento o un refactoring complessivo.

Di conseguenza, Adobe fornisce le seguenti raccomandazioni:

* **Nuovi progetti** I nuovi progetti devono sempre tentare di utilizzare i componenti core. Se i componenti core non possono essere utilizzati direttamente o [estesi](customizing.md) per soddisfare i requisiti del progetto, create un componente personalizzato seguendo l’architettura dei componenti impostata nei componenti core. Eccetto dove non altrimenti possibile, evitare di utilizzare i componenti [](developing.md)di base.
* **La** raccomandazione progetti [esistenti viene mantenuta utilizzando i componenti](developing.md)di base, a meno che non sia pianificato il refactoring di un sito o di un componente.\
   Poiché sono ampiamente utilizzati dalla maggior parte dei progetti esistenti, i componenti di base [continueranno ad essere sostenuti.](developing.md)
* **Nuovi componenti** personalizzati Se è possibile personalizzare [un componente](customizing.md)core esistente.\
   In caso contrario, si consiglia di creare un nuovo componente personalizzato seguendo le linee guida [sui](guidelines.md)componenti.
* **Componenti** personalizzati esistenti Se i componenti funzionano come previsto, mantenerli come sono.\
   In caso contrario, fare riferimento a "Nuovi componenti personalizzati" sopra.

## Migrazione ai componenti core

Qualsiasi nuovo progetto deve essere implementato con i componenti core. Tuttavia, i progetti esistenti avranno generalmente ampie implementazioni dei componenti di base.

Uno sforzo maggiore su un progetto esistente (ad esempio un rebranding o un refactoring complessivo) spesso offre la possibilità di eseguire la migrazione ai componenti core. Per facilitare questa migrazione, Adobe ha fornito una serie di strumenti di migrazione per incoraggiare l'adozione dei componenti core e della più recente tecnologia AEM.

[Gli strumenti](http://opensource.adobe.com/aem-modernize-tools/) di modernizzazione AEM consentono di convertire facilmente:

* Modelli statici per modelli modificabili
* Progettare configurazioni per i criteri
* Componenti di base per componenti core
* Interfaccia classica per interfaccia touch

Per ulteriori informazioni sull’utilizzo di questi strumenti, [consulta la relativa documentazione](http://opensource.adobe.com/aem-modernize-tools/).

>[!NOTE]
>
>Gli strumenti AEM Modernize sono uno sforzo della community e non sono supportati o giustificati da Adobe.

## Supporto dei componenti core {#core-component-support}

I componenti core sono parte integrante di AEM e sono supportati così come lo sono, secondo gli stessi termini e condizioni come se fossero stati consegnati come parte del Quickstart.

Come per le altre funzioni del prodotto AEM, la regola generale è: I componenti vengono inizialmente dichiarati obsoleti e i primi rimossi per la seguente release di AEM. Questo consente ai clienti di passare alla nuova versione del componente almeno un ciclo di rilascio prima di lasciarne indietro il supporto.

La versione di ciascun componente indica chiaramente le versioni AEM supportate. Quando il supporto per una versione di AEM cessa, viene utilizzato anche il supporto dei componenti core per tale versione di AEM.

Per informazioni dettagliate sul supporto delle personalizzazioni dei componenti, consultate la pagina [Personalizzazione dei componenti](customizing.md) core.

## Supporto dei componenti di base {#foundation-component-support}

Poiché i componenti di base sono stati utilizzati come base per lo sviluppo di molti progetti in molte versioni di AEM, continueranno a essere supportati nel prossimo futuro.

Tuttavia, l'enfasi di sviluppo di Adobe si è spostata sui componenti core e le nuove funzioni verranno aggiunte a tali componenti, mentre [quasi tutti i componenti di base sono stati dichiarati obsoleti con AEM 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) e solo le correzioni di bug verranno apportate ai componenti di base in futuro.

**Ulteriori informazioni:**

* [Utilizzo dei componenti](using.md) di base: per iniziare a usare i componenti di base nel tuo progetto.
* [Linee guida](guidelines.md) per i componenti - per apprendere i pattern di implementazione dei componenti core.
