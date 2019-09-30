---
title: Authoring con i componenti core
seo-title: Authoring con i componenti core
description: In AEM, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine create. I componenti core offrono funzionalità di authoring flessibili e avanzate.
seo-description: In AEM, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine create. I componenti core offrono funzionalità di authoring flessibili e avanzate.
uuid: 4a54cd4c-3d89-4683-8301-bf1e634736e3
content-type: riferimento
topic-tags: authoring
discoiquuid: 8751e490-d427-44f2-b767-51935afda988
translation-type: tm+mt
source-git-commit: bf1993085c4cd95121cb6d78be8c52934802b645

---


# Creazione con componenti core

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create.

I componenti core offrono funzionalità di authoring flessibili e avanzate. The [We.Retail reference site](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) illustrates how the core components can be used.

Per conoscere i componenti core e vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)componenti.

Per un’introduzione più dettagliata e orientata agli sviluppatori all’implementazione dei componenti core in un progetto AEM, consultate [l’esercitazione WKND.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

>[!NOTE]
>
>Core Components are not immediately available to authors, the [development team must first integrate them to your environment](using.md). Once integrated, they may be made available and pre-configured via the [template editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html).

>[!CAUTION]
>
>I componenti core [richiedono AEM 6.3 o versione successiva](versions.md) e richiedono l’uso di modelli [](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)modificabili. Non funzionano né con l’interfaccia classica né con modelli statici.

## Authoring con i componenti core {#authoring-with-core-components}

Come autore, noterete diversi vantaggi dei componenti core, tra cui:

* Simple to use and well-integrated with the [page editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)

* Funzionalità avanzate per soddisfare molti casi di utilizzo, come [illustrato in We.Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) e nella libreria [di componenti](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)

* [Possibilità di pre-configurazione](#pre-configuring-core-components) per definire le funzioni disponibili per gli autori di pagine tramite l’editor [modelli](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

* Built around [accessibility guidelines](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

* Built to support [responsive layout](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/responsive-layout.html)

* Progettato per supportare una localizzazione [semplice](localization.md)

Components are available on the **Components** tab of the side panel of the page editor when [editing a page](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html).

I componenti sono raggruppati in base alle categorie denominate gruppi di componenti per organizzare e filtrare facilmente i componenti. Il nome del gruppo di componenti viene visualizzato con il componente nel browser [dei](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) componenti ed è anche possibile filtrare per gruppo per trovare facilmente il componente corretto.

>[!NOTE]
>
>Per impostazione predefinita, i componenti core fanno parte di un gruppo nascosto e non sono visibili nel browser dei componenti.
>
>Aggiungete i componenti richiesti a un gruppo visibile o personalizzateli affinché siano disponibili per gli autori.

## Pre-configurazione dei componenti core {#pre-configuring-core-components}

La configurazione dei componenti di base era il lavoro di uno sviluppatore. Tuttavia, con i componenti core, un autore di modelli può ora configurare diverse funzionalità tramite l'editor modelli.

Ad esempio, se un componente immagine non deve consentire il caricamento di immagini dal file system, o se un componente di testo deve consentire solo la formattazione di alcuni paragrafi, queste funzioni possono essere attivate o disattivate con un semplice clic.

Per ulteriori informazioni, consultate [Creazione di modelli](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) di pagina.

### Finestre di dialogo Modifica e Progettazione {#edit-and-design-dialogs}

Poiché i componenti core possono essere preconfigurati dagli autori dei modelli per definire le opzioni consentite come parte di un modello, e successivamente configurati dall'autore della pagina per definire il contenuto effettivo della pagina, ciascun componente può avere opzioni in due diverse finestre di dialogo.

|  | Descrizione | Controlli | Esempi |
|--- |--- |--- |--- |
| **Finestra di dialogo Modifica** | Opzioni che un autore **di** pagina può modificare durante la normale modifica della pagina per i componenti inseriti | Il contenuto visualizzato dal componente e la relativa visualizzazione finale sulla pagina. | Formattazione del testo del contenuto, rotazione di un'immagine su una pagina |
| **Finestra di dialogo Progettazione** | Opzioni che un autore **del** modello può modificare durante la configurazione di un modello di pagina. | Opzioni disponibili per l’autore della pagina durante la modifica del componente | Quali opzioni di formattazione del testo sono disponibili, quali opzioni di formattazione dell'immagine sono disponibili |

### Attribuzione stile componente {#component-styling}

Gli stili della maggior parte dei componenti core possono essere definiti utilizzando il sistema di stile di AEM.

* Un autore di un modello può definire gli stili disponibili per un particolare componente nella finestra di dialogo Progettazione del componente.
* L’autore del contenuto può quindi scegliere quali stili applicare quando aggiunge il componente e crea il contenuto.

Per ulteriori dettagli, consulta la documentazione [Style System](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/style-system.html) .

>[!NOTE]
>
>In AEM 6.3, per abilitare la funzione del sistema di stile è necessario Service Pack 2 (6.3.2.0) o successivo.

## Elenco dei componenti core disponibili {#list-of-core-components-available}

Di seguito è riportato un elenco dei componenti core disponibili collegati alle pagine che descrivono nel dettaglio le funzionalità di modifica e di progettazione della finestra di dialogo.

La versione corrente di Core Components include i seguenti componenti.

* [Accordion](accordion.md)
* [Breadcrumb](breadcrumb.md)
* [Pulsante](button.md)
* [Contenitore](container.md)
* [Carosello](carousel.md)
* [Frammento di contenuto](content-fragment-component.md)
* [Elenco frammenti di contenuto](content-fragment-list.md)
* [Scarica](download.md)
* [Incorpora](embed.md)
* [Frammento esperienza](experience-fragment.md)
* [Pulsante modulo](form-button.md)
* [Contenitore modulo](form-container.md)
* [Nascosto per modulo](form-hidden.md)
* [Opzioni modulo](form-options.md)
* [Testo modulo](form-text.md)
* [Immagine](image.md)
* [Navigazione lingua](language-navigation.md)
* [Elenco](list.md)
* [Navigazione](navigation.md)
* [Pagina](page.md)
* [Ricerca rapida](quick-search.md)
* [Separatore](separator.md)
* [Condivisione social media](sharing.md)
* [Schede](tabs.md)
* [Testo](text.md)
* [Titolo](title.md)

>[!CAUTION]
>
>Alcune versioni di singoli componenti core possono essere compatibili solo con determinate versioni di AEM.
>
>Per informazioni sulla compatibilità, consultate la singola pagina della guida (collegata all’elenco precedente) per il componente specifico oppure fate riferimento al documento Versioni [dei componenti](versions.md) core per ulteriori informazioni.

>[!NOTE]
>
>A seconda dell’istanza corrente è possibile che siano presenti componenti personalizzati sviluppati esplicitamente per le tue esigenze. Questi possono anche avere lo stesso nome di alcuni dei componenti qui descritti.
>I componenti core del modulo non sono correlati ad AEM Forms.

## Riferimenti per sviluppatori {#developer-resources}

Per informazioni tecniche sui componenti di base, consulta la documentazione per gli sviluppatori [Sviluppo di componenti](developing.md) di base.
