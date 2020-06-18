---
title: Introduzione ai componenti core
description: 'I componenti core sono stati introdotti per offrire componenti di base affidabili ed estensibili, basati sulle tecnologie e le best practice più recenti. '
translation-type: tm+mt
source-git-commit: bbbd918c7caf508866ae6dadbb8c815dca4e900b
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 28%

---


# Introduzione ai componenti core{#core-components-introduction}

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create. I componenti sono sempre stati un elemento fondamentale dell’esperienza AEM perché permettono agli autori di creare pagine in modo semplice e potente e agli sviluppatori di realizzare componenti in modo flessibile ed estensibile.

I componenti core sono una serie di componenti Web Content Management (WCM) standardizzati che consentono ad AEM di accelerare i tempi di sviluppo e ridurre i costi di manutenzione dei siti Web.

## Riferimenti {#resources}

* **[Libreria dei componenti:](https://www.adobe.com/go/aem_cmp_library)**Una raccolta di esempi per visualizzare i componenti nelle rispettive configurazioni.
* **Documentazione del componente (questo documento):** Per sviluppatori e autori, con dettagli su ciascun componente.
* **[Repository GitHub dei componenti core:](https://github.com/adobe/aem-core-wcm-components)**Per informazioni sullo sviluppo di ciascun componente e di ciascun progetto, scaricate.
* Introduzione:
   * **[Successo con i componenti core:](/help/developing/success.md)**Linee guida da prendere in considerazione prima dell’inizio di qualsiasi progetto che utilizzerà i componenti core.
   * **[Esercitazione WKND:](https://docs.adobe.com/content/help/it-IT/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)**Esercitazione di due giorni per la creazione di un nuovo sito.
   * **[Esercitazione Summit:](https://expleague.azureedge.net/labs/L767/index.html)**Un&#39;esercitazione di due ore per la costruzione di un nuovo sito (da un laboratorio al Summit degli Stati Uniti 2019).
   * **[Webinar Gems:](https://helpx.adobe.com/it/experience-manager/kt/eseminars/gems/AEM-Core-Components.html.)**Visita guidata dei componenti core (registrata il dicembre 2018).

## Funzioni {#features}

|  |  |
|---|---|
| Pronti per la produzione | I componenti core sono 28 componenti robusti che sono ben testati, ampiamente utilizzati e che funzionano bene. |
| Pronto per il cloud | Sia che si tratti di [AEM come Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html), di [Adobi Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) o in sede, funzionano. |
| Versatili | I componenti rappresentano concetti generici con i quali gli autori possono assemblare praticamente qualsiasi layout. |
| Configurabile | I criteri [per il](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/page-templates-editable.html#content-policies) contenuto a livello di modello definiscono le funzioni che gli autori delle pagine possono utilizzare o meno. |
| Tracciabile | L&#39;integrazione [di](/help/developing/data-layer/overview.md) Adobe Client Data Layer consente di tenere traccia di tutti gli aspetti dell&#39;esperienza del visitatore. |
| Accessibili | They comply [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), provide ARIA labels, and support keyboard navigation ([known issues](https://github.com/adobe/aem-core-wcm-components/issues?utf8= ✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)). |
| SEO-Friendly | The HTML output is semantic and provides [schema.org](https://schema.org) microdata annotations. |
| WebApp-Ready | L&#39;output [JSON](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/develop-sling-model-exporter.html) ottimizzato consente il rendering lato client, pur con la possibilità di effettuare modifiche [contestuali](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html). |
| Kit di progettazione | Un kit di [interfaccia utente per Adobe XD](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_Wireframe.xd) consente ai designer di creare wireframe che potranno quindi [definire in base alle esigenze](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_WKND.xd). |
| Tema | The components implement the [Style System](https://docs.adobe.com/content/help/en/experience-manager-65/developing/components/style-system.html), and the markup follows [BEM CSS conventions](http://getbem.com/). |
| Personalizzabile | Diversi pattern consentono [una facile personalizzazione](developing/customizing.md), dalla regolazione dell’HTML al riutilizzo avanzato delle funzionalità. |
| Gestione versioni | La politica [di controllo delle](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) versioni garantisce che i componenti core non interrompano il sito quando migliorano gli elementi che potrebbero avere un impatto sull&#39;utente. |
| Localizzabile | Smart reference resolution allows certain components to find and [render corresponding localized content automatically](get-started/localization.md). |
| Apri origine | Se qualcosa non è come dovrebbe, [contribuire i vostri miglioramenti!](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## Componenti {#the-components}

La versione corrente dei componenti core include i seguenti componenti.

### Componenti per modelli {#template-components}

* [Pagina](components/page.md)
* [Navigazione](components/navigation.md)
* [Navigazione lingua](components/language-navigation.md)
* [Breadcrumb](components/breadcrumb.md)
* [Ricerca rapida](components/quick-search.md)

### Componenti per l’authoring delle pagine {#page-authoring-components}

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
>I componenti core non sono immediatamente disponibili per gli autori; [devono prima essere integrarti nell’ambiente dal team di sviluppo](get-started/using.md). Once integrated, they may be made available and pre-configured via the [template editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>Alcune versioni di singoli componenti core potrebbero essere compatibili solo con determinate versioni di AEM.
>
>Consulta la pagina della guida del componente specifico (mediante il collegamento incluso nell’elenco precedente) per informazioni sulla compatibilità, oppure fai riferimento al documento [Versioni dei componenti core](versions.md).

## Requisiti di sistema {#system-requirements}

| Componenti core | AEM as a Cloud Service | AEM 6.5 | AEM 6.4   | Java SE | Paradiso |
---------|---------|---------|---------|---------|---------
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | Continuo | 6.5.0.0+ | 6.4.4.0+ | 8, 11 | 3.3.9+ |

Per i requisiti delle precedenti versioni dei componenti core, consulta Versioni [dei componenti](versions.md)core.

I componenti core richiedono l’uso di modelli [](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) modificabili e non supportano l’interfaccia classica né i modelli statici. Se necessario, controllate [AEM Modernization Tools](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html) per aggiornare il progetto con queste moderne funzioni AEM.

Per configurare l’ambiente di sviluppo locale, consultate [questa panoramica per AEM come Cloud Service SDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) oppure questo documento [per le versioni precedenti di AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).
