---
title: AEM Project Archetype
description: Un modello di progetto per applicazioni basate su AEM
translation-type: tm+mt
source-git-commit: 794408e8b643de2234664e69e59e1108cf286cd7
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 10%

---


# AEM Project Archetype {#aem-project-archetype}

AEM Project Archetype è un modello Maven che crea un progetto Adobe Experience Manager (AEM) minimale basato sulle best practice come punto di partenza per il sito Web.

>[!TIP]
>
>L&#39;ultimo AEM Project Archetype [è disponibile su GitHub](https://github.com/adobe/aem-project-archetype).

## Riferimenti {#resources}

* **Documentazione Archetype (questo documento):** Panoramica dell&#39;architettura archetype e dei suoi diversi moduli.
   * **[Utilizzo di Archetype:](using.md)** ulteriori dettagli sull&#39;utilizzo di archetype e dei moduli disponibili
   * **[ui.frontend:](uifrontend.md)** Come utilizzare il modulo di compilazione front-end
* Le seguenti esercitazioni sono basate su questo tipo di archetipo:
   * **[Sito WKND:](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** Scopri come avviare un nuovo sito Web.
   * **[App WKND per pagina singola:](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** scoprite come creare un&#39;app Web React o Angular completamente authoring in AEM.

## Funzioni {#features}

* **Procedure ottimali:** Bootstrap del sito con tutte  Adobi  procedure consigliate più recenti.
* **Basso codice:** modificate i modelli, create i contenuti, distribuite i CSS e il sito è pronto per essere live.
* **Cloud-Ready:** Se lo desideri, usa  [AEM come servizio cloud per ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) vivere in pochi giorni e semplificare la scalabilità e la manutenzione.
* **Dispatcher:** Un progetto è completo solo con una  [configurazione ](https://docs.adobe.com/content/help/it-IT/experience-manager-dispatcher/using/dispatcher.html) Dispatcher che garantisca velocità e sicurezza.
* **Multi-sito:** se necessario, archetype genera la struttura del contenuto per una configurazione [ ](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/msm.html)multi-lingua e multi-regione.
* **Componenti di base:** gli autori possono creare praticamente qualsiasi layout con il nostro  [set versatile di componenti](/help/introduction.md) standardizzati.
* **Modelli modificabili:** Assemblate praticamente qualsiasi  [modello senza codice](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) e definite gli elementi che gli autori possono modificare.
* **Layout reattivo:** nei modelli o nelle singole pagine,  [definire il modo in cui gli elementi vengono ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html) ridisposti per i punti di interruzione definiti.
* **Intestazione e piè di pagina:** Assemblare e localizzare i componenti senza codice, utilizzando le funzioni di  [localizzazione dei componenti](https://docs.adobe.com/content/help/it-IT/experience-manager-core-components/using/get-started/localization.html).
* **Sistema di stile:** evitate di creare componenti personalizzati consentendo agli autori di  [applicare ](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/style-system.html) stili diversi a tali componenti.
* **build front-end: gli sviluppatori** front-end possono  [creare blocchi AEM ](uifrontend.md#webpack-dev-server) pagine e  [creare ](uifrontend.md) librerie client con webpack, TypeScript e SASS.
* **WebApp-Ready:** Per i siti che utilizzano  [](uifrontend-react.md) Reactor  [Angular](uifrontend-angular.md), utilizza l’ [SPA ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/developing.html) SDKper mantenere la creazione  [contestuale dell’app](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html).
* **Commerce abilitato:** per progetti che desiderano integrare  [AEM ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/commerce/home.html) Commerceologia con soluzioni commerciali come  [](https://magento.com/) Magentousing the  [Commerce Core Components](https://github.com/adobe/aem-core-cif-components).
* **Esempio di codice:** estraete il componente HelloWorld e i modelli, i servlet, i filtri e i pianificatori di esempio.
* **Open Sourced:** se qualcosa non è come dovrebbe,  [](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) contribuisci ai tuoi miglioramenti!

## Utilizzo

Per generare un progetto, regola la seguente riga di comando in base alle tue esigenze:

```shell
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=24 \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* Impostare `aemVersion=cloud` per [AEM come Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   Impostare `aemVersion=6.5.0` per [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) o in sede.
La dipendenza Componenti di base viene aggiunta solo per le versioni Aem non cloud, in quanto i Componenti di base vengono forniti come Cloud Service OOOTB per AEM.
* Regolate `appTitle="My Site"` per definire il titolo del sito Web e i gruppi di componenti.
* Regolate `appId="mysite"` per definire il Maven artifactId, i nomi dei componenti, della configurazione e delle cartelle di contenuto, nonché i nomi delle librerie client.
* Regolate `groupId="com.mysite"` per definire il Maven groupId e il pacchetto di origine Java.
* Consultate l’elenco delle proprietà disponibili per verificare se vi sono altre proprietà da regolare.

## Proprietà disponibili

| Nome | Predefiniti | Descrizione |
--------------------------|----------------|--------------------
| `appTitle` |  | Titolo applicazione, verrà utilizzato per il titolo del sito Web e i gruppi di componenti (ad es. `"My Site"`). |
| `appId` |  | Nome tecnico, verrà utilizzato per i nomi dei componenti, delle cartelle di configurazione e di contenuto, nonché per i nomi delle librerie client (ad esempio `"mysite"`). |
| `artifactId` | *`${appId}`* | ID artifact di base Maven (ad es. `"mysite"`). |
| `groupId` |  | ID gruppo Base Paradiso (ad es. `"com.mysite"`). |
| `package` | *`${groupId}`* | Pacchetto di origine Java (ad esempio `"com.mysite"`). |
| `version` | `1.0-SNAPSHOT` | Versione del progetto (ad es. `1.0-SNAPSHOT`). |
| `aemVersion` | `cloud` | AEM versione di destinazione (può essere `cloud` per [AEM come Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html); oppure `6.5.0` o `6.4.4` per [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) o in sede). |
| `sdkVersion` | `latest` | Quando è possibile specificare una versione `aemVersion=cloud` di [SDK](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) (ad esempio `2020.02.2265.20200217T222518Z-200130`). |
| `includeDispatcherConfig` | `y` | Include una configurazione dispatcher sia per il cloud che per AMS/locale, a seconda del valore di `aemVersion` (può essere `y` o `n`). |
| `frontendModule` | `general` | Include un modulo di generazione dei frontend per webpack che genera le librerie client (può essere `general` o `none` per i siti regolari; può essere `angular` o `react` per un&#39;app a pagina singola che implementa l&#39;editor [SPA](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/editor-overview.html)). |
| `language` | `en` | Codice della lingua (ISO 639-1) per creare la struttura del contenuto da (ad esempio `en`, `deu`). |
| `country` | `us` | Codice del paese (ISO 3166-1) per creare la struttura del contenuto da (ad esempio `US`). |
| `singleCountry` | `y` | Include una struttura del contenuto principale per le lingue (può essere `y` o `n`). |
| `includeExamples` | `n` | Include un sito di esempio [Libreria componenti](https://www.aemcomponents.dev/) (può essere `y` o `n`). |
| `includeErrorHandler` | `n` | Include una pagina di risposta personalizzata 404 che sarà globale per l&#39;intera istanza (può essere `y` o `n`). |
| `includeCommerce` | `n` | Include dipendenze [CIF dei componenti core](https://github.com/adobe/aem-core-cif-components) e genera artefatti corrispondenti. |
| `commerceEndpoint` |  | Obbligatorio solo per CIF. Endpoint opzionale del servizio GraphQL del sistema commerciale da utilizzare (ad esempio `https://hostname.com/grapql`). |
| `datalayer` | `y` | Attivare l&#39;integrazione con [ livello dati client Adobe](/help/developing/data-layer/overview.md). |
| `amp` | `n` | Abilita il supporto di [AMP](/help/developing/amp.md) per i modelli di progetto generati. |

## Requisiti di sistema

| Archetype | AEM as a Cloud Service | AEM 6.5 | AEM 6.4   | Java SE | Paradiso |
|---------|---------|---------|---------|---------|---------|
| [24](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-24) | Continuo | 6.5.5.0+ | 6.4.8.1+ | 8, 11 | 3.3.9+ |

Imposta l&#39;ambiente di sviluppo locale per [AEM come Cloud Service SDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) o per [versioni precedenti di AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).

### Problemi noti

Quando si esegue in Windows e si genera la configurazione del dispatcher, è necessario eseguire un prompt dei comandi elevato o il sottosistema Windows per Linux (vedere [#329](https://github.com/adobe/aem-project-archetype/issues/329)).

Durante l&#39;esecuzione dell&#39;archetype in modalità interattiva (senza il parametro `-B`), le proprietà con i valori predefiniti non possono essere modificate, a meno che la conferma finale non venga chiusa, il che ripete le domande includendo nelle domande le proprietà con i valori predefiniti (vedete
[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) per i dettagli).

## Lettura successiva {#further-reading}

Per ulteriori dettagli sull&#39;utilizzo dell&#39;archetype, compresi i vantaggi, le opzioni e il funzionamento dei moduli, vedere il documento [Using the Archetype document.](using.md)
