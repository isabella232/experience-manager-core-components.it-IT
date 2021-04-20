---
title: Build front-end per SPA React
description: Descrizione del processo di compilazione front-end per i progetti SPA basati su React
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 0%

---


# Build front-end per React SPA {#frontend-react}

In questo documento vengono illustrati i dettagli del progetto creato quando si utilizza l&#39;archetipo per creare un&#39;applicazione a pagina singola (SPA) basata sul framework React. Ad esempio, quando imposti l’opzione `frontendModule` su `react`.

## Panoramica {#overview}

Questo progetto è stato avviato con [create-react-app](https://github.com/facebook/create-react-app).

Questa applicazione è creata per utilizzare il modello AEM di un sito. Genererà automaticamente il layout utilizzando i componenti helper del pacchetto [@adobe/cq-react-editable-components](https://www.npmjs.com/package/@adobe/cq-react-editable-components) .

## Script {#scripts}

Nella directory di progetto, puoi eseguire i seguenti comandi:

### inizio npm {#npm-start}

```shell
npm start
```

Questo comando esegue l&#39;app in modalità di sviluppo tramite il proxy del modello JSON da un&#39;istanza AEM locale in esecuzione su http://localhost:4502. Ciò presuppone che l’intero progetto sia stato distribuito per AEM almeno una volta (`mvn clean install -PautoInstallPackage` nella directory principale del progetto).

Dopo aver eseguito `npm start` nella directory [ui.frontend](uifrontend.md), l’app verrà automaticamente aperta nel browser (nel percorso `http://localhost:3000/content/<appId>/<country>/<language>/home.html`). Se apporti modifiche, la pagina verrà ricaricata.

Se ricevi errori relativi a CORS, configura AEM come segue:

1. Passa a Configuration Manager (http://localhost:4502/system/console/configMgr)
1. Apri la configurazione per &quot;Adobe Granite Cross-Origin Resource Sharing Policy&quot;
1. Crea una nuova configurazione con i seguenti valori aggiuntivi:
   * Origini consentite: http://localhost:3000
   * Intestazioni supportate: Autorizzazione
   * Metodi consentiti: OPTIONS

### test npm {#npm-test}

```shell
npm test
```

Questo comando avvia l&#39;esecuzione del test in modalità orologio interattivo. Per ulteriori informazioni, consulta la documentazione [React sull&#39;esecuzione di test](https://facebook.github.io/create-react-app/docs/running-tests) .

### build di esecuzione npm {#npm-run-build}

```shell
npm run build
```

Questo comando crea l&#39;app per la produzione nella cartella build. Offre la funzionalità React in modalità di produzione e ottimizza la build per ottenere le migliori prestazioni. Per ulteriori informazioni, consulta la documentazione [React sulla distribuzione](https://facebook.github.io/create-react-app/docs/deployment) .

Inoltre, un AEM ClientLib viene generato dall&#39;app utilizzando il pacchetto [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator) .

## Supporto browser {#browser-support}

Per impostazione predefinita, questo progetto utilizza l&#39;opzione predefinita [BrowserList](https://github.com/browserslist/browserslist) per identificare i browser di destinazione. Inoltre, include i polyfills per le funzioni della lingua moderna per supportare i browser più vecchi (ad esempio Internet Explorer 11). Se il supporto di tali browser non è un requisito, le dipendenze di polyfill e le importazioni possono essere rimosse.

## Suddivisione del codice {#code-splitting}

L&#39;app React è configurata per l&#39;utilizzo di [suddivisione del codice](https://webpack.js.org/guides/code-splitting) per impostazione predefinita. Durante la creazione dell&#39;app per la produzione, il codice viene inviato in diversi blocchi:

```shell
$ ls build/static/js
2.5b77f553.chunk.js
2.5b77f553.chunk.js.map
main.cff1a559.chunk.js
main.cff1a559.chunk.js.map
runtime~main.a8a9905a.js
runtime~main.a8a9905a.js.map
```

Il caricamento dei blocchi solo quando necessari può migliorare notevolmente le prestazioni dell’app.

Affinché questa funzione funzioni con AEM, l’app deve essere in grado di identificare quali file JS e CSS devono essere richiesti dall’HTML generato da AEM. Questo può essere ottenuto utilizzando la chiave &quot;entrypoints&quot; nel file asset-manifest.json. Il file viene analizzato in clientlib.config.js e solo i file entrypoint sono raggruppati in ClientLib. I file rimanenti vengono inseriti nella directory delle risorse di ClientLib e verranno richiesti dinamicamente e quindi caricati solo quando sono effettivamente necessari.

Per ulteriori informazioni sull&#39;utilizzo di ClientLibs AEM dall&#39;archetipo del progetto, consulta la documentazione generale del modulo [ui.frontend](uifrontend.md#clientlibs) .
