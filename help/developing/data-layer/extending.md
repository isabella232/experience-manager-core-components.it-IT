---
title: Estensione di Adobe Client Data Layer
description: Adobe Client Data Layer può essere esteso seguendo alcuni pattern di base
feature: Componenti core, Adobe Client Data Layer
role: Architetto, Sviluppatore, Amministratore
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---


# Estensione di Adobe Client Data Layer {#extending-acdl}

È possibile estendere i componenti core con opzioni di dialogo personalizzate che consentono agli autori dei contenuti di immettere ulteriori informazioni relative al livello dati.

Per includere questi campi nel livello dati fornito dai componenti core, devi estendere il modello del componente che implementa i propri metodi specifici del livello dati.

## Esempio: Componente titolo {#example}

Un componente di base come [Componente titolo](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) estende [Componente](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) che dispone di un metodo `getData` che per impostazione predefinita restituisce [`ComponentData`.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` serializza i campi predefiniti che il componente può implementare, come  `getDataLayerLinkUrl` e  `getDataLayerTitle` per  [`TitleImpl`.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

Pertanto, il modello Sling personalizzato potrebbe avere un metodo `getData` che restituisce un oggetto che si estende `ComponentData` per restituire altri campi.

A questo scopo, aggiungerà un attributo `data-cmp-data-layer` all’elemento HTML del componente con il JSON dei dati che verranno compilati al livello dati. A questo punto, è possibile implementare script che ascoltano questi dati o gli eventi correlati.

>[!TIP]
>
>Per esplorare ulteriormente la flessibilità di Data Layer, controlla le opzioni di integrazione, tra cui come abilitare Data Layer per i componenti personalizzati.
