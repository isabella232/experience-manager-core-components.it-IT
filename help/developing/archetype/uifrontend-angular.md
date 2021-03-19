---
title: Generazione front-end, ad Angular SPA
description: Una descrizione del processo di compilazione front-end per i progetti SPA basati su Angular
feature: Componenti core, AEM Project Archetype
role: Architetto, Sviluppatore, Amministratore
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 0%

---


# Build front-end, ad Angular SPA {#frontend-angular}

In questo documento vengono illustrati i dettagli del progetto creato quando si utilizza l’archetipo per creare un’applicazione a pagina singola (SPA) basata sul framework di Angular. Ad esempio, quando imposti l’opzione `frontendModule` su `angular`.

## Panoramica {#overview}

Questo progetto è stato avviato con l&#39;Angular CLI](https://github.com/angular/angular-cli) [di.

Questa applicazione è creata per utilizzare il modello AEM di un sito. Genererà automaticamente il layout utilizzando i componenti helper del pacchetto [@adobe/cq-angular-editable-components](https://www.npmjs.com/package/@adobe/cq-angular-editable-components) .

## Script {#scripts}

Nella directory di progetto, è possibile eseguire i seguenti comandi.

### inizio npm {#npm-start}

```
npm start
```

Questo comando esegue l&#39;app in modalità di sviluppo tramite il proxy del modello JSON da un&#39;istanza AEM locale in esecuzione su http://localhost:4502. Ciò presuppone che l’intero progetto sia stato distribuito per AEM almeno una volta (`mvn clean install -PautoInstallPackage` nella directory principale del progetto).

Dopo aver eseguito npm start nella directory ui.frontend, l’app verrà automaticamente aperta nel browser (nel percorso http://localhost:4200/content/${appId}/${country}/${language}/home.html). Se apporti modifiche, la pagina verrà ricaricata.

Se ricevi errori relativi a CORS, configura AEM come segue:

1. Passa a Configuration Manager (http://localhost:4502/system/console/configMgr)
1. Apri la configurazione per &quot;Adobe Granite Cross-Origin Resource Sharing Policy&quot;
1. Crea una nuova configurazione con i seguenti valori aggiuntivi:
   * Origini consentite: http://localhost:4200
   * Intestazioni supportate: Autorizzazione
   * Metodi consentiti: OPTIONS

### test npm {#npm-test}

```shell
npm test
```

Questo comando avvia il runner di test Karma. Per ulteriori informazioni, consulta la [documentazione di Angular sull&#39;esecuzione di test](https://angular.io/guide/testing) .

### test di esecuzione npm:debug {#npm-run-test-debug}

```shell
npm run test:debug
```

Questo comando avvia il runner di test Karma in modalità orologio interattivo.

### build di esecuzione npm {#npm-run-build}

```shell
npm run build
```

Questo comando crea l&#39;app per la produzione nella cartella build. Offre l&#39;Angular in modalità di produzione e ottimizza la build per ottenere le migliori prestazioni. Per ulteriori informazioni, consulta la [documentazione di Angular sulla distribuzione](https://angular.io/guide/deployment) .

Inoltre, un AEM ClientLib viene generato dall&#39;app utilizzando il pacchetto [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator) .

Per ulteriori informazioni sull&#39;utilizzo di ClientLibs AEM dall&#39;archetipo del progetto, consulta la documentazione generale del modulo [ui.frontend](uifrontend.md#clientlibs) .

## Supporto browser {#browser-support}

Per impostazione predefinita, questo progetto utilizza l&#39;opzione predefinita [BrowserList](https://github.com/browserslist/browserslist) per identificare i browser di destinazione. Inoltre, include i polyfills per le funzioni della lingua moderna per supportare i browser più vecchi (ad esempio Internet Explorer 11). Se il supporto di tali browser non è un requisito, le dipendenze di polyfill e le importazioni possono essere rimosse.
