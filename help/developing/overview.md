---
title: Sviluppo di Componenti core
description: I Componenti core forniscono componenti di base affidabili ed estensibili che offrono funzionalità avanzate, distribuzione continua, controllo delle versioni dei componenti, implementazione moderna, markup snello ed esportazione JSON di contenuto.
role: Architect, Developer, Admin
exl-id: 0f79cac1-a3b0-487e-90be-0bd8263d3912
source-git-commit: faf73c70a4bff387bed2f8cf6e48c39e597e51c7
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Sviluppo di Componenti core {#developing-core-components}

## Quando utilizzare i Componenti core? {#when-to-use-the-core-components}

Poiché i Componenti core sono completamente nuovi e offrono molteplici vantaggi, si consiglia di utilizzarli nei nuovi progetti AEM. Per i progetti esistenti, è consigliabile prevedere una migrazione dei componenti solo nell’ambito di una sostanziale rilavorazione di un progetto, ad esempio in caso di rebranding o refactoring globale.

Pertanto, Adobe fornisce le seguenti raccomandazioni:

* **Nuovi progetti**
Per i nuovi progetti si deve sempre tentare di utilizzare i Componenti core. Se i Componenti core non possono essere utilizzati direttamente o [nella versione estesa](customizing.md) per soddisfare i requisiti del progetto, si consiglia di creare un componente personalizzato seguendo l’architettura dei componenti impostata nei Componenti core. Ad eccezione dei casi in cui non esiste un’alternativa possibile, evita di utilizzare i [componenti di base](/help/versions.md#foundation-component-support).
* **Progetti esistenti**
Si raccomanda di continuare a utilizzare i [componenti di base](/help/versions.md#foundation-component-support), a meno che non sia pianificato il refactoring di un sito o di un componente.\
   In quanto ampiamente utilizzati nella maggior parte dei progetti esistenti, i componenti di base [continueranno a essere supportati.](/help/versions.md#foundation-component-support)
* **Nuovi componenti personalizzati**
Valuta se è possibile [personalizzare un componente core](customizing.md) esistente.\
   In caso contrario, si consiglia di creare un nuovo componente personalizzato seguendo le [Linee guida per i componenti](guidelines.md).
* **Componenti personalizzati esistenti**
Se i componenti funzionano come previsto, mantienili così come sono.
\
   In caso contrario, vedi “Nuovi componenti personalizzati” sopra.

## Come utilizzare in modo efficace i Componenti core {#how-to-succeed}

I Componenti core sono efficienti, flessibili e facili da usare e personalizzare. [L’aderenza ad alcune linee guida chiave](success.md) garantirà il successo del tuo progetto con i Componenti core.

## Migrazione ai Componenti core

Tutti i nuovi progetti devono essere implementati con i Componenti core. Tuttavia, i progetti esistenti hanno in genere implementazioni estese di componenti di base.

### Migrazione dai componenti di base {#from-foundation}

Una sostanziale rilavorazione di un progetto esistente (ad esempio, in caso di rebranding o refactoring globale) spesso offre la possibilità di migrazione ai Componenti core. Per facilitare questa migrazione, Adobe ha fornito una serie di strumenti di migrazione per incoraggiare l’adozione dei Componenti core e della tecnologia AEM più recente.

[Gli strumenti di modernizzazione AEM](http://opensource.adobe.com/aem-modernize-tools/) consentono di convertire facilmente:

* Modelli statici in modelli modificabili
* Configurazioni di progettazione in criteri
* Componenti di base in Componenti core
* Interfaccia utente classica in interfaccia utente touch

Per ulteriori informazioni sull’utilizzo di questi strumenti, [vedi la relativa documentazione](http://opensource.adobe.com/aem-modernize-tools/).

>[!NOTE]
>
>Gli strumenti di modernizzazione AEM sono un’iniziativa della community e non sono supportati o garantiti da Adobe.

## Migrazione tramite il passaggio ad AEM as a Cloud Service {#via-aemaacs}

Poiché AEM as a Cloud Service viene fornito automaticamente con l’ultima versione dei Componenti core, quando effettui il passaggio da un’installazione AEM on-premise, devi rimuovere qualsiasi dipendenza dai Componenti core nel file `pom.xml` dei tuoi progetti.

I componenti proxy continueranno a funzionare come prima perché i proxy puntano al supertipo necessario e il percorso del supertipo contiene già la versione. In questo modo, la semplice rimozione della dipendenza consente ai Componenti core di funzionare in AEMaaCS proprio come accadeva con AEM on-premise.

Come per qualsiasi altro progetto AEMaaCS, dovrai aggiungere anche una dipendenza al jar del Software Development Kit (SDK) di AEM. Questa dipendenza non è specifica per i Componenti core, ma è obbligatoria.

```xml
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-sdk-api</artifactId>
</dependency>
```

Per ulteriori informazioni sui progetti AEMaaCS, vedi il documento [Struttura dei progetti AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=it).

## Supporto dei Componenti core {#core-component-support}

I Componenti core sono parte integrante di AEM e sono supportati in quanto tali, soggetti agli stessi termini e condizioni dei prodotti forniti con Quickstart.

Come altre caratteristiche dei prodotti AEM, la regola generale è: i componenti vengono inizialmente dichiarati obsoleti e i meno recenti vengono rimossi nella successiva versione di AEM. In questo modo i clienti hanno il tempo per passare alla nuova versione del componente prima della fine del supporto.

La versione di ogni componente indica chiaramente le versioni di AEM supportate. Quando cessa il supporto per una versione di AEM, cessa anche il supporto dei Componenti core per quella versione di AEM.

Per informazioni dettagliate sul supporto delle personalizzazioni dei componenti, visita la pagina [Personalizzazione dei Componenti core](customizing.md).


## Funzionalità tecniche {#technical-capabilities}

La tabella che segue offre una panoramica delle differenze tra i Componenti core e i componenti di base.

Per informazioni dettagliate sulle loro funzionalità di authoring e sulle opzioni per preconfigurarle, [visita la pagina di authoring relativa a tali funzionalità](/help/get-started/authoring.md).

| **Funzionalità** | **Componente core** | **Componente di base** |
|-----|---|---|
| Implementazione logica | Java POJO con annotazioni di [modelli Sling](https://sling.apache.org/documentation/bundles/models.html) | Codice JSP |
| Definizione del markup | Sintassi di [HTML Template Language](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=it) (HTL) | Codice JSP |
| Bonifica XSS | Automatizzata tramite HTL | Principalmente manuale |
| Denominazione delle classi CSS | Convenzione di denominazione standardizzata basata sulla notazione [Block Element Modifier](https://getbem.com/) (BEM) (a partire dalla versione 2.0.0) | Schemi personalizzati |
| Definizione della finestra di dialogo | [Coral 3](https://helpx.adobe.com/it/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral 2 + Interfaccia utente classica |
| Output JSON | [Sling Models Exporter con serializzazione Jackson](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | Servlet Sling predefinito |
| Controllo delle versioni | [Per il modello e HTL](guidelines.md) | Nessuno |
| Test | Test unità + Integration test | Integration test |
| Distribuzione | [Tramite GitHub pubblico](https://github.com/adobe/aem-core-wcm-components) | Tramite Quickstart |
| Licenza | [Licenza Apache](https://www.apache.org/licenses/LICENSE-2.0) | Proprietaria di Adobe |
| Contributo | Tramite richiesta pull | Impossibile |
| Accessibilità | Completamente conforme allo standard [WCAG 2.0 AA](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html?lang=it) | Solo parzialmente conforme allo standard [WCAG 2.0 AA](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) |

## Elenco dei componenti {#component-list}

La tabella che segue riporta i Componenti core disponibili, il collegamento alle relative API e l’indicazione di quali componenti di base sostituiscono.

| Componente core | Descrizione | Componente o componenti di base sostituiti |
|---|---|---|
| [Pagina](https://adobe.com/go/aem_cmp_tech_page_v2_it) | Pagina reattiva che funziona con l’editor di modelli | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [Breadcrumb](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2_it) | Navigazione gerarchica delle pagine | `/libs/foundation/components/breadcrumb` |
| [Titolo](https://adobe.com/go/aem_cmp_tech_title_v2_it) | Titolo H1-H6 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [Testo](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | Rich Text Format (RTF) | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [Immagine](https://adobe.com/go/aem_cmp_tech_image_v2_it) | Caricamento intelligente e lento della dimensione di rendering ottimale | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [Elenco](https://adobe.com/go/aem_cmp_tech_list_v2_it) | Elenco delle pagine | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [Condivisione sui social media](https://adobe.com/go/aem_cmp_tech_sharing_v1_it) | Widget di condivisione su Facebook e Pinterest | `-` |
| [Contenitore modulo](https://adobe.com/go/aem_cmp_tech_form_container_v2_it) | Sistema di paragrafi in forma reattiva | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [Testo modulo](https://adobe.com/go/aem_cmp_tech_form_text_v2_it) | Campo di immissione testo | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [Opzioni modulo](https://adobe.com/go/aem_cmp_tech_form_options_v2_it) | Campo di immissione a più opzioni | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [Campo nascosto modulo](https://adobe.com/go/aem_cmp_tech_form_hidden_v2_it) | Campo di immissione nascosto | `/libs/foundation/components/form/hidden` |
| [Pulsante modulo](https://adobe.com/go/aem_cmp_tech_form_button_v2_it) | Pulsante Invia o personalizzato | `/libs/foundation/components/form/submit` |
| [Navigazione](https://adobe.com/go/aem_cmp_tech_navigation_v1_it) | Componente di navigazione del sito che elenca la gerarchia delle pagine nidificate | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [Navigazione lingua](https://adobe.com/go/aem_cmp_tech_langnav_v1_it) | Un selettore di lingua e paese che elenca la struttura globale delle lingue | `-` |
| [Ricerca rapida](https://adobe.com/go/aem_cmp_tech_search_v1_it) | Un componente di ricerca che visualizza i risultati come suggerimenti ordinati in un menu a discesa | `/libs/foundation/components/search` |
| [Teaser](https://adobe.com/go/aem_cmp_tech_teaser_v1_it) | Consente all’autore di contenuto di creare facilmente un teaser per ulteriore contenuto utilizzando un’immagine, un titolo o un testo RTF e di collegarsi a ulteriore contenuto o ad altre azioni | `-` |
| [Schede](https://adobe.com/go/aem_cmp_tech_tabs_v1_it) | Consente all’autore di contenuto di organizzare il contenuto della pagina in più schede | `-` |
| [Carosello](https://adobe.com/go/aem_cmp_tech_carousel_v1_it) | Consente all’autore di contenuto di organizzare il contenuto in un carosello di diapositive | `/libs/foundation/components/carousel` |
| [Frammento di contenuto](https://adobe.com/go/aem_cmp_tech_cf_v1_it) | Consente la visualizzazione di un frammento di contenuto | `-` |
| [Elenco di frammenti di contenuto](https://adobe.com/go/aem_cmp_tech_cflist_v1_it) | Consente la visualizzazione di un elenco di frammenti di contenuto | `-` |
| [Separatore](https://adobe.com/go/aem_cmp_tech_separator_v1_it) | Separa il contenuto su una pagina | `-` |
| [Pannello a soffietto](https://adobe.com/go/aem_cmp_tech_accordion_v1) | Organizza i pannelli di contenuto in un pannello a soffietto comprimibile | `-` |
| [Contenitore](https://adobe.com/go/aem_cmp_tech_container_v1_it) | Organizza i componenti all’interno di un contenitore | `-` |
| [Pulsante](https://adobe.com/go/aem_cmp_tech_button_v1) | Crea un pulsante su una pagina | `-` |
| [Scarica](https://adobe.com/go/aem_cmp_tech_download_v1) | Aggiunge una risorsa scaricabile a una pagina | `-` |
| [Frammento esperienza](https://adobe.com/go/aem_cmp_tech_xf_v1) | Aggiunge un frammento esperienza a una pagina | `/libs/cq/experience-fragments/editor/components/experiencefragment` |
| [Incorpora](https://adobe.com/go/aem_cmp_tech_embed_v1) | Incorpora una risorsa esterna all’interno di una pagina | - |
| [Barra di avanzamento](https://adobe.com/go/aem_cmp_tech_progress_v1) | Fornisce una rappresentazione visiva del progresso verso un obiettivo | - |
| [Visualizzatore PDF](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1_it) | Visualizza un documento PDF su una pagina | - |

## Aggiornamento dei Componenti core {#upgrade-of-core-components}

Uno dei vantaggi dei componenti con versione è la possibilità di separare la migrazione a una nuova versione di AEM dalla migrazione a nuove versioni dei componenti. Inoltre, se sono disponibili nuove versioni dei componenti, consente la migrazione individuale di ciascun componente alla nuova versione.

Le migrazioni a una nuova versione di AEM non influiscono sul funzionamento dei Componenti core, purché le loro versioni supportino anche la nuova versione di AEM a cui si migra. Neppure le personalizzazioni apportate ai Componenti core vengono influenzate, a condizione che non utilizzino API [obsolete o rimosse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html?lang=it).

Le migrazioni a nuove versioni dei Componenti core non influiscono neppure sulla modalità di funzionamento del componente. Tuttavia, gli autori delle pagine potrebbero avere a disposizione nuove funzioni che potrebbero richiedere un aggiustamento della configurazione tramite un editor di modelli, nel caso in cui il comportamento predefinito non fosse quello desiderato. Inoltre, potrebbe essere necessario adattare le personalizzazioni. Per ulteriori dettagli, visita la pagina [Personalizzazione dei Componenti core](customizing.md#upgrade-compatibility-of-customizations).
