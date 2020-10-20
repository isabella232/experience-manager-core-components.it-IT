---
title: Configurazione e componenti core in base al contesto Sling
description: I componenti core sfruttano le configurazioni basate sul contesto Sling per alcune funzioni
translation-type: tm+mt
source-git-commit: 11e2c6da0fa93084b601437fd45fd65dd8d73231
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 0%

---


# Configurazione e componenti core in base al contesto Sling {#sling-context-aware-configurations}

Le configurazioni basate sul contesto sono una funzione di Sling e sono configurazioni correlate a una risorsa di contenuto o a una struttura di risorse e sono sfruttate dai componenti core per consentire configurazioni a livello di sito.

## Configurazione Sling in base al contesto {#context-aware-configurations}

Il sito potrebbe richiedere configurazioni diverse per diverse aree del sito, ad esempio dove alcuni parametri possono essere condivisi e richiedere l&#39;ereditarietà per i contesti nidificati e i valori di fallback globali. AEM utilizza le configurazioni basate sul contesto Sling, che consentono questa possibilità.

Per informazioni dettagliate sulle configurazioni in AEM, [consultate la documentazione Configurations and Configuration Browser (Configurazioni e browser di configurazione).](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/configurations.html)

## Uso nei componenti core {#core-components}

Diverse funzioni di Componenti di base utilizzano configurazioni basate sul contesto. Tutte queste configurazioni si trovano sotto il nodo seguente:

* `/conf/<my-site>/sling:configs/<my-configuration>`

Le singole configurazioni dipendono dal componente o dalla funzione specifica. Le funzioni dei componenti core che utilizzano configurazioni basate sul contesto sono:

* [Componente visualizzatore PDF](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Livello dati client Adobe](/help/developing/data-layer/overview.md#installation-activation)
* [Supporto AMP](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
