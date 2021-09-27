---
title: Modulo core Archetipo progetto AEM
description: Modulo core Archetipo progetto AEM
feature: Componenti core, Archetipo progetto AEM
role: Architect, Developer, Admin
exl-id: 49e80d8c-2b41-4c42-b45e-c2e3b4b16a59
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '187'
ht-degree: 100%

---

# Modulo core Archetipo progetto AEM {#core-module}

Il modulo maven ui.apps (`<src-directory>/<project>/core`) include tutto il codice Java necessario per l’implementazione. Il modulo riunisce in un pacchetto tutto il codice Java e lo distribuisce all’istanza di AEM come Bundle OSGi.

Il plug-in Maven Bundle definito in `<src-directory>/<project>/core/pom.xml` è responsabile della compilazione del codice Java in un bundle OSGi che può essere riconosciuto dal contenitore OSGi di AEM. Tieni presente che è qui che è definita la posizione dei modelli Sling.

Sebbene sia raro che il bundle core debba essere distribuito indipendentemente dal modulo ui.apps negli ambienti di livello superiore, la distribuzione diretta del bundle core è utile durante lo sviluppo e i test locali. Il plug-in Maven Sling consente di distribuire il bundle core ad AEM utilizzando direttamente il profilo `autoInstallBundle` come definito nel [POM (Project Object Model) padre](/help/developing/archetype/using.md#parent-pom).

```shell
mvn -PautoInstallBundle clean install
```

Una volta eseguita correttamente la distribuzione, dovresti poter visualizzare la console dei bundle in `http://<host>:<port>/system/console/bundles`.

## Test unità {#unit-tests}

Il test unità nel modulo core mostra i classici test unità del codice contenuto nel bundle. Per effettuare il test, esegui:

```shell
mvn clean test
```
