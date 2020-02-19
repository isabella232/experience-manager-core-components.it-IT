---
title: ui.test Modulo di archivio progetti AEM
description: Come utilizzare i test JUnit di tipo archivio AEM Project
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# ui.test Modulo dell’archivio del progetto AEM {#uitests-module}

Il progetto prevede tre livelli di test:

## Prove di unità {#unit-tests}

Il test dell&#39;unità nel modulo [](core.md) principale mostra il test classico dell&#39;unità del codice contenuto nel pacchetto. Per eseguire il test, eseguire:

```
mvn clean test
```

## Test di integrazione {#integration-tests}

I test di integrazione lato server consentono l’esecuzione di test di tipo unit nell’ambiente AEM, ad esempio sul server AEM. Per eseguire il test, eseguire:

```
mvn clean verify -PintegrationTests
```

## Test lato client {#client-side-tests}

I `client-side Hobbes.js` test sono test basati su JavaScript basati su browser che verificano il comportamento sul lato browser.

Per verificare, quando visualizzate una pagina AEM da sottoporre a test nel browser, aprite la pagina in modalità **** Sviluppatore aprendo il pannello a sinistra e passando alla scheda **Test** , individuate e eseguite i test **** MyName generati.
