---
title: Script in bundle precompilati
description: Scopri come distribuire gli script dei componenti tramite bundle OSGi in Adobe Experience Manager Cloud Service.
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 3edc388f-01b2-45cc-bd56-f22e5a5a8624
source-git-commit: 554be9539428cd75462a38fc45f1bece04baf066
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 53%

---


# Script in bundle precompilati {#precompiled-bundled-scripts}

AEM as a Cloud Service supporta la distribuzione di script di componenti [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=it#code-packages-%2F-osgi-bundles) come script in bundle precompilati. Questo consente agli sviluppatori di precompilare gli script in fase di generazione della build e di assemblarli come bundle OSGi.

## Vantaggi della distribuzione di script precompilati tramite bundle OSGi {#advantages}

La distribuzione di script in bundle precompilati presenta i seguenti vantaggi:

+ La compilazione degli script in fase di creazione consente agli sviluppatori di individuare gli errori nelle prime fasi del processo di sviluppo.
+ Le dipendenze degli script da API Java sono esplicitamente definite tramite `Import-Package` e `Export-Package` intestazioni del bundle.
+ Ereditarietà (tramite `sling:resourceSuperType`) e la delega ad altri tipi di risorse (tramite HTL `data-sly-resource` blocco o tramite il `sling:include` Il tag JSP, ad esempio) può essere mappato tramite i metadati del bundle.
+ Il controllo delle versioni del tipo di risorsa può essere applicato in modo simile alle API Java.

## Precompilazione e importazioni dei pacchetti {#precompilation}

[`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html) può convalidare la sintassi degli script HTL, ma può anche essere utilizzata per eseguire la transpilazione degli script HTL in classi Java. Questi vengono quindi aggiunti alla cartella `generated-sources` del progetto Maven e selezionati da `maven-compiler-plugin`.

È possibile aggiungere [`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin) per generare i metadati del bundle OSGi per le importazioni API Java.

## Ereditarietà e delega {#inheritance-delegation}

Il framework OSGi permette di definire [requisiti e funzionalità](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies) per esprimere contratti tra vari componenti. Questi vengono descritti tramite metadati e applicati in fase di runtime. Gli script in bundle utilizzano questo meccanismo per esprimere sia le relazioni di ereditarietà (`sling:resourceSuperType`) che la delega (anche per altri tipi di risorse nel processo di rendering).

Il `bnd` plug-in da [scriptingbundle-maven-plugin](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html) project può essere utilizzato per estrarre i requisiti e le funzionalità corrispondenti agli script forniti da [`ui.apps`.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=it#code-packages-%2F-osgi-bundles) pacchetto di contenuti

## Supporto di Archetipo progetto AEM {#support}

A partire dalla versione 31, il [Archetipo progetto AEM](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html?lang=it) può essere utilizzato per configurare correttamente un progetto as a Cloud Service dell’AEM per l’utilizzo di script in bundle precompilati.

Inoltre, l’Archetipo progetto AEM configura il [plug-in Maven di Build Analyzer per AEM as a Cloud Service SDK](/help/developing/archetype/build-analyzer-maven-plugin.md) per convalidare le dipendenze a livello di pacchetto Java e di script.
