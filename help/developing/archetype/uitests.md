---
title: Modulo ui.tests di Archetipo progetto AEM
description: Come utilizzare i test dell’interfaccia utente di Archetipo progetto AEM
feature: Componenti core, Archetipo progetto AEM
role: Architect, Developer, Admin
exl-id: eb3c9b34-f10e-410f-bcf3-34f94f124c7c
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '117'
ht-degree: 100%

---

# Modulo ui.tests di Archetipo progetto AEM {#uitests-module}

Il progetto prevede tre livelli di test:

* [Test unità](core.md#unit-tests)
* [Integration test](ittests.md)
* Test dell’interfaccia utente

Questo articolo descrive i test dell’interfaccia utente disponibili come parte del modulo ui.tests.

## Esecuzione dei test dell’interfaccia utente {#running-tests}

Per effettuare il test, esegui:

```shell
mvn verify -Pui-tests-local-execution
```

Dopo l’esecuzione, i report e i registri sono disponibili nella cartella `target/reports`.

## Opzioni aggiuntive {#additional-options}

I test dell’interfaccia utente possono essere eseguiti con diverse opzioni, tra cui test senza intestazione su un browser locale e come immagine Docker. Per ulteriori informazioni, vedi il file [README.md del modulo ui.tests](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/ui.tests).
