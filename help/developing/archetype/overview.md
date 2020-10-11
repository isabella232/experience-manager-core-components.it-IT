---
title: AEM Project Archetype
description: Un modello di progetto per applicazioni basate su AEM
translation-type: tm+mt
source-git-commit: 52f2c4dbba54261863a98fa2b992fe4690da3511
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
   * **[Utilizzo di Archetype:](using.md)** ulteriori dettagli sull&#39;utilizzo del archetipo e dei moduli disponibili
   * **[ui.frontend:](uifrontend.md)** Come utilizzare il modulo di build front-end
* Le seguenti esercitazioni sono basate su questo tipo di archetipo:
   * **[Sito WKND:](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** Scoprite come avviare un nuovo sito Web.
   * **[App per pagina singola WKND:](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** Scopri come creare un&#39;app Web React o Angular completamente authoring in AEM.

## Funzioni {#features}

* **Best practice:** Bootstrap il tuo sito con tutte  Adobe  procedure consigliate più recenti.
* **Codice basso:** Modificate i modelli, create contenuti, distribuite i CSS e il sito è pronto per essere trasmesso in diretta.
* **Pronto per il cloud:** Se lo desiderate, utilizzate [AEM come Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) per vivere in pochi giorni e semplificare la scalabilità e la manutenzione.
* **Dispatcher:** Un progetto è completo solo con una configurazione [](https://docs.adobe.com/content/help/it-IT/experience-manager-dispatcher/using/dispatcher.html) Dispatcher che ne garantisca la velocità e la sicurezza.
* **Più siti:** Se necessario, l&#39;archetipo genera la struttura del contenuto per una configurazione [in](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/msm.html)più lingue e in più aree.
* **Componenti di base:** Gli autori possono creare praticamente qualsiasi layout con il nostro [set versatile di componenti](/help/introduction.md)standardizzati.
* **Modelli modificabili:** Assemblate praticamente qualsiasi [modello senza codice](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)e definite gli elementi che gli autori possono modificare.
* **Layout reattivo:** Nei modelli o nelle singole pagine, [definite il modo in cui gli elementi si ridispongono](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html) per i punti di interruzione definiti.
* **Intestazione e piè di pagina:** Assemblate e localizzate i componenti senza codice, utilizzando le funzioni di [localizzazione dei componenti](https://docs.adobe.com/content/help/it-IT/experience-manager-core-components/using/get-started/localization.html).
* **Sistema di stile:** Evitate di creare componenti personalizzati consentendo agli autori di [applicare stili](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/style-system.html) diversi.
* **Build front-end:** Gli sviluppatori front-end possono [mascherare AEM pagine](uifrontend.md#webpack-dev-server) e [creare librerie](uifrontend.md) client con Webpack, TypeScript e SASS.
* **WebApp-Ready:** Per i siti che utilizzano [React](uifrontend-react.md) o [Angular](uifrontend-angular.md), utilizzate [SPA SDK](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/developing.html) per mantenere la creazione [contestuale dell’app](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html).
* **Commerce abilitato:** Per progetti che desiderano integrare [AEM Commerce](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/commerce/home.html) con soluzioni di commercio come [Magento](https://magento.com/) utilizzando i componenti [core di](https://github.com/adobe/aem-core-cif-components)Commerce.
* **Esempio di codice:** Estrarre il componente HelloWorld e i modelli, servlet, filtri e pianificatori di esempio.
* **Apri origine:** Se qualcosa non è come dovrebbe, [contribuire](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) ai vostri miglioramenti!

## Utilizzo

Per generare un progetto, regola la seguente riga di comando in base alle tue esigenze:

```
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=24 \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* Impostare `aemVersion=cloud` per [AEM come Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   Impostato `aemVersion=6.5.0` per [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)o locale.
La dipendenza Componenti di base viene aggiunta solo per le versioni Aem non cloud, in quanto i Componenti di base vengono forniti come Cloud Service OOOTB per AEM.
* Regolate `appTitle="My Site"` per definire il titolo del sito Web e i gruppi di componenti.
* Regolate `appId="mysite"` per definire il Maven artifactId, i nomi delle cartelle dei componenti, delle configurazioni e dei contenuti, nonché i nomi delle librerie dei client.
* Regola `groupId="com.mysite"` per definire il Maven groupId e il pacchetto di origine Java.
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
| `aemVersion` | `cloud` | AEM versione di destinazione (può essere `cloud` AEM come [Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html); oppure `6.5.0`, `6.4.4` per i servizi [gestiti](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) Adobe o locali). |
| `sdkVersion` | `latest` | Quando è possibile specificare `aemVersion=cloud` una versione [SDK](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) (ad es. `2020.02.2265.20200217T222518Z-200130`). |
| `includeDispatcherConfig` | `y` | Include una configurazione dispatcher sia per il cloud che per AMS/locale, a seconda del valore di `aemVersion` (può essere `y` o `n`). |
| `frontendModule` | `general` | Include un modulo di generazione frontale Webpack che genera le librerie client (può essere `general` o `none` per siti regolari); può essere `angular` o `react` per un&#39;app a pagina singola che implementa l&#39;Editor [](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/editor-overview.html)SPA). |
| `language` | `en` | Codice della lingua (ISO 639-1) per creare la struttura del contenuto da (ad esempio `en`, `deu`). |
| `country` | `us` | Codice del paese (ISO 3166-1) per creare la struttura del contenuto da (ad esempio `US`). |
| `singleCountry` | `y` | Include una struttura del contenuto master del linguaggio (può essere `y`o `n`). |
| `includeExamples` | `n` | Include un sito di esempio della libreria [di](https://www.aemcomponents.dev/) componenti (può essere `y`o `n`). |
| `includeErrorHandler` | `n` | Include una pagina di risposta personalizzata 404 che sarà globale per l&#39;intera istanza (può essere `y` o `n`). |
| `includeCommerce` | `n` | Include dipendenze [CIF dei componenti](https://github.com/adobe/aem-core-cif-components) core e genera artefatti corrispondenti. |
| `commerceEndpoint` |  | Obbligatorio solo per CIF. Endpoint opzionale del servizio GraphQL del sistema commerciale da utilizzare (ad esempio `https://hostname.com/grapql`). |
| `datalayer` | `y` | Attiva l&#39;integrazione con [livello](/help/developing/data-layer/overview.md)dati client Adobe. |
| `amp` | `n` | Abilita il supporto [AMP](/help/developing/amp.md) per i modelli di progetto generati. |

## Requisiti di sistema

| Archetype | AEM as a Cloud Service | AEM 6.5 | AEM 6.4   | Java SE | Paradiso |
|---------|---------|---------|---------|---------|---------|
| [24](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-24) | Continuo | 6.5.5.0+ | 6.4.8.1+ | 8, 11 | 3.3.9+ |

Imposta l’ambiente di sviluppo locale per [AEM come SDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) Cloud Service o per versioni [precedenti di AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).

### Problemi noti

Quando si esegue in Windows e si genera la configurazione del dispatcher, è necessario eseguire un prompt di comando elevato o il sottosistema Windows per Linux (vedere [#329](https://github.com/adobe/aem-project-archetype/issues/329)).

Durante l&#39;esecuzione dell&#39;archetype in modalità interattiva (senza il `-B` parametro), le proprietà con i valori predefiniti non possono essere modificate, a meno che la conferma finale non venga chiusa, il che ripete le domande includendo nelle domande le proprietà con i valori predefiniti (consultate[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) per i dettagli).

## Lettura {#further-reading}

Per ulteriori dettagli sull&#39;utilizzo dell&#39;archetipo, compresi i vantaggi, le opzioni e il funzionamento dei moduli, vedere il documento [Utilizzo di Archetype.](using.md)
