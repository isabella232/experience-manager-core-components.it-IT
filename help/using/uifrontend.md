---
title: Creazione front-end tipo di archivio AEM
seo-title: Creazione front-end tipo di archivio AEM
description: Un modello di progetto per le applicazioni basate su AEM
seo-description: Un modello di progetto per le applicazioni basate su AEM
contentOwner: bohnert
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: 5f905b0231b5f07924a55dd3d79d347e019f76f4

---


# modulo ui.frontend dell’archivio progetti AEM {#uifrontend-module}

Il tipo di archivio dei progetti AEM include un meccanismo di compilazione front-end opzionale basato su Webpack. Il modulo ui.frontend diventa quindi la posizione centrale per tutte le risorse front-end del progetto, inclusi i file JavaScript e CSS. Per sfruttare appieno questa funzione utile e flessibile, è importante comprendere in che modo lo sviluppo front-end si inserisce in un progetto AEM.

## Progetti AEM e sviluppo front-end {#aem-and-front-end-development}

In termini molto semplificati, i progetti AEM possono essere considerati composti di due parti separate ma correlate:

* Sviluppo di back-end che supporta la logica di AEM e produce librerie Java, servizi OSGi, ecc.
* Sviluppo front-end che guida la presentazione e il comportamento del sito Web risultante e produce librerie JavaScript e CSS

Poiché questi due processi di sviluppo si concentrano su parti diverse del progetto, lo sviluppo back-end e front-end può avvenire in parallelo.

![](assets/front-end-flow.png)

Tuttavia, qualsiasi progetto risultante deve utilizzare il risultato di entrambi questi sforzi di sviluppo, sia back-end che front-end.

L'esecuzione `npm run dev` avvia il processo di compilazione front-end che raccoglie i file JavaScript e CSS memorizzati nel modulo ui.frontend e produce due librerie client o clientlibs minificati chiamati `clientlib-site` e `clientlib-dependencies` li deposita nel modulo ui.apps. clientlibs possono essere distribuiti in AEM e consentono di archiviare il codice lato client nell’archivio.

Quando l’intero archetipo del progetto AEM viene eseguito utilizzando `mvn clean install -pautoinstallPackage` tutti gli artefatti del progetto, inclusi i clientlibs, viene quindi inviato all’istanza di AEM.

>[!TIP]
>Ulteriori informazioni sui clientlibs sono disponibili nella documentazione [di sviluppo di](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html) AEM e [come il modulo ui.frontend li utilizza di seguito](#clientlib-generation).

## Possibili flussi di lavoro di sviluppo front-end {#possible-workflows}

Il modulo di compilazione front-end è uno strumento utile e molto flessibile, ma non impone particolari opinioni su come dovrebbe essere utilizzato. Di seguito sono riportati due esempi di utilizzo *possibile* , ma le esigenze dei singoli progetti possono dettare altri modelli di utilizzo.

### Utilizzo del server di sviluppo statico Webpack {#using-webpack}

Webpack consente di progettare e sviluppare contenuti basati sull’output statico delle pagine Web AEM nel modulo ui.frontend.

1. Anteprima pagina in AEM tramite la modalità di anteprima pagina o passaggio `wcmmode=disabled` nell’URL
1. Visualizzare l'origine della pagina e salvare come HTML statico nel modulo ui.frontend
1. [Avviare il webpack](#webpack-dev-server) e iniziare a creare lo stile e generare i JavaScript e CSS necessari
1. Eseguire `npm run dev` per generare i clientlibs

In questo flusso, uno sviluppatore AEM può eseguire i passaggi uno e due e trasmettere l’HTML statico allo sviluppatore front-end che si sviluppa in base all’output HTML di AEM.

>[!TIP]
>
>È inoltre possibile utilizzare la libreria [](https://opensource.adobe.com/aem-core-wcm-components/library.html) dei componenti per acquisire esempi dell'output di markup di ciascun componente per lavorare a livello di componente anziché a livello di pagina.

### Utilizzo di Storybook {#using-storybook}

Utilizzando [Storybook](https://storybook.js.org) è possibile eseguire più sviluppo atomico front-end. Sebbene Storybook non sia incluso nel Project Archetype di AEM, puoi installarlo e archiviare i tuoi artifact storybook nel modulo ui.frontend. Una volta pronti per essere testati in AEM, possono essere distribuiti come clientlibs eseguendo `npm run dev`.

>[!NOTE]
>
>[Storybook](https://storybook.js.org) non è incluso nel Project Archetype di AEM. Se scegliete di utilizzarlo, dovete installarlo separatamente.

### Determinazione della marcatura {#determining-markup}

Indipendentemente dal flusso di lavoro di sviluppo front-end che decidete di implementare per il progetto, gli sviluppatori back-end e gli sviluppatori front-end devono prima accordarsi sulla marcatura. In genere, AEM definisce la marcatura, fornita dai componenti core. [Tuttavia, se necessario](https://docs.adobe.com/content/help/en/experience-manager-core-components/using/developing/customizing.html#customizing-the-markup), questo può essere personalizzato.

## Modulo ui.frontend {#ui-frontend-module}

Il tipo di archivio dei progetti AEM include un meccanismo opzionale per la creazione front-end basato su Webpack con le seguenti funzionalità.

* Supporto completo per TypeScript, ES6 e ES5 (con wrapper per webpack applicabili)
* Collegamento TypeScript e JavaScript con un set di regole TSLint
* Uscita ES5 per il supporto dei browser legacy
* Globbing
   * Nessuna necessità di aggiungere importazioni da nessuna parte
   * Tutti i file JS e CSS possono ora essere aggiunti a ciascun componente.
      * La best practice è `/clientlib/js`, `/clientlib/css`, o `/clientlib/scss`
   * Non sono necessari `.content.xml` né `js.txt`/`css.txt` file in quanto tutto viene eseguito tramite Webpack.
   * Il globo estrae tutti i file JS sotto la `/component/` cartella.
      * Webpack consente di collegare i file CSS/SCSS tramite file JS.
      * Vengono inseriti attraverso i due punti di ingresso `sites.js` e `vendors.js`.
   * L’unico file utilizzato da AEM è rappresentato dai file di output `site.js` e `site.css` in `/clientlib-site` nonché `dependencies.js` e `dependencies.css` in `/clientlib-dependencies`
* Gocce
   * Main (sito js/css)
   * Fornitori (dipendenze js/css)
* Supporto Sass/Scss completo (Sass viene compilato in CSS tramite Webpack)
* Server di sviluppo webpack statico con proxy integrato in un’istanza locale di AEM

## Installazione {#installation}

1. Installate [NodeJS](https://nodejs.org/en/download/) (v10+) a livello globale. Verrà installato anche npm.
1. Andate a ui.frontend nel progetto ed eseguite `npm install`.

>[!NOTE]
>
>È necessario aver [eseguito archetype](overview.md) con l'opzione `-DoptionIncludeFrontendModule=y` per compilare la cartella ui.frontend.

## Utilizzo {#usage}

I seguenti script npm generano il flusso di lavoro front-end:

* `npm run dev` - build completa con ottimizzazione JS disattivata (tremolio ad albero, ecc.) e mappe sorgente abilitate e ottimizzazione CSS disattivata.
* `npm run prod` - build completa con ottimizzazione JS abilitata (tremolio ad albero, ecc.), mappe sorgente disattivate e ottimizzazione CSS abilitata.
* `npm run start` - Avvia un server di sviluppo webpack statico per lo sviluppo locale con dipendenze minime su AEM.

## Output {#output}

Il modulo ui.frontend compila il codice sotto la `ui.frontend/src` cartella e produce i CSS e JS compilati, nonché tutte le risorse sotto una cartella denominata `ui.frontend/dist`.

* **Sito** - `site.js`, `site.css` e una `resources/` cartella per le immagini e i font dipendenti dal layout vengono creati in una cartella `dist/`clientlib-site.
* **Dipendenze** - `dependencies.js` e `dependencies.css` vengono create in una `dist/clientlib-dependencies` cartella.

### JavaScript {#javascript}

* Ottimizzazione - Per le build di produzione, viene rimosso tutto il JS che non viene utilizzato o chiamato.

### CSS {#css}

* Prefisso automatico - Tutti i CSS vengono eseguiti tramite un prefissatore e tutte le proprietà che richiedono il prefissaggio avranno automaticamente quelle aggiunte nel CSS.
* Ottimizzazione - Al momento del post, tutto il CSS viene eseguito tramite un ottimizzatore (cssnano) che lo normalizza in base alle seguenti regole predefinite:
   * Riduce l'espressione CSS calc laddove possibile, garantendo sia la compatibilità del browser che la compressioneEffettua la conversione tra valori di lunghezza, tempo e angolatura equivalenti. Per impostazione predefinita, i valori di lunghezza non vengono convertiti.
   * Rimuove i commenti da regole, selettori e dichiarazioni
   * Rimuove regole, regole e dichiarazioni duplicate
      * Questo funziona solo per i duplicati esatti.
   * Rimuove regole vuote, query multimediali e regole con selettori vuoti, in quanto non influiscono sull'output
   * Unisce regole adiacenti tramite selettori e coppie proprietà/valore sovrapposte
   * Assicurarsi che nel file CSS sia presente un solo @charset e spostarlo nella parte superiore del documento
   * Sostituisce la parola chiave iniziale CSS con il valore effettivo, quando l'output risultante è minore
   * Comprime le definizioni SVG in linea con SVGO
* Pulizia - Include un'attività di pulizia esplicita per eliminare i file CSS, JS e Mappa generati su richiesta.
* Mappatura origine - solo build di sviluppo

>[!NOTE]
>L'opzione front-end build utilizza file di configurazione di webpack solo per dev e solo per prod che condividono un file di configurazione comune. In questo modo le impostazioni di sviluppo e produzione possono essere modificate in modo indipendente.

### Generazione libreria client {#clientlib-generation}

Il processo di compilazione del modulo ui.frontend si basa sul plug-in [aem-clientlib-generator](https://www.npmjs.com/package/aem-clientlib-generator) per spostare CSS, JS e qualsiasi risorsa nel modulo ui.apps compilato. La configurazione aem-clientlib-generator è definita in `clientlib.config.js`. Vengono generate le seguenti librerie client:

* **clientlib-site** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-site`
* **clientlib-dipendenze** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-dependencies`

### Inclusione di librerie client nelle pagine {#clientlib-inclusion}

`clientlib-site` e `clientlib-dependencies` le categorie sono incluse nelle pagine tramite la configurazione [Criteri di](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/page-templates-editable.html#TemplateDefinitions) pagina come parte del modello predefinito. Per visualizzare il criterio, modificate il modello di pagina **Contenuto &gt; Informazioni pagina &gt; Criteri** pagina.

L'inclusione finale delle librerie client nella pagina dei siti è la seguente:

```
<HTML>
    <head>
        <link rel="stylesheet" href="clientlib-base.css" type="text/css">
        <script type="text/javascript" src="clientlib-dependencies.js"></script>
        <link rel="stylesheet" href="clientlib-dependencies.css" type="text/css">
        <link rel="stylesheet" href="clientlib-site.css" type="text/css">
    </head>
    <body>
        ....
        <script type="text/javascript" src="clientlib-site.js"></script>
        <script type="text/javascript" src="clientlib-base.js"></script>
    </body>
</HTML>
```

L'inclusione di cui sopra può ovviamente essere modificata aggiornando i Criteri pagina e/o modificando le categorie e le proprietà di incorporamento delle rispettive librerie client.

### Server di sviluppo webpack statico {#webpack-dev-server}

Incluso nel modulo ui.frontend è un webpack-dev-server che fornisce il ricaricamento live per uno sviluppo front-end rapido al di fuori di AEM. La configurazione utilizza il plug-in html-webpack-plug per iniettare automaticamente CSS e JS compilati dal modulo ui.frontend in un modello HTML statico.

#### File importanti {#important-files}

* `ui.frontend/webpack.dev.js`
   * Contiene la configurazione del webpack-dev-serve e punta al modello html da utilizzare.
   * Contiene inoltre una configurazione proxy per un’istanza di AEM in esecuzione su localhost:4502.
* `ui.frontend/src/main/webpack/static/index.html`
   * Si tratta dell’HTML statico con cui verrà eseguito il server.
   * Questo consente agli sviluppatori di apportare modifiche CSS/JS e di visualizzarle immediatamente nella marcatura.
   * Si presume che la marcatura inserita in questo file rifletta accuratamente la marcatura generata dai componenti AEM.
   * Il markup in questo file non viene sincronizzato automaticamente con il markup del componente AEM.
   * Questo file contiene anche riferimenti alle librerie client memorizzate in AEM, come i componenti core CSS e i CSS griglia reattiva.
   * Il server di sviluppo del webpack è configurato per il proxy che questi CSS/JS include da un'istanza AEM locale in esecuzione, in base alla configurazione trovata in `ui.frontend/webpack.dev.js`.

#### Utilizzando {#using-webpack-server}

1. Dall’interno della directory principale del progetto eseguite il comando `mvn -PautoInstallSinglePackage clean install` per installare l’intero progetto in un’istanza di AEM in esecuzione in `localhost:4502`.
1. Spostatevi all’interno della `ui.frontend` cartella.
1. Eseguite il comando seguente `npm run start` per avviare il server di sviluppo webpack. Una volta avviato, dovrebbe aprire un browser (`localhost:8080` o la successiva porta disponibile).

Ora potete modificare i file CSS, JS, SCSS e TS e visualizzare le modifiche immediatamente riflesse nel server di sviluppo dei webpack.
