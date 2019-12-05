---
title: Archetipo progetto AEM
seo-title: Archetipo progetto AEM
description: Un modello di progetto per le applicazioni basate su AEM
seo-description: Un modello di progetto per le applicazioni basate su AEM
contentOwner: bohnert
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: 0f84eb6d52b9d6d76a4347d371367acf3d34e58e

---


# Archetipo progetto AEM {#aem-project-archetype}

AEM Project Archetype crea un progetto Adobe Experience Manager minimo basato su best practice, come punto di partenza per i progetti AEM. Le proprietà che devono essere fornite quando si utilizza questo archetype consentono di specificare i nomi di tutte le parti del progetto e di controllare alcune funzioni facoltative.

>[!NOTE]
>
>L’ultimo tipo di archivio del progetto AEM e i dettagli tecnici completi [sono disponibili su GitHub](https://github.com/adobe/aem-project-archetype).

>[!NOTE]
>
>Consulta la [Guida introduttiva ad AEM Sites - Esercitazione](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) WKND nella documentazione di AEM per un esempio pratico che illustra come utilizzare l’archetipo per implementare un progetto semplice.

## Funzioni {#features}

L’archetype offre diverse funzioni che rappresentano un punto di partenza conveniente per i nuovi progetti AEM:

* Pagine in inglese e francese con contenuto di esempio
* Un modello di contenuto basato sulla funzione di modello modificabile con criteri di contenuto di esempio
* Componente pagina basato sul componente core della pagina [AEM](page.md)
* Esempi di componenti di contenuto implementati con il pattern di proxy consigliato e un componente personalizzato di esempio per il mondo dell’helloworld basati su componenti [core di](introduction.md)AEM.
* Esempi di componenti [modulo](form-container.md)
* Configurazioni per emulatori dispositivo, configurazione tramite trascinamento e internazionalizzazione
* Librerie client che seguono le convenzioni di denominazione di BEM e gli stili specifici dei componenti
* Esempi di bundle con modelli di esempio, servelet, filtri e pianificatori
* Unità, integrazione e test sul lato client

## Perché utilizzare Archetype {#why-use-the-archetype}

L’utilizzo di AEM Project Archetype consente di creare un progetto AEM basato su procedure ottimali con pochi tasti. Utilizzando l’archetipo, tutti i pezzi saranno già in funzione in modo che, mentre il progetto risultante è minimo, implementa già tutte le caratteristiche [](#features) chiave di AEM, in modo che tutto ciò che devi fare è costruire sopra ed estendere.

Naturalmente sono molti gli elementi che entrano in un progetto AEM di successo, ma l’utilizzo di AEM Project Archetype è una solida base ed è vivamente consigliato per qualsiasi progetto AEM.

## Che cosa si ottiene usando Archetype {#what-you-get}

AEM Archetype è composto da moduli:

* **[core](core.md)**: è un pacchetto Java contenente tutte le funzionalità di base come servizi OSGi, listener e pianificatori, nonché il codice Java relativo ai componenti, come servlet e filtri di richiesta.
* **[ui.apps](uiapps.md)**: contiene le `/apps` e `/etc` parti del progetto, ad esempio clientlibs JS e CSS, componenti, modelli, configurazioni specifiche per la modalità di esecuzione e test Hobbes.
* **[ui.content](uicontent.md)**: contiene contenuto di esempio utilizzando i componenti del modulo ui.apps.
* **ui.test**: è un pacchetto Java contenente test JUnit eseguiti sul lato server. Questo bundle non deve essere distribuito in produzione.
* **ui.launcher**: contiene codice colla che distribuisce il bundle ui.test (e i bundle dipendenti) al server e attiva l'esecuzione JUnit remota.
* **[ui.frontend](uifrontend.md)**: **(facoltativo)** contiene gli artefatti necessari per utilizzare il modulo di build front-end basato su Webpack.

![](assets/archetype-structure.png)

I moduli di AEM Archetype rappresentati in Maven sono distribuiti in AEM come pacchetti di contenuto che rappresentano l’applicazione, il contenuto e i bundle OSGi necessari.

## Requisiti {#requirements}

La versione corrente di archetype presenta i seguenti requisiti:

* Adobe Experience Manager 6.3.3.0 o versione successiva
* Apache Maven (3.3.9 o successivo)
* Archivio Adobe Public Maven nelle impostazioni Maven. Consulta questo articolo della [Knowledge Base per ulteriori dettagli](https://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html).

Per un elenco delle versioni AEM supportate delle versioni precedenti di archetipo, consultate le versioni [AEM](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md)storiche supportate.

## Come utilizzare Archetype {#how-to-use-the-archetype}

Per utilizzare l'archetipo, è innanzitutto necessario creare un progetto, che genera i moduli in una struttura di file locale come [precedentemente descritto](#what-you-get). Durante la generazione del progetto, è possibile definire diverse proprietà per il progetto, ad esempio nome, versione e così via.

La creazione del progetto con Maven crea gli artefatti (pacchetti e pacchetti OSGi) che possono essere distribuiti in AEM. Per distribuire gli artifact del progetto a un’istanza di AEM è possibile utilizzare ulteriori comandi e profili Maven.

### Creazione di un progetto {#create-project}

Per iniziare, puoi semplicemente utilizzare l’estensione [](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/aem-eclipse.html) AEM Eclipse e seguire la procedura guidata Nuovo progetto e scegliere **AEM Sample Multi-Module Project** per utilizzare una versione rilasciata dell’archetipo.

Naturalmente si può anche invocare direttamente Maven.

```
mvn archetype:generate \
 -DarchetypeGroupId=com.adobe.granite.archetypes \
 -DarchetypeArtifactId=aem-project-archetype \
 -DarchetypeVersion=XX
```

Dove `XX` è il numero [di](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md) versione dell’ultimo tipo di archivio progetti AEM.

>[!NOTE]
>
>È buona norma aggiungere il `adobe-public` profilo al file Maven `settings.xml` per aggiungere automaticamente repo.adobe.com al processo di creazione di maven.
>
>Un esempio di POM [è disponibile qui](https://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html).

### Proprietà {#properties}

Le seguenti proprietà sono disponibili quando si crea un progetto utilizzando archetype.

| Nome | Predefiniti | Descrizione |
----------------------------|---------|--------------------
| `groupId` |  | Base Paradiso `groupId` |
| `artifactId` |  | Base Maven ArtifactId |
| `version` |  | Versione |
| `package` |  | Pacchetto origine Java |
| `appsFolderName` |  | `/apps` nome cartella |
| `artifactName` |  | Nome progetto Maven |
| `componentGroupName` |  | Nome gruppo di componenti AEM |
| `contentFolderName` |  | `/content` nome cartella |
| `confFolderName` |  | `/conf` nome cartella |
| `cssId` |  | prefisso utilizzato in css generato |
| `packageGroup` |  | Nome gruppo di pacchetti di contenuti |
| `siteName` |  | Nome del sito AEM |
| `optionAemVersion` | 6.5.0 | Versione di destinazione AEM |
| `optionIncludeExamples` | y | Includi un sito di esempio nella libreria [di](http://opensource.adobe.com/aem-core-wcm-components/library.html) componenti |
| `optionIncludeErrorHandler` | n | Includi una pagina di risposta personalizzata 404 |
| `optionIncludeFrontendModule` | n | [Includere un modulo front-end dedicato](uifrontend.md) |

>[!NOTE]
> Se l'archetype viene eseguito in modalità interattiva la prima volta, le proprietà con valori predefiniti non possono essere modificate (per ulteriori dettagli, vedere [ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) ). Il valore può essere modificato quando la conferma della proprietà alla fine viene negata e il questionario viene ripetuto, o passando il parametro nella riga di comando (ad es. `-DoptionIncludeExamples=n`).

### Profili {#profiles}

Il progetto generato maven supporta profili di distribuzione diversi durante l'esecuzione `mvn install`.

| ID profilo | Descrizione |
--------------------------|------------------------------
| `autoInstallBundle` | Installa il pacchetto di base con il plugin maven-sling in OSGi |
| `autoInstallPackage` | Installa il pacchetto di contenuto ui.content e ui.apps con il plug-in content-package-maven-in nel gestore pacchetti fino all'istanza di creazione predefinita sull'host locale, porta 4502. Il nome host e la porta possono essere modificati con le proprietà `aem.host` e definite dall' `aem.port` utente. |
| `autoInstallPackagePublish` | Installate il pacchetto di contenuto ui.content e ui.apps con il plug-in content-package-maven-in nel gestore pacchetti per impostare l'istanza di pubblicazione predefinita su localhost, porta 4503. Il nome host e la porta possono essere modificati con le proprietà `aem.host` e definite dall' `aem.port` utente. |
| `integrationTests` | Esegue i test di integrazione forniti sull’istanza di AEM (solo per la `verify` fase) |

### Creazione e installazione {#building-and-installing}

Per creare tutti i moduli eseguiti nella directory principale del progetto, utilizzate il seguente comando Maven.

```
mvn clean install
```

Se disponete di un’istanza AEM in esecuzione, potete creare e creare un pacchetto per l’intero progetto e distribuirlo in AEM con il seguente comando Maven.

```
mvn clean install -PautoInstallPackage
```

Per distribuirlo in un'istanza pubblicata, eseguite questo comando.

```
mvn clean install -PautoInstallPackagePublish
```

In alternativa, per distribuire in un'istanza di pubblicazione, eseguite questo comando.

```
mvn clean install -PautoInstallPackage -Daem.port=4503
```

Oppure, per distribuire solo il bundle all'autore, eseguite questo comando.

```
mvn clean install -PautoInstallBundle
```

## POM principale {#parent-pom}

Il `pom.xml` livello principale del progetto (`<src-directory>/<project>/pom.xml`) è noto come POM padre e guida la struttura del progetto, oltre a gestire le dipendenze e alcune proprietà globali del progetto.

### Proprietà progetto globale {#global-properties}

La `<properties>` sezione del POM principale definisce diverse proprietà globali importanti per la distribuzione del progetto in un’istanza di AEM, come nome utente/password, nome host/porta, ecc.

Queste proprietà sono configurate per la distribuzione in un’istanza AEM locale, in quanto si tratta della build più comune che gli sviluppatori faranno. Notate che esistono proprietà da distribuire a un’istanza di creazione e a un’istanza di pubblicazione. Anche in questo caso le credenziali sono impostate per l’autenticazione con l’istanza AEM. Vengono utilizzate le credenziali admin:admin predefinite.

Queste proprietà sono configurate in modo che possano essere sostituite durante la distribuzione in ambienti di livello superiore. In questo modo i file POM non devono essere modificati, ma le variabili come `aem.host` e `sling.password` possono essere sostituite tramite gli argomenti della riga di comando:

````
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
````

### Struttura del modulo {#module-structure}

La `<modules>` sezione del POM padre definisce i moduli che il progetto genererà. Per impostazione predefinita, il progetto crea [i moduli standard precedentemente definiti](#what-you-get): core, ui.apps, ui.content, ui.test e it.launcher. È sempre possibile aggiungere più moduli con l'evoluzione di un progetto.

### Dipendenze {#dependencies}

La `<dependencyManagement>` sezione del POM principale definisce tutte le dipendenze e le versioni delle API utilizzate nel progetto. Le versioni devono essere gestite nel POM principale. I sottomoduli come core e ui.apps non devono includere informazioni sulle versioni.

#### Uber-Jar {#uber-jar}

Una delle dipendenze chiave è l’URL di [AEM](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/ht-projects-maven.html#ExperienceManagerAPIDependencies). Questo includerà tutte le API AEM con una sola voce di dipendenza per la versione di AEM.

>[!NOTE]
>
>È consigliabile aggiornare la versione uber-jar in modo che corrisponda alla versione di destinazione di AEM. Ad esempio, se intendi distribuire in AEM 6.4 devi aggiornare la versione di uber-jar a 6.4.0.

#### Componenti core {#core-components}

Il tipo di archivio dei progetti AEM sfrutta ovviamente i componenti core.

I componenti core vengono installati automaticamente in AEM in modalità di esecuzione predefinita e utilizzati dal sito Web di esempio We.Retail. In una modalità [di esecuzione](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/production-ready.html) di produzione (`nosamplecontent`) i componenti core non sono disponibili.

Pertanto, al fine di sfruttare i componenti core in tutte le distribuzioni, è consigliabile includerli come parte del progetto Maven.

>[!NOTE]
>
>A ogni versione dei componenti core segue generalmente una release dell’archivio dei progetti AEM, in modo che l’ultimo archetipo utilizzi la versione più recente dei componenti core.
>
>Tuttavia, una nuova versione dell'archetipo potrebbe non seguire direttamente una nuova versione dei componenti core, pertanto è possibile aggiornare la dipendenza dai componenti core alla versione più recente.

>[!NOTE]
>
>Gli esempi core.wcm.components.example sono una serie di pagine di esempio che illustrano esempi dei componenti core. Come procedura ottimale, quando si distribuisce un progetto per la produzione è necessario rimuovere questa dipendenza e l'inclusione del sottopacchetto.

## Test {#testing}

Il progetto contiene tre livelli di test e, poiché sono tipi diversi di test, vengono eseguiti in modi diversi o in luoghi diversi.

* Prova di unità nel nucleo: Questo mostra il classico unit testing del codice contenuto nel bundle. Per eseguire il test, eseguire:
   * `mvn clean test`
* Test di integrazione lato server: Questi test vengono eseguiti come unità nell’ambiente AEM, ad esempio nel server AEM. Per eseguire il test, eseguire:
   * `mvn clean verify -PintegrationTests`
* Test Hobbes.js lato client: Si tratta di test basati su JavaScript sul browser per verificare il comportamento sul lato browser. Per eseguire il test:
   1. Caricate AEM nel browser come fareste per creare una pagina.
   1. Open the page in [Developer mode](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/developer-mode.html)
   1. Aprite il pannello a sinistra e passate alla scheda **Test** .
   1. Individuare e eseguire i test **MyName generati** .

## Passaggi successivi {#next-steps}

Quindi hai creato e installato AEM Project Archetype. E adesso? Il tipo archetipo è piccolo, ma è costituito da molti esempi di potenti funzioni di AEM configurate in base alle best practice consigliate. Utilizzate queste opzioni per indicare come sfruttare queste funzionalità nel progetto. Per qualsiasi progetto è probabilmente necessario:

* [Personalizzare i componenti estendendo i componenti core esistenti](customizing.md)
* [Aggiungere altri modelli](https://helpx.adobe.com/content/help/en/experience-manager/6-5/sites/authoring/using/templates.html)
* [Adattare la struttura di localizzazione](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-prep.html)
* [Informazioni sul modulo di build front-end](uifrontend.md)
