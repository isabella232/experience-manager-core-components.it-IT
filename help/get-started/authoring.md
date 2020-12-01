---
title: Authoring con i componenti core
description: In AEM, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine create. I componenti core offrono funzionalità di authoring flessibili e avanzate.
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 7%

---


# Authoring con componenti core

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create.

I componenti core offrono funzionalità di authoring flessibili e avanzate. Il sito di riferimento [WKND](https://wknd.site) e i relativi componenti di base possono essere utilizzati per implementare un&#39;esperienza Web avanzata.

Per conoscere i componenti core e vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library).

Per un&#39;introduzione più dettagliata e orientata agli sviluppatori all&#39;implementazione dei componenti core in un progetto AEM, utilizzate il [AEM Project Archetype](/help/developing/archetype/overview.md) [check-out dell&#39;esercitazione WKND.](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!NOTE]
>
>I componenti core non sono immediatamente disponibili per gli autori; [devono prima essere integrarti nell’ambiente dal team di sviluppo](/help/get-started/using.md). Una volta integrati, possono essere resi disponibili e preconfigurati tramite l&#39;editor [modello](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!CAUTION]
>
>I componenti core [richiedono AEM 6.4 o superiore](/help/versions.md) e richiedono l&#39;uso di [modelli modificabili](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html). Non funzionano né con l’interfaccia classica né con modelli statici.

## Authoring con i componenti core {#authoring-with-core-components}

Come autore, noterete diversi vantaggi dei componenti core, tra cui:

* Semplice da usare e ben integrato con l&#39;editor di [pagine](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)

* Funzionalità avanzate per soddisfare molti casi di utilizzo, come illustrato dal [sito di riferimento WKND](https://wknd.site) e nella [Libreria componenti](https://adobe.com/go/aem_cmp_library)

* [Possibilità di pre-](#pre-configuring-core-components) configurazione per definire le funzioni disponibili per gli autori delle pagine tramite l’editor  [modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

* Progettazione basata sulle [linee guida sull&#39;accessibilità](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)

* Progettato per supportare [layout reattivo](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)

* Progettato per supportare [localizzazione semplice](localization.md)

I componenti sono disponibili nella scheda **Componenti** del pannello laterale dell&#39;Editor pagina durante la [modifica di una pagina](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html).

I componenti sono raggruppati in base alle categorie denominate gruppi di componenti per organizzare e filtrare facilmente i componenti. Il nome del gruppo di componenti viene visualizzato con il componente nel [browser Componenti](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html) ed è anche possibile filtrare per gruppo per trovare facilmente il componente giusto.

>[!NOTE]
>
>Per impostazione predefinita, i componenti core fanno parte di un gruppo nascosto e non sono visibili nel browser dei componenti.
>
>Aggiungete i componenti richiesti a un gruppo visibile o personalizzateli affinché siano disponibili per gli autori.

## Pre-configurazione dei componenti core {#pre-configuring-core-components}

La configurazione dei componenti di base era il lavoro di uno sviluppatore. Tuttavia, con i componenti core, un autore di modelli può ora configurare diverse funzionalità tramite l&#39;editor modelli.

Ad esempio, se un componente immagine non deve consentire il caricamento di immagini dal file system, o se un componente di testo deve consentire solo la formattazione di alcuni paragrafi, queste funzioni possono essere attivate o disattivate con un semplice clic.

Per ulteriori informazioni, vedere [Creazione di modelli di pagina](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

### Finestre di dialogo Modifica e Progettazione {#edit-and-design-dialogs}

Poiché i componenti core possono essere preconfigurati dagli autori dei modelli per definire le opzioni consentite come parte di un modello, e successivamente configurati dall&#39;autore della pagina per definire il contenuto effettivo della pagina, ciascun componente può avere opzioni in due diverse finestre di dialogo.

|  | Descrizione | Controlli | Esempi |
|--- |--- |--- |--- |
| **Finestra di dialogo Modifica** | Opzioni che un **autore di pagina** può modificare durante la normale modifica di pagina per i componenti inseriti | Il contenuto visualizzato dal componente e la relativa visualizzazione finale sulla pagina. | Formattazione del testo del contenuto, rotazione di un&#39;immagine su una pagina |
| **Finestra di dialogo Progettazione** | Opzioni che un **autore del modello** può modificare durante la configurazione di un modello di pagina. | Opzioni disponibili per l’autore della pagina durante la modifica del componente | Quali opzioni di formattazione del testo sono disponibili, quali opzioni di formattazione dell&#39;immagine sono disponibili |

### Attribuzione stile componente {#component-styling}

Gli stili della maggior parte dei componenti core possono essere definiti utilizzando il sistema di stile AEM.

* Un autore di un modello può definire gli stili disponibili per un particolare componente nella finestra di dialogo Progettazione del componente.
* L’autore del contenuto può quindi scegliere quali stili applicare quando aggiunge il componente e crea il contenuto.

Per ulteriori dettagli, consultare la documentazione relativa al [Sistema di stile](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html).

## Riferimenti per sviluppatori {#developer-resources}

Per informazioni tecniche sui componenti core, consultate la documentazione per gli sviluppatori [Developing Core Components](/help/developing/overview.md) .
