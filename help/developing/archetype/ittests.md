---
title: modulo it.test di AEM Project Archetype
description: Come utilizzare i test di integrazione di AEM Project Archetype
feature: Componenti core, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 0abc0265-3a3f-4323-97e6-3af0c62299ef
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '80'
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
