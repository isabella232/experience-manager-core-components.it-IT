---
title: Modulo di base dell’archivio del progetto AEM
seo-title: Modulo di base dell’archivio del progetto AEM
description: Modulo di base dell’archivio del progetto AEM
seo-description: Modulo di base dell’archivio del progetto AEM
contentOwner: bohnert
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: 683b4f4705c226275439a408423cbf1b23bea66f

---


# Modulo di base dell’archivio del progetto AEM {#core-module}

Il modulo core maven (`<src-directory>/<project>/core`) include tutto il codice Java necessario per l'implementazione. Il modulo crea un pacchetto con tutto il codice Java e distribuisce nell’istanza AEM come un pacchetto OSGi.

Il plug-in Maven Bundle definito in `<src-directory>/<project>/core/pom.xml` è responsabile della compilazione del codice Java in un bundle OSGi che può essere riconosciuto dal contenitore OSGi di AEM. Tenere presente che in questo punto è definita la posizione di Sling Models.

Anche se è raro che il bundle principale debba essere distribuito indipendentemente dal modulo ui.apps negli ambienti di livello superiore, la distribuzione diretta del bundle principale è utile durante lo sviluppo e il test locali. Il plug-in Maven Sling consente di distribuire il bundle core ad AEM sfruttando direttamente il `autoInstallBundle` profilo come definito nel POM [](overview.md#parent-pom)padre.

```
mvn -PautoInstallBundle clean install
```

Una volta eseguita correttamente, dovreste essere in grado di visualizzare la console Bundels all'indirizzo `http://<host>:<port>/system/console/bundles`.
