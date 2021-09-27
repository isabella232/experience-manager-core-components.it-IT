---
title: Estensione di Adobe Client Data Layer
description: Adobe Client Data Layer può essere esteso seguendo alcuni modelli di base
feature: Componenti core, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: f3d5555b-4f08-49de-ab0f-dc0fb04aadf8
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '282'
ht-degree: 100%

---

# Estensione di Adobe Client Data Layer {#extending-acdl}

È possibile estendere Componenti core tramite le opzioni della finestra di dialogo per personalizzazione, che consentono agli autori di contenuto di immettere ulteriori informazioni relative a Data Layer.

Per includere questi campi in Data Layer, fornito da Componenti core, devi estendere il modello del componente che implementa i propri specifici metodi di Data Layer.

## Esempio: componente Titolo {#example}

Un componente core come il [componente Titolo](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) estende il [componente](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) che ha un metodo `getData`, il quale per impostazione predefinita restituisce [`ComponentData`.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` serializza campi predefiniti che il componente può implementare, come `getDataLayerLinkUrl` e `getDataLayerTitle` per [`TitleImpl`.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

Pertanto, il tuo modello Sling personalizzato potrebbe avere un metodo `getData` che restituisce un oggetto che estende `ComponentData` per restituire altri campi.

Per farlo, aggiungerà un attributo `data-cmp-data-layer` all’elemento HTML del componente con il JSON dei dati che verranno inseriti in Data Layer. A questo punto, puoi implementare degli script che effettuano il “listen” (ascolto) di questi dati o di eventi correlati.

>[!TIP]
>
>Per saperne di più sulla flessibilità di Data Layer, vedi le opzioni di integrazione, tra cui come abilitare Data Layer per i tuoi componenti personalizzati.
