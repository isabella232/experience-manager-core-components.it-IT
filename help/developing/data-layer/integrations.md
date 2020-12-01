---
title: 'Integrazioni e livello dati client del Adobe '
description: Scoprite come il livello dati client  Adobe può integrarsi con i componenti personalizzati e come le integrazioni con  Adobe Analytics e  Adobe Target possono aiutarti a ottenere informazioni approfondite sul tuo sito Web
translation-type: tm+mt
source-git-commit: ea7a0e08ea1b769b400fce275c8ce7e0db6f9407
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---


# Integrazioni con il livello dati client del Adobe  {#integrations}

Il livello dati client del Adobe  riduce lo sforzo di strumentalizzare i siti Web fornendo un metodo standardizzato per esporre e accedere a qualsiasi tipo di dati per qualsiasi script.

Il livello dati client del Adobe  può essere integrato con i componenti personalizzati e le integrazioni con  Adobe Analytics e  Adobe Target per consentirvi di acquisire informazioni dettagliate sul sito Web.

## Abilitazione del livello dati per i componenti personalizzati {#enabling-custom-components}

Per aggiungere automaticamente un componente personalizzato al livello dati:

1. Definire le proprietà del modello di componente personalizzato da tenere traccia.
1. Aggiungete l&#39;attributo `data-cmp-data-layer` al componente personalizzato HTL. Ad esempio `data-cmp-data-layer="${mycomponent.data.json}"`.

Per fare in modo che il livello dati attivi automaticamente un evento `cmp:click` ogni volta che si fa clic su un elemento specifico del componente personalizzato, aggiungete l&#39;attributo `data-cmp-clickable` all&#39;elemento da tracciare nel componente personalizzato HTL.

È possibile interrogare l&#39;attributo `data-cmp-data-layer-enabled` sul lato client per verificare se il livello dati è abilitato.

>[!TIP]
>
>Per ulteriori informazioni tecniche sull&#39;integrazione del livello dati client del Adobe  con i componenti core e su come abilitare il livello dati sui componenti personalizzati, vedere il file [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) nell&#39;archivio dei componenti core.

## Integrazione con  Adobe Analytics e  Adobe Target {#analytics-target}

In coppia con  Adobe Analytics e  Adobe Target, il  Adobe Client Data Layer diventa il fondamento di un set di strumenti molto potente e flessibile per acquisire informazioni approfondite sulle esperienze digitali. Le seguenti esercitazioni forniscono informazioni introduttive sulle integrazioni di esempio.

### Raccolta di dati di pagina con  Adobe Analytics {#collect-page-data}

Scoprite come utilizzare le funzionalità integrate del livello dati client  Adobe con AEM componenti core per raccogliere i dati su una pagina in  Adobe Experience Manager Sites. Il Experience Platform Launch e l&#39;estensione Adobe Analytics  verranno utilizzati per creare regole per inviare i dati di pagina a  Adobe Analytics.

[Guardate l&#39;esercitazione qui.](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/collect-data-analytics.html)

### Tenere traccia dei componenti selezionati con  Adobe Analytics {#track-clicked-components}

Utilizzate il livello dati client  Adobe basato sull&#39;evento con AEM componenti core per monitorare i clic di componenti specifici su un sito Adobe Experience Manager. Scopri come utilizzare le regole del Experience Platform Launch per ascoltare gli eventi click, filtrare per componente e inviare i dati a un Adobe Analytics  con un beacon di collegamento track.

[Guardate l&#39;esercitazione qui.](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/track-clicked-component.html)
