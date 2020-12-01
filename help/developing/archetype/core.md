---
title: Modulo di base del tipo di archivio del progetto AEM
description: Modulo di base del tipo di archivio del progetto AEM
translation-type: tm+mt
source-git-commit: 6f7166c46940ed451721e0760d565d58efe412ab
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 0%

---


# Modulo di base dell&#39;archivio AEM progetto {#core-module}

Il modulo core maven (`<src-directory>/<project>/core`) include tutto il codice Java necessario per l&#39;implementazione. Il modulo crea un pacchetto con tutto il codice Java e distribuisce nell’istanza AEM come Bundle OSGi.

Il plug-in Maven Bundle definito in `<src-directory>/<project>/core/pom.xml` è responsabile della compilazione del codice Java in un bundle OSGi che può essere riconosciuto AEM contenitore OSGi. Tenere presente che in questo punto è definita la posizione di Sling Models.

Anche se è raro che il bundle principale debba essere distribuito indipendentemente dal modulo ui.apps negli ambienti di livello superiore, la distribuzione diretta del bundle principale è utile durante lo sviluppo e il test locali. Il plug-in Maven Sling consente di distribuire il pacchetto di base per AEM direttamente utilizzando il profilo `autoInstallBundle` come definito nel [POM](/help/developing/archetype/using.md#parent-pom) padre.

```
mvn -PautoInstallBundle clean install
```

Una volta eseguita correttamente, dovreste essere in grado di visualizzare la console Bundles in `http://<host>:<port>/system/console/bundles`.
