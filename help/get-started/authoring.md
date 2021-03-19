---
title: Authoring con i componenti core
description: 'In AEM, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create: i componenti core offrono funzionalità flessibili e avanzate per l’authoring.'
role: Architetto, Sviluppatore, Amministratore, Business Practices
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 8%

---


# Authoring con i componenti core

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create.

I componenti core offrono funzionalità flessibili e avanzate per l’authoring. Il [sito di riferimento WKND](https://wknd.site) e i relativi componenti illustrano come i componenti core possono essere utilizzati per implementare un’esperienza Web avanzata.

Per scoprire i componenti core e vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library).

Per un’introduzione più dettagliata e orientata agli sviluppatori all’implementazione dei componenti core in un progetto AEM, utilizza l’ [AEM Archetipo di progetto](/help/developing/archetype/overview.md) , controlla [l’esercitazione WKND.](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!NOTE]
>
>I componenti core non sono immediatamente disponibili per gli autori; [devono prima essere integrarti nell’ambiente dal team di sviluppo](/help/get-started/using.md). Una volta integrati, possono essere resi disponibili e preconfigurati tramite l’ [editor modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!CAUTION]
>
>I componenti core [richiedono AEM 6.4 o versioni successive](/help/versions.md) e richiedono l&#39;uso di [modelli modificabili](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html). Non funzionano né con l’interfaccia classica né con modelli statici.

## Authoring con i componenti core {#authoring-with-core-components}

In qualità di autore, noterai diversi vantaggi dei componenti core, tra cui:

* Semplice da usare e ben integrato con l&#39; [editor di pagine](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)

* Funzionalità avanzate per soddisfare molti casi d&#39;uso, come illustrato dal [sito di riferimento WKND](https://wknd.site) e dalla [Libreria dei componenti](https://adobe.com/go/aem_cmp_library)

* [Possibilità di pre-](#pre-configuring-core-components) configurazione per definire le funzioni disponibili per gli autori di pagine tramite l’editor  [modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

* Progettazione basata sulle [linee guida sull&#39;accessibilità](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)

* Progettato per supportare il [layout reattivo](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)

* Progettato per supportare [una localizzazione semplice](localization.md)

I componenti sono disponibili nella scheda **Componenti** del pannello laterale dell’Editor pagina durante la [modifica di una pagina](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html).

I componenti sono raggruppati in base alle categorie definite gruppi di componenti per organizzare e filtrare facilmente i componenti. Il nome del gruppo di componenti viene visualizzato con il componente nel [browser componenti](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html) ed è anche possibile filtrare per gruppo per trovare facilmente il componente giusto.

>[!NOTE]
>
>I componenti core sono per impostazione predefinita parte di un gruppo nascosto e non sono visibili nel browser dei componenti.
>
>Aggiungi i componenti richiesti a un gruppo visibile o personalizzali affinché siano disponibili per gli autori.

## Preconfigurazione dei componenti core {#pre-configuring-core-components}

La configurazione dei componenti di base era compito di uno sviluppatore. Tuttavia, con i componenti core, un autore di modelli può ora configurare diverse funzionalità tramite l’editor di modelli.

Ad esempio, se un componente immagine non deve consentire il caricamento di immagini dal file system o se un componente testo deve consentire solo determinate formattazioni di paragrafo, queste funzioni possono essere abilitate o disabilitate con un semplice clic.

Per ulteriori informazioni, consulta [Creazione di modelli di pagina](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) .

### Finestre di dialogo di modifica e progettazione {#edit-and-design-dialogs}

Poiché gli autori dei modelli possono preconfigurare i componenti core per definire le opzioni consentite come parte di un modello, e poi ulteriormente configurati dall’autore della pagina per definire il contenuto della pagina effettiva, ogni componente può avere opzioni in due diverse finestre di dialogo.

|  | Descrizione | Controlli | Esempi |
|--- |--- |--- |--- |
| **Finestra di dialogo Modifica** | Opzioni che un **autore di pagina** può modificare durante la normale modifica della pagina per i componenti inseriti | Il contenuto visualizzato dal componente e come apparirà alla fine sulla pagina. | Formattazione del testo di contenuto, rotazione di un&#39;immagine su una pagina |
| **Finestra di dialogo Progettazione** | Opzioni che un **autore di modelli** può modificare durante la configurazione di un modello di pagina. | Opzioni disponibili per l’autore della pagina durante la modifica del componente | Quali opzioni di formattazione del testo sono disponibili, quali opzioni di formattazione dell&#39;immagine sono disponibili |

### Stile del componente {#component-styling}

Gli stili della maggior parte dei componenti core possono essere definiti utilizzando il sistema di stili AEM.

* Un autore di modelli può definire gli stili disponibili per un particolare componente nella finestra di dialogo Progettazione di tale componente.
* L’autore del contenuto può quindi scegliere quali stili applicare quando aggiunge il componente e crea il contenuto.

Per ulteriori dettagli, consulta la documentazione [Sistema di stili](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html) .

## Riferimenti per sviluppatori {#developer-resources}

Per informazioni tecniche sui componenti core, consulta la documentazione per gli sviluppatori [Sviluppo di componenti core](/help/developing/overview.md) .
