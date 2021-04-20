---
title: modulo ui.test di AEM Project Archetype
description: Come utilizzare i test dell’interfaccia utente di AEM Project Archetype
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 0%

---


# modulo ui.test dell&#39;Archetipo di progetto AEM {#uitests-module}

Il progetto prevede tre livelli di test:

* [Test di unità](core.md#unit-tests)
* [Test di integrazione](ittests.md)
* Test dell&#39;interfaccia utente

Questo articolo descrive i test dell&#39;interfaccia utente disponibili come parte del modulo ui.test .

## Esecuzione di test dell&#39;interfaccia utente {#running-tests}

Per eseguire il test, esegui:

```shell
mvn verify -Pui-tests-local-execution
```

Dopo l’esecuzione, i rapporti e i registri sono disponibili nella cartella `target/reports` .

## Opzioni aggiuntive {#additional-options}

I test dell’interfaccia utente possono essere eseguiti con diverse opzioni, tra cui per test headless su un browser locale e come immagine Docker. Per ulteriori informazioni, consulta il file [README.md del modulo ui.test](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/ui.tests) .
