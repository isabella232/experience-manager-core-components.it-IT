---
title: Creazione front-end per SPA React
description: Descrizione del processo di build front-end per i progetti SPA basati su React
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 0%

---


# Creazione front-end per SPA di reazione {#frontend-react}

In questo documento vengono illustrati i dettagli del progetto creato quando si utilizza archetype per creare un&#39;applicazione a pagina singola (SPA) basata sul framework React. Ad esempio, quando si imposta l&#39;opzione `frontendModule` su `react`.

## Panoramica {#overview}

Il progetto è stato avviato con [create-response-app](https://github.com/facebook/create-react-app).

Questa applicazione è progettata per utilizzare il modello AEM di un sito. Il layout verrà generato automaticamente utilizzando i componenti helper del pacchetto [@adobe/cq-response-editable-components](https://www.npmjs.com/package/@adobe/cq-react-editable-components).

## Script {#scripts}

Nella directory del progetto potete eseguire i comandi seguenti:

### npm start {#npm-start}

```
npm start
```

Questo comando esegue l&#39;app in modalità di sviluppo eseguendo il proxy del modello JSON da un&#39;istanza AEM locale in esecuzione su http://localhost:4502. Ciò presuppone che l&#39;intero progetto sia stato distribuito per AEM almeno una volta (`mvn clean install -PautoInstallPackage` nella radice del progetto).

Dopo aver eseguito `npm start` nella directory [ui.frontend](uifrontend.md), l&#39;app verrà automaticamente aperta nel browser (nel percorso `http://localhost:3000/content/<appId>/<country>/<language>/home.html`). Se apportate delle modifiche, la pagina verrà ricaricata.

Se si verificano errori relativi a CORS, è possibile configurare AEM come segue:

1. Passare a Gestione configurazione (http://localhost:4502/system/console/configMgr)
1. Aprite la configurazione per &quot;Criteri di condivisione risorse tra le origini di  Adobe Granite&quot;
1. Create una nuova configurazione con i seguenti valori aggiuntivi:
   * Origini consentite: http://localhost:3000
   * Intestazioni supportate: Autorizzazione
   * Metodi Consentiti: OPTIONS 

### test npm {#npm-test}

```
npm test
```

Questo comando avvia il runtime di test nella modalità orologio interattiva. Per ulteriori informazioni, vedere la [React documentation about run test](https://facebook.github.io/create-react-app/docs/running-tests).

### build di esecuzione npm {#npm-run-build}

```
npm run build
```

Questo comando crea l&#39;app per la produzione nella cartella build. Offre la funzione React in modalità di produzione e ottimizza la build per ottenere le migliori prestazioni. Per ulteriori informazioni, consultare la [React documentation about deployment](https://facebook.github.io/create-react-app/docs/deployment).

Inoltre, AEM ClientLib viene generato dall&#39;app utilizzando il pacchetto [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator).

## Supporto browser {#browser-support}

Per impostazione predefinita, questo progetto utilizza l&#39;opzione predefinita di [Browserslist](https://github.com/browserslist/browserslist) per identificare i browser di destinazione. Inoltre, include i riempimenti per le funzioni in lingue moderne per supportare i browser meno recenti (ad esempio Internet Explorer 11). Se il supporto di tali browser non è un requisito, le dipendenze di polifugo e le importazioni possono essere rimosse.

## Suddivisione codice {#code-splitting}

L&#39;app React è configurata per utilizzare per impostazione predefinita [la suddivisione del codice](https://webpack.js.org/guides/code-splitting). Durante la creazione dell&#39;app per la produzione, il codice viene generato in diversi blocchi:

```
$ ls build/static/js
2.5b77f553.chunk.js
2.5b77f553.chunk.js.map
main.cff1a559.chunk.js
main.cff1a559.chunk.js.map
runtime~main.a8a9905a.js
runtime~main.a8a9905a.js.map
```

Il caricamento dei blocchi solo quando sono necessari può migliorare notevolmente le prestazioni dell&#39;app.

Affinché questa funzione funzioni con AEM, l&#39;app deve essere in grado di identificare quali file JS e CSS devono essere richiesti dall&#39;HTML generato da AEM. Questo può essere ottenuto utilizzando la chiave &quot;entrypoints&quot; nel file asset-manifest.json. Il file viene analizzato in clientlib.config.js e solo i file entrypoint sono inclusi nel bundle in ClientLib. I file rimanenti vengono inseriti nella directory delle risorse di ClientLib e vengono richiesti dinamicamente e quindi caricati solo quando sono effettivamente necessari.

Per ulteriori informazioni sull&#39;utilizzo di AEM ClientLibs da parte dell&#39;archetipo del progetto, vedere la documentazione generale del modulo [ui.frontend](uifrontend.md#clientlibs).
