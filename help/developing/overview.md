---
title: Sviluppo di componenti core
description: I componenti core forniscono componenti di base affidabili ed estensibili che offrono funzionalità avanzate, distribuzione continua, controllo delle versioni dei componenti, implementazione moderna, marcatura snella ed esportazione JSON di contenuti.
translation-type: tm+mt
source-git-commit: d2e69e5657ed32cc0579579df49ee083212b9333
workflow-type: tm+mt
source-wordcount: '1442'
ht-degree: 14%

---


# Sviluppo di componenti core {#developing-core-components}

## When to Use the Core Components? {#when-to-use-the-core-components}

Poiché i componenti core sono completamente nuovi e offrono molteplici vantaggi, si consiglia di utilizzarli nei nuovi progetti AEM. Per i progetti esistenti, la migrazione dei componenti dovrà essere eseguita nell’ambito di un’attività più ampia, ad esempio in occasione di un progetto di rebranding o riformattazione generale.

Pertanto,  Adobe formula le seguenti raccomandazioni:

* **Nuovi progetti** I nuovi progetti devono sempre tentare di utilizzare i componenti core. Se i componenti core non possono essere utilizzati direttamente o [estesi](customizing.md) per soddisfare i requisiti del progetto, create un componente personalizzato seguendo l’architettura dei componenti impostata nei componenti core. Eccetto dove non altrimenti possibile, evitare di utilizzare i componenti [](/help/versions.md#foundation-component-support)di base.
* **La** raccomandazione progetti [esistenti viene mantenuta utilizzando i componenti](/help/versions.md#foundation-component-support)di base, a meno che non sia pianificato il refactoring di un sito o di un componente.\
   Poiché sono ampiamente utilizzati dalla maggior parte dei progetti esistenti, i componenti di base [continueranno ad essere sostenuti.](/help/versions.md#foundation-component-support)
* **Nuovi componenti** personalizzati Se è possibile personalizzare [un componente](customizing.md)core esistente.\
   In caso contrario, si consiglia di creare un nuovo componente personalizzato seguendo le linee guida [sui](guidelines.md)componenti.
* **Componenti** personalizzati esistenti Se i componenti funzionano come previsto, mantenerli come sono.
\
   In caso contrario, fare riferimento a &quot;Nuovi componenti personalizzati&quot; sopra.

## Come ottenere successo con i componenti core {#how-to-succeed}

I componenti core sono potenti, flessibili e facili da usare e personalizzare. [Seguendo alcune linee guida](success.md) chiave, il progetto con i componenti core avrà successo.

## Migrazione ai componenti core

Eventuali nuovi progetti devono essere implementati con i componenti core. Tuttavia, i progetti esistenti avranno in genere ampie implementazioni dei componenti di base.

Uno sforzo maggiore su un progetto esistente (ad esempio un rebranding o un refactoring complessivo) spesso offre la possibilità di eseguire la migrazione ai componenti core. Per facilitare questa migrazione,  Adobe ha fornito una serie di strumenti di migrazione per incoraggiare l&#39;adozione dei componenti core e della tecnologia AEM più recente.

[Gli AEM Strumenti](http://opensource.adobe.com/aem-modernize-tools/) di Modernizzazione consentono una facile conversione di:

* Modelli statici in modelli modificabili
* Configurazioni di progettazione in policy
* Componenti di base in componenti core
* Interfaccia classica in interfaccia touch

Per ulteriori informazioni sull’utilizzo di questi strumenti, [consulta la relativa documentazione](http://opensource.adobe.com/aem-modernize-tools/).

>[!NOTE]
>
>Gli strumenti AEM Modernizza sono uno sforzo della comunità e non sono supportati o giustificati dal Adobe .

## Supporto dei componenti core {#core-component-support}

I componenti core sono parte integrante di AEM e sono supportati così come sono. Sono soggetti agli stessi termini e condizioni dei prodotti forniti con Quickstart.

Come per altre funzionalità AEM prodotto, la regola generale è: I componenti vengono inizialmente dichiarati obsoleti e i primi rimossi per la release AEM successiva. Questo consente ai clienti di passare alla nuova versione del componente almeno un ciclo di rilascio prima di lasciarne indietro il supporto.

La versione di ogni componente indica chiaramente le versioni di AEM che supporta. Quando cessa il supporto per una versione di AEM, cessa anche il supporto dei componenti core per tale versione di AEM.

Per informazioni dettagliate sul supporto delle personalizzazioni dei componenti, consultate la pagina [Personalizzazione dei componenti](customizing.md) core.


## Funzionalità tecniche {#technical-capabilities}

La tabella seguente fornisce una panoramica delle differenze tra i componenti core e i componenti di base.

Per informazioni dettagliate sulle funzionalità di authoring e sulle opzioni per la preconfigurazione, [consultare la pagina dedicata](/help/get-started/authoring.md)all’authoring.

| **Funzionalità** | **Componente core** | **Componente Foundation** |
|-----|---|---|
| Implementazione logica | Java POJO con annotazioni [Sling Models](https://sling.apache.org/documentation/bundles/models.html) | Codice JSP |
| Definizione di markup | [Sintassi HTML Template Language](https://docs.adobe.com/content/help/it-IT/experience-manager-htl/using/overview.html) (HTL) | Codice JSP |
| Scarico XSS | Automatizzato da HTL | Principalmente manuale |
| Denominazione delle classi CSS | Convenzione di denominazione standard basata sulla notazione [del modificatore](https://getbem.com/) di elementi di blocco (BEM) (a partire dalla release 2.0.0) | Schemi personalizzati |
| Definizione finestra di dialogo | [Corallo 3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Corallo 2 + Interfaccia classica |
| Uscita JSON | [Sling Models Exporter con serializzazione Jackson](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | Servlet Sling predefinito |
| Gestione versioni | [Per il modello e l&#39;HTL](guidelines.md) | Nessuno |
| Test | Prove di unità + Test di integrazione | Test di integrazione |
| Consegna | [Tramite GitHub pubblico](https://github.com/adobe/aem-core-wcm-components) | Via Quickstart |
| Licenza | [Licenza Apache](https://www.apache.org/licenses/LICENSE-2.0) |  Adobe proprietario |
| Contributo | Tramite richiesta pull | Impossibile |
| Accessibilità | Completamente conforme allo standard [WCAG 2.0 AA](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) | Solo parzialmente conforme allo standard [WCAG 2.0 AA](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) |

## Elenco componenti {#component-list}

Nella tabella seguente sono elencati i componenti core disponibili, che si collegano all&#39;API e indicano quali componenti di base sostituire.

| Componente core | Descrizione | Componenti di base sostituiti |
|---|---|---|
| [Pagina](https://adobe.com/go/aem_cmp_tech_page_v2) | Pagina reattiva che funziona con l’editor modelli | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [Breadcrumb](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2) | Navigazione gerarchica delle pagine | `/libs/foundation/components/breadcrumb` |
| [Titolo](https://adobe.com/go/aem_cmp_tech_title_v2) | Titolo H1-H6 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [Testo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | RTF | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [Immagine](https://adobe.com/go/aem_cmp_tech_image_v2) | Caricamento intelligente e pigro delle dimensioni di rappresentazione ottimali | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [Elenco](https://adobe.com/go/aem_cmp_tech_list_v2) | Elenco di pagine | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [Condivisione social media](https://adobe.com/go/aem_cmp_tech_sharing_v1) | widget di condivisione Facebook e Pinterest | `-` |
| [Contenitore modulo](https://adobe.com/go/aem_cmp_tech_form_container_v2) | Sistema paragrafo modulo reattivo | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [Testo modulo](https://adobe.com/go/aem_cmp_tech_form_text_v2) | Campo di immissione testo | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [Opzioni modulo](https://adobe.com/go/aem_cmp_tech_form_options_v2) | Campo di immissione opzioni multiple | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [Nascosto per modulo](https://adobe.com/go/aem_cmp_tech_form_hidden_v2) | Campo di input nascosto | `/libs/foundation/components/form/hidden` |
| [Pulsante modulo](https://adobe.com/go/aem_cmp_tech_form_button_v2) | Pulsante Invia o personalizzato | `/libs/foundation/components/form/submit` |
| [Navigazione](https://adobe.com/go/aem_cmp_tech_navigation_v1) | Un componente di navigazione del sito che elenca la gerarchia di pagine nidificata | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [Navigazione lingua](https://adobe.com/go/aem_cmp_tech_langnav_v1) | Uno switcher di lingua e Paese che elenca la struttura globale della lingua | `-` |
| [Ricerca rapida](https://adobe.com/go/aem_cmp_tech_search_v1) | Componente di ricerca che visualizza i risultati come suggerimenti inseriti in un menu a discesa | `/libs/foundation/components/search` |
| [Teaser](https://adobe.com/go/aem_cmp_tech_teaser_v1) | Consente all’autore del contenuto di creare facilmente un teaser per l’ulteriore contenuto utilizzando un’immagine, un titolo o un RTF e collegando altri contenuti o altre azioni | `-` |
| [Schede](https://adobe.com/go/aem_cmp_tech_tabs_v1) | Consente all’autore del contenuto di organizzare il contenuto della pagina all’interno di più schede | `-` |
| [Carosello](https://adobe.com/go/aem_cmp_tech_carousel_v1) | Consente all’autore del contenuto di organizzare il contenuto in un carosello rotante di diapositive | `/libs/foundation/components/carousel` |
| [Frammento di contenuto](https://adobe.com/go/aem_cmp_tech_cf_v1) | Consente la visualizzazione di un frammento di contenuto | `-` |
| [Elenco di frammenti di contenuto](https://adobe.com/go/aem_cmp_tech_cflist_v1) | Consente di visualizzare un elenco dei frammenti di contenuto | `-` |
| [Separatore](https://adobe.com/go/aem_cmp_tech_separator_v1) | Separa il contenuto di una pagina | `-` |
| [Pannello a soffietto](https://adobe.com/go/aem_cmp_tech_accordion_v1) | Organizzare i pannelli dei contenuti in un ambiente comprimibile | `-` |
| [Contenitore](https://adobe.com/go/aem_cmp_tech_container_v1) | Organizzare i componenti all’interno di un contenitore | `-` |
| [Pulsante](https://adobe.com/go/aem_cmp_tech_button_v1) | Creare un pulsante su una pagina | `-` |
| [Scarica](https://adobe.com/go/aem_cmp_tech_download_v1) | Aggiunta di una risorsa scaricabile a una pagina | `-` |
| [Frammento esperienza](https://adobe.com/go/aem_cmp_tech_xf_v1) | Aggiunta di un frammento esperienza a una pagina | `/libs/cq/experience-fragments/editor/components/experiencefragment` |
| [Incorpora](https://adobe.com/go/aem_cmp_tech_embed_v1) | Incorporare una risorsa esterna in una pagina | - |
| [Barra di avanzamento](https://adobe.com/go/aem_cmp_tech_progress_v1) | Fornire una rappresentazione visiva del progresso verso un obiettivo | - |
| [Visualizzatore PDF](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1) | Presenta un documento PDF su una pagina | - |

### Componenti in arrivo {#upcoming-components}

Per una panoramica della road map dei componenti core, consulta il [progetto wiki su GitHub](https://github.com/adobe/aem-core-wcm-components/wiki/home).

## Aggiornamento dei componenti core {#upgrade-of-core-components}

Un vantaggio dei componenti con versione è rappresentato dal fatto che consente di separare la migrazione a una nuova versione AEM dalla migrazione alle nuove versioni dei componenti. Inoltre, se sono disponibili nuove versioni di componenti, è possibile migrare singolarmente ogni componente alla nuova versione.

Le migrazioni a una nuova versione AEM non avranno alcun impatto sul funzionamento dei componenti core, a condizione che le loro versioni supportino anche la nuova versione AEM a cui viene eseguita la migrazione. Le personalizzazioni effettuate sui componenti core non devono essere influenzate, a condizione che non utilizzino API che sono state [obsolete o rimosse](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/release-notes/deprecated-removed-features.html).

Le migrazioni a nuove versioni dei componenti core non influiranno neanche sul funzionamento del componente, ma potrebbero essere introdotte nuove funzionalità agli autori di pagine, che potrebbero richiedere alcune configurazioni da parte di un editor modelli, nel caso in cui il comportamento predefinito non sia desiderato. Potrebbe tuttavia essere necessario adattare le personalizzazioni, per ulteriori dettagli consultate la pagina [Personalizzazione dei componenti](customizing.md#upgrade-compatibility-of-customizations) core.
