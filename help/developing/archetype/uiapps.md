---
title: ui.apps Modulo dell’archivio progetti AEM
description: ui.apps Modulo dell’archivio progetti AEM
translation-type: tm+mt
source-git-commit: 6f7166c46940ed451721e0760d565d58efe412ab
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 0%

---


# ui.apps Modulo dell’archivio progetti AEM {#uiapps-module}

Il modulo ui.apps maven (`<src-directory>/<project>/ui.apps`) include tutto il codice di rendering necessario per il sito sottostante `/apps`. Ciò include CSS/JS che verranno memorizzati in un formato AEM denominato clientlibs. Sono inclusi anche gli script HTL per il rendering HTML dinamico. Il modulo ui.apps può essere considerato come una mappa della struttura nel JCR, ma in un formato che può essere memorizzato in un file system e impegnato nel controllo del codice sorgente.

Il plug-in Apache Jackrabbit FileVault Package viene utilizzato per compilare il contenuto del modulo ui.apps in un pacchetto AEM che può essere distribuito in AEM. Le configurazioni globali per il plug-in sono definite nel file pom.xml principale.

## POM principale {#parent-pom}

[Il POM](/help/developing/archetype/using.md#parent-pom) padre (`<src>/<project>/pom.xml`) include `<plugin>` sezioni che definiscono diverse configurazioni per i plug-in utilizzati nel progetto. Include una configurazione per il plug-in pacchetto `filterSource` Jackrabbit FileVault. Indica `filterSource` la posizione del `filter.xml` file utilizzato per definire i percorsi jcr inclusi nel pacchetto.

Oltre al plug-in Jackrabbit FileVault è una definizione del plug-in Content Package che viene utilizzato per inviare il pacchetto in AEM. Si noti che le variabili per `aem.host`, `aem.port`, `vault.user`e `vault.password` sono utilizzate che corrispondono alle proprietà globali definite nello stesso POM principale.

## ui.apps/pom.xml {#uiapps-pom}

ui.apps pom (`<src>/<project>/ui.apps/pom.xml`) fornisce i `embedded` tag per il `filevault-package-maven-plugin`. I `embedded` tag includono il pacchetto di base compilato come parte del pacchetto ui.apps e dove verrà installato.

I pacchetti core.wcm.components.all e core.wcm.components.example sono inclusi come sottopacchetto. Questo distribuirà il pacchetto Componenti di base insieme al codice WKND ogni volta.

Gli esempi core.wcm.components.all e core.wcm.components.examples sono inclusi come dipendenze nell&#39;elenco delle dipendenze. Tuttavia, come procedura ottimale, le versioni per le dipendenze vengono omesse qui e gestite nel file pom [principale](/help/developing/archetype/using.md#core-components).

## filter.xml {#filter}

Il `filter.xml` file per il modulo ui.apps si trova in `<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml` e contiene i percorsi che verranno inclusi e installati con il pacchetto ui.apps.
