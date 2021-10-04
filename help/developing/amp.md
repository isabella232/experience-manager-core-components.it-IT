---
title: Supporto AMP per i Componenti core
description: 'I Componenti core supportano AMP: Accelerated Mobile Pages'
role: Architect, Developer, Admin
exl-id: 1fd9b6b5-0e4d-48c7-8faa-42e0d4a6bbd0
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 96%

---

# Supporto AMP per i Componenti core {#amp-support}

A partire dalla [versione 2.11.0](/help/versions.md) dei Componenti core, è pienamente supportato [AMP: Accelerated Mobile Pages](https://developers.google.com/amp).

Questo documento offre una panoramica del supporto AMP e delle modalità di abilitazione di tale funzionalità per i siti. Tuttavia, per informazioni tecniche complete, vedi la [documentazione per gli sviluppatori GitHub.](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## Che cos’è AMP? {#what-is-amp}

Accelerated Mobile Pages o AMP è un framework open-source progettato originariamente da Google per ottimizzare le pagine per la navigazione mobile. Le pagine AMP vengono generalmente caricate molto più rapidamente delle pagine web standard, offrendo una migliore esperienza sui dispositivi mobili.

## AMP nei Componenti core {#amp-in-core-components}

Il supporto per AMP nei Componenti core è [completamente configurabile.](#enabling-amp) Le versioni AMP delle pagine possono essere servite in via esclusiva, insieme alle versioni HTML standard, o non servite affatto.

I Componenti core utilizzano `amp` come selettore Sling per eseguire il rendering di una pagina AMP. Ad esempio, `example.html` esegue il rendering della pagina normale e `example.amp.html` è la versione AMP.

I singoli progetti possono decidere se utilizzare o meno AMP. Infatti, poiché le pagine AMP e HTML standard possono essere distribuite in parallelo, un progetto può scegliere di utilizzare AMP solo su determinate pagine.

## Introduzione al supporto AMP nel progetto {#getting-started}

Sebbene il supporto AMP offra una grande flessibilità, per iniziare a utilizzarlo occorrono solo alcuni semplici passaggi:

1. Se necessario, installa l’estensione del supporto AMP.
   * Per i progetti AEM as a Cloud Service, l’estensione è automaticamente disponibile con i Componenti core e non è necessaria alcuna installazione.
   * Per i progetti on-premise e AMS, l’estensione deve essere installata esplicitamente durante l’installazione dei Componenti core.
1. Una volta installata l’estensione AMP, l’autore del componente deve semplicemente far puntare i supertipi del componente a quelli dell’estensione.
1. [Abilita il supporto AMP](#enabling-amp) a livello di modello oppure sulle singole pagine.
1. [Distribuisci i file CSS allineati](#css-requirements) come richiesto.

### Abilitazione di AMP per le pagine {#enabling-amp}

Per abilitare AMP per una pagina, è necessario selezionare la **Modalità AMP** in [Criterio pagina.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-page-policy-template-author-developer)

![Opzioni di Criterio pagina AMP](/help/assets/amp-policy.png)

* **Nessun AMP**: la pagina viene distribuita solo come HTML standard.
* **AMP abbinato**: la pagina viene distribuita sia come AMP che come HTML.
* **Solo AMP**: la pagina viene distribuita solo come AMP.

Le impostazioni AMP per una pagina possono anche essere ignorate in [Proprietà pagina](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) per una singola pagina.

![Proprietà pagina AMP](/help/assets/amp-page-properties.png)

* **Eredita da modello pagina**: questo è il valore predefinito che consente di prendere l’impostazione dal criterio del modello della pagina.
* **Nessun AMP**: la pagina viene distribuita solo come HTML standard.
* **AMP abbinato**: la pagina viene distribuita sia come AMP che come HTML.
* **Solo AMP**: la pagina viene distribuita solo come AMP.

### Requisiti CSS {#css-requirements}

Quando si utilizza AMP con i Componenti core, la differenza principale è che AMP richiede che tutti i [CSS siano allineati](including-clientlibs.md#inlining) nell’elemento `<head>` e ottimizzati.

Per supportare questa funzione, viene utilizzato un componente pagina personalizzato che carica solo il CSS specifico per AMP per i componenti presenti nella pagina.

>[!NOTE]
>
>A causa di limitazioni di progettazione AMP, Adobe non supporta l’uso della griglia reattiva con la versione AMP della pagina.

Per ulteriori requisiti e dettagli tecnici, vedi la [documentazione per gli sviluppatori GitHub.](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
