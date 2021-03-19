---
title: Integrazioni e livello dati client Adobe
description: Scopri come Adobe Client Data Layer può integrarsi con i componenti personalizzati e come le integrazioni con Adobe Analytics e Adobe Target possono aiutarti a ottenere informazioni sul tuo sito web
feature: Componenti core, Adobe Client Data Layer
role: Architetto, Sviluppatore, Amministratore
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---


# Integrazioni con Adobe Client Data Layer {#integrations}

Adobe Client Data Layer riduce lo sforzo di strumentalizzare i siti web fornendo un metodo standardizzato per esporre e accedere a qualsiasi tipo di dati per qualsiasi script.

Adobe Client Data Layer può integrarsi con i componenti personalizzati e le integrazioni con Adobe Analytics e Adobe Target per ottenere informazioni approfondite sul sito web.

## Abilitazione del livello dati per i componenti personalizzati {#enabling-custom-components}

Per aggiungere automaticamente un componente personalizzato al livello dati:

1. Definisci le proprietà del modello di componente personalizzato da tracciare.
1. Aggiungi l’attributo `data-cmp-data-layer` al componente personalizzato HTL. Ad esempio `data-cmp-data-layer="${mycomponent.data.json}"`.

Per fare in modo che il livello dati attivi automaticamente un evento `cmp:click` ogni volta che si fa clic su un elemento specifico del componente personalizzato, aggiungi l’attributo `data-cmp-clickable` all’elemento da tracciare nel componente personalizzato HTL.

È possibile eseguire una query sull&#39;attributo `data-cmp-data-layer-enabled` sul lato client per verificare se il livello dati è abilitato.

>[!TIP]
>
>Per ulteriori dettagli tecnici sull’integrazione di Adobe Client Data Layer con i componenti core e su come abilitare Data Layer sui componenti personalizzati, consulta il file [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) nell’archivio dei componenti core.

## Integrazione con Adobe Analytics e Adobe Target {#analytics-target}

Insieme ad Adobe Analytics e Adobe Target, Adobe Client Data Layer diventa la base di uno strumento molto potente e flessibile per acquisire informazioni approfondite sulle tue esperienze digitali. Le seguenti esercitazioni ti guidano attraverso integrazioni di esempio.

### Raccogliere dati di pagina con Adobe Analytics {#collect-page-data}

Scopri come utilizzare le funzioni integrate di Adobe Client Data Layer con AEM componenti core per raccogliere i dati su una pagina in Adobe Experience Manager Sites. Il Experience Platform Launch e l’estensione Adobe Analytics verranno utilizzati per creare regole per inviare dati di pagina ad Adobe Analytics.

[Visualizza l&#39;esercitazione qui.](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/collect-data-analytics.html)

### Tracciare i componenti selezionati con Adobe Analytics {#track-clicked-components}

Utilizza Adobe Client Data Layer basato su eventi con i componenti core AEM per tenere traccia dei clic su componenti specifici su un sito Adobe Experience Manager. Scopri come utilizzare le regole in Experience Platform Launch per rilevare gli eventi di clic, filtrare per componente e inviare i dati a un Adobe Analytics con un beacon di tracciamento dei collegamenti.

[Visualizza l&#39;esercitazione qui.](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/track-clicked-component.html)
