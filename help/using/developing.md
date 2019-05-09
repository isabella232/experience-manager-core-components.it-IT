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
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# Sviluppo di componenti core{#developing-core-components}

## Panoramica {#overview}

I componenti core forniscono componenti base affidabili ed estensibili e le relative evidenziazioni sono:

* Funzionalità avanzate
   * [Opzioni](authoring.md) di configurazione flessibili per contenere molti casi d&#39;uso
   * [Funzionalità preconfigurabili](authoring.md#pre-configuring-core-components) per definire quali funzioni sono disponibili per gli autori delle pagine
* Distribuzione continua
   * Miglioramenti frequenti alle funzionalità incrementali
   * Disponibilità del codice [sorgente su github](https://github.com/adobe/aem-core-wcm-components) per consentire alla comunità di sviluppatori di fornire feedback e contribuire
   * Installazione tramite un [pacchetto di contenuto rilasciato separatamente](https://github.com/adobe/aem-core-wcm-components/releases) per gli aggiornamenti dei componenti che devono essere eseguiti in modo indipendente dagli aggiornamenti AEM
* [Controllo delle versioni dei componenti](guidelines.md#component-versioning)
   * [Garantire la compatibilità all&#39;interno di una versione](#upgrade-of-core-components), ma consentire l&#39;evoluzione dei componenti
   * Consente la coesistere di più versioni di un componente nello stesso ambiente
* Implementazione moderna
   * Marcatura definita in [HTML Template Language](https://helpx.adobe.com/experience-manager/htl/using/overview.html) (HTL)
   * Logica del modello contenuto implementata con [Sling Models](https://sling.apache.org/documentation/bundles/models.html)
* Marcatura lean
   * La notazione BEM ( [Block Element Modificator](https://getbem.com/) ) seguente a partire dalla release 2.0.0
      * La versione precedente segue [le convenzioni](https://getbootstrap.com/css/) di denominazione di Bootstrap
   * Basato sulle [linee guida per l&#39;accessibilità](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)
   * Può essere utilizzato per siti reattivi e mobili
* Funzionalità per serializzare come JSON il modello di contenuto per i casi di utilizzo headless CMS
* Accessibile
   * Conforme allo standard [WCAG 2.0 AA](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

>[!CAUTION]
>
>I componenti core richiedono AEM 6.3 o versione successiva e Java 8.
>
>I componenti core non funzionano con l&#39;interfaccia classica.

## Panoramica della sessione Gems {#gems-session-overview}

Per un&#39;introduzione ai componenti core, alle funzioni che essi offrono e alle modalità di utilizzo in AEM, consulta i componenti core [AEM Gems Session AEM.](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) è una serie di approfondimenti tecnici offerti dagli esperti Adobe. Questa serie integra la documentazione di prodotto e tutti gli altri canali tecnici, consentendo agli sviluppatori di mettersi in contatto con un argomento specifico.

## WKND Developer Tutorial {#wknd-developer-tutorial}

[Scopri come sviluppare AEM Sites con componenti core seguendo questa esercitazione.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## Consegnato tramite github {#delivered-over-github}

I componenti core vengono sviluppati e consegnati tramite github.

CODICE SU GITHUB

Potete trovare il codice di questa pagina su github

* [Apri progetto aem-core-wcm-components su github](https://github.com/adobe/aem-core-wcm-components)
* Scaricare il progetto come [file ZIP](https://github.com/adobe/aem-core-wcm-components/archive/master.zip)

Consulta la [pagina della](using.md) documentazione Utilizzo dei componenti core per apprendere come iniziare a utilizzarli nel progetto.

La disponibilità dei componenti core su github consentirà di effettuare aggiornamenti frequenti e di ascoltare i commenti della community di sviluppatori AEM. Inoltre, questa funzione dovrebbe aiutare clienti e partner a seguire pattern simili durante la creazione di componenti personalizzati.

>[!NOTE]
>
>Per tenere aggiornato le modifiche più recenti apportate ai componenti core, puoi guardare l&#39;archivio Componenti [core](https://github.com/adobe/aem-core-wcm-components) su github.

## Libreria componenti

Controllate la [Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library.html), che mostra la versione corrente dei componenti core e ne fornisce esempi di utilizzo.

### Esempio di esecuzione contenuto {#sample-content-run-mode}

I componenti core sono visibili nell&#39;Avvio rapido quando il contenuto di esempio è presente, in quanto il sito di riferimento [We. Retail li](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) utilizza. Tuttavia, quando in fase di esecuzione (in `nosamplecontent` modalità runmode, senza contenuto di esempio abilitato), i componenti core non saranno più presenti e devono essere installati nelle istanze AEM dal team di sviluppo e/o operazioni.

>[!NOTE]
>
>In ambienti di produzione, eseguite sempre l&#39;Avvio rapido in `nosamplecontent` modalità runmode. Per utilizzare i componenti core in `nosamplecontent` modalità runmode, seguite le istruzioni della pagina [della documentazione Utilizzo dei componenti](using.md) core.

## Funzionalità tecniche {#technical-capabilities}

La tabella seguente fornisce una panoramica delle differenze tra componenti core e componenti di base.

Per informazioni dettagliate sulle capacità e sulle opzioni di authoring per preconfigurarle, [fate riferimento alla pagina di authoring](authoring.md).

| **Funzionalità** | **Componente core** | **Componente Foundation** |
|-----|---|---|
| Implementazione logica | Java pojos con [annotazioni per modelli](https://sling.apache.org/documentation/bundles/models.html) Sling | Codice JSP |
| Definizione di marcatura | [Sintassi HTL](https://helpx.adobe.com/experience-manager/htl/user-guide.html) (HTML Template Language) | Codice JSP |
| Pulizia XSS | Automatizzato per HTL | Più manuale |
| Denominazione delle classi CSS | Convenzione di denominazione standardizzata basata [sulla notazione del modificatore](https://getbem.com/) elemento block (BEM) (a partire dalla release 2.0.0) | Schemi personalizzati |
| Definizione finestra di dialogo | [Coral 3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Interfaccia Coral 2 + Classic |
| Output JSON | [Sling Models Exporter con serializzazione Jackson](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | Servlet Sling predefinito |
| Gestione versioni | [Per il modello e l&#39;HTL](guidelines.md) | Nessuno |
| Test | Test unità + Test integrazione | Test integrazione |
| Consegna | [Tramite github pubblico](https://github.com/adobe/aem-core-wcm-components) | Tramite Avvio rapido |
| Licenza | [Licenza Apache](https://www.apache.org/licenses/LICENSE-2.0) | Proprietario di Adobe |
| Contributo | Tramite richiesta di pull | Non possibile |
| Accessibilità | Completamente conforme allo standard [WCAG 2.0 AA](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) | Conforme solo parzialmente allo [standard WCAG 2.0 AA](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) |

## Elenco componenti {#component-list}

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

### Componenti imminenti {#upcoming-components}

Stiamo lavorando attivamente sui seguenti componenti core. Non sono ancora state rilasciate, ma possono essere visualizzate in anteprima nel ramo [di sviluppo](https://github.com/adobe/aem-core-wcm-components/tree/development):

* Video
* Scarica

## Aggiornamento dei componenti core {#upgrade-of-core-components}

Un vantaggio dei componenti su versione è che consente di separare la migrazione a una nuova versione AEM dalla migrazione alle nuove versioni dei componenti. Inoltre, se sono disponibili nuove versioni dei componenti, consente la singola migrazione di ciascun componente alla nuova versione.

Le migrazioni a una nuova versione AEM non influenzeranno l&#39;utilizzo dei componenti core, a condizione che le loro versioni supportino anche la nuova versione AEM alla quale viene trasferito. Le personalizzazioni effettuate ai componenti core non devono essere interessate da alcuna modifica, purché non vengano utilizzate API che sono [state dichiarate obsoleto o rimosse](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html).

Le migrazioni a nuove versioni dei componenti core non influenzeranno l&#39;utilizzo del componente, ma le nuove funzioni potrebbero essere introdotte agli autori delle pagine, che potrebbero richiedere alcune configurazioni da parte di un editor modelli, nel caso in cui il comportamento predefinito non sia desiderato. Potrebbe essere necessario adattare le personalizzazioni, per maggiori dettagli consultate [la pagina Personalizzazione componenti](customizing.md#upgrade-compatibility-of-customizations) core.

## Quando utilizzare i componenti core? {#when-to-use-the-core-components}

Poiché i componenti core sono completamente nuovi e offrono più vantaggi, è consigliabile utilizzare i nuovi progetti AEM. Per i progetti esistenti, una migrazione deve far parte di un&#39;attività di progetto più grande, ad esempio un rebranding o un refactoring complessivo.

Di conseguenza, Adobe fornisce le raccomandazioni seguenti:

* **Nuovi progetti**
I nuovi progetti devono sempre tentare di utilizzare componenti core. Se i componenti core non possono essere utilizzati direttamente o [estesi](customizing.md) per soddisfare i requisiti di progetto, create un componente personalizzato dopo l&#39;architettura dei componenti impostata nei componenti core. Eccetto ove non possibile, evitate di usare i [componenti di base](developing.md).
* **La raccomandazione Progetti**
esistenti continua a utilizzare i componenti [di base](developing.md), a meno che sia pianificato un sito o una funzione di reimpostazione del componente.\
   Poiché sono ampiamente utilizzati dalla maggior parte dei progetti esistenti, i componenti [di base continueranno a essere supportati.](developing.md)
* **Nuovi componenti
personalizzati** Valuta se un componente [di base esistente può essere personalizzato](customizing.md).\
   In caso contrario, si consiglia di creare un nuovo componente personalizzato seguendo le Linee guida [sui componenti](guidelines.md).
* **Componenti
personalizzati esistenti** Se i componenti funzionano come previsto, conservali così come sono.\
   In caso contrario, fai riferimento a «Nuovi componenti personalizzati» sopra.

### Supporto per componente core {#core-component-support}

I componenti core sono parte integrante di AEM e sono supportati così come sono, con gli stessi termini e condizioni di questa distribuzione come parte della sezione Quickstart.

Come per le altre funzionalità del prodotto AEM, la regola generale è: I componenti vengono inizialmente dichiarati obsoleti e il primo viene rimosso per la seguente release AEM. Questo offre ai clienti almeno un processo di rilascio per passare alla nuova versione del componente, prima di rilasciare il supporto.

La versione di ciascun componente indica chiaramente le versioni AEM supportate. Quando il supporto viene interrotto per una versione di AEM, questo supporta anche i componenti core per quella versione di AEM.

Per informazioni dettagliate sul supporto delle personalizzazioni dei componenti, consultate [la pagina Personalizzazione componenti](customizing.md) core.

### Supporto per componenti Foundation {#foundation-component-support}

Poiché i componenti di base sono stati gestiti come base per lo sviluppo di progetti in molte versioni, continueranno a essere supportati nel prossimo futuro.

Tuttavia, l&#39;enfasi di sviluppo di Adobe è stata spostata sui componenti core e le nuove funzioni saranno aggiunte loro, mentre verranno applicate solo correzioni di bug ai componenti di base.

**Leggi avanti:**

* [Utilizzo dei componenti](using.md) core: diventa disponibile con componenti core nel tuo progetto.
* [Linee guida sui componenti](guidelines.md) - per apprendere i pattern di implementazione dei componenti core.
