---
title: Authoring con i Componenti core
description: 'In AEM, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create: i Componenti core offrono funzionalità flessibili e avanzate per l’authoring.'
role: Architect, Developer, Admin, User
exl-id: 56e58303-a178-45ab-b59d-e374c9cf90cf
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 100%

---

# Authoring con i Componenti core

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create.

I Componenti core offrono funzionalità flessibili e avanzate per l’authoring. Il [sito di riferimento WKND](https://wknd.site) e i relativi componenti illustrano come i Componenti core possono essere utilizzati per implementare un’esperienza avanzata con i siti web.

Per avere un’idea dei Componenti core e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_it).

Per un’introduzione più dettagliata e orientata agli sviluppatori dell’implementazione dei Componenti core in un progetto AEM utilizzando [Archetipo progetto AEM](/help/developing/archetype/overview.md), vedi [l’esercitazione WKND.](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=it)

>[!NOTE]
>
>I Componenti core non sono immediatamente disponibili per gli autori; il [team di sviluppo deve prima integrarli nel tuo ambiente](/help/get-started/using.md). Una volta integrati, possono essere resi disponibili e preconfigurati tramite l’[editor di modelli](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it).

>[!CAUTION]
>
>I Componenti core [richiedono AEM 6.4 o versioni successive](/help/versions.md) e l’uso di [modelli modificabili](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it). Non funzionano né con l’interfaccia utente classica né con i modelli statici.

## Authoring con i Componenti core {#authoring-with-core-components}

In qualità di autore, ti renderai conto dei molti vantaggi offerti dai Componenti core, tra cui:

* Semplicità di utilizzo e ottima integrazione con [l’editor di pagine](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=it)

* Funzionalità avanzate per soddisfare molti casi d’uso, come illustrato dal [sito di riferimento WKND](https://wknd.site) e dalla [libreria dei componenti](https://adobe.com/go/aem_cmp_library_it)

* [Possibilità di pre-configurazione](#pre-configuring-core-components) per definire le funzioni disponibili per gli autori di pagine tramite [l’editor di modelli](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it)

* Progettazione basata sulle [linee guida per l’accessibilità](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html?lang=it)

* Supporto del [layout reattivo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html?lang=it)

* [Facilità di localizzazione](localization.md)

I componenti sono disponibili nella scheda **Componenti** visualizzata nel pannello laterale dell’editor di pagine durante la [modifica di una pagina](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=it).

I componenti sono raggruppati in categorie, chiamate gruppi di componenti, per semplificarne l’organizzazione e l’applicazione di filtri. Il nome del gruppo di componenti viene visualizzato con il componente nel [browser di componenti](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=it) ed è anche possibile filtrare per gruppo per trovare facilmente il componente giusto.

>[!NOTE]
>
>Per impostazione predefinita, i Componenti core fanno parte di un gruppo nascosto e non sono visibili nel browser di componenti.
>
>Aggiungi i componenti richiesti a un gruppo visibile o personalizzali affinché siano disponibili per gli autori.

## Preconfigurazione dei Componenti core {#pre-configuring-core-components}

La configurazione dei Componenti di base era compito di uno sviluppatore. Tuttavia, con i Componenti core, un autore di modelli può ora configurare diverse funzionalità tramite l’editor di modelli.

Ad esempio, se un componente Immagine non deve consentire il caricamento di immagini dal file system oppure se un componente Testo deve consentire solo determinate formattazioni dei paragrafi, queste funzioni possono essere abilitate o disabilitate con un semplice clic.

Per ulteriori informazioni, vedi [Creazione di modelli di pagina](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it).

### Finestre di dialogo per modifica e per progettazione {#edit-and-design-dialogs}

Poiché gli autori dei modelli possono preconfigurare i Componenti core per definire le opzioni consentite come parte di un modello e poi l’autore della pagina può ulteriormente configurarli per definire il contenuto della pagina effettiva, ogni componente può avere opzioni in due diverse finestre di dialogo.

|  | Descrizione | Cosa controlla | Esempi |
|--- |--- |--- |--- |
| **Finestra di dialogo per modifica** | Le opzioni che un **autore di pagine** può modificare durante la normale modifica di una pagina in relazione ai componenti inseriti | Il contenuto visualizzato dal componente e come apparirà alla fine sulla pagina. | Formattazione del testo del contenuto, rotazione di un’immagine su una pagina |
| **Finestra di dialogo per progettazione** | Le opzioni che un **autore di modelli** può modificare durante la configurazione del modello di una pagina. | Le opzioni disponibili per l’autore della pagina durante la modifica del componente | Quali opzioni di formattazione del testo e quali opzioni di posizionamento dell’immagine sono disponibili |

### Stili dei componenti {#component-styling}

Gli stili della maggior parte dei Componenti core possono essere definiti utilizzando il sistema di stili di AEM.

* Un autore di modelli può definire gli stili disponibili per un particolare componente nella finestra di dialogo per progettazione di quel componente.
* L’autore di contenuto può quindi scegliere quali stili applicare quando aggiunge il componente e crea il contenuto.

Per ulteriori dettagli, vedi la documentazione sul [sistema di stili](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html?lang=it).

## Risorse per sviluppatori {#developer-resources}

Per informazioni tecniche sui Componenti core, vedi la documentazione [Sviluppo di Componenti core](/help/developing/overview.md) per gli sviluppatori.
