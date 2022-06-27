---
title: Adaptive Image Servlet
description: Scopri in che modo i componenti core utilizzano il servlet immagine adattivo per la distribuzione delle immagini e come ottimizzarne l’utilizzo.
role: Architect, Developer, Admin, User
source-git-commit: 3ff1343ab4ef7a52f910984a0bcd8fc4201441bf
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 58%

---


# Servlet immagine adattivo {#adaptive-image-servlet}

Scopri in che modo i componenti core utilizzano il servlet immagine adattivo per la distribuzione delle immagini e come ottimizzarne l’utilizzo.

## Distribuzione di immagini adattive o ottimizzate per il web? {#options}

Il componente di base Immagine può utilizzare due metodi per la distribuzione delle immagini.

* Il servlet immagine adattivo è il predefinito.
* [Distribuzione di immagini ottimizzata per il web](/help/developing/web-optimized-image-delivery.md) è disponibile per AEMaaCS e riduce la dimensione del download del 25% in media.

Questo documento descrive il Servlet immagine adattivo predefinito.

## Panoramica {#overview}

Per impostazione predefinita, il componente immagine utilizza il servlet immagine adattivo del componente core per distribuire le immagini. [L’Adaptive Image Servlet](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) è responsabile dell’elaborazione e dello streaming delle immagini e può essere utilizzato dagli sviluppatori nelle loro [personalizzazioni dei Componenti core](/help/developing/customizing.md).

## Ottimizzazione della selezione della rappresentazione {#optimizing-rendition-selection}

Il servlet per immagini adattive cercherà di scegliere la rappresentazione migliore per le dimensioni e il tipo di immagine richiesti. Si consiglia di definire in sincronia le rappresentazioni DAM e le larghezze consentite del componente Immagine, in modo che il servlet per immagini adattive possa eseguire la minor quantità di elaborazione possibile.

Ciò migliora le prestazioni ed evita che alcune immagini non vengano elaborate correttamente dalla libreria di elaborazione delle immagini sottostante.

## Utilizzo delle intestazioni modificate per ultimo {#last-modified}

Le richieste condizionali tramite l’intestazione `Last-Modified` sono supportate dall’Adaptive Image Servlet, ma il caching dell’intestazione `Last-Modified` [deve essere abilitato in Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=it#caching-http-response-headers).

L’esempio di configurazione di Dispatcher in [Archetipo progetto AEM](/help/developing/archetype/overview.md) già include questa configurazione.
