---
title: Utilizzo di Archetipo progetto AEM
description: Istruzioni d’uso dettagliate per Archetipo progetto AEM
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: a3978d8b-4904-42aa-9ee2-9c1f884327bb
source-git-commit: 017790c5a0e53ba6203a5c3d5ddebcce9c00cb01
workflow-type: ht
source-wordcount: '2193'
ht-degree: 100%

---

# Archetipo progetto AEM {#aem-project-archetype}

L’Archetipo progetto AEM crea un progetto AEM minimo basato sulle best practice di Adobe Experience Manager come punto di partenza per i tuoi progetti AEM. Le proprietà che devono essere fornite quando si utilizza questo archetipo consentono di specificare i nomi di tutte le parti del progetto e di controllare alcune funzioni facoltative.

## Perché utilizzare Archetipo {#why-use-the-archetype}

Utilizzando Archetipo progetto AEM puoi creare un progetto AEM basato sulle best practice con poche sequenze di tasti. Con l’archetipo, tutti i pezzi sono già in posizione in modo che, pur se il progetto risultante è minimo, implementa già tutte le [caratteristiche chiave](#what-you-get) di AEM in modo che tutto quello che devi fare è continuare a sviluppare ed estendere.

Naturalmente, ci sono molti elementi che entrano in un progetto di AEM riuscito, ma l’utilizzo di Archetipo progetto AEM è una solida base ed è vivamente consigliato per qualsiasi progetto AEM.

## Guida introduttiva {#getting-started}

L’archetipo del progetto rende facile iniziare a sviluppare in AEM. Puoi iniziare in diversi modi.

* Esercitazione WKND: per un’ottima introduzione allo sviluppo in AEM, incluso il modo di utilizzare l’archetipo, vedi la [Guida introduttiva ai AEM Sites: esercitazione WKND](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=it) per un esempio pratico che illustra come utilizzare l’archetipo per implementare un semplice progetto.
* Esercitazione eventi WKND: se sei particolarmente interessato allo sviluppo di applicazioni a pagina singola (SPA) in AEM, vedi [l’esercitazione sugli eventi WKND](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=it) dedicata.
* Scarica e inizia da solo! - Puoi scaricare facilmente l’archetipo del progetto corrente disponibile su GitHub e creare il tuo primo progetto [seguendo i semplici passaggi descritti di seguito](#how-to-use-the-archetype).

## Informazioni sull’utilizzo dell’archetipo {#what-you-get}

L’Archetipo progetto AEM è costituito da moduli:

* **[core](core.md)**: è un bundle Java contenente tutte le funzionalità core come servizi OSGi, listener e schedulatori nonché il codice Java relativo ai componenti, come servlet e filtri di richiesta.
* **[it.test](ittests.md)**: integration test basati su Java.
* **[ui.apps](uiapps.md)**: contiene le parti `/apps` e `/etc` del progetto, ad esempio clientlib JS e CSS, componenti e modelli.
* **[ui.content](uicontent.md)**: contiene esempi di contenuto che utilizzando i componenti del modulo ui.apps.
* **ui.config**: contiene le configurazioni OSGi specifiche per la modalità di esecuzione del il progetto.
* **[ui.frontend.general](uifrontend.md)**: **(facoltativo)** contiene gli artefatti necessari per utilizzare il modulo di sviluppo front-end generale basato su Webpack.
* **[ui.frontend.react](uifrontend-react.md)**: **(facoltativo)** contiene gli artefatti necessari quando si utilizza l’archetipo per creare progetti SPA basati su React.
* **[ui.frontend.angular](uifrontend-angular.md)**: **(facoltativo)** contiene gli artefatti necessari quando si utilizza l’archetipo per creare progetti SPA basati su Angular.
* **[ui.tests](uitests.md)**: contiene i test dell’interfaccia utente basati su Selenium.
* **all**: è un singolo pacchetto di contenuti che incorpora tutti i moduli compilati (bundle e pacchetti di contenuti), comprese le dipendenze dei fornitori.
* **analyse**: esegue l’analisi del progetto, che fornisce una convalida aggiuntiva per la distribuzione in AEM as a Cloud Service.

![](/help/assets/archetype-structure.png)

I moduli di Archetipo progetto AEM rappresentati in Maven vengono distribuiti ad AEM come pacchetti di contenuti che rappresentano l’applicazione, il contenuto e i bundle OSGi necessari.

## Come utilizzare l’archetipo {#how-to-use-the-archetype}

Per utilizzare l’archetipo, devi innanzitutto creare un progetto che generi i moduli in una struttura di file locale come [descritto in precedenza](#what-you-get). Come parte della creazione del progetto, è possibile definire una serie di proprietà del progetto, come, ad esempio, nome, versione e così via.

Lo sviluppo del progetto con Maven crea gli artefatti (pacchetti e bundle OSGi) che possono essere distribuiti ad AEM. Ulteriori comandi e profili Maven possono essere utilizzati per distribuire gli artefatti del progetto s un’istanza di AEM.

### Creazione di un progetto {#create-project}

Per iniziare, puoi semplicemente utilizzare l’[estensione AEM Eclipse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/eclipse.html?lang=it) e seguire la procedura guidata Nuovo progetto e scegliere **Esempio di progetto con più moduli in AEM** per utilizzare una versione rilasciata dell’archetipo.

Naturalmente, puoi anche richiamare direttamente Maven.

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

* Imposta `XX` sul [numero di versione](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md) del più recente Archetipo progetto AEM.
* Imposta `aemVersion=cloud` per [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=it);\
   Imposta `aemVersion=6.5.0` per [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) oppure on-premise.
La dipendenza dai Componenti core viene aggiunta solo per le versioni di AEM non cloud, in quanto i Componenti core vengono forniti come OOTB per AEM as a Cloud
Service.
* Imposta `appTitle="My Site"` per definire il titolo del sito web e i gruppi di componenti.
* Imposta `appId="mysite"` per definire l’ID dell’artefatto Maven, i nomi delle cartelle di componenti, configurazione e contenuto nonché i nomi delle librerie client.
* Imposta `groupId="com.mysite"` per definire l’ID gruppo Maven e il pacchetto sorgente Java.
* Ricercare l’elenco delle proprietà disponibili per verificare se è necessario apportare ulteriori modifiche.

>[!NOTE]
>
>È consigliabile aggiungere il profilo `adobe-public` al file Maven `settings.xml` per aggiungere automaticamente repo.adobe.com al processo di sviluppo Maven.
>
>Un esempio di POM (Project Object Model) [è disponibile qui](https://helpx.adobe.com/it/experience-manager/kb/SetUpTheAdobeMavenRepository.html).

### Proprietà {#properties}

Quando crei un progetto utilizzando l’archetipo, sono disponibili le seguenti proprietà.

| Nome | Predefiniti | Descrizione |
|---------------------------|----------------|--------------------|
| `appTitle` |  | Titolo dell’applicazione, verrà utilizzato come titolo del sito web e dei gruppi di componenti (ad esempio, `"My Site"`). |
| `appId` |  | Nome tecnico, verrà utilizzato per i nomi di componenti, cartelle di configurazione e cartelle di contenuto nonché per i nomi delle librerie client (ad esempio, `"mysite"`). |
| `artifactId` | *`${appId}`* | ID artefatto Maven di base (ad esempio, `"mysite"`). |
| `groupId` |  | ID gruppo Maven di base (ad esempio, `"com.mysite"`). |
| `package` | *`${groupId}`* | Pacchetto sorgente Java (ad esempio, `"com.mysite"`). |
| `version` | `1.0-SNAPSHOT` | Versione del progetto (ad esempio, `1.0-SNAPSHOT`). |
| `aemVersion` | `cloud` | Versione AEM di destinazione (può essere `cloud` per [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=it); `6.5.0` o `6.4.4` per [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) oppure on-premise). |
| `sdkVersion` | `latest` | Con `aemVersion=cloud` è possibile specificare una versione del [Software Development Kit (SDK)](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html?lang=it) (ad esempio, `2020.02.2265.20200217T222518Z-200130`). |
| `includeDispatcherConfig` | `y` | Include una configurazione di Dispatcher sia per il cloud che per AMS/on-premise, a seconda del valore di `aemVersion` (può essere `y` o `n`). |
| `frontendModule` | `general` | Include un modulo di sviluppo front-end di Webpack che genera le librerie client (può essere `general` o `none` per i siti normali; può essere `angular` o `react` per una SPA (Single Page App) che implementa l’[editor di SPA](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/headless/spa/editor-overview.html?lang=it)). |
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
| `precompiledScripts` | `n` | Opzione per [precompilare](/help/developing/archetype/precompiled-bundled-scripts.md) gli script lato server da `ui.apps` e allegarli alla build come artefatto bundle secondario nel progetto `ui.apps`. `aemVersion` deve essere impostato su `cloud`. |

>[!NOTE]
>
> Se l’archetipo viene eseguito in modalità interattiva la prima volta, le proprietà con valori predefiniti non possono essere modificate (per ulteriori informazioni, vedi [ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308)). Il valore può essere modificato quando la conferma della proprietà alla fine viene negata e il questionario viene ripetuto oppure fornendo il parametro nella riga di comando (ad esempio, `-DoptionIncludeExamples=n`).

>[!NOTE]
>
>Se l’esecuzione è su Windows e stai generando la configurazione di Dispatcher, l’esecuzione deve avvenire da un prompt dei comandi con privilegi elevati oppure nel Sottosistema Windows per Linux (vedi il [problema 329](https://github.com/adobe/aem-project-archetype/issues/329)).

### Profili {#profiles}

Il progetto Maven generato supporta diversi profili di distribuzione durante l’esecuzione del comando `mvn install`.

| ID profilo | Descrizione |
| --------------------------|------------------------------|
| `autoInstallBundle` | Installa il bundle core con maven-sling-plugin nella console Felix |
| `autoInstallPackage` | Installa i pacchetti di contenuti ui.content e ui.apps con content-package-maven-plugin nel gestore di pacchetti per impostare l’istanza Autore predefinita su localhost, porta 4502. È possibile modificare il nome host e la porta con le proprietà `aem.host` e `aem.port` definite dall’utente. |
| `autoInstallPackagePublish` | Installa i pacchetti di contenuti ui.content e ui.apps con content-package-maven-plugin nel gestore di pacchetti per impostare l’istanza Publish predefinita su localhost, porta 4503. È possibile modificare il nome host e la porta con le proprietà `aem.host` e `aem.port` definite dall’utente. |
| `autoInstallSinglePackage` | Installa il pacchetto di contenuti `all` con content-package-maven-plugin nel gestore di pacchetti per impostare l’istanza Autore predefinita su localhost, porta 4502. È possibile modificare il nome host e la porta con le proprietà `aem.host` e `aem.port` definite dall’utente. |
| `autoInstallSinglePackagePublish` | Installa il pacchetto di contenuti `all` con content-package-maven-plugin nel gestore di pacchetti per impostare l’istanza Publish predefinita su localhost, porta 4503. È possibile modificare il nome host e la porta con le proprietà `aem.host` e `aem.port` definite dall’utente. |
| `integrationTests` | Esegue gli integration test forniti sull’istanza di AEM (solo per la fase `verify`) |
| `precompiledScripts` | Viene definito automaticamente quando il progetto viene generato con la proprietà `precompiledScripts` impostata su `y`. Il profilo è attivo per impostazione predefinita e genera un bundle OSGi all’interno di `ui.apps` con gli script precompilati, che verranno inclusi nel pacchetto di contenuti `all`. Il profilo può essere disabilitato con `-DskipScriptPrecompilation=true`. |

### Sviluppo e installazione {#building-and-installing}

Per sviluppare tutti i moduli eseguiti nella directory principale del progetto, utilizza il seguente comando Maven.

```shell
mvn clean install
```

Se hai un’istanza di AEM in esecuzione, puoi sviluppare e creare un pacchetto dell’l’intero progetto e distribuirlo ad AEM con il seguente comando Maven.

```shell
mvn clean install -PautoInstallPackage
```

Per distribuirlo a un’istanza Publish, esegui questo comando.

```shell
mvn clean install -PautoInstallPackagePublish
```

In alternativa, per distribuirlo a un’istanza Publish, esegui questo comando.

```shell
mvn clean install -PautoInstallPackage -Daem.port=4503
```

Per distribuire solo il bundle all’autore, esegui questo comando.

```shell
mvn clean install -PautoInstallBundle
```

## POM (Project Object Model) padre {#parent-pom}

Il file `pom.xml` nella directory principale del progetto (`<src-directory>/<project>/pom.xml`) è noto come POM padre e gestisce la struttura del progetto nonché le dipendenze e alcune proprietà globali del progetto stesso.

### Proprietà globali del progetto {#global-properties}

La sezione `<properties>` del POM padre definisce diverse proprietà globali importanti per la distribuzione del progetto a un’istanza di AEM, come nome utente/password, nome host/porta, ecc.

Queste proprietà sono configurate per la distribuzione a un’istanza di AEM locale, in quanto si tratta dello sviluppo più comune utilizzato dagli sviluppatori. Tieni presente che esistono anche proprietà configurate per la distribuzione a un’istanza Autore e un’istanza Publish. Qui vengono impostate anche le credenziali per l’autenticazione nell’istanza di AEM. Vengono utilizzate le credenziali admin:admin predefinite.

Queste proprietà sono configurate in modo che possano essere ignorate durante la distribuzione in ambienti di livello superiore. In questo modo, i file POM non devono essere modificati, ma le variabili come `aem.host` e `sling.password` possono essere ignorate inserendo argomenti nella riga di comando:

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### Struttura modulare {#module-structure}

La sezione `<modules>` del POM padre definisce i moduli che verranno sviluppati nel progetto. Per impostazione predefinita, il progetto sviluppa [i moduli standard precedentemente definiti](#what-you-get): core, ui.apps, ui.content, ui.tests e it.launcher. Man mano che un progetto evolve, si potranno sempre aggiungere altri moduli.

### Dipendenze {#dependencies}

La sezione `<dependencyManagement>` del POM padre definisce tutte le dipendenze e le versioni delle API utilizzate nel progetto. Le versioni devono essere gestite nel POM padre. I sottomoduli, come core e ui.apps, non devono includere informazioni sulle versioni.

#### Uber-Jar {#uber-jar}

Una delle dipendenze chiave è [AEM Java API Jar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html?lang=it). Ciò includerà tutte le API di AEM in sola dipendenza per la versione di AEM.

>[!NOTE]
>
>Come best practice, aggiorna la versione di uber-jar in modo che corrisponda alla versione di destinazione di AEM. Ad esempio, se prevedi di distribuire ad AEM 6.4, devi aggiornare la versione di uber-jar alla 6.4.0.

#### Componenti core {#core-components}

L’Archetipo progetto AEM, ovviamente, utilizza i Componenti core.

I Componenti core vengono automaticamente installati in AEM nella modalità di esecuzione predefinita e vengono utilizzati dall’esempio di sito WKND. In [modalità di esecuzione per la produzione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=it#runmodes) (`nosamplecontent`) i Componenti core non sono disponibili.

Pertanto, per utilizzare i Componenti core in tutte le implementazioni, è consigliabile includerli come parte del progetto Maven.

>[!NOTE]
>
>Ogni versione dei Componenti core è generalmente seguita da una versione di Archetipo progetto AEM, in modo che l’archetipo più recente utilizzi la versione più recente dei Componenti core.
>
>Tuttavia, una nuova versione dell’archetipo potrebbe non seguire direttamente una nuova versione dei Componenti core, pertanto potrebbe essere opportuno aggiornare la dipendenza dai Componenti core alla versione più recente.

>[!NOTE]
>
>I core.wcm.components.examples sono un set di esempi di pagine che illustrano esempi di Componenti core. Come best practice, quando distribuisci un progetto per la produzione, dovresti rimuovere questa dipendenza e l’inclusione di pacchetti secondari.

## Test {#testing}

Il progetto contiene tre livelli di test e, poiché esistono diversi tipi di test, essi vengono eseguiti in modi diversi o in posizioni diverse.

* Test unità in core: si tratta del classico test unità del codice contenuto nel bundle. Per effettuare il test, esegui:
   * `mvn clean test`
* Integration test lato server: questi test vengono eseguiti come test unità in ambiente AEM, ad esempio sul server AEM. Per effettuare il test, esegui:
   * `mvn clean verify -PintegrationTests`
* Test di Hobbes.js lato client: si tratta di test lato browser basati su JavaScript per verificare il comportamento del browser. Per effettuare il test:
   1. Carica AEM nel browser come quando crei una pagina.
   1. Apri la pagina in modalità [Sviluppatore](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/developer-mode.html?lang=it)
   1. Apri il pannello a sinistra e passa alla scheda **Test**.
   1. Trova i **Test MyName** generati ed eseguili.

## Passaggi successivi {#next-steps}

In questo modo, hai sviluppato e installato Archetipo progetto AEM. E adesso? Bene, l’archetipo è piccolo, ma è costituito da molti esempi di efficienti funzioni AEM configurate in base alle best practice consigliate. Utilizzali come indicatori di come sfruttare queste funzioni nel progetto. Per qualsiasi progetto è probabilmente necessario:

* [Personalizzare i componenti estendendo i Componenti core esistenti](/help/developing/customizing.md)
* [Aggiungere altri modelli](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it)
* [Adattare la struttura di localizzazione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=it)
* [Informazioni sul modulo di sviluppo front-end](uifrontend.md)
