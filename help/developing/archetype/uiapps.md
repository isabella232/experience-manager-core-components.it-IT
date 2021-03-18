---
title: modulo ui.apps del AEM Project Archetype
description: modulo ui.apps del AEM Project Archetype
feature: Componenti core, AEM Project Archetype
role: Architetto, Sviluppatore, Amministratore
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 0%

---


# modulo ui.apps dell&#39;Archetipo di progetto AEM {#uiapps-module}

Il modulo maven ui.apps (`<src-directory>/<project>/ui.apps`) include tutto il codice di rendering necessario per il sito sotto `/apps`. Ciò include CSS/JS che verranno memorizzati in un formato AEM denominato [clientlibs.](uifrontend.md#clientlibs) Sono inclusi anche gli script HTL per il rendering di HTML dinamico. Puoi considerare il modulo ui.apps come una mappa della struttura nel JCR, ma in un formato che può essere memorizzato in un file system e impegnato nel controllo del codice sorgente.

Il plug-in Apache Jackrabbit FileVault Package viene utilizzato per compilare il contenuto del modulo ui.apps in un pacchetto AEM che può essere distribuito a AEM. Le configurazioni globali per il plug-in sono definite nel file pom.xml principale.

## POM padre {#parent-pom}

[Il POM](/help/developing/archetype/using.md#parent-pom)  padre (`<src>/<project>/pom.xml`) include  `<plugin>` sezioni che definiscono diverse configurazioni per i plug-in utilizzati nel progetto. Questo include una configurazione per `filterSource` per il plug-in pacchetto Jackrabbit FileVault. Il `filterSource` punta alla posizione del file `filter.xml` utilizzato per definire i percorsi jcr inclusi nel pacchetto.

Oltre al plugin Jackrabbit FileVault Package è una definizione del plugin Content Package che viene utilizzato per poi spingere il pacchetto in AEM. Si noti che le variabili per `aem.host`, `aem.port`, `vault.user` e `vault.password` sono utilizzate che corrispondono alle proprietà globali definite nello stesso POM principale.

## ui.apps/pom.xml {#uiapps-pom}

Il file pom ui.apps (`<src>/<project>/ui.apps/pom.xml`) fornisce i tag `embedded` per il tag `filevault-package-maven-plugin`. I tag `embedded` includono il bundle core compilato come parte del pacchetto ui.apps e dove verrà installato.

I pacchetti core.wcm.components.all e core.wcm.components.examples sono inclusi come pacchetto secondario. Questo distribuirà ogni volta il pacchetto dei componenti core insieme al codice WKND.

Gli esempi core.wcm.components.all e core.wcm.components.examples sono inclusi come dipendenze nell’elenco delle dipendenze. Tuttavia, come best practice, le versioni per le dipendenze vengono omesse qui e gestite nel [file pom padre](/help/developing/archetype/using.md#core-components).

## filter.xml {#filter}

Il file `filter.xml` per il modulo ui.apps si trova in `<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml` e contiene i percorsi che verranno inclusi e installati con il pacchetto ui.apps .
