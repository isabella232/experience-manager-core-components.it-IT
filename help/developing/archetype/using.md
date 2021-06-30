---
title: Utilizzo di AEM Project Archetype
description: Istruzioni d'uso dettagliate per AEM Project Archetype
feature: Componenti core, AEM Project Archetype
role: Architect, Developer, Administrator
exl-id: a3978d8b-4904-42aa-9ee2-9c1f884327bb
source-git-commit: 17081a073998512a52aebfc662f2bc125ca2a2c4
workflow-type: tm+mt
source-wordcount: '2147'
ht-degree: 1%

---

# AEM Project Archetype {#aem-project-archetype}

AEM Project Archetype crea un progetto Adobe Experience Manager minimale basato su best practice come punto di partenza per i tuoi progetti AEM. Le proprietà che devono essere fornite quando si utilizza questo archetipo consentono di specificare i nomi di tutte le parti del progetto e di controllare alcune funzioni facoltative.

## Perché utilizzare Archetype {#why-use-the-archetype}

Utilizzando AEM Project Archetype puoi creare un progetto AEM basato su best practice con poche sequenze di tasti. Utilizzando l&#39;archetipo, tutti i pezzi saranno già in posizione in modo che, mentre il progetto risultante è minimo, implementa già tutte le [caratteristiche chiave](#what-you-get) di AEM in modo che tutto quello che dovete fare è costruire sopra e estendere.

Naturalmente ci sono molti elementi che entrano in un progetto di AEM di successo, ma l&#39;utilizzo di AEM Project Archetype è una solida base ed è vivamente consigliato per qualsiasi progetto AEM.

## Guida introduttiva {#getting-started}

L&#39;archetipo del progetto rende facile iniziare a sviluppare su AEM. Puoi intraprendere i tuoi primi passi in diversi modi.

* Esercitazione WKND : per una grande introduzione allo sviluppo di AEM, tra cui come sfruttare l’archetipo, consulta la [Guida introduttiva ad AEM Sites - WKND Tutorial](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) per un esempio pratico che illustra come utilizzare l’archetipo per implementare un semplice progetto.
* Esercitazione eventi WKND : se sei particolarmente interessato allo sviluppo di applicazioni a pagina singola (SPA) su AEM, assicurati di controllare l’ esercitazione dedicata [Eventi WKND](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html).
* Scarica e inizia da solo! - Puoi scaricare facilmente l’archetipo di progetto corrente disponibile su GitHub e creare il primo progetto da [seguendo i semplici passaggi descritti di seguito](#how-to-use-the-archetype).

## Informazioni sull’utilizzo di Archetype {#what-you-get}

L&#39;Archetipo AEM è costituito da moduli:

* **[core](core.md)**: è un bundle Java contenente tutte le funzionalità di base come i servizi OSGi, gli ascoltatori e i programmatori, nonché il codice Java relativo ai componenti come i servlet e i filtri di richiesta.
* **[it.test](ittests.md)**: sono test di integrazione basati su Java.
* **[ui.apps](uiapps.md)**: contiene  `/apps` e  `/etc` parti del progetto, ad esempio clientlib JS e CSS, componenti e modelli.
* **[ui.content](uicontent.md)**: contiene contenuto di esempio utilizzando i componenti del modulo ui.apps .
* **ui.config**: contiene configurazioni OSGi specifiche per la modalità di esecuzione per il progetto.
* **[ui.frontend.general](uifrontend.md)**:  **(facoltativo)** contiene gli artefatti necessari per utilizzare il modulo di compilazione front-end generale basato su Webpack.
* **[ui.frontend.react](uifrontend-react.md)**:  **(facoltativo)** contiene gli artefatti necessari quando si utilizza l’archetipo per creare progetti SPA basati su React.
* **[ui.frontend.angular](uifrontend-angular.md)**:  **(Facoltativo)** contiene gli artefatti necessari quando si utilizza l’archetipo per creare progetti di SPA basati sull’Angular.
* **[ui.test](uitests.md)**: contiene test di interfaccia utente basati su selenio.
* **tutti**: è un singolo pacchetto di contenuti che incorpora tutti i moduli compilati (bundle e pacchetti di contenuti), comprese le dipendenze dei fornitori.
* **analizzare**: esegue l’analisi del progetto, che fornisce una convalida aggiuntiva per la distribuzione in AEM come Cloud Service.

![](/help/assets/archetype-structure.png)

I moduli di Archetype AEM rappresentati in Maven vengono distribuiti per AEM come pacchetti di contenuto che rappresentano l’applicazione, il contenuto e i bundle OSGi necessari.

## Come utilizzare Archetype {#how-to-use-the-archetype}

Per utilizzare l&#39;archetipo, devi innanzitutto creare un progetto, che genera i moduli in una struttura di file locale come [descritto in precedenza](#what-you-get). Come parte della generazione del progetto, è possibile definire una serie di proprietà per il progetto, ad esempio nome, versione e così via.

La creazione del progetto con Maven crea gli artefatti (pacchetti e bundle OSGi) che possono essere distribuiti in AEM. Ulteriori comandi e profili Maven possono essere utilizzati per distribuire gli artefatti del progetto in un’istanza AEM.

### Creazione di un progetto  {#create-project}

Per iniziare, puoi semplicemente utilizzare l&#39; [AEM estensione Eclipse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/eclipse.html) e seguire la procedura guidata Nuovo progetto e scegliere **AEM Progetto Multi-Modulo di esempio** per utilizzare una versione rilasciata dell&#39;archetipo.

Naturalmente puoi anche invocare direttamente Maven.

```shell
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D aemVersion=cloud \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
 -D frontendModule=general \
 -D includeExamples=n
```

* Imposta `XX` sul [numero di versione](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md) dell&#39;ultimo Archetipo di progetto AEM.
* Imposta `aemVersion=cloud` per [AEM come Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   Imposta `aemVersion=6.5.0` per [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) o on-premise.
La dipendenza dai componenti core viene aggiunta solo per le versioni aem non cloud, in quanto i componenti core vengono forniti come OOTB per AEM as a Cloud
Servizio.
* Regola `appTitle="My Site"` per definire il titolo del sito web e i gruppi di componenti.
* Regola `appId="mysite"` per definire l&#39;artifactId Maven, i nomi delle cartelle dei componenti, della configurazione e del contenuto e i nomi delle librerie client.
* Regola `groupId="com.mysite"` per definire il valore groupId Maven e il pacchetto di origine Java.
* Ricercare l’elenco delle proprietà disponibili per verificare se è necessario apportare ulteriori modifiche.

>[!NOTE]
>
>È consigliabile aggiungere il profilo `adobe-public` al file Maven `settings.xml` per aggiungere automaticamente repo.adobe.com al processo di creazione maven.
>
>Un esempio POM [è disponibile qui](https://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html).

### Proprietà {#properties}

Le seguenti proprietà sono disponibili quando crei un progetto utilizzando l’archetipo .

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

>[!NOTE]
>
> Se l&#39;archetipo viene eseguito in modalità interattiva la prima volta, le proprietà con valori predefiniti non possono essere modificate (per ulteriori informazioni, vedere [ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) ). Il valore può essere modificato quando la conferma della proprietà alla fine viene negata e il questionario viene ripetuto, o passando il parametro nella riga di comando (ad esempio `-DoptionIncludeExamples=n`).

>[!NOTE]
>
>Quando esegui Windows e genera la configurazione del dispatcher, devi essere in esecuzione in un prompt dei comandi con privilegi elevati o nel sottosistema Windows per Linux (vedi [problema 329](https://github.com/adobe/aem-project-archetype/issues/329)).

### Profili {#profiles}

Il progetto maven generato supporta diversi profili di distribuzione durante l’esecuzione di `mvn install`.

| ID profilo | Descrizione |
| --------------------------|------------------------------|
| `autoInstallBundle` | Installa il bundle core con maven-sling-plugin nella console felix |
| `autoInstallPackage` | Installa il pacchetto di contenuti ui.content e ui.apps con content-package-maven-plugin nel gestore di pacchetti per impostare l&#39;istanza di authoring predefinita su localhost, porta 4502. È possibile modificare nome host e porta con le proprietà definite dall&#39;utente `aem.host` e `aem.port` . |
| `autoInstallPackagePublish` | Installa il pacchetto di contenuti ui.content e ui.apps con il content-package-maven-plugin nel gestore di pacchetti per pubblicare l&#39;istanza predefinita su localhost, porta 4503. È possibile modificare nome host e porta con le proprietà definite dall&#39;utente `aem.host` e `aem.port` . |
| `autoInstallSinglePackage` | Installa il pacchetto di contenuti `all` con content-package-maven-plugin nel gestore di pacchetti per creare l&#39;istanza di authoring predefinita su localhost, porta 4502. È possibile modificare nome host e porta con le proprietà definite dall&#39;utente `aem.host` e `aem.port` . |
| `autoInstallSinglePackagePublish` | Installa il pacchetto di contenuti `all` con il content-package-maven-plugin nel gestore di pacchetti per eseguire l&#39;istanza di pubblicazione predefinita su localhost, porta 4503. È possibile modificare nome host e porta con le proprietà definite dall&#39;utente `aem.host` e `aem.port` . |
| `integrationTests` | Esegue i test di integrazione forniti sull&#39;istanza AEM (solo per la fase `verify`) |

### Creazione e installazione {#building-and-installing}

Per generare tutti i moduli eseguiti nella directory principale del progetto, utilizza il seguente comando Maven.

```shell
mvn clean install
```

Se disponi di un&#39;istanza AEM in esecuzione, puoi generare e creare un pacchetto per l&#39;intero progetto e distribuirlo in AEM con il seguente comando Maven.

```shell
mvn clean install -PautoInstallPackage
```

Per distribuirlo in un&#39;istanza di pubblicazione, esegui questo comando.

```shell
mvn clean install -PautoInstallPackagePublish
```

In alternativa, per distribuire in un&#39;istanza di pubblicazione, esegui questo comando.

```shell
mvn clean install -PautoInstallPackage -Daem.port=4503
```

Oppure per distribuire solo il bundle all&#39;autore, esegui questo comando.

```shell
mvn clean install -PautoInstallBundle
```

## POM principale {#parent-pom}

Il `pom.xml` nella directory principale del progetto (`<src-directory>/<project>/pom.xml`) è noto come POM principale e gestisce la struttura del progetto, nonché le dipendenze e alcune proprietà globali del progetto.

### Proprietà progetto globale {#global-properties}

La sezione `<properties>` del POM principale definisce diverse proprietà globali importanti per la distribuzione del progetto in un’istanza AEM come nome utente/password, nome host/porta, ecc.

Queste proprietà sono configurate per la distribuzione in un&#39;istanza AEM locale, in quanto si tratta della build più comune che gli sviluppatori faranno. Tieni presente che esistono proprietà da distribuire a un’istanza di authoring e a un’istanza di pubblicazione. In questo punto vengono anche impostate le credenziali per l’autenticazione con l’istanza AEM. Vengono utilizzate le credenziali amministratore:admin predefinite.

Queste proprietà sono configurate in modo che possano essere ignorate durante la distribuzione in ambienti di livello superiore. In questo modo i file POM non devono essere modificati, ma le variabili come `aem.host` e `sling.password` possono essere ignorate tramite argomenti della riga di comando:

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### Struttura del modulo {#module-structure}

La sezione `<modules>` del POM principale definisce i moduli che il progetto creerà. Per impostazione predefinita, il progetto crea [i moduli standard precedentemente definiti](#what-you-get): core, ui.apps, ui.content, ui.test e it.launcher. È sempre possibile aggiungere più moduli man mano che un progetto si evolve.

### Dipendenze {#dependencies}

La sezione `<dependencyManagement>` del POM principale definisce tutte le dipendenze e le versioni delle API utilizzate nel progetto. Le versioni devono essere gestite nel POM principale. I sottomoduli come core e ui.apps non devono includere informazioni sulle versioni.

#### Uber-Jar {#uber-jar}

Una delle dipendenze chiave è [AEM uber-jar](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/ht-projects-maven.html#ExperienceManagerAPIDependencies). Questo includerà tutte le API AEM con una sola voce di dipendenza per la versione di AEM.

>[!NOTE]
>
>Come best practice, aggiorna la versione uber-jar in modo che corrisponda alla versione di destinazione di AEM. Ad esempio, se prevedi di distribuire a AEM 6.4, devi aggiornare la versione di uber-jar a 6.4.0.

#### Componenti core {#core-components}

Il AEM Project Archetype, ovviamente, sfrutta i Componenti core.

I componenti core vengono installati in AEM automaticamente nella modalità di esecuzione predefinita e vengono utilizzati dal sito WKND di esempio. In una [modalità di esecuzione di produzione](https://docs.adobe.com/content/help/en/experience-manager-65/administering/security/production-ready.html) (`nosamplecontent`) i componenti core non sono disponibili.

Pertanto, per sfruttare i componenti core in tutte le implementazioni, è consigliabile includerli come parte del progetto Maven.

>[!NOTE]
>
>A ogni versione dei componenti core fa generalmente seguito un rilascio dell’Archetipo di progetto AEM in modo che l’archetipo più recente utilizzi la versione più recente dei componenti core.
>
>Tuttavia, una nuova versione dell’archetipo potrebbe non seguire direttamente una nuova versione dei componenti core, pertanto potresti voler aggiornare la dipendenza dai componenti core alla versione più recente.

>[!NOTE]
>
>Gli esempi core.wcm.components.examples sono un set di pagine di esempio che illustrano esempi di componenti core. Come best practice, quando distribuisci un progetto per la produzione utilizza rimuovi questa dipendenza e l’inclusione dei sottopacchetti.

## Test {#testing}

Il progetto contiene tre livelli di test e, poiché sono diversi tipi di test, vengono eseguiti in modi diversi o in posizioni diverse.

* Test di unità nel nucleo: Questo mostra il classico unit testing del codice contenuto nel bundle. Per eseguire il test, esegui:
   * `mvn clean test`
* Test di integrazione lato server: Questi test vengono eseguiti come unità nell’ambiente AEM, ad esempio sul server AEM. Per eseguire il test, esegui:
   * `mvn clean verify -PintegrationTests`
* Test Hobbes.js lato client: Si tratta di test lato browser basati su JavaScript per verificare il comportamento lato browser. Per eseguire il test:
   1. Carica AEM nel browser come faresti per creare una pagina.
   1. Apri la pagina in [Modalità sviluppatore](https://docs.adobe.com/content/help/en/experience-manager-65/developing/components/developer-mode.html)
   1. Apri il pannello a sinistra e passa alla scheda **Test** .
   1. Trova i **Test MyName** generati ed eseguili.

## Passaggi successivi {#next-steps}

Così hai costruito e installato il AEM Project Archetype. E adesso? Beh, l&#39;archetipo è piccolo, ma è costituito da molti esempi di potenti funzioni AEM configurate in base alle best practice consigliate. Questi sono indicatori di come sfruttare queste funzioni nel progetto. Per qualsiasi progetto è probabilmente necessario:

* [Personalizzare i componenti estendendo i componenti core esistenti](/help/developing/customizing.md)
* [Aggiungi altri modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)
* [Adattare la struttura di localizzazione](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/tc-prep.html)
* [Informazioni sul modulo di compilazione front-end](uifrontend.md)
