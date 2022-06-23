---
title: Archetipo progetto AEM
description: Un modello di progetto per applicazioni basate su AEM
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: 8b6f0a38d27911f23afa1fe26fd1800b4d200d33
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 100%

---

# Archetipo progetto AEM {#aem-project-archetype}

L’Archetipo progetto AEM è un modello Maven che crea un progetto AEM minimo basato sulle best practice di Adobe Experience Manager (AEM) come punto di partenza per il tuo sito web.

>[!TIP]
>
>La versione più recente di Archetipo progetto AEM [è disponibile su GitHub.](https://github.com/adobe/aem-project-archetype)

## Riferimenti {#resources}

* **Documentazione di Archetipo (questo documento):** panoramica dell’architettura di Archetipo e dei suoi vari moduli.
   * **[Utilizzo di Archetipo:](using.md)** ulteriori dettagli sull’utilizzo di Archetipo e dei moduli disponibili
   * **[ui.frontend:](uifrontend.md)** come utilizzare il modulo di sviluppo front-end
* **I seguenti tutorial sono basati su questo archetipo:**
   * **[Sito WKND:](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=it)** scopri come iniziare un nuovo sito web.
   * **[SPA (Single Page App) WKND:](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=it)** scopri come sviluppare un’app web React o Angular completamente personalizzabile in AEM.

## Funzioni {#features}

* **Best practice:** avvia il tuo sito con tutte le più recenti best practice di Adobe.
* **Codice basso:** modifica i modelli, crea contenuto, distribuisci i file CSS e il tuo sito è pronto per andare “live”.
* **Predisposto per il cloud:** se vuoi, utilizza [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=it) per andare “live” in pochi giorni e semplificare scalabilità e manutenzione.
* **Dispatcher:** un progetto è completo solo con una [configurazione di Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=it) che ne garantisca velocità e sicurezza.
* **Multi-sito:** se necessario, Archetipo genera la struttura del contenuto con una [configurazione per più lingue e aree geografiche](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/msm/overview.html?lang=it).
* **Componenti core:** gli autori possono creare quasi tutti i layout con il nostro versatile [set di componenti standard](/help/introduction.md).
* **Modelli modificabili:** assembla virtualmente qualsiasi [modello senza codice](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html?lang=it) e definisci cosa gli autori possono modificare.
* **Layout reattivo:** nei modelli o nelle singole pagine, [definisci il reflow degli elementi](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html?lang=it) per i punti di interruzione definiti.
* **Intestazione e piè di pagina:** assemblali e localizzali senza codice, utilizzando le [funzioni di localizzazione dei componenti](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html).
* **Sistema di stili:** evita di creare componenti personalizzati consentendo agli autori di [applicare loro stili diversi](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/style-system.html?lang=it).
* **Sviluppo front-end:** gli sviluppatori front-end possono [simulare pagine AEM](uifrontend.md#webpack-dev-server) e [creare librerie client](uifrontend.md) con Webpack, TypeScript e SASS.
* **Predisposto per WebApp:** per i siti che utilizzano [React](uifrontend-react.md) o [Angular](uifrontend-angular.md), utilizza l’[SDK SPA](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/developing.html?lang=it) per mantenere [l’authoring nel contesto dell’app](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html).
* **Predisposto per l’e-Commerce:** per progetti che intendono integrare [AEM Commerce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/home.html?lang=it) con soluzioni commerciali come [Magento](https://magento.com/) utilizzando i [Componenti Core commerciali](https://github.com/adobe/aem-core-cif-components).
* **Esempio di codice:** seleziona il componente HelloWorld e gli esempi di modelli, servlet, filtri e schedulatori.
* **Open source:** se qualcosa non va come dovrebbe, [suggerisci](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) i tuoi miglioramenti!

## Utilizzo {#usage}

Per generare un progetto, modifica la seguente riga di comando in base alle tue esigenze:

```shell
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* Sostituisci `XX` con il [numero di versione di Archetipo](#requirements) più recente.
* Imposta `aemVersion=cloud` per [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html);\
   Imposta `aemVersion=6.5.0` per [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) oppure on-premise.
La dipendenza dai Componenti core viene aggiunta solo per le versioni di AEM non cloud, in quanto i Componenti core vengono forniti come OOTB per AEM as a Cloud Service.
* Imposta `appTitle="My Site"` per definire il titolo del sito web e i gruppi di componenti.
* Imposta `appId="mysite"` per definire l’ID dell’artefatto Maven, i nomi delle cartelle di componenti, configurazione e contenuto nonché i nomi delle librerie client.
* Imposta `groupId="com.mysite"` per definire l’ID gruppo Maven e il pacchetto sorgente Java.
* Ricercare l’elenco delle proprietà disponibili per verificare se è necessario apportare ulteriori modifiche.

## Proprietà disponibili {#available-properties}

| Nome | Predefiniti | Descrizione |
|---------------------------|----------------|--------------------|
| `appTitle` |  | Titolo dell’applicazione, verrà utilizzato come titolo del sito web e dei gruppi di componenti (ad esempio, `"My Site"`). |
| `appId` |  | Nome tecnico, verrà utilizzato per i nomi di componenti, cartelle di configurazione e cartelle di contenuto nonché per i nomi delle librerie client (ad esempio, `"mysite"`). |
| `artifactId` | *`${appId}`* | ID artefatto Maven di base (ad esempio, `"mysite"`). |
| `groupId` |  | ID gruppo Maven di base (ad esempio, `"com.mysite"`). |
| `package` | *`${groupId}`* | Pacchetto sorgente Java (ad esempio, `"com.mysite"`). |
| `version` | `1.0-SNAPSHOT` | Versione del progetto (ad esempio, `1.0-SNAPSHOT`). |
| `aemVersion` | `cloud` | Versione AEM di destinazione (può essere `cloud` per [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html); `6.5.0` o `6.4.4` per [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) oppure on-premise). |
| `sdkVersion` | `latest` | Con `aemVersion=cloud` è possibile specificare una versione del [Software Development Kit (SDK)](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html?lang=it) (ad esempio, `2020.02.2265.20200217T222518Z-200130`). |
| `includeDispatcherConfig` | `y` | Include una configurazione di Dispatcher sia per il cloud che per AMS/on-premise, a seconda del valore di `aemVersion` (può essere `y` o `n`). |
| `frontendModule` | `general` | Include un modulo di sviluppo front-end di Webpack che genera le librerie client (può essere `general` o `none` per i siti normali; può essere `angular` o `react` per una SPA (Single Page App) che implementa l’[editor di SPA](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/editor-overview.html?lang=it)). |
| `language` | `en` | Codice lingua (ISO 639-1) dal quale creare la struttura del contenuto (ad esempio, `en`, `deu`). |
| `country` | `us` | Codice paese (ISO 3166-1) dal quale creare la struttura del contenuto (ad esempio, `US`). |
| `singleCountry` | `y` | Include una struttura di contenuto language-master (può essere `y` o `n`). |
| `includeExamples` | `n` | Include un esempio di sito nella [Libreria dei componenti](https://www.aemcomponents.dev/) (può essere `y` o `n`). |
| `includeErrorHandler` | `n` | Include una pagina di risposta 404 personalizzata che sarà globale per l’intera istanza (può essere `y` o `n`). |
| `includeCommerce` | `n` | Include le dipendenze dei [Componenti core CIF](https://github.com/adobe/aem-core-cif-components) e genera gli artefatti corrispondenti. |
| `commerceEndpoint` |  | Obbligatorio solo per CIF. Endpoint opzionale del servizio GraphQL del sistema commerciale da utilizzare (ad esempio `https://hostname.com/grapql`). |
| `datalayer` | `y` | Attiva l’integrazione con [Adobe Client Data Layer](/help/developing/data-layer/overview.md). |
| `amp` | `n` | Abilita il supporto [AMP](/help/developing/amp.md) per i modelli di progetto generati. |
| `enableDynamicMedia` | `n` | Abilita i componenti Dynamic Media di base nelle impostazioni dei criteri dei progetti e attiva le funzioni Dynamic Media nel criterio del componente core Immagine. |
| `enableSSR` | `n` | Opzione per l’abilitazione di SSR per il progetto front-end |
| `precompiledScripts` | `n` | Opzione per [precompilare](/help/developing/archetype/precompiled-bundled-scripts.md) gli script lato server da `ui.apps` e allegarli alla build come artefatto del bundle secondario nel progetto `ui.apps`. `aemVersion` deve essere impostato su `cloud`. |
| `includeFormscommunications` | `n` | Include [componenti core Forms](https://github.com/adobe/aem-core-forms-components) dipendenze, modelli, modelli di dati dei moduli, temi e genera artefatti corrispondenti per i programmi Forms Communications. |
| `includeFormsenrollment` | `n` | Include [Componenti core Forms](https://github.com/adobe/aem-core-forms-components) dipendenze, modelli, modelli di dati dei moduli, temi e genera artefatti corrispondenti per i programmi di iscrizione Forms. |

## Requisiti di sistema {#requirements}

| Archetipo | AEM as a Cloud Service | AEM 6.5 | Java SE | Maven |
|---------|---------|---------|---------|---------|
| [37](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-37) | Continua | 6.5.7.0+ | 8, 11 | 3.3.9+ |

Imposta l’ambiente di sviluppo locale per l’[SDK di AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html?lang=it) o per [versioni precedenti di AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html?lang=it).

### Problemi noti {#known-issues}

Se l’esecuzione è su Windows e stai generando la configurazione di Dispatcher, l’esecuzione deve avvenire da un prompt dei comandi con privilegi elevati oppure nel Sottosistema Windows per Linux (vedi il [problema n. 329](https://github.com/adobe/aem-project-archetype/issues/329)).

Durante l’esecuzione di Archetipo in modalità interattiva (senza il parametro `-B`), le proprietà con i valori predefiniti non possono essere modificate, a meno che la conferma finale non venga saltata, il che ripete le domande includendovi le proprietà con i valori predefiniti (per i dettagli, vedi
[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308)).

Non puoi utilizzare questo archetipo in Eclipse quando inizi un nuovo progetto con `File -> New -> Maven Project`, in quanto lo script di post-generazione `archetype-post-generate.groovy` non verrà eseguito a causa di un [problema di Eclipse.](https://bugs.eclipse.org/bugs/show_bug.cgi?id=514993) Per ovviare a questo problema. utilizza la riga di comando precedente, quindi in Eclipse utilizza `File -> Import -> Existing Maven Project`.

## Ulteriori informazioni {#further-reading}

Per ulteriori dettagli sull’utilizzo di Archetipo, compresi i vantaggi, le opzioni e il funzionamento dei moduli, vedi il documento [Utilizzo di Archetipo.](using.md)
