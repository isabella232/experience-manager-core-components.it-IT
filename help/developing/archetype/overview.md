---
title: Archetipo progetto AEM
description: Scopri l’Archetipo progetto AEM, che funge da modello per le applicazioni basate su AEM.
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: 8940285f4c5e5870b6a135dac674f06e4c1d8b5a
workflow-type: ht
source-wordcount: '527'
ht-degree: 100%

---


# Archetipo progetto AEM {#aem-project-archetype}

L’Archetipo progetto AEM è un modello Maven che crea un progetto AEM minimo basato sulle best practice di Adobe Experience Manager (AEM) come punto di partenza per il tuo sito web. Questa documentazione fornisce una panoramica dei vantaggi dell’archetipo e dell’utilizzo generale. Istruzioni tecniche dettagliate e la documentazione sono disponibili nell’archivio GitHub di Archetipo.

>[!TIP]
>
> La versione più recente dell’Archetipo progetto AEM [è disponibile su GitHub.](https://github.com/adobe/aem-project-archetype)

## Perché utilizzare Archetipo {#why-use-the-archetype}

Utilizzando Archetipo progetto AEM puoi creare un progetto AEM basato sulle best practice con poche sequenze di tasti. Con l’archetipo, tutti i pezzi sono già in posizione in modo che, pur se il progetto risultante è minimo, implementa già tutte le [caratteristiche chiave](/help/developing/archetype/using.md#what-you-get) di AEM in modo che tutto quello che devi fare è continuare a sviluppare ed estendere.

Naturalmente, ci sono molti elementi che entrano in [un progetto di AEM riuscito,](/help/developing/success.md) ma l’utilizzo di Archetipo progetto AEM è una solida base ed è vivamente consigliato per qualsiasi progetto AEM.

## Funzioni {#features}

* **Best practice:** avvia il tuo sito con tutte le più recenti best practice di Adobe.
* **Codice basso:** modifica i modelli, crea contenuto, distribuisci i file CSS e il tuo sito è pronto per andare “live”.
* **Predisposto per il cloud:** se vuoi, utilizza [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=it) per andare “live” in pochi giorni e semplificare scalabilità e manutenzione.
* **Dispatcher:** un progetto è completo solo con una [configurazione di Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=it) che ne garantisca velocità e sicurezza.
* **Multi-sito:** se necessario, Archetipo genera la struttura del contenuto con una [configurazione per più lingue e aree geografiche](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/msm/overview.html?lang=it).
* **Componenti core:** gli autori possono creare quasi tutti i layout con il nostro versatile [set di componenti standard](/help/introduction.md).
* **Modelli modificabili:** assembla virtualmente qualsiasi [modello senza codice](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html?lang=it) e definisci cosa gli autori possono modificare.
* **Layout reattivo:** nei modelli o nelle singole pagine, [definisci il reflow degli elementi](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html?lang=it) per i punti di interruzione definiti.
* **Intestazione e piè di pagina:** assemblali e localizzali senza codice, utilizzando le [funzioni di localizzazione dei componenti](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html?lang=it).
* **Sistema di stili:** evita di creare componenti personalizzati consentendo agli autori di [applicare loro stili diversi](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/style-system.html?lang=it).
* **Sviluppo front-end:** gli sviluppatori front-end possono [simulare pagine AEM](front-end.md) e creare librerie client con Webpack, TypeScript e SASS.
* **Predisposto per WebApp:** per i siti che utilizzano React o Angular, utilizza l’[SDK SPA](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/developing.html?lang=it) per mantenere [l’authoring nel contesto dell’app](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=it).
* **Predisposto per l’e-Commerce:** per progetti che intendono integrare [AEM Commerce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/home.html?lang=it) con soluzioni commerciali come [Magento](https://magento.com/it) utilizzando i [Componenti Core commerciali](https://github.com/adobe/aem-core-cif-components).
* **Esempio di codice:** seleziona il componente HelloWorld e gli esempi di modelli, servlet, filtri e schedulatori.
* **Open source:** se qualcosa non va come dovrebbe, [suggerisci](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) i tuoi miglioramenti!

## Ulteriori informazioni {#further-reading}

* **[GitHub Archetipo progetto AEM](https://github.com/adobe/aem-project-archetype)**: per informazioni complete sull’utilizzo e i dettagli tecnici dell’archetipo
* **[Utilizzo di Archetipo](using.md)**: panoramica sull’utilizzo dell’archetipo nel progetto e dei moduli generati
* **[Sviluppo front-end con l’archetipo del progetto AEM](front-end.md)**: come utilizzare il modulo front-end dell’archetipo
* **I seguenti tutorial sono basati su questo archetipo:**
   * **[Sito WKND:](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=it)** scopri come iniziare un nuovo sito web.
   * **[SPA (Applicazioni a pagina singola) WKND](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=it)**: scopri come sviluppare un’app web React o Angular completamente sottoposta ad authoring in AEM.
