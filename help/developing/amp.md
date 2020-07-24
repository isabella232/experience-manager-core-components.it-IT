---
title: Supporto AMP per i componenti core
description: I componenti core supportano AMP - Pagine mobili con accelerazione
translation-type: tm+mt
source-git-commit: 905096d909d4fbf624152ba3b5cbc1d80637245f
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 0%

---


# Supporto AMP per i componenti core {#amp-support}

A partire dalla [release 2.11.0](/help/versions.md) dei componenti core, [AMP - Pagine](https://developers.google.com/amp) mobili con accelerazione - è completamente supportato.

Questo documento fornisce una panoramica del supporto di AMP e di come attivarlo per i siti. Tuttavia, per informazioni tecniche complete, consultate la documentazione per gli sviluppatori [GitHub.](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## Cos&#39;è AMP? {#what-is-amp}

Pagine mobili o AMP con accelerazione è un framework open-source progettato originariamente da Google per ottimizzare le pagine per la navigazione mobile. Le pagine AMP vengono caricate più rapidamente rispetto alle pagine Web standard, offrendo esperienze mobili migliori.

## AMP nei componenti core {#amp-in-core-components}

Il supporto per AMP nei componenti core è [completamente configurabile.](#enabling-amp) Le versioni AMP delle pagine possono essere servite esclusivamente, accanto alle versioni HTML standard, o meno.

I componenti core vengono utilizzati `amp` come selettore Sling per eseguire il rendering di una pagina AMP. Ad esempio, `example.html` eseguirebbe il rendering della pagina normale e `example.amp.html` sarebbe la versione AMP.

### Requisiti {#requirements}

Quando si utilizza AMP con i componenti core, la differenza principale è che AMP richiede che tutti i CSS siano allineati nell&#39; `<head>` elemento e ottimizzati.

A questo scopo, viene utilizzato un componente pagina personalizzato, che carica solo il CSS specifico di AMP per i componenti presenti sulla pagina.

Per ulteriori requisiti e dettagli tecnici, consulta la documentazione per gli sviluppatori [GitHub.](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

### Utilizzo di AMP nei componenti core {#using-amp}

I singoli progetti possono decidere se utilizzare o meno AMP. Infatti, poiché AMP e pagine HTML standard possono essere distribuite in parallelo, un progetto può scegliere di utilizzare AMP solo su determinate pagine del progetto.

### Installazione del supporto AMP {#installing-amp}

Poiché AMP è opzionale, viene distribuito come estensione ai componenti core.

* Per AEM come progetto Cloud Service, l&#39;estensione è automaticamente disponibile.
* Per i progetti in sede e AMS, l’estensione deve essere installata in modo esplicito durante l’installazione dei componenti core.

Una volta installata l’estensione, l’autore del componente deve semplicemente puntare i supertipi di componente a quelli presenti nell’estensione.

### Abilitazione di AMP per le pagine {#enabling-amp}

Per abilitare AMP per una pagina, la modalità **** AMP deve essere selezionata nel criterio [pagina.](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/templates.html#editingatemplatepagepolicies)

![Opzioni criteri pagina AMP](/help/assets/amp-policy.png)

* **Nessuna AMP** - La pagina viene distribuita solo come HTML standard.
* **Coppia AMP** - La pagina viene distribuita sia in formato AMP che HTML.
* **Solo** AMP - La pagina viene consegnata solo come AMP.

Le impostazioni AMP per una pagina possono anche essere sostituite in Proprietà [](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/authoring/editing-page-properties.html) pagina per una singola pagina.

![Proprietà pagina AMP](/help/assets/amp-page-properties.png)

* **Eredita da modello** pagina - Questo è il valore predefinito, che consente di prelevare l&#39;impostazione dal criterio del modello di pagina.
* **Nessuna AMP** - La pagina viene distribuita solo come HTML standard.
* **Coppia AMP** - La pagina viene distribuita sia in formato AMP che HTML.
* **Solo** AMP - La pagina viene consegnata solo come AMP.
