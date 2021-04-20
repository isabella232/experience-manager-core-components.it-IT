---
title: Configurazioni in base al contesto Sling e componenti core
description: I componenti core sfruttano le configurazioni basate sul contesto Sling per alcune funzioni
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---


# Configurazioni in base al contesto Sling e componenti core {#sling-context-aware-configurations}

Le configurazioni in base al contesto sono una funzione di Sling](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html). [ Si tratta di configurazioni correlate a una risorsa di contenuto o a una struttura di risorse e sfruttate dai componenti core per consentire configurazioni a livello di sito.

## Configurazioni in base al contesto Sling {#context-aware-configurations}

Il sito potrebbe richiedere configurazioni diverse per aree di siti diversi, ad esempio dove alcuni parametri possono essere condivisi e richiedere l’ereditarietà per contesti nidificati e valori di fallback globali. AEM sfrutta le configurazioni basate sul contesto Sling, che consentono questa possibilità.

Per informazioni dettagliate sulle configurazioni in AEM, [consulta la documentazione sulle configurazioni e sul browser di configurazione.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/configurations.html)

## Utilizzare nei componenti core {#core-components}

Molte funzionalità dei componenti core sfruttano configurazioni basate sul contesto. Tutte queste configurazioni si trovano sotto il seguente nodo:

* `/conf/<my-site>/sling:configs/<my-configuration>`

Le singole configurazioni dipendono dal componente o dalla funzione specifica. Le funzioni dei componenti core che utilizzano configurazioni in base al contesto sono le seguenti:

* [Componente visualizzatore PDF](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Livello dati client di Adobe](/help/developing/data-layer/overview.md#installation-activation)
* [Supporto AMP](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
