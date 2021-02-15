---
title: Build front-end per SPA angolare
description: Descrizione del processo di compilazione front-end per progetti SPA basati su Angular
translation-type: tm+mt
source-git-commit: 9d737b31efc8c346775ea5296f7599295af07cf1
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 0%

---


# Build front-end per SPA angolare {#frontend-angular}

In questo documento vengono illustrati i dettagli del progetto creato quando si utilizza archetype per creare un&#39;applicazione (SPA) a pagina singola basata sul framework Angular. Ad esempio, quando si imposta l&#39;opzione `frontendModule` su `angular`.

## Panoramica {#overview}

Questo progetto è stato avviato con [CLI angolare](https://github.com/angular/angular-cli).

Questa applicazione è progettata per utilizzare il modello AEM di un sito. Il layout verrà generato automaticamente utilizzando i componenti helper del pacchetto [@adobe/cq-angular-editable-components](https://www.npmjs.com/package/@adobe/cq-angular-editable-components).

## Script {#scripts}

Nella directory del progetto potete eseguire i seguenti comandi.

### npm start {#npm-start}

```
npm start
```

Questo comando esegue l&#39;app in modalità di sviluppo eseguendo il proxy del modello JSON da un&#39;istanza AEM locale in esecuzione su http://localhost:4502. Ciò presuppone che l&#39;intero progetto sia stato distribuito per AEM almeno una volta (`mvn clean install -PautoInstallPackage` nella radice del progetto).

Dopo l&#39;avvio npm nella directory ui.frontend, l&#39;app verrà automaticamente aperta nel browser (nel percorso http://localhost:4200/content/${appId}/${country}/${language}/home.html). Se apportate delle modifiche, la pagina verrà ricaricata.

Se si verificano errori relativi a CORS, è possibile configurare AEM come segue:

1. Passare a Gestione configurazione (http://localhost:4502/system/console/configMgr)
1. Aprite la configurazione per &quot;Criteri di condivisione risorse tra le origini di  Adobe Granite&quot;
1. Create una nuova configurazione con i seguenti valori aggiuntivi:
   * Origini consentite: http://localhost:4200
   * Intestazioni supportate: Autorizzazione
   * Metodi Consentiti: OPTIONS 

### test npm {#npm-test}

```shell
npm test
```

Questo comando avvia il runtime di test Karma. Per ulteriori informazioni, consultare la [Documentazione angolare sull&#39;esecuzione di test](https://angular.io/guide/testing).

### test di esecuzione npm:debug {#npm-run-test-debug}

```shell
npm run test:debug
```

Questo comando avvia il corridore di test Karma in modalità orologio interattiva.

### build di esecuzione npm {#npm-run-build}

```shell
npm run build
```

Questo comando crea l&#39;app per la produzione nella cartella build. Offre il bundle Angular in modalità di produzione e ottimizza la build per ottenere le migliori prestazioni. Per ulteriori informazioni, consultare la [Documentazione angolare sulla distribuzione](https://angular.io/guide/deployment).

Inoltre, AEM ClientLib viene generato dall&#39;app utilizzando il pacchetto [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator).

Per ulteriori informazioni sull&#39;utilizzo di AEM ClientLibs da parte dell&#39;archetipo del progetto, vedere la documentazione generale del modulo [ui.frontend](uifrontend.md#clientlibs).

## Supporto browser {#browser-support}

Per impostazione predefinita, questo progetto utilizza l&#39;opzione predefinita di [Browserslist](https://github.com/browserslist/browserslist) per identificare i browser di destinazione. Inoltre, include i riempimenti per le funzioni in lingue moderne per supportare i browser meno recenti (ad esempio Internet Explorer 11). Se il supporto di tali browser non è un requisito, le dipendenze di polifugo e le importazioni possono essere rimosse.
