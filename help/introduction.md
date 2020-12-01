---
title: Introduzione ai componenti core
description: 'I componenti core forniscono componenti di base affidabili ed estensibili, basati sulle tecnologie e sulle best practice più recenti. '
translation-type: tm+mt
source-git-commit: 850fbeec3cb31f4ea6873daa2555953684fd5a8d
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 26%

---


# Introduzione ai componenti core{#core-components-introduction}

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create. I componenti sono sempre stati un elemento fondamentale dell’esperienza AEM perché permettono agli autori di creare pagine in modo semplice e potente e agli sviluppatori di realizzare componenti in modo flessibile ed estensibile.

I componenti core sono una serie di componenti Web Content Management (WCM) standardizzati per AEM di velocizzare i tempi di sviluppo e ridurre i costi di manutenzione dei siti Web.

## Riferimenti {#resources}

* **[Libreria dei componenti:](https://www.adobe.com/go/aem_cmp_library)** Raccolta di esempi per visualizzare i componenti nelle varie configurazioni.
* **Documentazione del componente (questo documento):** Per sviluppatori e autori, con dettagli su ciascun componente.
* **[Repository GitHub dei componenti core:](https://github.com/adobe/aem-core-wcm-components)** per informazioni sullo sviluppo di ciascun componente e del download del progetto.
* Introduzione:
   * **[Successo con i componenti di base:](/help/developing/success.md)** Linee guida da considerare molto prima dell’inizio di qualsiasi progetto che utilizzerà i componenti di base.
   * **[Esercitazione WKND: ](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** esercitazione di due giorni per la creazione di un nuovo sito.
   * **[Summit Tutorial:](https://expleague.azureedge.net/labs/L767/index.html)** Un&#39;esercitazione di due ore per la creazione di un nuovo sito (da un laboratorio al Summit degli Stati Uniti 2019).
   * **[Webinar Gems: ](https://helpx.adobe.com/it/experience-manager/kt/eseminars/gems/AEM-Core-Components.html.)** una visita guidata dei componenti core (registrata il dicembre 2018).

## Funzioni {#features}

|  |  |
|---|---|
| Pronti per la produzione | I componenti core sono 28 componenti robusti che sono ben testati, ampiamente utilizzati e che funzionano bene. |
| Pronto per il cloud | Sia su [AEM come Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html), su [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams), sia in sede, funzionano. |
| Versatili | I componenti rappresentano concetti generici con i quali gli autori possono assemblare praticamente qualsiasi layout. |
| Configurabile | Le [policy di contenuto a livello di modello](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html#content-policies) definiscono quali funzioni gli autori delle pagine possono utilizzare o meno. |
| Tracciabile | L&#39;integrazione dei [ Adobi Client Data Layer](/help/developing/data-layer/overview.md) consente di tenere traccia di tutti gli aspetti dell&#39;esperienza del visitatore. |
| Accessibili | Sono conformi allo standard [WCAG 2.1](https://www.w3.org/TR/WCAG21/), forniscono etichette ARIA e supportano la navigazione da tastiera ([problemi noti](https://github.com/adobe/aem-core-wcm-components/issues?utf8= ✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)). |
| SEO-Friendly | L&#39;output HTML è semantico e fornisce [schema.org](https://schema.org) annotazioni di microdati. |
| WebApp-Ready | L&#39; [output JSON ottimizzato](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/develop-sling-model-exporter.html) consente il rendering lato client, pur con la possibilità di [modifica contestuale](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html). |
| Supporto AMP | I componenti dispongono del supporto [integrato per lo standard AMP,](/help/developing/amp.md) per accelerare le esperienze mobili. |
| Kit di progettazione | Un [kit di interfaccia utente per  Adobe XD](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_Wireframe.xd) consente ai designer di creare wireframe che possono quindi [utilizzare come necessario](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_WKND.xd). |
| Tema | I componenti implementano il [Sistema di stile](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/style-system.html) e la marcatura segue le [convenzioni CSS di BEM](http://getbem.com/). |
| Personalizzabile | Diversi pattern consentono [una facile personalizzazione](developing/customizing.md), dalla regolazione dell&#39;HTML al riutilizzo avanzato delle funzionalità. |
| Gestione versioni | Il [criterio di controllo delle versioni](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) garantisce che i componenti core non interrompano il sito quando si migliorano gli elementi che potrebbero avere un impatto sull&#39;utente. |
| Localizzabile | La risoluzione dei riferimenti intelligenti consente ad alcuni componenti di trovare e [eseguire automaticamente il rendering del contenuto localizzato corrispondente](get-started/localization.md). |
| Apri origine | Se qualcosa non è come dovrebbe, [contribuire ai miglioramenti!](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## Componenti {#the-components}

La versione corrente dei componenti core include i seguenti componenti.

### Componenti modello {#template-components}

* [Pagina](components/page.md)
* [Navigazione](components/navigation.md)
* [Navigazione lingua](components/language-navigation.md)
* [Breadcrumb](components/breadcrumb.md)
* [Ricerca rapida](components/quick-search.md)

### Componenti per l&#39;authoring delle pagine {#page-authoring-components}

* [Titolo](components/title.md)
* [Testo](components/text.md)
* [Immagine](components/image.md)
* [Pulsante](components/button.md)
* [Teaser](components/teaser.md)
* [Scarica](components/download.md)
* [Elenco](components/list.md)
* [Frammento esperienza](components/experience-fragment.md)
* [Frammento di contenuto](components/content-fragment-component.md)
* [Elenco di frammenti di contenuto](components/content-fragment-list.md)
* [Incorpora](components/embed.md)
* [Condivisione social media](components/sharing.md)
* [Separatore](components/separator.md)
* [Barra di avanzamento](components/progress-bar.md)
* [Visualizzatore PDF](components/pdf-viewer.md)

### Componenti contenitore {#container-components}

* [Contenitore](components/container.md)
* [Carosello](components/carousel.md)
* [Schede](components/tabs.md)
* [Pannello a soffietto](components/accordion.md)

### Componenti per moduli {#form-components}

* [Contenitore modulo](components/forms/form-container.md)
* [Testo modulo](components/forms/form-text.md)
* [Opzioni modulo](components/forms/form-options.md)
* [Nascosto per modulo](components/forms/form-hidden.md)
* [Pulsante modulo](components/forms/form-button.md)

>[!NOTE]
>
>I componenti core non sono immediatamente disponibili per gli autori; [devono prima essere integrarti nell’ambiente dal team di sviluppo](get-started/using.md). Una volta integrati, possono essere resi disponibili e preconfigurati tramite l&#39;editor [modello](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>Alcune versioni di singoli componenti core potrebbero essere compatibili solo con determinate versioni di AEM.
>
>Consulta la pagina della guida del componente specifico (mediante il collegamento incluso nell’elenco precedente) per informazioni sulla compatibilità, oppure fai riferimento al documento [Versioni dei componenti core](versions.md).

## Requisiti di sistema {#system-requirements}

| Componenti core | AEM as a Cloud Service | AEM 6.5 | AEM 6.4   | Java SE | Paradiso |
|---------|---------|---------|---------|---------|---------|
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | Continuo | 6.5.5.0+ * | 6.4.8.1+ * | 8, 11 | 3.3.9+ |

>[!NOTE]
>
>(*) Poiché la versione 2.11.0 è necessaria la versione `org.apache.sling.models.impl` 1.4.12 o successiva (a causa di [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)). Questo verrà fornito per AEM 6.4 e 6.5 in un futuro Service Pack. Fino ad allora, il bundle Sling Models è incluso nel pacchetto `core.wcm.components.all`.

Per i requisiti delle precedenti versioni dei componenti core, consultare [Versioni dei componenti core](versions.md).

I componenti core richiedono l&#39;uso di [modelli modificabili](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) e non supportano l&#39;interfaccia classica né i modelli statici. Se necessario, controllare gli [AEM Strumenti di modernizzazione](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html) per aggiornare il progetto con queste moderne funzionalità AEM.

Per configurare l&#39;ambiente di sviluppo locale, consultare [questa panoramica per AEM come SDK di Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) o questo documento [per versioni precedenti di AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).
