---
title: Authoring con i componenti core
description: In AEM, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine create. I componenti core offrono funzionalità di authoring flessibili e avanzate.
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Authoring con componenti core

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create.

I componenti core offrono funzionalità di authoring flessibili e avanzate. Il sito [di riferimento](https://wknd.site) WKND e i suoi componenti illustrano come i componenti core possono essere utilizzati per implementare un’esperienza Web avanzata.

Per conoscere i componenti core e vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](https://adobe.com/go/aem_cmp_library)componenti.

Per un&#39;introduzione più dettagliata e orientata agli sviluppatori all&#39;implementazione dei componenti core in un progetto AEM, utilizzate l&#39; [AEM Project Archetype](/help/developing/archetype/overview.md) , controllate [l&#39;esercitazione WKND.](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!NOTE]
>
>I componenti core non sono immediatamente disponibili per gli autori; [devono prima essere integrarti nell’ambiente dal team di sviluppo](/help/get-started/using.md). Once integrated, they may be made available and pre-configured via the [template editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!CAUTION]
>
>I componenti core [richiedono AEM 6.4 o versioni successive](/help/versions.md) e richiedono l’uso di modelli [](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)modificabili. Non funzionano né con l’interfaccia classica né con modelli statici.

## Authoring con i componenti core {#authoring-with-core-components}

Come autore, noterete diversi vantaggi dei componenti core, tra cui:

* Simple to use and well-integrated with the [page editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)

* Funzionalità avanzate per soddisfare molti casi di utilizzo, come illustrato dal sito [di riferimento](https://wknd.site) WKND e dalla libreria [di componenti](https://adobe.com/go/aem_cmp_library)

* [Possibilità di pre-configurazione](#pre-configuring-core-components) per definire quali funzioni sono disponibili per gli autori di pagine tramite l’editor [modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

* Built around [accessibility guidelines](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)

* Built to support [responsive layout](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)

* Progettato per supportare una localizzazione [semplice](localization.md)

Components are available on the **Components** tab of the side panel of the page editor when [editing a page](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html).

I componenti sono raggruppati in base alle categorie denominate gruppi di componenti per organizzare e filtrare facilmente i componenti. Il nome del gruppo di componenti viene visualizzato con il componente nel browser [dei](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html) componenti ed è anche possibile filtrare per gruppo per trovare facilmente il componente corretto.

>[!NOTE]
>
>Per impostazione predefinita, i componenti core fanno parte di un gruppo nascosto e non sono visibili nel browser dei componenti.
>
>Aggiungete i componenti richiesti a un gruppo visibile o personalizzateli affinché siano disponibili per gli autori.

## Pre-configurazione dei componenti core {#pre-configuring-core-components}

La configurazione dei componenti di base era il lavoro di uno sviluppatore. Tuttavia, con i componenti core, un autore di modelli può ora configurare diverse funzionalità tramite l&#39;editor modelli.

Ad esempio, se un componente immagine non deve consentire il caricamento di immagini dal file system, o se un componente di testo deve consentire solo la formattazione di alcuni paragrafi, queste funzioni possono essere attivate o disattivate con un semplice clic.

Per ulteriori informazioni, consultate [Creazione di modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) di pagina.

### Finestre di dialogo Modifica e Progettazione {#edit-and-design-dialogs}

Poiché i componenti core possono essere preconfigurati dagli autori dei modelli per definire le opzioni consentite come parte di un modello, e successivamente configurati dall&#39;autore della pagina per definire il contenuto effettivo della pagina, ciascun componente può avere opzioni in due diverse finestre di dialogo.

|  | Descrizione | Controlli | Esempi |
|--- |--- |--- |--- |
| **Finestra di dialogo Modifica** | Opzioni che un autore **di** pagina può modificare durante la normale modifica della pagina per i componenti inseriti | Il contenuto visualizzato dal componente e la relativa visualizzazione finale sulla pagina. | Formattazione del testo del contenuto, rotazione di un&#39;immagine su una pagina |
| **Finestra di dialogo Progettazione** | Opzioni che un autore **del** modello può modificare durante la configurazione di un modello di pagina. | Opzioni disponibili per l’autore della pagina durante la modifica del componente | Quali opzioni di formattazione del testo sono disponibili, quali opzioni di formattazione dell&#39;immagine sono disponibili |

### Attribuzione stile componente {#component-styling}

Gli stili della maggior parte dei componenti core possono essere definiti utilizzando il sistema di stile AEM.

* Un autore di un modello può definire gli stili disponibili per un particolare componente nella finestra di dialogo Progettazione del componente.
* L’autore del contenuto può quindi scegliere quali stili applicare quando aggiunge il componente e crea il contenuto.

Per ulteriori dettagli, consulta la documentazione [Style System](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html) .

## Riferimenti per sviluppatori {#developer-resources}

Per informazioni tecniche sui componenti di base, consulta la documentazione per gli sviluppatori [Sviluppo di componenti](/help/developing/overview.md) di base.
