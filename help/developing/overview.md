---
title: Sviluppo di componenti core
description: I componenti core forniscono componenti di base affidabili ed estensibili che offrono funzionalità avanzate, distribuzione continua, controllo delle versioni dei componenti, implementazione moderna, markup snello ed esportazione JSON di contenuti.
role: Architect, Developer, Admin
exl-id: 0f79cac1-a3b0-487e-90be-0bd8263d3912
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '1591'
ht-degree: 14%

---

# Sviluppo di componenti core {#developing-core-components}

## Quando utilizzare i componenti core? {#when-to-use-the-core-components}

Poiché i componenti core sono completamente nuovi e offrono molteplici vantaggi, si consiglia di utilizzarli nei nuovi progetti AEM. Per i progetti esistenti, la migrazione dei componenti dovrà essere eseguita nell’ambito di un’attività più ampia, ad esempio in occasione di un progetto di rebranding o riformattazione generale.

Pertanto, Adobe fornisce le seguenti raccomandazioni:

* **Nuovi**
progettiI nuovi progetti devono sempre cercare di utilizzare i componenti core. Se i componenti core non possono essere utilizzati direttamente o [estesi](customizing.md) per soddisfare i requisiti del progetto, crea un componente personalizzato seguendo l’architettura dei componenti impostata nei componenti core. Se non diversamente possibile, evita di utilizzare i [componenti di base](/help/versions.md#foundation-component-support).
* ****
ProjectsRecommendations esistente continua a utilizzare i componenti di  [base](/help/versions.md#foundation-component-support), a meno che non sia pianificato il refactoring di un sito o di un componente.\
   Poiché sono ampiamente utilizzati dalla maggior parte dei progetti esistenti, i componenti di base [continueranno a essere supportati.](/help/versions.md#foundation-component-support)
* **Nuovi**
componenti personalizzatiValutare se è possibile personalizzare [ un componente ](customizing.md)core esistente.\
   In caso contrario, si consiglia di creare un nuovo componente personalizzato seguendo le [Linee guida per i componenti](guidelines.md).
* **Componenti personalizzati esistentiSe i componenti funzionano come previsto, mantenili come sono.**

\
   In caso contrario, fare riferimento a &quot;Nuovi componenti personalizzati&quot; sopra.

## Come utilizzare con successo i componenti core {#how-to-succeed}

I componenti core sono potenti, flessibili e facili da usare e personalizzare. [Seguendo alcune ](success.md) linee guida chiave, assicurati che il progetto con i componenti core sia un successo.

## Migrazione ai componenti core

Eventuali nuovi progetti devono essere implementati con i componenti core. Tuttavia, i progetti esistenti avranno in genere implementazioni estese dei componenti di base.

### Migrazione dai componenti di base {#from-foundation}

Uno sforzo maggiore su un progetto esistente (ad esempio un rebranding o un refactoring complessivo) spesso offre la possibilità di migrare ai componenti core. Per facilitare questa migrazione, Adobe ha fornito una serie di strumenti di migrazione per incoraggiare l’adozione dei componenti core e della tecnologia AEM più recente.

[Il ](http://opensource.adobe.com/aem-modernize-tools/) Saldo degli strumenti di modernizzazione AEM per la facile conversione di:

* Modelli statici in modelli modificabili
* Configurazioni di progettazione in policy
* Componenti di base in componenti core
* Interfaccia classica in interfaccia touch

Per ulteriori informazioni sull&#39;utilizzo di questi strumenti, [consulta la relativa documentazione](http://opensource.adobe.com/aem-modernize-tools/).

>[!NOTE]
>
>Gli strumenti di modernizzazione AEM sono uno sforzo comunitario e non sono supportati o garantiti dall&#39;Adobe.

## Migrazione tramite Sposta a AEM come Cloud Service {#via-aemaacs}

Poiché AEM come Cloud Service viene fornito automaticamente l’ultima versione dei componenti core, quando passi da un’installazione AEM locale, dovrai rimuovere qualsiasi dipendenza dai componenti core nel file `pom.xml` dei progetti.

I componenti proxy continueranno a funzionare come prima perché   i proxy indicano il supertipo necessario e il percorso del supertipo contiene la versione. In questo modo, la semplice rimozione della dipendenza consente ai componenti core di funzionare in AEMaaCS proprio come nei locali.

Come qualsiasi altro progetto AEMaaCS, dovrai aggiungere anche una dipendenza al jar dell’SDK AEM. Questo non è specifico per i componenti core, ma è obbligatorio.

```xml
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-sdk-api</artifactId>
</dependency>
```

Per ulteriori informazioni sui progetti AEMaaCS, consulta il documento [AEM Struttura del progetto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html) .

## Supporto per componenti core {#core-component-support}

I componenti core sono parte integrante di AEM e sono supportati così come sono. Sono soggetti agli stessi termini e condizioni dei prodotti forniti con Quickstart.

Come altre caratteristiche del prodotto AEM, la regola generale è: I componenti vengono inizialmente dichiarati obsoleti e i primi rimossi per la versione AEM successiva. Questo offre ai clienti almeno un ciclo di rilascio per passare alla nuova versione del componente prima di interrompere il supporto.

La versione di ogni componente indica chiaramente le versioni di AEM che supporta. Quando cessa il supporto per una versione di AEM, cessa anche il supporto dei componenti core per tale versione di AEM.

Per informazioni dettagliate sul supporto delle personalizzazioni dei componenti, consulta la pagina [Personalizzazione dei componenti core](customizing.md) .


## Funzionalità tecniche {#technical-capabilities}

La tabella seguente offre una panoramica delle differenze tra i componenti core e i componenti di base.

Per informazioni dettagliate sulle funzionalità di authoring e sulle opzioni per preconfigurarle, [fai riferimento alla pagina di authoring relativa a tali funzionalità](/help/get-started/authoring.md).

| **Funzionalità** | **Componente core** | **Componente di base** |
|-----|---|---|
| Implementazione logica | Java POJO con annotazioni [Sling Models](https://sling.apache.org/documentation/bundles/models.html) | Codice JSP |
| Definizione markup | [Sintassi HTML Template Language](https://docs.adobe.com/content/help/it-IT/experience-manager-htl/using/overview.html)  (HTL) | Codice JSP |
| Smaltimento XSS | Automatizzato da HTL | Principalmente manuale |
| Denominazione delle classi CSS | Convenzione di denominazione standardizzata basata sulla notazione [Modificatore elemento blocco](https://getbem.com/) (BEM) (a partire dalla versione 2.0.0) | Schemi personalizzati |
| Definizione finestra di dialogo | [Corallo 3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Corallo 2 + Interfaccia classica |
| Output JSON | [Esportatore di modelli Sling con serializzazione Jackson](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | Servlet Sling predefinito |
| Gestione versioni | [Per il modello e l’HTL](guidelines.md) | Nessuna |
| Test | Test di unità + test di integrazione | Test di integrazione |
| Consegna | [Tramite GitHub pubblico](https://github.com/adobe/aem-core-wcm-components) | Tramite Quickstart |
| Licenza | [Licenza Apache](https://www.apache.org/licenses/LICENSE-2.0) | Adobe proprietario |
| Contributo | Tramite richiesta pull | Impossibile |
| Accessibilità | Completamente conforme allo standard [WCAG 2.0 AA](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) | Solo parzialmente conforme allo standard [WCAG 2.0 AA](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) |

## Elenco componenti {#component-list}

Nella tabella seguente sono elencati i componenti core disponibili, con collegamento alle relative API, e sono indicati i componenti di base che sostituiscono.

| Componente core | Descrizione | Componenti di base sostituiti |
|---|---|---|
| [Pagina](https://adobe.com/go/aem_cmp_tech_page_v2) | Pagina reattiva che funziona con l’editor di modelli | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [Breadcrumb](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2) | Navigazione gerarchica delle pagine | `/libs/foundation/components/breadcrumb` |
| [Titolo](https://adobe.com/go/aem_cmp_tech_title_v2) | Titolo H1-H6 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [Testo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | Rich text | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [Immagine](https://adobe.com/go/aem_cmp_tech_image_v2) | Caricamento intelligente e lento delle dimensioni ottimali del rendering | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [Elenco](https://adobe.com/go/aem_cmp_tech_list_v2) | Elenco delle pagine | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [Condivisione social media](https://adobe.com/go/aem_cmp_tech_sharing_v1) | Widget di condivisione facebook e Pinterest | `-` |
| [Contenitore modulo](https://adobe.com/go/aem_cmp_tech_form_container_v2) | Sistema di paragrafi a forma reattiva | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [Testo modulo](https://adobe.com/go/aem_cmp_tech_form_text_v2) | Campo di immissione testo | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [Opzioni modulo](https://adobe.com/go/aem_cmp_tech_form_options_v2) | Campo di input a più opzioni | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [Nascosto per modulo](https://adobe.com/go/aem_cmp_tech_form_hidden_v2) | Campo di input nascosto | `/libs/foundation/components/form/hidden` |
| [Pulsante modulo](https://adobe.com/go/aem_cmp_tech_form_button_v2) | Pulsante Invia o personalizzato | `/libs/foundation/components/form/submit` |
| [Navigazione](https://adobe.com/go/aem_cmp_tech_navigation_v1) | Componente di navigazione del sito che elenca la gerarchia di pagine nidificata | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [Navigazione lingua](https://adobe.com/go/aem_cmp_tech_langnav_v1) | Un commutatore di lingua e Paese che elenca la struttura globale della lingua | `-` |
| [Ricerca rapida](https://adobe.com/go/aem_cmp_tech_search_v1) | Un componente di ricerca che visualizza i risultati come suggerimenti in-place in un menu a discesa | `/libs/foundation/components/search` |
| [Teaser](https://adobe.com/go/aem_cmp_tech_teaser_v1) | Consente all’autore del contenuto di creare facilmente un teaser per ulteriori contenuti utilizzando un’immagine, un titolo o un testo RTF e di collegarsi a ulteriori contenuti o altre azioni | `-` |
| [Schede](https://adobe.com/go/aem_cmp_tech_tabs_v1) | Consente all’autore del contenuto di organizzare il contenuto della pagina all’interno di più schede | `-` |
| [Carosello](https://adobe.com/go/aem_cmp_tech_carousel_v1) | Consente all’autore del contenuto di organizzare il contenuto in un carosello rotante di diapositive | `/libs/foundation/components/carousel` |
| [Frammento di contenuto](https://adobe.com/go/aem_cmp_tech_cf_v1) | Consente la visualizzazione di un frammento di contenuto | `-` |
| [Elenco di frammenti di contenuto](https://adobe.com/go/aem_cmp_tech_cflist_v1) | Consente la visualizzazione di un elenco di frammenti di contenuto | `-` |
| [Separatore](https://adobe.com/go/aem_cmp_tech_separator_v1) | Separa il contenuto di una pagina | `-` |
| [Pannello a soffietto](https://adobe.com/go/aem_cmp_tech_accordion_v1) | Organizzare pannelli di contenuto in un pannello a soffietto comprimibile | `-` |
| [Contenitore](https://adobe.com/go/aem_cmp_tech_container_v1) | Organizzare i componenti all’interno di un contenitore | `-` |
| [Pulsante](https://adobe.com/go/aem_cmp_tech_button_v1) | Creare un pulsante su una pagina | `-` |
| [Scarica](https://adobe.com/go/aem_cmp_tech_download_v1) | Aggiungere una risorsa scaricabile a una pagina | `-` |
| [Frammento esperienza](https://adobe.com/go/aem_cmp_tech_xf_v1) | Aggiungere un frammento esperienza a una pagina | `/libs/cq/experience-fragments/editor/components/experiencefragment` |
| [Incorpora](https://adobe.com/go/aem_cmp_tech_embed_v1) | Incorporare una risorsa esterna all’interno di una pagina | - |
| [Barra di avanzamento](https://adobe.com/go/aem_cmp_tech_progress_v1) | Fornire una rappresentazione visiva del progresso verso un obiettivo | - |
| [Visualizzatore PDF](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1) | Presenta un documento PDF su una pagina | - |

### Componenti in arrivo {#upcoming-components}

Per una panoramica della tabella di marcia dei componenti core in arrivo, consulta il progetto wiki [su GitHub](https://github.com/adobe/aem-core-wcm-components/wiki/home).

## Aggiornamento dei componenti core {#upgrade-of-core-components}

Un vantaggio dei componenti con versione è la possibilità di separare la migrazione a una nuova versione AEM dalla migrazione alle nuove versioni dei componenti. Inoltre, se sono disponibili nuove versioni dei componenti, consente la migrazione individuale di ciascun componente alla nuova versione.

Le migrazioni a una nuova versione AEM non avranno alcun impatto sul funzionamento dei componenti core, purché le loro versioni supportino anche la nuova versione AEM in cui viene effettuata la migrazione. Le personalizzazioni effettuate ai componenti core non devono essere influenzate, purché non utilizzino API [obsolete o rimosse](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/release-notes/deprecated-removed-features.html).

Le migrazioni a nuove versioni dei componenti core non avranno alcun impatto nemmeno sul funzionamento del componente, ma potrebbero essere introdotte nuove funzioni agli autori di pagine, che potrebbero richiedere alcune configurazioni da parte di un editor di modelli, nel caso in cui il comportamento predefinito non sia desiderato. Tuttavia, potrebbe essere necessario adattare le personalizzazioni. Per ulteriori dettagli, consulta la pagina [Personalizzazione dei componenti core](customizing.md#upgrade-compatibility-of-customizations) .
