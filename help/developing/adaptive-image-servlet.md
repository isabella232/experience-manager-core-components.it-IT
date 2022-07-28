---
title: Adaptive Image Servlet
description: Scopri in che modo i componenti core sfruttano Adaptive Image Servlet per la consegna delle immagini e come ottimizzarne l’utilizzo.
role: Architect, Developer, Admin, User
exl-id: d9199d51-6f09-4000-9525-afc30474437e
source-git-commit: dd07fa714a23759d43ca491232674d88bc7bf88e
workflow-type: ht
source-wordcount: '254'
ht-degree: 100%

---

# Adaptive Image Servlet {#adaptive-image-servlet}

Scopri in che modo i componenti core sfruttano Adaptive Image Servlet per la consegna delle immagini e come ottimizzarne l’utilizzo.

## Adaptive Image Servlet o consegna di immagini ottimizzate per il web? {#options}

Il componente core Immagine può utilizzare due metodi per la consegna delle immagini.

* Adaptive Image Servlet è il metodo predefinito.
* La [consegna di immagini ottimizzate per il web](/help/developing/web-optimized-image-delivery.md) è disponibile per AEMaaCS e riduce la dimensione del download del 25% in media.

Questo documento descrive il metodo predefinito, Adaptive Image Servlet.

## Panoramica {#overview}

Per impostazione predefinita, il componente Immagine utilizza Adaptive Image Servlet del componente core per consegnare le immagini. [Adaptive Image Servlet](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) è responsabile dell’elaborazione e dello streaming delle immagini e può essere utilizzato dagli sviluppatori nelle [personalizzazioni dei componenti core](/help/developing/customizing.md).

## Ottimizzazione della selezione della rappresentazione {#optimizing-rendition-selection}

Il servlet per immagini adattive cercherà di scegliere la rappresentazione migliore per le dimensioni e il tipo di immagine richiesti. Si consiglia di definire in sincronia le rappresentazioni DAM e le larghezze consentite del componente Immagine, in modo che il servlet per immagini adattive possa eseguire la minor quantità di elaborazione possibile.

Ciò migliora le prestazioni ed evita che alcune immagini non vengano elaborate correttamente dalla libreria di elaborazione delle immagini sottostante.

## Utilizzo delle intestazioni “Last-Mofified” {#last-modified}

Le richieste condizionali tramite l’intestazione `Last-Modified` sono supportate dall’Adaptive Image Servlet, ma il caching dell’intestazione `Last-Modified` [deve essere abilitato in Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=it#caching-http-response-headers).

L’esempio di configurazione di Dispatcher in [Archetipo progetto AEM](/help/developing/archetype/overview.md) già include questa configurazione.
