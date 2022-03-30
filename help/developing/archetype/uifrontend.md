---
title: Sviluppo front-end di Archetipo progetto AEM
description: Un modello di progetto per applicazioni basate su AEM
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 99132b49-bd06-4ac2-9348-12c0dfdfe8b2
source-git-commit: 0e8082b0c5db1f2efc7db51f13123b5264a3a608
workflow-type: tm+mt
source-wordcount: '1621'
ht-degree: 99%

---

# Modulo ui.frontend di Archetipo progetto AEM {#uifrontend-module}

L’Archetipo progetto AEM include un meccanismo di sviluppo front-end opzionale e dedicato basato su Webpack. Il modulo ui.frontend diventa così la posizione centrale per tutte le risorse front-end del progetto, inclusi i file JavaScript e CSS. Per sfruttare appieno questa funzione utile e flessibile, è importante comprendere in che modo lo sviluppo front-end si inserisce in un progetto AEM.

## Progetti AEM e sviluppo front-end {#aem-and-front-end-development}

In termini molto semplificati, i progetti AEM si possono considerare costituiti da due parti distinte, ma correlate:

* Lo sviluppo back-end che guida la logica di AEM e produce librerie Java, servizi OSGi, ecc.
* Lo sviluppo front-end che guida la visualizzazione e il comportamento del sito web risultante e la generazione di librerie JavaScript e CSS

Poiché questi due processi di sviluppo si concentrano su parti diverse del progetto, lo sviluppo back-end e front-end può avvenire in parallelo.

![Diagramma del flusso di lavoro front-end](/help/assets/front-end-flow.png)

Tuttavia, qualsiasi progetto risultante deve utilizzare l’output di entrambi i processi di sviluppo, sia back-end che front-end.

L’esecuzione del comando `npm run dev` avvia il processo di sviluppo front-end che raccoglie i file JavaScript e CSS memorizzati nel modulo ui.frontend, genera due librerie client minimizzate o ClientLibs denominate `clientlib-site` e `clientlib-dependencies` e deposita il tutto nel modulo ui.apps. Le ClientLibs possono essere distribuite ad AEM e consentono di memorizzare il codice lato client nell’archivio.

Quando l’intero Archetipo progetto AEM viene eseguito utilizzando `mvn clean install -PautoInstallPackage`, tutti gli artefatti del progetto, incluse le ClientLibs, vengono quindi inviati all’istanza di AEM.

>[!TIP]
>
>Puoi avere ulteriori informazioni su come AEM gestisce le ClientLibs nella [documentazione di sviluppo AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html?lang=it), su come [includerle](/help/developing/including-clientlibs.md) oppure vedi di seguito [come il modulo ui.frontend le utilizza.](#clientlib-generation)

## Panoramica delle ClientLibs {#clientlibs}

Il modulo frontend è reso disponibile utilizzando una [AEM ClientLib](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html). Durante l’esecuzione dello script di sviluppo NPM, l’app viene sviluppata e il pacchetto aem-clientlib-generator prende il risultante output di sviluppo e lo trasforma in una ClientLib.

Una ClientLib è costituita dai file e dalle directory seguenti:

* `css/`: file CSS che possono essere richiesti nel codice HTML
* `css.txt`: indica ad AEM l’ordine e i nomi dei file in `css/`, in modo che possano essere uniti
* `js/`: file JavaScript che possono essere richiesti nel codice HTML
* `js.txt` indica ad AEM l’ordine e i nomi dei file in `js/`, modo che possano essere uniti
* `resources/`: Mappe sorgente, blocchi di codice non-entrypoint (derivanti dalla suddivisione del codice), risorse statiche (ad esempio icone), ecc.

## Flussi di lavoro possibili per lo sviluppo front-end {#possible-workflows}

Il modulo di sviluppo front-end è uno strumento utile e molto flessibile, ma non c’è un’opinione prevalente su come dovrebbe essere utilizzato. Di seguito sono riportati due esempi di *possibile* utilizzo, ma le esigenze dei singoli progetti potrebbero sicuramente imporre altri modelli di utilizzo.

### Utilizzo del server di sviluppo statico Webpack {#using-webpack}

Utilizzando Webpack puoi creare stili e sviluppare in base all’output statico di pagine web AEM all’interno del modulo ui.frontend.

1. Visualizza un’anteprima della pagina in AEM utilizzando la modalità di anteprima pagina oppure specificando `wcmmode=disabled` nell’URL
1. Visualizza la sorgente della pagina e salvala come HTML statico nel modulo ui.frontend
1. [Avvia Webpack](#webpack-dev-server) e inizia a creare gli stili e generare i file JavaScript e CSS necessari
1. Esegui `npm run dev` per generare le ClientLibs

In questo flusso, uno sviluppatore AEM potrebbe eseguire i passaggi uno e due e passare l’HTML statico allo sviluppatore front-end che sviluppa in base all’output HTML di AEM.

>[!TIP]
>
>È inoltre possibile sfruttare la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_it) per acquisire campioni di output del markup di ciascun componente per lavorare a livello di componente anziché a livello di pagina.

### Utilizzo di Storybook {#using-storybook}

Utilizzando [Storybook](https://storybook.js.org) puoi eseguire uno sviluppo front-end più atomico. Anche se Storybook non è incluso in Archetipo progetto AEM, puoi installarlo e memorizzare gli artefatti di Storybook nel modulo ui.frontend. Quando sono pronti per il test in AEM, possono essere distribuiti come ClientLibs eseguendo il comando`npm run dev`.

>[!NOTE]
>
>[Storybook](https://storybook.js.org) non è incluso in Archetipo progetto AEM. Se scegli di utilizzarlo, devi installarlo separatamente.

### Determinazione del markup {#determining-markup}

Qualunque sia il flusso di lavoro di sviluppo front-end che decidi di implementare per il progetto, gli sviluppatori back-end e gli sviluppatori front-end devono prima concordare il markup. In genere, è AEM che definisce il markup, fornito dai Componenti core. [Tuttavia, il markup può essere personalizzato, se necessario](/help/developing/customizing.md#customizing-the-markup).

## Modulo ui.frontend {#ui-frontend-module}

L’Archetipo progetto AEM include un meccanismo opzionale di sviluppo front-end basato su Webpack con le seguenti funzionalità.

* Supporto completo di TypeScript, ES6 e ES5 (con i wrapper Webpack applicabili)
* Linting del codice TypeScript e JavaScript con un set di regole TSLint
* Output ES5 per il supporto di browser legacy
* Globbing
   * Non è necessario aggiungere alcuna importazione
   * Ora è possibile aggiungere a ciascun componente tutti i file JS e CSS.
      * La best practice si trova in `/clientlib/js`, `/clientlib/css` o `/clientlib/scss`
   * Non sono necessari file `.content.xml` o `js.txt`/`css.txt`, in quanto tutto viene eseguito tramite Webpack.
   * Il globber estrae tutti i file JS sotto la cartella `/component/`.
      * Webpack consente il concatenamento dei file CSS/SCSS tramite i file JS.
      * I file vengono inseriti attraverso tra i due punti di ingresso `sites.js` e `vendors.js`.
   * Gli unici file utilizzati da AEM sono i file di output `site.js` e `site.css` in `/clientlib-site` nonché `dependencies.js` e `dependencies.css` in `/clientlib-dependencies`
* Blocchi
   * Principale (js/css del sito)
   * Fornitori (js/css dipendenze)
* Supporto completo di Sass/Scss (Sass viene compilato in CSS tramite Webpack)
* Server di sviluppo di Webpack statico con proxy integrato a un’istanza locale di AEM

>[!NOTE]
>
>Per ulteriori informazioni tecniche sul modulo ui.frontend, vedi la [documentazione su GitHub](https://github.com/adobe/aem-project-archetype/blob/master/src/main/archetype/ui.frontend.general/README.md).

## Installazione {#installation}

1. Installa [NodeJS](https://nodejs.org/it/download/) (v10+) a livello globale. Verrà installato anche lo script NPM.
1. Vai a ui.frontend nel tuo progetto ed esegui `npm install`.

>[!NOTE]
>
>Per compilare la cartella ui.frontend, devi [eseguire l’Archetipo](overview.md) con l’opzione `-DoptionIncludeFrontendModule=y`.

## Utilizzo {#usage}

I seguenti script NPM guidano il flusso di lavoro front-end:

* `npm run dev`: sviluppo completo con ottimizzazione JS disabilitata (tree shaking, ecc.), mappe sorgente abilitate e ottimizzazione CSS disabilitata.
* `npm run prod`: sviluppo completo con ottimizzazione JS abilitata (tree shaking, ecc.), mappe sorgente disabilitate e ottimizzazione CSS abilitata.
* `npm run start`: avvia un server di sviluppo Webpack statico per lo sviluppo locale con dipendenze minime da AEM.

## Output {#output}

Il modulo ui.frontend compila il codice sotto la cartella `ui.frontend/src` e restituisce i file CSS e JS compilati e tutte le risorse sotto una cartella denominata `ui.frontend/dist`.

* **Sito**: i file `site.js`, `site.css` e una cartella`resources/` per le immagini e i font dipendenti dal layout vengono creati in una cartella `dist/`clientlib-site.
* **Dipendenze**: i file `dependencies.js` e `dependencies.css` vengono creati in una cartella `dist/clientlib-dependencies`.

### JavaScript {#javascript}

* Ottimizzazione: per lo sviluppo di produzione, vengono rimossi tutti i file JS che non sono utilizzati o richiamati.

### CSS {#css}

* Prefisso automatico: tutti i file CSS vengono eseguiti tramite un assegnazione di prefisso e tutte le proprietà che richiedono il prefisso avranno automaticamente i prefissi aggiunti nel CSS.
* Ottimizzazione: a posteriori, tutti i file CSS vengono eseguiti tramite un ottimizzatore (cssnano) che li normalizza in base alle seguenti regole predefinite:
   * Riduce l’espressione CSS calc laddove possibile, garantendo compatibilità e compressione nel browser
Esegue la conversione tra valori equivalenti di lunghezza, tempo e angolo. Tieni presente che per impostazione predefinita i valori di lunghezza non vengono convertiti.
   * Rimuove i commenti in e intorno a regole, selettori e dichiarazioni
   * Rimuove le regole duplicate, le regole at e le dichiarazioni
      * Questo funziona solo per i duplicati esatti.
   * Rimuove regole vuote, query multimediali e regole con selettori vuoti, in quanto non influiscono sull’output
   * Unisce le regole adiacenti tramite selettori e coppie proprietà/valore sovrapposte
   * Garantisce che nel file CSS sia presente un solo @charset e lo sposta in alto nel documento
   * Sostituisce la parola chiave iniziale CSS con il valore effettivo, quando l’output risultante è minore
   * Comprime le definizioni SVG in linea con SVGO
* Pulizia: include un’attività di pulizia esplicita per eliminare i file CSS, JS e Map generati on-demand.
* Mapping sorgente: solo attività di sviluppo

>[!NOTE]
>
>L’opzione di sviluppo front-end utilizza i file di configurazione Webpack dev-only e prod-only che condividono un file di configurazione comune. In questo modo le impostazioni di sviluppo e produzione possono essere modificate in modo indipendente.

### Generazione di librerie client {#clientlib-generation}

Il processo di sviluppo del modulo ui.frontend sfrutta il plug-in [aem-clientlib-generator](https://www.npmjs.com/package/aem-clientlib-generator) per spostare i file CSS, JS compilati e tutte le risorse nel modulo ui.apps. La configurazione di aem-clientlib-generator è definita in `clientlib.config.js`. Vengono generate le seguenti librerie client:

* **clientlib-site** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-site`
* **clientlib-dependencies** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-dependencies`

### Inclusione delle librerie client nelle pagine {#clientlib-inclusion}

Le categorie `clientlib-site` e `clientlib-dependencies` vengono incluse nelle pagine tramite la [configurazione di Criterio pagina ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#template-definitions) come parte del modello predefinito. Per visualizzare il criterio, modifica **Modello pagina di contenuto > Informazioni pagina > Criterio pagina**.

L’inclusione finale delle librerie client nella pagina del sito è la seguente:

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

L’inclusione di cui sopra può ovviamente essere modificata aggiornando Criterio pagina e/o modificando le categorie e le proprietà di incorporamento delle rispettive librerie client.

### Server di sviluppo Webpack statico {#webpack-dev-server}

Nel modulo ui.frontend è incluso un webpack-dev-server che fornisce un ricaricamento live per uno sviluppo front-end rapido al di fuori di AEM. La configurazione sfrutta html-webpack-plugin per inserire automaticamente i file CSS e JS compilati dal modulo ui.frontend in un modello HTML statico.

#### File importanti {#important-files}

* `ui.frontend/webpack.dev.js`
   * Contiene la configurazione del webpack-dev-server e punta al modello html da utilizzare.
   * Contiene anche una configurazione proxy a un’istanza di AEM in esecuzione su localhost:4502.
* `ui.frontend/src/main/webpack/static/index.html`
   * Si tratta dell’HTML statico rispetto al quale verrà eseguito il server.
   * Ciò consente a uno sviluppatore di apportare modifiche ai file CSS/JS e di visualizzarle immediatamente nel markup.
   * Si presuppone che il markup inserito in questo file rifletta accuratamente il markup generato dai componenti AEM.
   * Il markup in questo file non viene sincronizzato automaticamente con il markup del componente AEM.
   * Questo file contiene anche riferimenti alle librerie client memorizzate in AEM, come Componente core CSS e Griglia reattiva CSS.
   * Il server di sviluppo Webpack è configurato per fungere da proxy di queste inclusioni di file CSS/JS da un’istanza di AEM in esecuzione locale basata sulla configurazione trovata in `ui.frontend/webpack.dev.js`.

#### Utilizzando {#using-webpack-server}

1. Dall’interno della directory principale del progetto, esegui il comando `mvn -PautoInstallSinglePackage clean install` per installare l’intero progetto su un’istanza di AEM in esecuzione su `localhost:4502`.
1. Naviga all’interno della cartella `ui.frontend`.
1. Esegui il comando `npm run start` per avviare il server di sviluppo Webpack. Una volta avviato, si dovrebbe aprire un browser (`localhost:8080` o la successiva porta disponibile).

Ora puoi modificare i file CSS, JS, SCSS e TS e vedere le modifiche immediatamente riflesse nel server di sviluppo Webpack.
