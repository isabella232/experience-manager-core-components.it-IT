---
title: modulo it.test di AEM Project Archetype
description: Come utilizzare i test di integrazione di AEM Project Archetype
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 0%

---


# modulo it.testing dell&#39;Archetipo di progetto AEM {#ittests-module}

Il progetto prevede tre livelli di test:

* [Test di unità](core.md#unit-tests)
* Test di integrazione
* [Test dell&#39;interfaccia utente](uitests.md)

Questo articolo descrive i test di integrazione disponibili come parte del modulo it.testing .

## Esecuzione di test di integrazione {#running-tests}

I test di integrazione lato server consentono l’esecuzione di test di tipo unit nell’ambiente AEM, ad esempio sul server AEM. Per eseguire il test, esegui:

```
mvn clean verify -PintegrationTests
```
