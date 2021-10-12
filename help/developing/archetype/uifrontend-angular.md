---
title: Sviluppo front-end per SPA Angular
description: Una descrizione del processo di sviluppo front-end per i progetti SPA basati su Angular
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 5726e29d-081c-42bb-bf4e-2852043b21d6
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '404'
ht-degree: 100%

---

# Sviluppo front-end per SPA Angular {#frontend-angular}

In questo documento vengono illustrati i dettagli del progetto creato quando si utilizza l’archetipo per creare un’applicazione a pagina singola (SPA) basata sul framework Angular. Ad esempio, quando imposti l’opzione `frontendModule` su `angular`.

## Panoramica {#overview}

Questo progetto è stato avviato con [l’interfaccia della riga di comando Angular](https://github.com/angular/angular-cli).

Questa applicazione è stata sviluppata per avvalersi del modello AEM di un sito. Genera automaticamente il layout utilizzando i componenti helper del pacchetto [@adobe/cq-angular-editable-components](https://www.npmjs.com/package/@adobe/cq-angular-editable-components).

## Script {#scripts}

Nella directory del progetto, è possibile eseguire i comandi sotto riportati.

### npm start {#npm-start}

```
npm start
```

Questo comando esegue l’app in modalità di sviluppo tramite il proxy del modello JSON da un’istanza di AEM locale in esecuzione su http://localhost:4502. Ciò presuppone che l’intero progetto sia stato distribuito ad AEM almeno una volta (`mvn clean install -PautoInstallPackage` nella directory principale del progetto).

Dopo aver eseguito il comando npm start nella directory ui.frontend, l’app viene automaticamente aperta nel browser (nel percorso http://localhost:4200/content/${appId}/${paese}/${lingua}/home.html). Se apporti modifiche, la pagina viene ricaricata.

Se ricevi errori relativi a CORS, configura AEM come segue:

1. Vai a Gestione configurazione (http://localhost:4502/system/console/configMgr)
1. Apri la configurazione per &quot;Adobe Granite Cross-Origin Resource Sharing Policy&quot;
1. Crea una nuova configurazione con i seguenti valori aggiuntivi:
   * Origini consentite: http://localhost:4200
   * Intestazioni supportate: autorizzazione
   * Metodi consentiti: OPZIONI

### npm test {#npm-test}

```shell
npm test
```

Questo comando avvia l’esecuzione del test Karma. Per ulteriori informazioni, vedi la [documentazione di Angular sull’esecuzione dei test](https://angular.io/guide/testing).

### npm run test:debug {#npm-run-test-debug}

```shell
npm run test:debug
```

Questo comando avvia l’esecuzione dei test Karma in modalità espressione di controllo interattivo.

### npm run build {#npm-run-build}

```shell
npm run build
```

Questo comando esegue lo sviluppo dell’app per la produzione nella cartella di sviluppo. Crea il bundle Angular in modalità di produzione e ottimizza lo sviluppo per ottenere le migliori prestazioni. Per ulteriori informazioni, vedi la [documentazione di Angular sulla distribuzione](https://angular.io/guide/deployment).

Inoltre, dall’app viene generata un’AEM ClientLib utilizzando il pacchetto [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator).

Per ulteriori informazioni sull’utilizzo delle AEM ClientLib da parte dell’Archetipo di progetto, vedi la [documentazione generale del modulo ui.frontend](uifrontend.md#clientlibs).

## Supporto del browser {#browser-support}

Per impostazione predefinita, questo progetto utilizza l’opzione predefinita [Browserslist](https://github.com/browserslist/browserslist) per identificare i browser di destinazione. Inoltre, include i polyfill per permettere alle moderne funzioni di lingua di supportare i browser precedenti (ad esempio, Internet Explorer 11). Se il supporto di questi browser non è un requisito, le dipendenze e importazioni di polyfill possono essere rimosse.
