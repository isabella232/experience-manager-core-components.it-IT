---
title: Modulo principale dell’Archetipo di progetto AEM
description: Modulo principale dell’Archetipo di progetto AEM
feature: Componenti core, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 49e80d8c-2b41-4c42-b45e-c2e3b4b16a59
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# Modulo principale dell’Archetipo di progetto AEM {#core-module}

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
