---
title: Adaptive Image Servlet
description: Scopri in che modo i componenti core sfruttano Adaptive Image Servlet per la consegna delle immagini e come ottimizzarne l’utilizzo.
role: Architect, Developer, Admin, User
exl-id: d9199d51-6f09-4000-9525-afc30474437e
source-git-commit: 420e6085da57e5dc6deb670a5f0498b018441cb8
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 61%

---

# Servlet immagine adattivo {#adaptive-image-servlet}

Scopri in che modo i componenti core sfruttano Adaptive Image Servlet per la consegna delle immagini e come ottimizzarne l’utilizzo.

## Adaptive Image Servlet o consegna di immagini ottimizzate per il web? {#options}

Il componente core Immagine può utilizzare due metodi per la consegna delle immagini.

* Adaptive Image Servlet è il metodo predefinito.
* La [consegna di immagini ottimizzate per il web](/help/developing/web-optimized-image-delivery.md) è disponibile per AEMaaCS e riduce la dimensione del download del 25% in media.

Questo documento descrive il metodo predefinito, Adaptive Image Servlet.

## Panoramica {#overview}

Per impostazione predefinita, il componente Immagine utilizza Adaptive Image Servlet del componente core per consegnare le immagini. [Adaptive Image Servlet](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) è responsabile dell’elaborazione e dello streaming delle immagini e può essere utilizzato dagli sviluppatori nelle [personalizzazioni dei componenti core](/help/developing/customizing.md).

## Selezione della rappresentazione {#rendition-selection}

Il servlet di immagini adattive selezionerà automaticamente il rendering più appropriato da visualizzare in base alle dimensioni del contenitore in cui viene visualizzato. Il processo di selezione del rendering è il seguente.

1. Il Adaptive Image Servlet rivede tutte le rappresentazioni disponibili della risorsa immagine.
1. Seleziona solo quelli con lo stesso mime/tipo della risorsa di riferimento originale.
   * Ad esempio, se la risorsa originale era un PNG, considererà solo le rappresentazioni PNG.
1. Di queste rappresentazioni considera le dimensioni e le confronta con le dimensioni del contenitore in cui deve essere visualizzata l&#39;immagine.
   1. Se il rendering è >= la dimensione del contenitore, viene aggiunto a un elenco di rappresentazioni candidate.
   1. Se il rendering è &lt; la dimensione del contenitore, viene ignorato.
   1. Questi criteri garantiscono che il rendering non venga aggiornato, con un conseguente impatto sulla qualità delle immagini.
1. Il servlet immagine adattivo seleziona quindi il rendering con le dimensioni di file più piccole dall’elenco dei file candidati.

## Ottimizzazione della selezione della rappresentazione {#optimizing-rendition-selection}

Il servlet per immagini adattive cercherà di scegliere la rappresentazione migliore per le dimensioni e il tipo di immagine richiesti. Si consiglia di definire in sincronia le rappresentazioni DAM e le larghezze consentite del componente Immagine, in modo che il servlet per immagini adattive possa eseguire la minor quantità di elaborazione possibile.

Ciò migliora le prestazioni ed evita che alcune immagini non vengano elaborate correttamente dalla libreria di elaborazione delle immagini sottostante.

## Utilizzo delle intestazioni modificate {#last-modified}

Le richieste condizionali tramite l’intestazione `Last-Modified` sono supportate dall’Adaptive Image Servlet, ma il caching dell’intestazione `Last-Modified` [deve essere abilitato in Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=it#caching-http-response-headers).

L’esempio di configurazione di Dispatcher in [Archetipo progetto AEM](/help/developing/archetype/overview.md) già include questa configurazione.
