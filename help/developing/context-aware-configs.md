---
title: Configurazioni in base al contesto di Sling e Componenti core
description: I Componenti core utilizzano le configurazioni in base al contesto di Sling per alcune funzioni
role: Architect, Developer, Admin
exl-id: d35210f7-a65d-4768-ab9e-f12ec406da2d
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 96%

---

# Configurazioni in base al contesto di Sling e Componenti core {#sling-context-aware-configurations}

Le configurazioni in base al contesto sono una funzione di [Sling](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html). Si tratta di configurazioni correlate a una risorsa di contenuto o a una struttura di risorse e vengono utilizzate dai Componenti core per consentire configurazioni a livello di sito.

## Configurazioni in base al contesto di Sling {#context-aware-configurations}

Un sito potrebbe richiedere configurazioni diverse per le varie aree, ad esempio laddove alcuni parametri potrebbero essere condivisi e richiedere la capacità di ereditarli per contesti nidificati e valori di regresso globali. AEM utilizza le configurazioni in base contesto di Sling, in quanto offrono questa possibilità.

Per informazioni dettagliate sulle configurazioni in AEM, [vedi la documentazione sulle configurazioni e sul browser di configurazione.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/configurations.html)

## Utilizzo nei Componenti core {#core-components}

Molte funzionalità dei Componenti core utilizzano le configurazioni in base al contesto. Tutte queste configurazioni si trovano sotto il seguente nodo:

* `/conf/<my-site>/sling:configs/<my-configuration>`

Le singole configurazioni dipendono dal componente o dalla funzione specifica. Le funzioni dei Componenti core che utilizzano le configurazioni in base al contesto sono:

* [Componente Visualizzatore PDF](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe Client Data Layer](/help/developing/data-layer/overview.md#installation-activation)
* [Supporto AMP](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
