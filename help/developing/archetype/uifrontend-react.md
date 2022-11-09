---
title: Sviluppo front-end per SPA React
description: Descrizione del processo di compilazione front-end per i progetti SPA basati su React
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: dd8ef13a-9686-47a9-b6af-e486ff10c4d8
source-git-commit: 0eea0cd65063c739e5b405b0380b73962a858e48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Sviluppo front-end per SPA React {#frontend-react}

In questo documento vengono illustrati i dettagli del progetto creato quando si utilizza l’archetipo per creare un’applicazione a pagina singola (SPA) basata sul framework React. Ad esempio, quando imposti l’opzione `frontendModule` su `react`.

## Panoramica {#overview}

Questo progetto è stato avviato con il comando [create-react-app](https://github.com/facebook/create-react-app).

Questa applicazione è stata sviluppata per avvalersi del modello AEM di un sito. Genera automaticamente il layout utilizzando i componenti helper del pacchetto [@adobe/cq-react-editable-components](https://www.npmjs.com/package/@adobe/aem-react-editable-components).

## Script {#scripts}

Nella directory del progetto, è possibile eseguire i comandi sotto riportati:

### npm start {#npm-start}

```shell
npm start
```

Questo comando esegue l’app in modalità di sviluppo tramite il proxy del modello JSON da un’istanza di AEM locale in esecuzione su http://localhost:4502. Ciò presuppone che l’intero progetto sia stato distribuito ad AEM almeno una volta (`mvn clean install -PautoInstallPackage` nella directory principale del progetto).

Dopo aver eseguito il comando `npm start` nella directory [ui.frontend](uifrontend.md), l’app verrà automaticamente aperta nel browser (nel percorso `http://localhost:3000/content/<appId>/<country>/<language>/home.html`). Se apporti modifiche, la pagina viene ricaricata.

Se ricevi errori relativi a CORS, configura AEM come segue:

1. Vai a Gestione configurazione (http://localhost:4502/system/console/configMgr)
1. Apri la configurazione per &quot;Adobe Granite Cross-Origin Resource Sharing Policy&quot;
1. Crea una nuova configurazione con i seguenti valori aggiuntivi:
   * Origini consentite: http://localhost:3000
   * Intestazioni supportate: autorizzazione
   * Metodi consentiti: OPZIONI

### npm test {#npm-test}

```shell
npm test
```

Questo comando avvia l’esecuzione dei test in modalità espressione di controllo interattivo. Per ulteriori informazioni, vedi la [documentazione di React sull’esecuzione dei test](https://facebook.github.io/create-react-app/docs/running-tests).

### npm run build {#npm-run-build}

```shell
npm run build
```

Questo comando esegue lo sviluppo dell’app per la produzione nella cartella di sviluppo. Crea il bundle React in modalità di produzione e ottimizza lo sviluppo per ottenere le migliori prestazioni. Per ulteriori informazioni, vedi la [documentazione di React sulla distribuzione](https://facebook.github.io/create-react-app/docs/deployment).

Inoltre, dall’app viene generata un’AEM ClientLib utilizzando il pacchetto [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator).

## Supporto del browser {#browser-support}

Per impostazione predefinita, questo progetto utilizza l’opzione predefinita [Browserslist](https://github.com/browserslist/browserslist) per identificare i browser di destinazione. Inoltre, include i polyfill per permettere alle moderne funzioni di lingua di supportare i browser precedenti (ad esempio, Internet Explorer 11). Se il supporto di questi browser non è un requisito, le dipendenze e importazioni di polyfill possono essere rimosse.

## Suddivisione del codice {#code-splitting}

Per impostazione predefinita, l’app React è configurata per utilizzare la [suddivisione del codice](https://webpack.js.org/guides/code-splitting). Durante lo sviluppo dell’app per la produzione, il codice viene inviato in diversi blocchi:

```shell
$ ls build/static/js
2.5b77f553.chunk.js
2.5b77f553.chunk.js.map
main.cff1a559.chunk.js
main.cff1a559.chunk.js.map
runtime~main.a8a9905a.js
runtime~main.a8a9905a.js.map
```

Il caricamento dei blocchi solo se necessari può migliorare notevolmente le prestazioni dell’app.

Perché questa funzione interagisca con AEM, l’app deve poter identificare quali file JS e CSS devono essere richiesti all’HTML generato da AEM. Ciò può essere ottenuto utilizzando la chiave “entrypoints” nel file asset-manifest.json. Il file viene analizzato in clientlib.config.js e solo i file entrypoint vengono inclusi nel bundle in ClientLib. I restanti file vengono inseriti nella directory delle risorse di ClientLib e verranno richiesti dinamicamente e quindi caricati solo quando saranno effettivamente necessari.

Per ulteriori informazioni sull’utilizzo delle AEM ClientLib da parte dell’Archetipo di progetto, vedi la [documentazione generale del modulo ui.frontend](uifrontend.md#clientlibs).
