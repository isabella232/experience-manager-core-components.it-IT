---
title: Adaptive Image Servlet
description: Scopri in che modo i componenti core sfruttano Adaptive Image Servlet per la consegna delle immagini e come ottimizzarne l’utilizzo.
role: Architect, Developer, Admin, User
exl-id: d9199d51-6f09-4000-9525-afc30474437e
source-git-commit: 420e6085da57e5dc6deb670a5f0498b018441cb8
workflow-type: ht
source-wordcount: '410'
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

## Selezione della rappresentazione {#rendition-selection}

Adaptive Image Servlet selezionerà automaticamente la rappresentazione più appropriata da visualizzare in base alle dimensioni del contenitore in cui viene visualizzata. Il processo di selezione della rappresentazione è il seguente.

1. Adaptive Image Servlet rivede tutte le rappresentazioni disponibili della risorsa immagine.
1. Seleziona solo quelle con lo stesso mime/tipo della risorsa di riferimento originale.
   * Ad esempio, se la risorsa originale era un file PNG, considererà solo le rappresentazioni PNG.
1. Di quelle rappresentazioni considera le dimensioni e le confronta con le dimensioni del contenitore in cui deve essere visualizzata l’immagine.
   1. Se la rappresentazione è >= alla dimensione del contenitore, viene aggiunta a un elenco di rappresentazioni candidate.
   1. Se la rappresentazione è &lt; alla dimensione del contenitore, viene ignorata.
   1. Questi criteri garantiscono che la rappresentazione non subisca un processo di upscaling, con un conseguente impatto sulla qualità delle immagini.
1. Adaptive Image Servlet seleziona quindi la rappresentazione con le dimensioni di file più piccole dall’elenco delle candidate.

## Ottimizzazione della selezione della rappresentazione {#optimizing-rendition-selection}

Il servlet per immagini adattive cercherà di scegliere la rappresentazione migliore per le dimensioni e il tipo di immagine richiesti. Si consiglia di definire in sincronia le rappresentazioni DAM e le larghezze consentite del componente Immagine, in modo che il servlet per immagini adattive possa eseguire la minor quantità di elaborazione possibile.

Ciò migliora le prestazioni ed evita che alcune immagini non vengano elaborate correttamente dalla libreria di elaborazione delle immagini sottostante.

## Utilizzo delle ultime intestazioni modificate {#last-modified}

Le richieste condizionali tramite l’intestazione `Last-Modified` sono supportate dall’Adaptive Image Servlet, ma il caching dell’intestazione `Last-Modified` [deve essere abilitato in Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=it#caching-http-response-headers).

L’esempio di configurazione di Dispatcher in [Archetipo progetto AEM](/help/developing/archetype/overview.md) già include questa configurazione.
