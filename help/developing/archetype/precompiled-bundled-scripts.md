---
title: Script raggruppati precompilati
description: Scopri come distribuire gli script dei componenti tramite i bundle OSGi al Cloud Service Adobe Experience Manager.
source-git-commit: 56464decc8d6ae3cef68d62bfe459bceda0539ef
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# Script raggruppati precompilati

AEM come Cloud Service supporta la distribuzione degli script di componenti [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles) come script di bundle precompilati. Questo consente agli sviluppatori di precompilare i loro script in fase di creazione e di assemblarli come bundle OSGi.

## Vantaggi della distribuzione di script precompilati tramite i bundle OSGi

La distribuzione degli script come script raggruppati precompilati presenta i seguenti vantaggi:

+ la compilazione degli script in fase di creazione consente agli sviluppatori di individuare gli errori nelle prime fasi del processo di sviluppo
+ Le dipendenze degli script Java API sono esplicitamente definite tramite le intestazioni del bundle `Import-Package` e `Export-Package`
+ L’ereditarietà (tramite `sling:resourceSuperType`) e la delega ad altri tipi di risorse (tramite l’elemento blocco HTL `data-sly-resource` o tramite il tag JSP `sling:include`, ad esempio) possono essere mappate tramite i metadati del bundle
+ il controllo delle versioni del tipo di risorsa può essere applicato in modo simile alle API Java

## Precompilazione e importazioni di pacchetti

La [`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html) può convalidare la sintassi degli script HTL, ma può anche essere utilizzata per tradurre gli script HTL in classi Java. Vengono quindi aggiunti alla cartella `generated-sources` del progetto Maven e selezionati da `maven-compiler-plugin`.

È possibile aggiungere [`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin) per generare i metadati del bundle OSGi per le importazioni API Java.

## Ereditarietà e delega

Il framework OSGi fornisce un potente modo di definire [Requisiti e funzionalità](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies) per esprimere contratti tra vari componenti. Questi vengono descritti tramite metadati e applicati in fase di runtime. Gli script in bundle utilizzano questo meccanismo per esprimere sia le relazioni di ereditarietà (`sling:resourceSuperType`) che la delega (inclusi altri tipi di risorse nel processo di rendering).

Il plug-in `bnd` dal progetto [scriptingbundle-maven-plugin](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html) può essere utilizzato per estrarre i requisiti e le funzionalità corrispondenti agli script forniti dal pacchetto di contenuto [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles).

## Supporto di Project Archetype AEM

A partire dalla versione 31, il [AEM Project Archetype](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html) può essere utilizzato per impostare correttamente un AEM come progetto di Cloud Service per utilizzare gli script raggruppati precompilati. Inoltre, il AEM Project Archetype configura il [AEM come Cloud Service SDK Build Analyzer Maven Plugin](/help/developing/archetype/build-analyzer-maven-plugin.md) per convalidare il livello del pacchetto Java e le dipendenze a livello di script.
