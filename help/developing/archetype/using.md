---
title: Utilizzo del tipo di archivio AEM progetti
description: Istruzioni d'uso dettagliate per AEM Project Archetype
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '2057'
ht-degree: 1%

---


# AEM Project Archetype {#aem-project-archetype}

AEM Project Archetype crea un progetto Adobe Experience Manager minimale basato sulle best practice come punto di partenza per i vostri progetti AEM. Le proprietà che devono essere fornite quando si utilizza questo archetype consentono di specificare i nomi di tutte le parti del progetto e di controllare alcune funzioni facoltative.

## Perché utilizzare Archetype {#why-use-the-archetype}

Utilizzando AEM Project Archetype (Tipo archivio progetti) si inizia a creare un progetto AEM basato su best practice con poche sequenze di tasti. Utilizzando l&#39;archetype, tutti i pezzi saranno già in atto in modo che mentre il progetto risultante è minimo, esso già implementa tutte le caratteristiche [](#what-you-get) chiave di AEM in modo che tutto quello che dovete fare è costruire sopra e estendere.

Naturalmente ci sono molti elementi che entrano in un progetto di AEM di successo, ma l&#39;utilizzo AEM Project Archetype è una solida base ed è fortemente consigliato per qualsiasi progetto AEM.

## Guida introduttiva {#getting-started}

L&#39;archetipo del progetto rende facile iniziare a sviluppare su AEM. I primi passi possono essere effettuati in diversi modi.

* Esercitazione WKND - Per un&#39;ottima introduzione allo sviluppo di AEM che include come sfruttare l&#39;archetype, vedere la [Guida introduttiva  AEM Sites - Esercitazione](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) WKND per un esempio pratico che vi guida attraverso l&#39;utilizzo dell&#39;archetype per implementare un progetto semplice.
* Esercitazione sugli eventi WKND - Se siete particolarmente interessati allo sviluppo di applicazioni a pagina singola (SPA) su AEM, controllate l&#39;esercitazione [dedicata agli eventi](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)WKND.
* Scarica e inizia da solo! - È possibile scaricare facilmente l&#39;archetipo di progetto corrente disponibile su GitHub e creare il primo progetto [seguendo i semplici passaggi indicati di seguito](#how-to-use-the-archetype).

## Che cosa si ottiene usando Archetype {#what-you-get}

AEM Archetype è composto da moduli:

* **[core](core.md)**: è un pacchetto Java contenente tutte le funzionalità di base come servizi OSGi, listener e pianificatori, nonché il codice Java relativo ai componenti, come servlet e filtri di richiesta.
* **[ui.apps](uiapps.md)**: contiene le `/apps` e `/etc` parti del progetto, ad esempio clientlibs JS e CSS, componenti, modelli, configurazioni specifiche per la modalità di esecuzione e test Hobbes.
* **[ui.content](uicontent.md)**: contiene contenuto di esempio utilizzando i componenti del modulo ui.apps.
* **[ui.test](uitests.md)**: è un pacchetto Java contenente test JUnit eseguiti sul lato server. Questo bundle non deve essere distribuito in produzione.
* **ui.launcher**: contiene codice colla che distribuisce il bundle ui.test (e i bundle dipendenti) al server e attiva l&#39;esecuzione JUnit remota.
* **[ui.frontend.general](uifrontend.md)**: **(facoltativo)** contiene gli artefatti necessari per utilizzare il modulo di build front-end basato su Webpack generale.
* **[ui.frontend.response](uifrontend-react.md)**: **(Facoltativo)** contiene gli artefatti necessari per creare un progetto SPA basato su React utilizzando archetype.
* **[ui.frontend.angular](uifrontend-angular.md)**: **(facoltativo)** contiene gli artefatti necessari per creare un progetto SPA basato su Angular utilizzando l’archetipo.

![](/help/assets/archetype-structure.png)

I moduli di Archetype AEM rappresentati in Maven sono distribuiti per AEM come pacchetti di contenuto che rappresentano l&#39;applicazione, il contenuto e i pacchetti OSGi necessari.

## Come utilizzare Archetype {#how-to-use-the-archetype}

Per utilizzare l&#39;archetipo, è innanzitutto necessario creare un progetto, che genera i moduli in una struttura di file locale come [precedentemente descritto](#what-you-get). Durante la generazione del progetto, è possibile definire diverse proprietà per il progetto, ad esempio nome, versione e così via.

La creazione del progetto con Maven crea gli artefatti (pacchetti e pacchetti OSGi) che possono essere distribuiti per AEM. Altri comandi e profili Maven possono essere utilizzati per distribuire gli artifact del progetto a un&#39;istanza AEM.

### Creazione di un progetto  {#create-project}

Per iniziare, potete semplicemente utilizzare l&#39;estensione [](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/aem-eclipse.html) AEM Eclipse e seguire la procedura guidata New Project (Nuovo progetto) e scegliere **AEM Sample Multi-Module Project** per utilizzare una versione rilasciata dell&#39;archetipo.

Naturalmente si può anche invocare direttamente Maven.

```
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.granite.archetypes \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D aemVersion=cloud \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
 -D frontendModule=general \
 -D includeExamples=n
```

* Impostate `XX` il numero [di](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md) versione dell&#39;ultimo tipo di archivio AEM progetto.
* Impostare `aemVersion=cloud` per [AEM come Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   Impostato `aemVersion=6.5.0` per [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)o locale.
La dipendenza Componenti di base viene aggiunta solo per le versioni Aem non cloud, in quanto i Componenti di base vengono forniti OOTB per AEM come servizio Cloud.
* Regolate `appTitle="My Site"` per definire il titolo del sito Web e i gruppi di componenti.
* Regolate `appId="mysite"` per definire il Maven artifactId, i nomi delle cartelle dei componenti, delle configurazioni e dei contenuti, nonché i nomi delle librerie dei client.
* Regola `groupId="com.mysite"` per definire il Maven groupId e il pacchetto di origine Java.
* Consultate l’elenco delle proprietà disponibili per verificare se vi sono altre proprietà da regolare.

>[!NOTE]
>
>È buona norma aggiungere il `adobe-public` profilo al file Maven `settings.xml` per aggiungere automaticamente repo.adobe.com al processo di creazione di maven.
>
>Un esempio di POM [è disponibile qui](https://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html).

### Proprietà {#properties}

Le seguenti proprietà sono disponibili quando si crea un progetto utilizzando archetype.

| Nome | Predefiniti | Descrizione |
--------------------------|----------------|--------------------
| `appTitle` |  | Titolo applicazione, verrà utilizzato per il titolo del sito Web e i gruppi di componenti (ad es. `"My Site"`). |
| `appId` |  | Nome tecnico, verrà utilizzato per i nomi dei componenti, delle cartelle di configurazione e di contenuto, nonché per i nomi delle librerie client (ad esempio `"mysite"`). |
| `artifactId` | *`${appId}`* | ID artifact di base Maven (ad es. `"mysite"`). |
| `groupId` |  | ID gruppo Base Paradiso (ad es. `"com.mysite"`). |
| `package` | *`${groupId}`* | Pacchetto di origine Java (ad esempio `"com.mysite"`). |
| `version` | `1.0-SNAPSHOT` | Versione del progetto (ad es. `1.0-SNAPSHOT`). |
| `aemVersion` | `6.5.0` | AEM versione di destinazione (può essere `cloud` AEM come [Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html); oppure `6.5.0`, `6.4.4` per i servizi [gestiti](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) Adobe o locali). |
| `sdkVersion` | `latest` | Quando è possibile specificare `aemVersion=cloud` una versione [SDK](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) (ad es. `2020.02.2265.20200217T222518Z-200130`). |
| `includeDispatcherConfig` | `y` | Include una configurazione dispatcher sia per il cloud che per AMS/locale, a seconda del valore di `aemVersion` (può essere `y` o `n`). |
| `frontendModule` | `none` | Include un modulo di generazione frontale Webpack che genera le librerie client (può essere `general` o `none` per siti regolari); può essere `angular` o `react` per un&#39;app a pagina singola che implementa l&#39;Editor [](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/introduction.html)SPA). |
| `languageCountry` | `en_us` | Lingua e codice del paese da cui creare la struttura del contenuto (ad esempio `en_us`). |
| `singleCountry` | `y` | Include una struttura del contenuto master del linguaggio (può essere `y`o `n`). |
| `includeExamples` | `y` | Include un sito di esempio della libreria [di](https://www.aemcomponents.dev/) componenti (può essere `y`o `n`). |
| `includeErrorHandler` | `n` | Include una pagina di risposta personalizzata 404 che sarà globale per l&#39;intera istanza (può essere `y` o `n`). |

>[!NOTE]
>
> Se l&#39;archetype viene eseguito in modalità interattiva la prima volta, le proprietà con valori predefiniti non possono essere modificate (per ulteriori dettagli, vedere [ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) ). Il valore può essere modificato quando la conferma della proprietà alla fine viene negata e il questionario viene ripetuto, o passando il parametro nella riga di comando (ad es. `-DoptionIncludeExamples=n`).

>[!NOTE]
>
>Quando si esegue in Windows e si genera la configurazione del dispatcher, è necessario eseguire un prompt di comando elevato o il sottosistema Windows per Linux (vedere [il numero 329](https://github.com/adobe/aem-project-archetype/issues/329)).

### Profili {#profiles}

Il progetto generato maven supporta profili di distribuzione diversi durante l&#39;esecuzione `mvn install`.

| ID profilo | Descrizione |
--------------------------|------------------------------
| `autoInstallBundle` | Installare il pacchetto di base con il plugin maven-sling alla console Felix |
| `autoInstallPackage` | Installate il pacchetto di contenuti ui.content e ui.apps con il plug-in content-package-maven-plug in nel gestore pacchetti per impostare l&#39;istanza di creazione predefinita su localhost, porta 4502. Nome host e porta possono essere modificati con le proprietà definite `aem.host` e `aem.port` dall&#39;utente. |
| `autoInstallPackagePublish` | Installate il pacchetto di contenuto ui.content e ui.apps con il plug-in content-package-maven-in nel gestore pacchetti per impostare l&#39;istanza di pubblicazione predefinita su localhost, porta 4503. Nome host e porta possono essere modificati con le proprietà definite `aem.host` e `aem.port` dall&#39;utente. |
| `autoInstallSinglePackage` | Installate il pacchetto di `all` contenuto con il plug-in content-package-maven al gestore pacchetti per impostare l’istanza di creazione predefinita su localhost, porta 4502. Nome host e porta possono essere modificati con le proprietà definite `aem.host` e `aem.port` dall&#39;utente. |
| `autoInstallSinglePackagePublish` | Installate il pacchetto di `all` contenuto con il plug-in content-package-maven al gestore pacchetti per impostare l’istanza di pubblicazione predefinita su localhost, porta 4503. Nome host e porta possono essere modificati con le proprietà definite `aem.host` e `aem.port` dall&#39;utente. |
| `integrationTests` | Esegue i test di integrazione forniti sull&#39;istanza AEM (solo per la `verify` fase) |

### Creazione e installazione {#building-and-installing}

Per creare tutti i moduli eseguiti nella directory principale del progetto, utilizzate il seguente comando Maven.

```
mvn clean install
```

Se disponete di un&#39;istanza AEM in esecuzione, potete creare e creare l&#39;intero progetto e distribuirlo in AEM con il seguente comando Maven.

```
mvn clean install -PautoInstallPackage
```

Per distribuirlo in un&#39;istanza di pubblicazione, eseguite questo comando.

```
mvn clean install -PautoInstallPackagePublish
```

In alternativa, per distribuire in un&#39;istanza di pubblicazione, eseguite questo comando.

```
mvn clean install -PautoInstallPackage -Daem.port=4503
```

Oppure, per distribuire solo il bundle all&#39;autore, eseguite questo comando.

```
mvn clean install -PautoInstallBundle
```

## POM principale {#parent-pom}

Il `pom.xml` livello principale del progetto (`<src-directory>/<project>/pom.xml`) è noto come POM padre e guida la struttura del progetto, oltre a gestire le dipendenze e alcune proprietà globali del progetto.

### Proprietà progetto globale {#global-properties}

La `<properties>` sezione del POM principale definisce diverse proprietà globali importanti per la distribuzione del progetto in un’istanza AEM come nome utente/password, nome host/porta, ecc.

Queste proprietà sono configurate per la distribuzione in un&#39;istanza AEM locale, in quanto si tratta della build più comune che gli sviluppatori faranno. Notate che esistono proprietà da distribuire a un’istanza di creazione e a un’istanza di pubblicazione. Anche in questo caso le credenziali sono impostate per l&#39;autenticazione con l&#39;istanza AEM. Vengono utilizzate le credenziali admin:admin predefinite.

Queste proprietà sono configurate in modo che possano essere sostituite durante la distribuzione in ambienti di livello superiore. In questo modo i file POM non devono essere modificati, ma le variabili come `aem.host` e `sling.password` possono essere sostituite tramite gli argomenti della riga di comando:

```
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### Struttura del modulo {#module-structure}

La `<modules>` sezione del POM padre definisce i moduli che il progetto genererà. Per impostazione predefinita, il progetto crea [i moduli standard precedentemente definiti](#what-you-get): core, ui.apps, ui.content, ui.test e it.launcher. È sempre possibile aggiungere più moduli man mano che un progetto si evolve.

### Dipendenze {#dependencies}

La `<dependencyManagement>` sezione del POM principale definisce tutte le dipendenze e le versioni delle API utilizzate nel progetto. Le versioni devono essere gestite nel POM principale. I sottomoduli come core e ui.apps non devono includere informazioni sulle versioni.

#### Uber-Jar {#uber-jar}

Una delle dipendenze chiave è il [AEM uber-jar](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/ht-projects-maven.html#ExperienceManagerAPIDependencies). Questo includerà tutte le API AEM con una sola voce di dipendenza per la versione di AEM.

>[!NOTE]
>
>È consigliabile aggiornare la versione uber-jar in modo che corrisponda alla versione di destinazione di AEM. Ad esempio, se pianificate di distribuire a AEM 6.4, aggiornate la versione di uber-jar a 6.4.0.

#### Componenti core {#core-components}

Il AEM Project Archetype, ovviamente, sfrutta i componenti core.

I componenti core vengono installati automaticamente in AEM in modalità di esecuzione predefinita e utilizzati dal sito WKND di esempio. In una modalità [di esecuzione](https://docs.adobe.com/content/help/en/experience-manager-65/administering/security/production-ready.html) di produzione (`nosamplecontent`) i componenti core non sono disponibili.

Pertanto, al fine di sfruttare i componenti core in tutte le distribuzioni, è consigliabile includerli come parte del progetto Maven.

>[!NOTE]
>
>A ogni rilascio dei componenti core segue generalmente una release dell’archivio AEM progetti, in modo che l’ultimo archetipo utilizzi la versione più recente dei componenti core.
>
>Tuttavia, una nuova versione dell&#39;archetipo potrebbe non seguire direttamente una nuova versione dei componenti core, pertanto è possibile aggiornare la dipendenza dai componenti core alla versione più recente.

>[!NOTE]
>
>Gli esempi core.wcm.components.example sono una serie di pagine di esempio che illustrano esempi dei componenti core. Come procedura ottimale, quando si distribuisce un progetto per la produzione è necessario rimuovere questa dipendenza e l&#39;inclusione del sottopacchetto.

## Test {#testing}

Il progetto contiene tre livelli di test e, poiché sono tipi diversi di test, vengono eseguiti in modi diversi o in luoghi diversi.

* Prova di unità nel nucleo: Questo mostra il classico unit testing del codice contenuto nel bundle. Per eseguire il test, eseguire:
   * `mvn clean test`
* Test di integrazione lato server: Questi test vengono eseguiti come unità nell&#39;ambiente AEM, ad esempio sul server AEM. Per eseguire il test, eseguire:
   * `mvn clean verify -PintegrationTests`
* Test Hobbes.js lato client: Si tratta di test basati su JavaScript sul browser per verificare il comportamento sul lato browser. Per eseguire il test:
   1. Caricate AEM nel browser come fareste per creare una pagina.
   1. Open the page in [Developer mode](https://docs.adobe.com/content/help/en/experience-manager-65/developing/components/developer-mode.html)
   1. Aprite il pannello a sinistra e passate alla scheda **Test** .
   1. Trovare i test **MyName generati** ed eseguirli.

## Passaggi successivi {#next-steps}

Quindi avete costruito e installato il AEM Project Archetype. E adesso? Beh, l&#39;archetipo è piccolo, ma è costituito da molti esempi di potenti funzioni AEM configurate in base alle best practice consigliate. Utilizzate queste opzioni per indicare come sfruttare queste funzionalità nel progetto. Per qualsiasi progetto è probabilmente necessario:

* [Personalizzare i componenti estendendo i componenti core esistenti](/help/developing/customizing.md)
* [Aggiungere altri modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)
* [Adattare la struttura di localizzazione](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/tc-prep.html)
* [Informazioni sul modulo di build front-end](uifrontend.md)
