---
title: Introduzione ai componenti core
description: 'I componenti core forniscono componenti di base affidabili ed estensibili, basati sulle tecnologie e le best practice più recenti. '
role: Architect, Developer, Administrator, Business Practitioner
exl-id: d294db22-4cb0-48a4-9366-03fda5b8bb8e
source-git-commit: cc1fc14e1ca9125a24c13ac68716951ef790afea
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 25%

---

# Introduzione ai componenti core{#core-components-introduction}

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create. I componenti sono sempre stati un elemento fondamentale dell’esperienza AEM perché permettono agli autori di creare pagine in modo semplice e potente e agli sviluppatori di realizzare componenti in modo flessibile ed estensibile.

I componenti core sono un set di componenti WCM (Web Content Management) standardizzati che consentono di AEM per velocizzare i tempi di sviluppo e ridurre i costi di manutenzione dei siti web.

## Riferimenti {#resources}

* **[Libreria dei componenti:](https://www.adobe.com/go/aem_cmp_library)** raccolta di esempi per visualizzare i componenti nelle relative configurazioni.
* **Documentazione del componente (questo documento):**  per sviluppatori e autori, con dettagli su ciascun componente.
* **[Repository GitHub dei componenti core:](https://github.com/adobe/aem-core-wcm-components)** per informazioni sugli sviluppatori di ogni componente e download di progetto.
* Introduzione:
   * **[Successo con i componenti core:](/help/developing/success.md)** linee guida da considerare molto prima dell’inizio di qualsiasi progetto che utilizzerà i componenti core.
   * **[Tutorial WKND:](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** esercitazione di due giorni per la creazione di un nuovo sito.
   * **[Tutorial sul Summit:](https://expleague.azureedge.net/labs/L767/index.html)** un tutorial di due ore per la costruzione di un nuovo sito (da un laboratorio al Summit degli Stati Uniti 2019).
   * **[Webinar Gems:](https://helpx.adobe.com/it/experience-manager/kt/eseminars/gems/AEM-Core-Components.html.)** visita guidata dei componenti core (registrata il 1 dicembre 2018).

## Funzioni {#features}

|  |  |
|---|---|
| Pronti per la produzione | I componenti core sono 28 componenti robusti testati, ampiamente utilizzati e con prestazioni ottimali. |
| Pronti per il cloud | Sia su [AEM come Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html), su [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) o on-premise, funzionano solo. |
| Versatili | I componenti rappresentano concetti generici con i quali gli autori possono assemblare quasi tutti i layout. |
| Configurabile | A livello di modello [criteri dei contenuti](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html#content-policies) definisci quali funzioni gli autori di pagine possono utilizzare o meno. |
| Tracciabile | L’ [integrazione Adobe Client Data Layer](/help/developing/data-layer/overview.md) consente il tracciamento di tutti gli aspetti dell’esperienza del visitatore. |
| Accessibili | Sono conformi a [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), forniscono etichette ARIA e supportano la navigazione da tastiera ([problemi noti](https://github.com/adobe/aem-core-wcm-components/issues?utf8= ✓&amp;q=is%3Aissue+is%3Aopen+accessibilità+in%3Atitle)). |
| SEO-friendly | L&#39;output HTML è semantico e fornisce annotazioni di microdati [schema.org](https://schema.org). |
| Pronti per WebApp | L’ [output JSON semplificato](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/develop-sling-model-exporter.html) consente il rendering lato client, con la possibilità di [modificare nel contesto](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html). |
| Supporto AMP | I componenti dispongono del supporto integrato [per lo standard AMP,](/help/developing/amp.md) per accelerare le esperienze mobile. |
| Kit di progettazione | Un [kit di interfaccia utente per Adobe XD](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd) consente ai designer di creare wireframe che possono quindi [personalizzare in base alle esigenze](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-0.0.2/AEM_UI-kit-WKND.xd). |
| Tema | I componenti implementano il [Sistema di stili](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/style-system.html) e il markup è conforme alle [convenzioni CSS BEM](http://getbem.com/). |
| Personalizzabile | Diversi pattern consentono [una facile personalizzazione](developing/customizing.md), dalla regolazione del codice HTML al riutilizzo avanzato delle funzionalità. |
| Gestione versioni | I [criteri di gestione delle versioni](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) garantiscono che i componenti core non alterino il sito quando si migliorano gli elementi che potrebbero interessarti. |
| Localizzabile | La risoluzione intelligente dei riferimenti consente ad alcuni componenti di trovare e [eseguire automaticamente il rendering del contenuto localizzato corrispondente](get-started/localization.md). |
| Apri origine | Se qualcosa non è come dovrebbe, [contribuire ai tuoi miglioramenti!](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## Componenti {#the-components}

La versione corrente dei componenti core include i seguenti componenti.

### Componenti modello {#template-components}

* [Pagina](components/page.md)
* [Navigazione](components/navigation.md)
* [Navigazione lingua](components/language-navigation.md)
* [Breadcrumb](components/breadcrumb.md)
* [Ricerca rapida](components/quick-search.md)

### Componenti di authoring delle pagine {#page-authoring-components}

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
>I componenti core non sono immediatamente disponibili per gli autori; [devono prima essere integrarti nell’ambiente dal team di sviluppo](get-started/using.md). Una volta integrati, possono essere resi disponibili e preconfigurati tramite l’ [editor modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>Alcune versioni di singoli componenti core potrebbero essere compatibili solo con determinate versioni di AEM.
>
>Consulta la pagina della guida del componente specifico (mediante il collegamento incluso nell’elenco precedente) per informazioni sulla compatibilità, oppure fai riferimento al documento [Versioni dei componenti core](versions.md).

## Requisiti di sistema {#system-requirements}

| Componenti core | AEM as a Cloud Service | AEM 6.5 | AEM 6.4 | Java SE | Maven |
|---------|---------|---------|---------|---------|---------|
| [2.17.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.0) | Continuo | 6.5.6.0+ * | 6.4.8.4+ * | 8, 11 | 3.3.9+ |

>[!NOTE]
>
>(*) A partire dalla versione 2.11.0, è richiesto `org.apache.sling.models.impl` versione 1.4.12 o successiva (a causa di [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)). Questo sarà previsto per AEM 6.4 e 6.5 in un futuro Service Pack. Fino ad allora, il bundle Sling Models è incluso nel pacchetto `core.wcm.components.all`.

Per i requisiti delle versioni precedenti dei componenti core, consulta [Versioni dei componenti core](versions.md) .

I componenti core richiedono l&#39;uso di [modelli modificabili](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) e non supportano l&#39;interfaccia classica né i modelli statici. Se necessario, controlla [AEM Strumenti di modernizzazione](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html) per aggiornare il progetto con queste funzioni AEM moderne.

Per configurare l&#39;ambiente di sviluppo locale, controlla [questa panoramica per AEM come Cloud Service SDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) o questo documento [per le versioni precedenti di AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).

>[!TIP]
>
>I componenti core fanno automaticamente parte di AEM come Cloud Service e disponi sempre dell’ultima versione dei componenti core.
>
>Consulta il documento [Utilizzo dei componenti core](/help/get-started/using.md) per ulteriori informazioni su come iniziare a utilizzare i componenti core sia in AEMaaCS che nei locali.
