---
title: Modulo principale dell’Archetipo di progetto AEM
description: Modulo principale dell’Archetipo di progetto AEM
feature: Componenti core, AEM Project Archetype
role: Architetto, Sviluppatore, Amministratore
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---


# Modulo di base dell&#39;Archetipo di progetto AEM {#core-module}

Il modulo maven di base (`<src-directory>/<project>/core`) include tutto il codice Java necessario per l&#39;implementazione. Il modulo raggrupperà tutto il codice Java e lo distribuirà nell’istanza AEM come Bundle OSGi.

Il plug-in Bundle Maven definito in `<src-directory>/<project>/core/pom.xml` è responsabile della compilazione del codice Java in un bundle OSGi che può essere riconosciuto da AEM contenitore OSGi. Tieni presente che è qui che è definita la posizione dei modelli Sling.

Sebbene sia raro che il bundle principale debba essere distribuito indipendentemente dal modulo ui.apps negli ambienti di livello superiore, la distribuzione diretta del bundle principale è utile durante lo sviluppo/il test locali. Il plug-in Maven Sling consente di implementare il bundle principale per AEM sfruttando direttamente il profilo `autoInstallBundle` come definito nel [POM principale](/help/developing/archetype/using.md#parent-pom).

```shell
mvn -PautoInstallBundle clean install
```

Una volta eseguita correttamente, dovresti essere in grado di visualizzare la console Bundles in `http://<host>:<port>/system/console/bundles`.

##  Test di unità {#unit-tests}

Il test di unità nel modulo principale mostra il classico unit testing del codice contenuto nel bundle. Per eseguire il test, esegui:

```shell
mvn clean test
```
