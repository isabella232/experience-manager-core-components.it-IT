---
title: ui.test Modulo AEM Project Archetype
description: Come utilizzare i test JUnit AEM Project Archetype
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 0%

---


# ui.test Modulo dell&#39;archivio AEM progetto {#uitests-module}

Il progetto prevede tre livelli di test:

## Prove di unità {#unit-tests}

Il test dell&#39;unità nel modulo [core](core.md) mostra il test dell&#39;unità classica per il codice contenuto nel pacchetto. Per eseguire il test, eseguire:

```
mvn clean test
```

## Test di integrazione {#integration-tests}

I test di integrazione lato server consentono l&#39;esecuzione di test simili a quelli dell&#39;unità nell&#39;ambiente AEM, ad esempio sul server AEM. Per eseguire il test, eseguire:

```
mvn clean verify -PintegrationTests
```

## Test lato client {#client-side-tests}

I `client-side Hobbes.js` test sono test basati su JavaScript basati su browser che verificano il comportamento sul lato browser.

Per eseguire il test, quando si visualizza una pagina AEM che si desidera testare nel browser, aprire la pagina in **Modalità Sviluppatore** aprendo il pannello a sinistra e passando alla scheda **Test**, individuare i **MyName Tests** generati ed eseguirli.
