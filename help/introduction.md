---
title: Introduzione ai Componenti core
description: 'I Componenti core sono stati introdotti per offrire componenti di base affidabili ed estensibili, basati sulle tecnologie e le best practice più recenti. '
role: Architect, Developer, Admin, User
exl-id: d294db22-4cb0-48a4-9366-03fda5b8bb8e
source-git-commit: 19a7057d0a37d8222dcb2441bba1e479d786fb10
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 98%

---

# Introduzione ai Componenti core{#core-components-introduction}

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create. I componenti sono sempre stati un elemento fondamentale dell’esperienza AEM perché permettono agli autori di creare pagine in modo semplice ed efficiente e agli sviluppatori di realizzare componenti in modo flessibile ed estensibile.

I Componenti core sono un set di componenti WCM (Web Content Management) standardizzati di AEM che consentono di velocizzare i tempi di sviluppo e ridurre i costi di manutenzione dei siti web.

## Riferimenti {#resources}

* **[Libreria dei componenti:](https://www.adobe.com/go/aem_cmp_library)** una raccolta di esempi per visualizzare i componenti nelle loro varie configurazioni.
* **Documentazione del componente (questo documento):** per sviluppatori e autori, con dettagli su ciascun componente.
* **[Archivio GitHub dei Componenti core:](https://github.com/adobe/aem-core-wcm-components)** informazioni su ciascun componente e sul download del progetto, per gli sviluppatori.
* Introduzione:
   * **[Utilizzo efficace dei Componenti core:](/help/developing/success.md)** linee guida da tenere bene in mente prima di iniziare qualsiasi progetto che preveda l’utilizzo dei Componenti core.
   * **[Esercitazione WKND:](https://docs.adobe.com/content/help/it-IT/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** esercitazione di due giorni per la creazione di un nuovo sito.
   * **[Esercitazione Summit:](https://expleague.azureedge.net/labs/L767/index.html)** un’esercitazione di due ore per la creazione di un nuovo sito (da un laboratorio presso US Summit 2019).
   * **[Webinar Gems:](https://helpx.adobe.com/it/experience-manager/kt/eseminars/gems/AEM-Core-Components.html.)** visita guidata dei Componenti core (registrata a dicembre 2018).

## Funzioni {#features}

|  |  |
|---|---|
| Pronti per la produzione | I Componenti core sono 28 efficienti componenti testati, ampiamente utilizzati e con prestazioni ottimali. |
| Pronti per il cloud | Che sia su [AEM as a Cloud Service](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/landing/home.html), su [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) oppure on-premise, semplicemente funzionano. |
| Versatili | I componenti rappresentano concetti generici con i quali gli autori possono assemblare quasi tutti i layout. |
| Configurabili | [Criteri di contenuto](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html#content-policies) a livello di modello definiscono quali funzioni gli autori di pagine possono utilizzare o meno. |
| Tracciabili | [L’integrazione con Adobe Client Data Layer](/help/developing/data-layer/overview.md) consente il tracciamento di tutti gli aspetti dell’esperienza del visitatore. |
| Accessibili | Sono conformi a [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), forniscono etichette ARIA e supportano la navigazione da tastiera ([problemi noti](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)). |
| SEO-friendly | L’output HTML è semantico e fornisce annotazioni di microdati [schema.org.](https://schema.org) |
| Pronti per WebApp | [L’output JSON ottimizzato](https://docs.adobe.com/content/help/it-IT/experience-manager-learn/foundation/development/develop-sling-model-exporter.html) consente il rendering lato client, ma ancora con la possibilità di [modifica nel contesto](https://docs.adobe.com/content/help/it-IT/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html). |
| Supporto AMP | I componenti hanno il [supporto integrato per lo standard AMP,](/help/developing/amp.md) per accelerare le tue esperienze mobili. |
| Kit di progettazione | Un [kit di interfaccia utente per Adobe XD](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd) consente ai designer di creare wireframe [personalizzabili in base alle esigenze](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-0.0.2/AEM_UI-kit-WKND.xd). |
| Supportano i temi | I componenti implementano il [sistema di stili](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/style-system.html) e il markup segue le [convenzioni BEM CSS](http://getbem.com/). |
| Personalizzabili | Diversi modelli consentono [una facile personalizzazione](developing/customizing.md), dalla rettifica del codice HTML al riutilizzo avanzato delle funzionalità. |
| Controllo delle versioni | I [criteri di controllo delle versioni](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) garantiscono che i Componenti core non blocchino il tuo sito in fase di miglioramento di elementi che potrebbero influire su di te. |
| Localizzabili | Grazie alla risoluzione intelligente dei riferimenti alcuni componenti possono trovare ed eseguire [automaticamente il rendering del contenuto localizzato corrispondente.](get-started/localization.md) |
| Open Source | Se qualcosa non va come dovrebbe, [suggerisci i tuoi miglioramenti!](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## Componenti {#the-components}

La versione corrente dei Componenti core include i seguenti componenti.

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
* [Condivisione sui social media](components/sharing.md)
* [Separatore](components/separator.md)
* [Barra di avanzamento](components/progress-bar.md)
* [Visualizzatore PDF](components/pdf-viewer.md)

### Componenti contenitore {#container-components}

* [Contenitore](components/container.md)
* [Carosello](components/carousel.md)
* [Schede](components/tabs.md)
* [Pannello a soffietto](components/accordion.md)

### Componenti del modulo {#form-components}

* [Contenitore modulo](components/forms/form-container.md)
* [Testo modulo](components/forms/form-text.md)
* [Opzioni modulo](components/forms/form-options.md)
* [Campo nascosto modulo](components/forms/form-hidden.md)
* [Pulsante modulo](components/forms/form-button.md)

>[!NOTE]
>
>I Componenti core non sono immediatamente disponibili per gli autori; il [team di sviluppo deve prima integrarli nel tuo ambiente](get-started/using.md). Una volta integrati, possono essere resi disponibili e preconfigurati tramite l’[editor di modelli](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>Alcune versioni di singoli Componenti core potrebbero essere compatibili solo con determinate versioni di AEM.
>
>Visita la pagina dell’aiuto per il componente specifico (tramite il collegamento incluso nell’elenco precedente) per informazioni sulla compatibilità oppure vedi il documento [Versioni dei Componenti core](versions.md).

## Requisiti di sistema {#system-requirements}

| Componenti core | AEM as a Cloud Service | AEM 6.5 | AEM 6.4 | Java SE | Maven |
|---------|---------|---------|---------|---------|---------|
| [2.17.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.10) | Continua | 6.5.6.0+ * | 6.4.8.4+ * | 8, 11 | 3.3.9+ |

>[!NOTE]
>
>(*) A partire dalla versione 2.11.0, è richiesto `org.apache.sling.models.impl` versione 1.4.12 o successiva (a causa di [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)). Ciò sarà previsto per AEM 6.4 e 6.5 in un futuro Service Pack. Fino ad allora, il bundle Sling Models è incluso nel pacchetto `core.wcm.components.all`.

Per i requisiti delle precedenti versioni dei Componenti core, vedi [Versioni dei Componenti core](versions.md).

I Componenti core richiedono l’utilizzo di [modelli modificabili](https://docs.adobe.com/content/help/it-IT/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) e non supportano l’interfaccia utente classica né i modelli statici. Se necessario, vedi [Strumenti di modernizzazione AEM](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html) per aggiornare il tuo progetto con queste nuove funzioni AEM.

Per configurare il tuo ambiente di sviluppo locale, vedi [questa panoramica sul SDK per AEM as a Cloud Service](https://docs.adobe.com/content/help/it-IT/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) o questo documento [per le versioni precedenti di AEM](https://docs.adobe.com/content/help/it-IT/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).

>[!TIP]
>
>I Componenti core fanno automaticamente parte di AEM as a Cloud Service, per cui avrai sempre l’ultima versione dei Componenti core.
>
>Vedi il documento [Utilizzo dei Componenti core](/help/get-started/using.md) per ulteriori informazioni su come iniziare a utilizzare i Componenti core sia in AEMaaCS che on-premise.
