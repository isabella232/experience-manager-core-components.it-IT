---
title: Script in bundle precompilati
description: Scopri come distribuire gli script dei componenti tramite bundle OSGi in Adobe Experience Manager Cloud Service.
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 3edc388f-01b2-45cc-bd56-f22e5a5a8624
source-git-commit: b39cd395d17f6aab7376e01fc01a7c0e98b2460f
workflow-type: ht
source-wordcount: '378'
ht-degree: 100%

---


# Script in bundle precompilati

AEM as a Cloud Service supporta la distribuzione di script di componenti [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=it#code-packages-%2F-osgi-bundles) come script in bundle precompilati. Questo consente agli sviluppatori di precompilare gli script in fase di generazione della build e di assemblarli come bundle OSGi.

## Vantaggi della distribuzione di script precompilati tramite bundle OSGi

La distribuzione di script in bundle precompilati presenta i seguenti vantaggi:

+ La compilazione degli script in fase di generazione della build consente agli sviluppatori di individuare gli errori nelle prime fasi del processo di sviluppo.
+ Le dipendenze degli script da API Java sono esplicitamente definite tramite le intestazioni del bundle `Import-Package` e `Export-Package`
+ L’ereditarietà (tramite `sling:resourceSuperType`) e la delega ad altri tipi di risorse (ad esempio tramite l’elemento blocco HTL `data-sly-resource` o tramite il tag JSP `sling:include`) possono essere mappate tramite i metadati del bundle.
+ Il controllo delle versioni del tipo di risorsa può essere applicato in modo simile alle API Java.

## Precompilazione e importazioni di pacchetti

[`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html) può convalidare la sintassi degli script HTL, ma può anche essere utilizzata per eseguire la transpilazione degli script HTL in classi Java. Questi vengono quindi aggiunti alla cartella `generated-sources` del progetto Maven e selezionati da `maven-compiler-plugin`.

È possibile aggiungere [`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin) per generare i metadati del bundle OSGi per le importazioni API Java.

## Ereditarietà e delega

Il framework OSGi permette di definire [Requisiti e funzionalità](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies) per esprimere relazioni e vincoli tra vari componenti. Questi vengono descritti tramite metadati e applicati in fase di runtime. Gli script in bundle utilizzano questo meccanismo per esprimere sia le relazioni di ereditarietà (`sling:resourceSuperType`) che la delega (anche per altri tipi di risorse nel processo di rendering).

Il plug-in `bnd` dal progetto [scriptingbundle-maven-plugin](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html) può essere utilizzato per estrarre i requisiti e le funzionalità in base agli script forniti dal pacchetto di contenuti [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=it#code-packages-%2F-osgi-bundles).

## Supporto di Archetipo progetto AEM

A partire dalla versione 31, è possibile utilizzare il modello [Archetipo progetto AEM](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html?lang=it) per impostare correttamente un progetto AEM as a Cloud Service per l’utilizzo di script in bundle precompilati. Inoltre, l’Archetipo progetto AEM configura il [plug-in Maven di Build Analyzer per AEM as a Cloud Service SDK](/help/developing/archetype/build-analyzer-maven-plugin.md) per convalidare le dipendenze a livello di pacchetto Java e di script.
