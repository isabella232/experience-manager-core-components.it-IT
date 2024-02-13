---
title: Utilizzo di Archetipo progetto AEM
description: L’Archetipo progetto AEM crea un progetto AEM minimo basato sulle best practice di Adobe Experience Manager come punto di partenza per i tuoi progetti AEM.
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: a3978d8b-4904-42aa-9ee2-9c1f884327bb
source-git-commit: bd92a5d1884056ca7b44ea28e5817d8bde10a4d9
workflow-type: ht
source-wordcount: '1092'
ht-degree: 100%

---


# Utilizzo di Archetipo progetto AEM {#using-the-archetype}

Questo documento spiega come utilizzare l’archetipo di progetto AEM per creare un progetto Adobe Experience Manager minimo basato su best practice come punto di partenza per i tuoi progetti AEM.

Si concentra sui pattern di utilizzo generali e su ciò che l’archetipo fa per te. Per opzioni di build e istruzioni tecniche dettagliate, consulta la documentazione nell’archivio GitHub dell’archetipo.

>[!TIP]
>
>La versione più recente dell’Archetipo progetto AEM [è disponibile su GitHub.](https://github.com/adobe/aem-project-archetype)

## Guida introduttiva {#getting-started}

L’archetipo del progetto rende facile iniziare a sviluppare in AEM. Puoi iniziare con l’Archetipo in diversi modi.

* **Tutorial WKND**: per un’ottima introduzione allo sviluppo in AEM, incluso il modo di utilizzare l’archetipo, consulta la [Guida introduttiva ai AEM Sites: tutorial WKND](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=it) per un esempio pratico che illustra come utilizzare l’archetipo per implementare un semplice progetto.
* **Tutorial eventi WKND**: se sei particolarmente interessato allo sviluppo di applicazioni a pagina singola (SPA) in AEM, consulta [tutorial dedicato sugli eventi WKND.](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=it)
* **Inizia da solo!**: puoi scaricare facilmente [l’archetipo del progetto corrente disponibile su GitHub](https://github.com/adobe/aem-project-archetype) e creare il tuo primo progetto da solo.

## Come utilizzare l’archetipo {#how-to-use-the-archetype}

Il primo passaggio utilizzando l’archetipo è la creazione di un progetto, che genera [i moduli](#what-you-get) in una struttura di file locale. Come parte della creazione del progetto, è possibile definire una serie di proprietà del progetto, come, ad esempio, nome, versione, abilitare diverse opzioni e così via.

>[!TIP]
>
>Ogni volta che crei l’archetipo, questo genera anche una serie di riferimenti, fornendo i dettagli tecnici e l’utilizzo di ciascun modulo come nel [collegamento qui sotto.](#what-you-get)

Lo sviluppo del progetto con Maven crea gli artefatti (pacchetti e bundle OSGi) che possono essere distribuiti ad AEM. Ulteriori comandi e profili Maven possono essere utilizzati per distribuire gli artefatti del progetto s un’istanza di AEM.

## Informazioni sull’utilizzo dell’archetipo {#what-you-get}

L’archetipo è costituito da moduli, tutti creati automaticamente quando si utilizza l’archetipo.

* **[core](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)** è un bundle Java contenente tutte le funzionalità core come servizi OSGi, ascoltatori e schedulatori nonché il codice Java relativo ai componenti, come servlet e filtri di richiesta.
* **[it.test](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)** sono test di integrazione basati su Java.
* **[ui.apps](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.apps)** contiene le parti `/apps` e `/etc` del progetto, ad esempio clientlib JS e CSS, componenti e modelli.
* **[ui.content](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.content)** contiene esempi di contenuto che utilizzano i componenti del modulo ui.apps.
* **[ui.config](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.config)** contiene le configurazioni OSGi specifiche per la modalità di esecuzione del progetto.
* **[ui.frontend.general](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.general)** contiene gli artefatti necessari per utilizzare il modulo di sviluppo front-end generale basato su Webpack (facoltativo).
* **[ui.frontend.react](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.react)** **(facoltativo)** contiene gli artefatti necessari quando si utilizza l’archetipo per creare progetti SPA basati su React (facoltativo, dipende dai parametri di build).
* **[ui.frontend.angular](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.angular)** **(facoltativo)** contiene gli artefatti necessari quando si utilizza l’archetipo per creare progetti SPA basati su Angular (facoltativo, dipende dai parametri di build).
* **[ui.tests](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)**: contiene i test dell’interfaccia utente basati su Selenium.
* **[all](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/all)**: è un singolo pacchetto di contenuti che incorpora tutti i moduli compilati (bundle e pacchetti di contenuti), comprese le dipendenze dei fornitori.
* **[dispatcher.ams](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.ams)**: contiene le configurazioni di base del dispatcher per i progetti AMS/on-premise (facoltativo, dipende dai parametri di build).
* **[dispatcher.cloud](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.cloud)**: contiene le configurazioni di base del dispatcher per i progetti AEMaaCS (facoltativo, dipende dai parametri di build).

![Organizzazione del pacchetto di contenuti](/help/assets/content-package-organization.png)

I moduli dell’archetipo rappresentati in Maven vengono distribuiti su AEM come pacchetti di contenuto che rappresentano l’applicazione, il contenuto e i bundle OSGi necessari.

## POM (Project Object Model) padre {#parent-pom}

Il file `pom.xml` nella directory principale del progetto (`<src-directory>/<project>/pom.xml`) è noto come POM padre e gestisce la struttura del progetto nonché le dipendenze e alcune proprietà globali del progetto stesso.

### Proprietà globali del progetto {#global-properties}

La sezione `<properties>` del POM padre definisce diverse proprietà globali importanti per la distribuzione del progetto a un’istanza di AEM, come nome utente/password, nome host/porta, ecc.

Queste proprietà sono configurate per la distribuzione a un’istanza di AEM locale, in quanto si tratta dello sviluppo più comune utilizzato dagli sviluppatori. Tieni presente che esistono anche proprietà configurate per la distribuzione a un’istanza Autore e un’istanza Publish. Qui vengono impostate anche le credenziali per l’autenticazione nell’istanza di AEM. Vengono utilizzate le credenziali `admin:admin` predefinite.

Queste proprietà sono configurate in modo che possano essere ignorate durante la distribuzione in ambienti di livello superiore. In questo modo, i file POM non devono essere modificati, ma le variabili come `aem.host` e `sling.password` possono essere ignorate inserendo argomenti nella riga di comando:

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### Struttura modulare {#module-structure}

La sezione `<modules>` del POM padre definisce i moduli che verranno sviluppati nel progetto. Per impostazione predefinita, il progetto genera [i moduli standard precedentemente definiti.](#what-you-get) Man mano che un progetto evolve, si possono sempre aggiungere altri moduli.

### Dipendenze {#dependencies}

La sezione `<dependencyManagement>` del POM padre definisce tutte le dipendenze e le versioni delle API utilizzate nel progetto. Le versioni devono essere gestite nel POM principale. I sottomoduli non devono includere informazioni sulle versioni.

#### Uber-Jar {#uber-jar}

Una delle dipendenze chiave è [AEM Java API Jar.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html?lang=it) Ciò includerà tutte le API di AEM con un’unica voce di dipendenza per la versione di AEM.

>[!NOTE]
>
>Come best practice, aggiorna la versione di uber-jar in modo che corrisponda alla versione di destinazione di AEM. Ad esempio, se prevedi di distribuire su AEM 6.5, devi aggiornare la versione di uber-jar alla 6.5.X, in cui `X` è il service pack più recente.

#### Componenti core {#core-components}

L’archetipo ovviamente utilizza i componenti core[.](/help/introduction.md) Pertanto, per sfruttare i componenti core in tutte le implementazioni, è consigliabile includerli come parte del progetto Maven.

I core.wcm.components.examples sono un set di esempi di pagine che illustrano esempi di Componenti core. Come best practice, quando distribuisci un progetto per la produzione, dovresti rimuovere questa dipendenza e l’inclusione di pacchetti secondari.

>[!NOTE]
>
>I componenti core e l’archetipo vengono mantenuti come progetti GitHub separati e come tali le loro versioni differiscono.
>
>Ogni versione di archetipo utilizzerà l’ultima versione dei componenti core disponibile al momento della versione. Tuttavia, potrebbe essere utile aggiornare manualmente la dipendenza dai componenti core.

## Test {#testing}

Il progetto contiene tre livelli di test e, poiché esistono diversi tipi di test, essi vengono eseguiti in modi diversi o in posizioni diverse.

* **[Test di unità](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)**: test di unità classici del codice contenuto nel bundle
* **[Test di integrazione](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)**: test di integrazione lato server che vengono eseguiti come test unità in ambiente AEM, ad esempio sul server AEM.
* **[Test dell’interfaccia utente](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)**: test lato browser basati su Selenium per verificare il comportamento lato browser
