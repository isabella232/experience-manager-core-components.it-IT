---
title: Integrazioni e Adobe Client Data Layer
description: Scopri come Adobe Client Data Layer può integrarsi con i componenti personalizzati e come le integrazioni con Adobe Analytics e Adobe Target possono aiutarti a ottenere insights sul tuo sito web
feature: Componenti core, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: 503dd3dc-fe95-4a17-83f5-1f0c1960993d
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '422'
ht-degree: 100%

---

# Integrazioni con Adobe Client Data Layer {#integrations}

Adobe Client Data Layer semplifica l’organizzazione di siti web fornendo un metodo standardizzato per visualizzare e accedere a qualsiasi tipo di dati per qualsiasi script.

Adobe Client Data Layer può integrarsi con i componenti personalizzati e le integrazioni con Adobe Analytics e Adobe Target possono aiutarti a ottenere insights sul tuo sito web.

## Abilitazione di Data Layer per componenti personalizzati {#enabling-custom-components}

Per aggiungere automaticamente un componente personalizzato a Data Layer:

1. Definisci le proprietà del modello del componente personalizzato da tracciare.
1. Aggiungi l’attributo `data-cmp-data-layer` al codice HTL del componente personalizzato. Ad esempio, `data-cmp-data-layer="${mycomponent.data.json}"`.

Per fare in modo che Data Layer attivi automaticamente un evento `cmp:click` ogni volta che si fa clic su un elemento specifico del componente personalizzato, aggiungi l’attributo `data-cmp-clickable` all’elemento da tracciare nel codice HTL del componente personalizzato.

È possibile eseguire una query sull’attributo `data-cmp-data-layer-enabled` lato client per stabilire se Data Layer è abilitato.

>[!TIP]
>
>Per ulteriori dettagli tecnici sull’integrazione di Adobe Client Data Layer con i Componenti core e su come abilitare Data Layer sui componenti personalizzati, vedi il file [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) nell’archivio dei Componenti core.

## Integrazione con Adobe Analytics e Adobe Target {#analytics-target}

Insieme ad Adobe Analytics e Adobe Target, Adobe Client Data Layer diventa il fondamento di uno strumento molto potente e flessibile per ottenere insights sulle tue esperienze digitali. Le seguenti esercitazioni ti guidano attraverso esempi di integrazioni.

### Raccolta dei dati di pagina con Adobe Analytics {#collect-page-data}

Scopri come utilizzare le funzioni integrate di Adobe Client Data Layer con i Componenti core AEM per raccogliere i dati di una pagina nei Adobe Experience Manager Sites. Experience Platform Launch e l’estensione Adobe Analytics verranno utilizzati per creare regole per inviare dati di pagina ad Adobe Analytics.

[Visualizza l’esercitazione qui.](https://docs.adobe.com/content/help/it-IT/experience-manager-learn/sites/integrations/analytics/collect-data-analytics.html)

### Tracciamento dei componenti selezionati con Adobe Analytics {#track-clicked-components}

Utilizza Adobe Client Data Layer basato sugli eventi con i Componenti core AEM per tracciare i clic su componenti specifici su un sito Adobe Experience Manager. Scopri come utilizzare le regole in Experience Platform Launch per rilevare gli eventi clic, filtrarli per componente e inviare i dati ad Adobe Analytics con un beacon di tracciamento dei collegamenti.

[Visualizza l’esercitazione qui.](https://docs.adobe.com/content/help/it-IT/experience-manager-learn/sites/integrations/analytics/track-clicked-component.html)
