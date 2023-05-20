---
title: Modulo it.tests di Archetipo progetto AEM
description: Come utilizzare gli integration test di Archetipo progetto AEM
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 0abc0265-3a3f-4323-97e6-3af0c62299ef
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 100%

---

# Modulo it.tests di Archetipo progetto AEM {#ittests-module}

Il progetto prevede tre livelli di test:

* [Test unità](core.md#unit-tests)
* Integration test
* [Test dell’interfaccia utente](uitests.md)

Questo articolo descrive gli integration test disponibili come parte del modulo it.tests.

## Esecuzione degli integration test {#running-tests}

Gli integration test lato server consentono l’esecuzione di test unità in ambiente AEM, ad esempio sul server AEM. Per effettuare il test, esegui:

```
mvn clean verify -PintegrationTests
```
