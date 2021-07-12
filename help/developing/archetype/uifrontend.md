---
title: Generazione front-end Archetype AEM progetto
description: Un modello di progetto per applicazioni basate su AEM
feature: Componenti core, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 99132b49-bd06-4ac2-9348-12c0dfdfe8b2
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '1625'
ht-degree: 0%

---

# modulo ui.frontend dell’Archetipo di progetto AEM {#uifrontend-module}

Il AEM Project Archetype include un meccanismo di compilazione front-end opzionale e dedicato basato su Webpack. Il modulo ui.frontend diventa così la posizione centrale per tutte le risorse front-end del progetto, inclusi i file JavaScript e CSS. Per sfruttare appieno questa funzione utile e flessibile, è importante comprendere in che modo lo sviluppo front-end si inserisce in un progetto AEM.

## Progetti AEM e sviluppo front-end {#aem-and-front-end-development}

In termini molto semplificati, AEM progetti si possono considerare costituiti da due parti distinte ma correlate:

* Sviluppo back-end che guida la logica di AEM e produce librerie Java, servizi OSGi, ecc.
* Sviluppo front-end per la presentazione e il comportamento del sito Web risultante e la generazione di librerie JavaScript e CSS

Poiché questi due processi di sviluppo si concentrano su parti diverse del progetto, lo sviluppo back-end e front-end può avvenire in parallelo.

![diagramma del flusso di lavoro front-end](/help/assets/front-end-flow.png)

Tuttavia, qualsiasi progetto risultante deve utilizzare i risultati di entrambi questi sforzi di sviluppo, sia back-end che front-end.

L’esecuzione di `npm run dev` avvia il processo di compilazione front-end che raccoglie i file JavaScript e CSS memorizzati nel modulo ui.frontend e produce due librerie client minimizzate o ClientLibs denominate `clientlib-site` e `clientlib-dependencies` e li deposita nel modulo ui.apps . Le librerie client sono distribuibili per AEM e consentono di memorizzare il codice lato client nell’archivio.

Quando l’intero archetipo di progetto AEM viene eseguito utilizzando `mvn clean install -PautoInstallPackage`, tutti gli artefatti di progetto, inclusi i ClientLibs, vengono quindi inviati all’istanza AEM.

>[!TIP]
>
>Ulteriori informazioni su come AEM gestire ClientLibs nella [AEM documentazione di sviluppo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html), su come [includerli](/help/developing/including-clientlibs.md) o vedi sotto [come il modulo ui.frontend li utilizza.](#clientlib-generation)

## Panoramica di ClientLibs {#clientlibs}

Il modulo frontend è reso disponibile utilizzando un [AEM ClientLib](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html). Durante l’esecuzione dello script di build NPM, l’app viene generata e il pacchetto aem-clientlib-generator prende l’output di build risultante e lo trasforma in una tale ClientLib.

Un ClientLib sarà costituito dai file e dalle directory seguenti:

* `css/`: File CSS che possono essere richiesti nell’HTML
* `css.txt`: Indica AEM&#39;ordine e i nomi dei file in  `css/` modo che possano essere uniti
* `js/`: File JavaScript che possono essere richiesti nel codice HTML
* `js.txt` Indica AEM&#39;ordine e i nomi dei file in  `js/` modo che possano essere uniti
* `resources/`: Mappe sorgente, blocchi di codice non di un punto di ingresso (derivanti dalla suddivisione del codice), risorse statiche (ad esempio icone), ecc.

## Possibili flussi di lavoro di sviluppo front-end {#possible-workflows}

Il modulo di compilazione front-end è uno strumento utile e molto flessibile, ma non impone un parere particolare su come dovrebbe essere utilizzato. Di seguito sono riportati due esempi di utilizzo *possibile* , ma le esigenze dei singoli progetti possono dettare altri modelli di utilizzo.

### Utilizzo del server di sviluppo statico Webpack {#using-webpack}

Utilizzando Webpack puoi creare stili e sviluppare in base all&#39;output statico di AEM pagine web all&#39;interno del modulo ui.frontend.

1. Anteprima pagina in AEM utilizzando la modalità di anteprima pagina o passando `wcmmode=disabled` nell’URL
1. Visualizza l’origine della pagina e salva come HTML statico nel modulo ui.frontend
1. [Avvia ](#webpack-dev-server) il pacchetto web, inizia lo stile e genera i necessari JavaScript e CSS
1. Esegui `npm run dev` per generare le librerie client

In questo flusso, uno sviluppatore AEM può eseguire i passaggi uno e due e passare l’HTML statico off allo sviluppatore front-end che si sviluppa in base all’output HTML AEM.

>[!TIP]
>
>È inoltre possibile sfruttare la [Libreria di componenti](https://adobe.com/go/aem_cmp_library) per acquisire campioni dell’output di markup di ciascun componente al fine di funzionare a livello di componente anziché a livello di pagina.

### Utilizzo di Storybook {#using-storybook}

Utilizzando [Storybook](https://storybook.js.org) puoi eseguire uno sviluppo front-end più atomico. Anche se Storybook non è incluso nel AEM Project Archetype, puoi installarlo e memorizzare gli artefatti di Storybook nel modulo ui.frontend. Quando sono pronti per il test in AEM, possono essere distribuiti come ClientLibs eseguendo `npm run dev`.

>[!NOTE]
>
>[](https://storybook.js.org) Storybookis non incluso nell&#39;Archetipo di progetto AEM. Se scegli di usarlo, devi installarlo separatamente.

### Determinazione del markup {#determining-markup}

Qualunque sia il flusso di lavoro di sviluppo front-end che decidi di implementare per il progetto, gli sviluppatori back-end e gli sviluppatori front-end devono prima concordare il markup. In genere AEM definisce il markup, fornito dai componenti core. [Tuttavia questo può essere personalizzato se necessario](/help/developing/customizing.md#customizing-the-markup).

## Modulo ui.frontend {#ui-frontend-module}

Il AEM Project Archetype include un meccanismo opzionale di creazione front-end basato su Webpack con le seguenti funzionalità.

* Supporto completo per TypeScript, ES6 e ES5 (con i wrapper Webpack applicabili)
* Stampaggio TypeScript e JavaScript utilizzando un set di regole TSLint
* Uscita ES5 per il supporto browser legacy
* Globbing
   * Non è necessario aggiungere importazioni da nessuna parte
   * Ora è possibile aggiungere a ciascun componente tutti i file JS e CSS.
      * La best practice si trova in `/clientlib/js`, `/clientlib/css` o `/clientlib/scss`
   * Non sono necessari file `.content.xml` o `js.txt`/`css.txt` in quanto tutto viene eseguito tramite Webpack.
   * Il globber estrae tutti i file JS sotto la cartella `/component/` .
      * Webpack consente il concatenamento dei file CSS/SCSS tramite file JS.
      * Vengono inseriti tra i due punti di ingresso, `sites.js` e `vendors.js`.
   * L&#39;unico file utilizzato da AEM sono i file di output `site.js` e `site.css` in `/clientlib-site` e `dependencies.js` e `dependencies.css` in `/clientlib-dependencies`
* Pezzi
   * Principale (sito js/css)
   * Fornitori (dipendenze js/css)
* Supporto completo Sass/Scss (Sass viene compilato in CSS tramite Webpack)
* Server di sviluppo del webpack statico con proxy integrato in un&#39;istanza locale di AEM

>[!NOTE]
>
>Per ulteriori informazioni tecniche sul modulo ui.frontend, consulta la documentazione [su GitHub](https://github.com/adobe/aem-project-archetype/blob/master/src/main/archetype/ui.frontend.general/README.md).

## Installazione {#installation}

1. Installa [NodeJS](https://nodejs.org/en/download/) (v10+) a livello globale. Questo installerà anche npm.
1. Passa a ui.frontend nel tuo progetto ed esegui `npm install`.

>[!NOTE]
>
>Per compilare la cartella ui.frontend, è necessario disporre di [eseguire l&#39;archetipo](overview.md) con l&#39;opzione `-DoptionIncludeFrontendModule=y`.

## Utilizzo {#usage}

I seguenti script npm generano il flusso di lavoro front-end:

* `npm run dev` - build completa con ottimizzazione JS disabilitata (ad albero, ecc.) e mappe sorgente abilitate e ottimizzazione CSS disabilitata.
* `npm run prod` - build completa con l’ottimizzazione JS abilitata (ad albero tremolante, ecc.), mappe sorgente disattivate e ottimizzazione CSS abilitata.
* `npm run start` - Avvia un server di sviluppo webpack statico per lo sviluppo locale con dipendenze minime da AEM.

## Output {#output}

Il modulo ui.frontend compila il codice sotto la cartella `ui.frontend/src` e restituisce i CSS e JS compilati e tutte le risorse sotto una cartella denominata `ui.frontend/dist`.

* **Sito** -  `site.js`,  `site.css` e una  `resources/` cartella per immagini e font dipendenti dal layout vengono creati in una cartella  `dist/`clientlib-site.
* **Dipendenze**  -  `dependencies.js` e  `dependencies.css` vengono create in una  `dist/clientlib-dependencies` cartella.

### JavaScript {#javascript}

* Ottimizzazione : per le build di produzione, viene rimosso tutto il JS che non viene utilizzato o chiamato.

### CSS {#css}

* Prefisso automatico : tutti i CSS vengono eseguiti tramite un prefissatore e tutte le proprietà che richiedono il prefisso avranno automaticamente quelli aggiunti nel CSS.
* Ottimizzazione - A posteriori, tutti i CSS vengono eseguiti tramite un ottimizzatore (cssnano) che li normalizza in base alle seguenti regole predefinite:
   * Riduce l&#39;espressione CSS calc laddove possibile, garantendo compatibilità e compressione sia del browser
Converte tra valori equivalenti di lunghezza, tempo e angolo. Per impostazione predefinita, i valori di lunghezza non vengono convertiti.
   * Rimuove i commenti in e intorno a regole, selettori e dichiarazioni
   * Rimuove le regole duplicate, le regole at e le dichiarazioni
      * Questo funziona solo per i duplicati esatti.
   * Rimuove regole vuote, query multimediali e regole con selettori vuoti, in quanto non influiscono sull’output
   * Unisce le regole adiacenti tramite selettori e coppie proprietà/valore sovrapposte
   * Assicura che nel file CSS sia presente un solo @charset e lo sposta nella parte superiore del documento
   * Sostituisce la parola chiave iniziale CSS con il valore effettivo, quando l’output risultante è minore
   * Comprime le definizioni SVG in linea con SVGO
* Pulizia: include un’attività pulita esplicita per eliminare i file CSS, JS e Mappa generati su richiesta.
* Mappatura origine - solo build di sviluppo

>[!NOTE]
>
>L&#39;opzione di compilazione front-end utilizza i file di configurazione del webpack solo per dev e solo per prod che condividono un file di configurazione comune. In questo modo le impostazioni di sviluppo e produzione possono essere modificate in modo indipendente.

### Generazione libreria client {#clientlib-generation}

Il processo di compilazione del modulo ui.frontend sfrutta il plug-in [aem-clientlib-generator](https://www.npmjs.com/package/aem-clientlib-generator) per spostare i CSS compilati, JS e tutte le risorse nel modulo ui.apps . La configurazione aem-clientlib-generator è definita in `clientlib.config.js`. Vengono generate le seguenti librerie client:

* **clientlib-site** -  `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-site`
* **clientlib-dipendenze**  -  `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-dependencies`

### Inclusione delle librerie client nelle pagine {#clientlib-inclusion}

`clientlib-site` Le  `clientlib-dependencies` categorie e sono incluse nelle pagine tramite la  [configurazione dei criteri di ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html#template-definitions) pagina come parte del modello predefinito. Per visualizzare il criterio, modifica **Modello pagina di contenuto > Informazioni pagina > Criterio pagina**.

L’inclusione finale delle librerie client nella pagina Sites è la seguente:

```html
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

L&#39;inclusione di cui sopra può ovviamente essere modificata aggiornando i Criteri di pagina e/o modificando le categorie e le proprietà di incorporamento delle rispettive librerie client.

### Server di sviluppo webpack statico {#webpack-dev-server}

Incluso nel modulo ui.frontend è un webpack-dev-server che fornisce un ricaricamento live per uno sviluppo front-end rapido al di fuori di AEM. La configurazione sfrutta l’html-webpack-plugin per inserire automaticamente CSS e JS compilati dal modulo ui.frontend in un modello HTML statico.

#### File importanti {#important-files}

* `ui.frontend/webpack.dev.js`
   * Questo contiene la configurazione del webpack-dev-serve e punta al modello html da utilizzare.
   * Contiene anche una configurazione proxy a un&#39;istanza AEM in esecuzione su localhost:4502.
* `ui.frontend/src/main/webpack/static/index.html`
   * Si tratta dell’HTML statico rispetto al quale verrà eseguito il server.
   * Questo consente a uno sviluppatore di apportare modifiche CSS/JS e di visualizzarle immediatamente nel markup.
   * Si presume che il markup inserito in questo file rifletta accuratamente il markup generato da componenti AEM.
   * Il markup in questo file non viene sincronizzato automaticamente con AEM markup del componente.
   * Questo file contiene anche riferimenti alle librerie client memorizzate in AEM, come Core Component CSS e Responsive Grid CSS.
   * Il server di sviluppo del webpack è impostato per il proxy che questi CSS/JS includono da un&#39;istanza di AEM in esecuzione locale basata sulla configurazione trovata in `ui.frontend/webpack.dev.js`.

#### Utilizzando {#using-webpack-server}

1. Dall’interno della directory principale del progetto esegui il comando `mvn -PautoInstallSinglePackage clean install` per installare l’intero progetto in un’istanza AEM in esecuzione in `localhost:4502`.
1. Naviga all’interno della cartella `ui.frontend` .
1. Esegui il seguente comando `npm run start` per avviare il server di sviluppo del webpack. Una volta avviato, dovrebbe aprire un browser (`localhost:8080` o la successiva porta disponibile).

Ora puoi modificare i file CSS, JS, SCSS e TS e vedere le modifiche immediatamente visibili nel server di sviluppo del webpack.
