---
title: it.test Modulo AEM Project Archetype
description: Come utilizzare i test di integrazione AEM Project Archetype
translation-type: tm+mt
source-git-commit: 9d737b31efc8c346775ea5296f7599295af07cf1
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 0%

---


# it.test Modulo dell&#39;archivio AEM progetto {#ittests-module}

Il progetto prevede tre livelli di test:

* [Prove di unità](core.md#unit-tests)
* Test di integrazione
* [Test interfaccia](uitests.md)

Questo articolo descrive i test di integrazione disponibili come parte del modulo it.test.

## Esecuzione di test di integrazione {#running-tests}

I test di integrazione lato server consentono l&#39;esecuzione di test simili a quelli dell&#39;unità nell&#39;ambiente AEM, ad esempio sul server AEM. Per eseguire il test, eseguire:

```
mvn clean verify -PintegrationTests
```
