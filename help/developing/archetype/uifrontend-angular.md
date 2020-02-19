---
title: Build front-end per SPA angolari
description: Descrizione del processo di costruzione front-end per i progetti SPA basati su Angular
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Build front-end per SPA angolari {#frontend-angular}

In questo documento vengono illustrati i dettagli del progetto creato utilizzando archetype per creare un&#39;applicazione SPA (Single Page Application) basata sul framework Angular. Ad esempio, quando si imposta l’ `frontendModule` opzione su `angular`.

## Panoramica {#overview}

Questo progetto è stato avviato con l&#39;interfaccia [angolare CLI](https://github.com/angular/angular-cli).

Questa applicazione è progettata per utilizzare il modello AEM di un sito. Viene generato automaticamente il layout utilizzando i componenti helper del pacchetto [@adobe/cq-angular-editable-components](https://www.npmjs.com/package/@adobe/cq-angular-editable-components) .

## Script {#scripts}

Nella directory del progetto potete eseguire i seguenti comandi.

### npm start {#npm-start}

```
npm start
```

Questo comando esegue l’app in modalità di sviluppo eseguendo il proxy del modello JSON da un’istanza AEM locale in esecuzione su http://localhost:4502. Ciò presuppone che l’intero progetto sia stato distribuito in AEM almeno una volta (`mvn clean install -PautoInstallPackage` nella directory principale del progetto).

Dopo l&#39;avvio npm nella directory ui.frontend, l&#39;app verrà automaticamente aperta nel browser (nel percorso http://localhost:4200/content/${appId}/${country}/${language}/home.html). Se apportate delle modifiche, la pagina verrà ricaricata.

Se si verificano errori relativi a CORS, è possibile configurare AEM come segue:

1. Passare a Gestione configurazione (http://localhost:4502/system/console/configMgr)
1. Aprite la configurazione per &quot;Criteri di condivisione risorse tra le origini di Adobe Granite&quot;
1. Create una nuova configurazione con i seguenti valori aggiuntivi:
   * Origini consentite: http://localhost:4200
   * Intestazioni supportate:Autorizzazione
   * Metodi Consentiti: OPZIONI

### test NPM {#npm-test}

```
npm test
```

Questo comando avvia il runtime di test Karma. Per ulteriori informazioni, consulta la documentazione [Angular sull’esecuzione di test](https://angular.io/guide/testing) .

### test di esecuzione npm:debug {#npm-run-test-debug}

```
npm run test:debug
```

Questo comando avvia il corridore di prova Karma in modalità orologio interattiva.

### build di esecuzione npm {#npm-run-build}

```
npm run build
```

Questo comando crea l&#39;app per la produzione nella cartella build. Offre il bundle Angular in modalità di produzione e ottimizza la build per ottenere le migliori prestazioni. Per ulteriori informazioni, consulta la documentazione [angolare sulla distribuzione](https://angular.io/guide/deployment) .

Inoltre, AEM ClientLib viene generato dall&#39;app utilizzando il pacchetto [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator) .

Per ulteriori informazioni sull’utilizzo di AEM ClientLibs da parte dell’archetipo del progetto, consulta la documentazione [generale del modulo](uifrontend.md#clientlibs) ui.frontend.

## Supporto browser {#browser-support}

Per impostazione predefinita, questo progetto utilizza l&#39;opzione predefinita [Browser](https://github.com/browserslist/browserslist)per identificare i browser di destinazione. Inoltre, include i riempimenti per le funzioni in lingue moderne per supportare i browser meno recenti (ad esempio Internet Explorer 11). Se il supporto di tali browser non è un requisito, le dipendenze di polifugo e le importazioni possono essere rimosse.
