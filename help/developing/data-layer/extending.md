---
title: 'Estensione del livello dati client del Adobe '
description: Il livello dati client del Adobe  può essere esteso in base ad alcuni pattern di base
translation-type: tm+mt
source-git-commit: 896ed679ed3351cb309a34b38bf97fe81adc2cfe
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 0%

---


# Estensione del livello dati client del Adobe  {#extending-acdl}

È possibile estendere i componenti core con opzioni di finestra di dialogo personalizzate che consentono agli autori dei contenuti di immettere informazioni aggiuntive relative al livello dati.

Per includere questi campi nel Livello dati fornito dai Componenti principali, è necessario estendere il modello del componente che implementa i propri metodi specifici del livello dati.

## Esempio: Componente titolo {#example}

Un componente di base come il componente [](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) Titolo estende [il componente](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) , che dispone di un `getData` metodo che per impostazione predefinita restituisce [`ComponentData`.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` serializza i campi predefiniti che il componente può implementare, come `getDataLayerLinkUrl` e `getDataLayerTitle` per il [`TitleImpl`.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

Pertanto, il modello Sling personalizzato potrebbe avere un `getData` metodo che restituisce un oggetto che si estende `ComponentData` per restituire altri campi.

In questo modo, verrà aggiunto un `data-cmp-data-layer` attributo all’elemento HTML del componente con il JSON dei dati che verranno popolati nel livello dati. A questo punto, è possibile implementare script che ascoltino questi dati o gli eventi correlati.
