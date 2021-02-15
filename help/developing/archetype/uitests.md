---
title: ui.test Modulo AEM Project Archetype
description: Come utilizzare i test dell'interfaccia utente AEM tipo archivio progetti
translation-type: tm+mt
source-git-commit: 9d737b31efc8c346775ea5296f7599295af07cf1
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---


# ui.test Modulo dell&#39;archivio AEM progetto {#uitests-module}

Il progetto prevede tre livelli di test:

* [Prove di unità](core.md#unit-tests)
* [Test di integrazione](ittests.md)
* Test interfaccia

Questo articolo descrive i test di interfaccia utente disponibili come parte del modulo ui.test.

## Esecuzione di test dell&#39;interfaccia utente {#running-tests}

Per eseguire il test, eseguire:

```shell
mvn verify -Pui-tests-local-execution
```

Dopo l&#39;esecuzione, i report e i file di registro sono disponibili nella cartella `target/reports`.

## Opzioni aggiuntive {#additional-options}

I test dell&#39;interfaccia utente possono essere eseguiti con diverse opzioni, tra cui test headless su un browser locale e come immagine Docker. Per ulteriori informazioni, vedere il file [README.md del modulo ui.test](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/ui.tests).
