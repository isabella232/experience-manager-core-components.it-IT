---
title: Supporto AMP per i componenti core
description: I componenti core supportano AMP - Pagine mobili accelerate
role: Architetto, Sviluppatore, Amministratore
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 1%

---


# Supporto AMP per i componenti core {#amp-support}

A partire dalla [versione 2.11.0](/help/versions.md) dei componenti core, [AMP - Pagine mobili accelerate](https://developers.google.com/amp) sono completamente supportate.

Questo documento offre una panoramica del supporto di AMP e delle modalità di abilitazione di tale funzionalità per i siti. Tuttavia, per informazioni tecniche complete, consulta la documentazione per gli sviluppatori [GitHub.](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## Cos’è AMP? {#what-is-amp}

Accelerated Mobile Pages o AMP è un framework open-source progettato originariamente da Google per ottimizzare le pagine per la navigazione mobile. Le pagine AMP vengono generalmente caricate molto più rapidamente delle pagine web standard, offrendo esperienze mobili migliori.

## AMP nei componenti core {#amp-in-core-components}

Il supporto per AMP nei componenti core è [completamente configurabile.](#enabling-amp) Le versioni AMP delle pagine possono essere servite esclusivamente, insieme alle versioni HTML standard o meno.

I componenti core utilizzano `amp` come selettore Sling per eseguire il rendering di una pagina AMP. Ad esempio, `example.html` esegue il rendering della pagina normale e `example.amp.html` è la versione AMP.

I singoli progetti possono decidere se sfruttare o meno AMP. Infatti, poiché le pagine AMP e HTML standard possono essere distribuite in parallelo, un progetto può scegliere di utilizzare AMP solo su determinate pagine del progetto.

## Guida introduttiva al supporto AMP nel progetto {#getting-started}

Sebbene il supporto AMP offra una grande flessibilità, per iniziare rapidamente a usarlo sono necessari solo alcuni semplici passaggi:

1. Se necessario, installa l’estensione del supporto AMP.
   * Per i progetti AEM come Cloud Service, l’estensione è automaticamente disponibile con i componenti core e non è necessaria alcuna installazione.
   * Per i progetti on-premise e AMS, l’estensione deve essere installata esplicitamente durante l’installazione dei componenti core.
1. Una volta installata l’estensione AMP, l’autore del componente deve semplicemente puntare le superproprietà dei componenti a quelle nell’estensione.
1. [Abilita il ](#enabling-amp) supporto AMP a livello di modello o sulle singole pagine.
1. [Distribuisci ](#css-requirements) CSS in linea come richiesto.

### Abilitazione di AMP per le pagine {#enabling-amp}

Per abilitare AMP per una pagina, è necessario selezionare la **modalità AMP** nel [Criterio pagina.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-page-policy-template-author-developer)

![Opzioni dei criteri di pagina AMP](/help/assets/amp-policy.png)

* **No AMP**  - La pagina viene consegnata solo come HTML standard.
* **AMP accoppiato**  - La pagina viene consegnata sia come AMP che come HTML.
* **Solo AMP**  - La pagina viene consegnata solo come AMP.

Le impostazioni AMP per una pagina possono essere ignorate anche in [Proprietà pagina](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) per una singola pagina.

![Proprietà pagina AMP](/help/assets/amp-page-properties.png)

* **Eredita da modello pagina** : questo è il valore predefinito, che consente di prelevare l’impostazione dal criterio del modello pagina.
* **No AMP**  - La pagina viene consegnata solo come HTML standard.
* **AMP accoppiato**  - La pagina viene consegnata sia come AMP che come HTML.
* **Solo AMP**  - La pagina viene consegnata solo come AMP.

### Requisiti CSS {#css-requirements}

Quando si utilizza AMP con i componenti core, la differenza principale è che AMP richiede che tutti i CSS [siano allineati](including-clientlibs.md#inlining) nell&#39;elemento `<head>` e ottimizzati.

Per supportare questa funzione, viene utilizzato un componente pagina personalizzato, che carica solo il CSS specifico per AMP per i componenti presenti nella pagina.

>[!NOTE]
>
>A causa di limitazioni di progettazione AMP, l’Adobe non supporta l’uso della griglia reattiva con la versione AMP della pagina.

Per ulteriori requisiti e dettagli tecnici, consulta la documentazione per gli sviluppatori [GitHub.](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
