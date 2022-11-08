---
title: Modulo ui.apps di Archetipo progetto AEM
description: Modulo ui.apps di Archetipo progetto AEM
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: fc63a19a-3253-44ee-96e2-bb5544c2235b
source-git-commit: 19bceb1d8ba07c70798f2e7203db957d3e8b3d03
workflow-type: ht
source-wordcount: '308'
ht-degree: 100%

---

# Modulo ui.apps di Archetipo progetto AEM {#uiapps-module}

Il modulo maven ui.apps (`<src-directory>/<project>/ui.apps`) include tutto il codice di rendering necessario per il sito sotto `/apps`. Ciò include i file CSS/JS che verranno memorizzati in un formato AEM denominato [clientlibs.](uifrontend.md#clientlibs) Sono inclusi anche gli script HTL per il rendering del codice HTML dinamico. Puoi considerare il modulo ui.apps come una mappa della struttura contenuta nel Java Content Repository (JCR), ma in un formato che può essere memorizzato in un file system e impegnato nel controllo del codice sorgente.

Il plug-in Apache Jackrabbit FileVault Package viene utilizzato per compilare il contenuto del modulo ui.apps in un pacchetto AEM che può essere distribuito ad AEM. Le configurazioni globali del plug-in sono definite nel file pom.xml padre.

## POM (Project Object Model) padre {#parent-pom}

[Il POM padre](/help/developing/archetype/using.md#parent-pom) (`<src>/<project>/pom.xml`) include sezioni `<plugin>` che definiscono le varie configurazioni dei plug-in utilizzati nel progetto. È inclusa anche una configurazione per la proprietà `filterSource` del plug-in Jackrabbit FileVault Package. La proprietà `filterSource` punta alla posizione del file `filter.xml` utilizzato per definire i percorsi JCR inclusi nel pacchetto.

Oltre al plug-in Jackrabbit FileVault Package, esiste una definizione del plug-in Content Package che viene utilizzato per poi inviare il pacchetto ad AEM. Considera che per `aem.host`, `aem.port`, `vault.user` e `vault.password` sono utilizzate delle variabili corrispondenti alle proprietà globali definite nello stesso POM padre.

## ui.apps/pom.xml {#uiapps-pom}

Considera che i pacchetti core.wcm.components.all e core.wcm.components.examples sono inclusi come un unico pacchetto secondario. Questo distribuirà ogni volta il pacchetto dei Componenti core insieme al codice WKND.

I pacchetti core.wcm.components.all e core.wcm.components.examples sono anche inclusi come dipendenze nell’elenco delle dipendenze. Tuttavia, come best practice, le versioni delle dipendenze vengono omesse in questa fase e sono gestite nel [file POM padre](/help/developing/archetype/using.md#core-components).

## File filter.xml {#filter}

Il file `filter.xml` del modulo ui.apps si trova in `<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml` e contiene i percorsi che verranno inclusi e installati con il pacchetto ui.apps.
