---
title: AEM Project Archetype
description: Un modello di progetto per applicazioni basate su AEM
feature: Componenti core, AEM Project Archetype
role: Architect, Developer, Administrator
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: b5ad1c874d5f6d6781c2d0b0cc992b278c91211b
workflow-type: tm+mt
source-wordcount: '1118'
ht-degree: 9%

---

# Archetipo di progetto AEM {#aem-project-archetype}

AEM Project Archetype è un modello Maven che crea un progetto Adobe Experience Manager (AEM) minimale basato su best practice come punto di partenza per il sito web.

>[!TIP]
>
>L&#39;ultimo Archetipo di progetto AEM [è disponibile su GitHub.](https://github.com/adobe/aem-project-archetype)

## Riferimenti {#resources}

* **Documentazione di Archetype (questo documento):** panoramica dell’architettura dell’archetipo e dei suoi diversi moduli.
   * **[Utilizzo dell&#39;Archetipo:](using.md)** ulteriori dettagli sull&#39;utilizzo dell&#39;archetipo e dei moduli disponibili
   * **[ui.frontend:](uifrontend.md)** come utilizzare il modulo di compilazione front-end
* Le seguenti esercitazioni sono basate su questo archetipo:
   * **[Sito WKND:](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** scopri come avviare un nuovo sito web.
   * **[App a pagina singola WKND:](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** scopri come creare un’app Web React o Angular completamente modificabile in AEM.

## Funzioni {#features}

* **Procedure consigliate:** Bootstrap il sito con tutte le ultime procedure consigliate di Adobe.
* **Codice basso:** modifica i modelli, crea contenuti, distribuisci i CSS e il tuo sito è pronto per essere live.
* **Cloud-Ready:** se lo desideri, utilizza  [AEM as a Cloud ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) Service per vivere in pochi giorni e semplificare scalabilità e manutenzione.
* **Dispatcher:** un progetto è completo solo con una  [configurazione di ](https://docs.adobe.com/content/help/it-IT/experience-manager-dispatcher/using/dispatcher.html) Dispatcher che ne garantisca la velocità e la sicurezza.
* **Multi-sito:** se necessario, l’archetipo genera la struttura del contenuto per una configurazione  [multilingue e con più aree geografiche](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/msm.html).
* **Componenti core:** gli autori possono creare quasi tutti i layout con il nostro versatile  [set di componenti standard](/help/introduction.md).
* **Modelli modificabili:** assembla virtualmente qualsiasi  [modello senza codice](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) e definisci cosa gli autori possono modificare.
* **Layout reattivo:** nei modelli o nelle singole pagine,  [definisci il ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html) flusso degli elementi per i punti di interruzione definiti.
* **Intestazione e piè di pagina:** assemblali e localizzali senza codice, utilizzando le funzioni di  [localizzazione dei componenti](https://docs.adobe.com/content/help/it/experience-manager-core-components/using/get-started/localization.html).
* **Sistema di stili:** evita di creare componenti personalizzati consentendo agli autori di  [applicare loro ](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/style-system.html) stili diversi.
* **Build front-end:** gli sviluppatori front-end possono  [simulare AEM ](uifrontend.md#webpack-dev-server) pagine e  [creare ](uifrontend.md) librerie client con Webpack, TypeScript e SASS.
* **WebApp-Ready:** per i siti che utilizzano  [](uifrontend-react.md) Reactor  [Angular](uifrontend-angular.md), utilizza l’ [SPA ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/developing.html) SDK [ per mantenere la creazione ](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)in-context dell’app.
* **Commerce Enabled:** per progetti che desiderano integrare  [AEM ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/commerce/home.html) Commerce con soluzioni commerce come  [](https://magento.com/) Magentousing the  [Commerce Core Components](https://github.com/adobe/aem-core-cif-components).
* **Esempio di codice:** seleziona il componente HelloWorld e i modelli, i servlet, i filtri e i programmatori di esempio.
* **Apri origine:** se qualcosa non è come dovrebbe,  [](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) contribuire ai tuoi miglioramenti!

## Utilizzo {#usage}

Per generare un progetto, regola la seguente riga di comando in base alle tue esigenze:

```shell
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* Sostituisci `XX` con il numero di versione più recente [archetipo.](#requirements)
* Imposta `aemVersion=cloud` per [AEM come Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   Imposta `aemVersion=6.5.0` per [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) o on-premise.
La dipendenza dai componenti core viene aggiunta solo per le versioni aem non cloud, in quanto i componenti core vengono forniti come Cloud Service da OOTB per AEM.
* Regola `appTitle="My Site"` per definire il titolo del sito web e i gruppi di componenti.
* Regola `appId="mysite"` per definire l&#39;artifactId Maven, i nomi delle cartelle dei componenti, della configurazione e del contenuto e i nomi delle librerie client.
* Regola `groupId="com.mysite"` per definire il valore groupId Maven e il pacchetto di origine Java.
* Ricercare l’elenco delle proprietà disponibili per verificare se è necessario apportare ulteriori modifiche.

## Proprietà disponibili {#available-properties}

| Nome | Predefiniti | Descrizione |
|---------------------------|----------------|--------------------|
| `appTitle` |  | Titolo applicazione, verrà utilizzato per i gruppi di titoli e componenti del sito web (ad es. `"My Site"`). |
| `appId` |  | Nome tecnico, verrà utilizzato per i nomi dei componenti, delle cartelle di configurazione e di contenuto, nonché per i nomi delle librerie client (ad esempio `"mysite"`). |
| `artifactId` | *`${appId}`* | ID artifact Maven di base (ad es. `"mysite"`). |
| `groupId` |  | ID gruppo Maven di base (ad es. `"com.mysite"`). |
| `package` | *`${groupId}`* | Pacchetto sorgente Java (ad esempio `"com.mysite"`). |
| `version` | `1.0-SNAPSHOT` | Versione del progetto (ad esempio `1.0-SNAPSHOT`). |
| `aemVersion` | `cloud` | Versione AEM di destinazione (può essere `cloud` per [AEM come Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html); oppure `6.5.0` o `6.4.4` per [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) o on-premise). |
| `sdkVersion` | `latest` | Quando è possibile specificare una versione `aemVersion=cloud` di [SDK](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) (ad esempio `2020.02.2265.20200217T222518Z-200130`). |
| `includeDispatcherConfig` | `y` | Include una configurazione del dispatcher sia per il cloud che per AMS/on-premise, a seconda del valore di `aemVersion` (può essere `y` o `n`). |
| `frontendModule` | `general` | Include un modulo di generazione front-end Webpack che genera le librerie client (può essere `general` o `none` per i siti normali; può essere `angular` o `react` per un&#39;app a pagina singola che implementa l&#39; [SPA Editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/editor-overview.html)). |
| `language` | `en` | Codice lingua (ISO 639-1) per creare la struttura del contenuto da (ad esempio `en`, `deu`). |
| `country` | `us` | Codice del paese (ISO 3166-1) da cui creare la struttura del contenuto (ad esempio `US`). |
| `singleCountry` | `y` | Include una struttura di contenuto principale per la lingua (può essere `y` o `n`). |
| `includeExamples` | `n` | Include un sito di esempio [Libreria componenti](https://www.aemcomponents.dev/) (può essere `y` o `n`). |
| `includeErrorHandler` | `n` | Include una pagina di risposta 404 personalizzata che sarà globale per l’intera istanza (può essere `y` o `n`). |
| `includeCommerce` | `n` | Include le dipendenze dei [componenti core CIF](https://github.com/adobe/aem-core-cif-components) e genera gli artefatti corrispondenti. |
| `commerceEndpoint` |  | Obbligatorio solo per CIF. Endpoint opzionale del servizio GraphQL del sistema commerce da utilizzare (ad esempio `https://hostname.com/grapql`). |
| `datalayer` | `y` | Attiva l&#39;integrazione con [Adobe Client Data Layer](/help/developing/data-layer/overview.md). |
| `amp` | `n` | Abilita il supporto di [AMP](/help/developing/amp.md) per i modelli di progetto generati. |
| `enableDynamicMedia` | `n` | Abilita le basi dei componenti Dynamic Media nelle impostazioni dei criteri dei progetti e attiva le funzioni Dynamic Media nei criteri del componente Immagine core. |
| `enableSSR` | `n` | Opzione per abilitare SSR per il progetto front-end |

## Requisiti di sistema {#requirements}

| Archetipo | AEM as a Cloud Service | AEM 6.5 | Java SE | Maven |
|---------|---------|---------|---------|---------|
| [28](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-28) | Continuo | 6.5.7.0+ | 8, 11 | 3.3.9+ |

Imposta l&#39;ambiente di sviluppo locale per [AEM come Cloud Service SDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) o per [versioni precedenti di AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).

### Problemi noti {#known-issues}

Quando si esegue su Windows e si genera la configurazione del dispatcher, è necessario eseguire un prompt dei comandi con privilegi elevati o il sottosistema Windows per Linux (vedere [#329](https://github.com/adobe/aem-project-archetype/issues/329)).

Durante l’esecuzione dell’archetipo in modalità interattiva (senza il parametro `-B` ), le proprietà con i valori predefiniti non possono essere modificate, a meno che la conferma finale non venga saltata, il che ripete le domande includendo nelle domande le proprietà con i valori predefiniti (consulta
[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) per i dettagli).

Non è possibile utilizzare questo archetipo in Eclipse quando si avvia un nuovo progetto con `File -> New -> Maven Project` poiché lo script di post generazione `archetype-post-generate.groovy` non verrà eseguito a causa di un problema [Eclipse.](https://bugs.eclipse.org/bugs/show_bug.cgi?id=514993) La soluzione è quella di utilizzare la riga di comando precedente e quindi in Eclipse usare  `File -> Import -> Existing Maven Project`.

## Ulteriori letture {#further-reading}

Per ulteriori dettagli sull&#39;utilizzo dell&#39;archetipo, compresi i vantaggi, le opzioni e il funzionamento dei moduli, vedere il documento [Utilizzo dell&#39;archetipo.](using.md)
