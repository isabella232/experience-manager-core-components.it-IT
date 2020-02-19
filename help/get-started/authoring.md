---
title: Authoring con i componenti core
description: In AEM, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine create. I componenti core offrono funzionalità di authoring flessibili e avanzate.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Creazione con componenti core

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create.

I componenti core offrono funzionalità di authoring flessibili e avanzate. Il sito [di riferimento](https://wknd.site) WKND e i suoi componenti illustrano come i componenti core possono essere utilizzati per implementare un’esperienza Web avanzata.

Per conoscere i componenti core e vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](https://adobe.com/go/aem_cmp_library)componenti.

Per un’introduzione più dettagliata e orientata agli sviluppatori all’implementazione dei componenti core in un progetto AEM, utilizzate l’archetipo [di progetto](/help/developing/archetype/overview.md) AEM e controllate [l’esercitazione WKND.](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!NOTE]
>
>I componenti core non sono immediatamente disponibili per gli autori; [devono prima essere integrarti nell’ambiente dal team di sviluppo](/help/get-started/using.md). Once integrated, they may be made available and pre-configured via the [template editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!CAUTION]
>
>I componenti core [richiedono AEM 6.3 o versione successiva](/help/versions.md) e richiedono l’uso di modelli [](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)modificabili. Non funzionano né con l’interfaccia classica né con modelli statici.

## Authoring con i componenti core {#authoring-with-core-components}

Come autore, noterete diversi vantaggi dei componenti core, tra cui:

* Simple to use and well-integrated with the [page editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)

* Funzionalità avanzate per soddisfare molti casi di utilizzo, come illustrato dal sito [di riferimento](https://wknd.site) WKND e dalla libreria [di componenti](https://adobe.com/go/aem_cmp_library)

* [Possibilità di pre-configurazione](#pre-configuring-core-components) per definire le funzioni disponibili per gli autori di pagine tramite l’editor [modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

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

Gli stili della maggior parte dei componenti core possono essere definiti utilizzando il sistema di stile di AEM.

* Un autore di un modello può definire gli stili disponibili per un particolare componente nella finestra di dialogo Progettazione del componente.
* L’autore del contenuto può quindi scegliere quali stili applicare quando aggiunge il componente e crea il contenuto.

Per ulteriori dettagli, consulta la documentazione [Style System](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html) .

>[!NOTE]
>
>In AEM 6.3, per abilitare la funzione del sistema di stile è necessario Service Pack 2 (6.3.2.0) o successivo.

## Elenco dei componenti core disponibili {#list-of-core-components-available}

Di seguito è riportato un elenco dei componenti core disponibili collegati alle pagine che descrivono nel dettaglio le funzionalità di modifica e di progettazione della finestra di dialogo.

La versione corrente dei componenti core include i seguenti componenti.

* [Pannello a soffietto](/help/components/accordion.md)
* [Breadcrumb](/help/components/breadcrumb.md)
* [Pulsante](/help/components/button.md)
* [Contenitore](/help/components/container.md)
* [Carosello](/help/components/carousel.md)
* [Frammento di contenuto](/help/components/content-fragment-component.md)
* [Elenco di frammenti di contenuto](/help/components/content-fragment-list.md)
* [Scarica](/help/components/download.md)
* [Incorpora](/help/components/embed.md)
* [Frammento esperienza](/help/components/experience-fragment.md)
* [Pulsante modulo](/help/components/forms/form-button.md)
* [Contenitore modulo](/help/components/forms/form-container.md)
* [Nascosto per modulo](/help/components/forms/form-hidden.md)
* [Opzioni modulo](/help/components/forms/form-options.md)
* [Testo modulo](/help/components/forms/form-text.md)
* [Immagine](/help/components/image.md)
* [Navigazione lingua](/help/components/language-navigation.md)
* [Elenco](/help/components/list.md)
* [Navigazione](/help/components/navigation.md)
* [Pagina](/help/components/page.md)
* [Ricerca rapida](/help/components/quick-search.md)
* [Separatore](/help/components/separator.md)
* [Condivisione social media](/help/components/sharing.md)
* [Schede](/help/components/tabs.md)
* [Testo](/help/components/text.md)
* [Titolo](/help/components/title.md)

>[!CAUTION]
>
>Alcune versioni di singoli componenti core potrebbero essere compatibili solo con determinate versioni di AEM.
>
>Consulta la pagina della guida del componente specifico (mediante il collegamento incluso nell’elenco precedente) per informazioni sulla compatibilità, oppure fai riferimento al documento [Versioni dei componenti core](/help/versions.md).

>[!NOTE]
>
>A seconda dell’istanza corrente è possibile che siano presenti componenti personalizzati sviluppati esplicitamente per le tue esigenze. Questi possono anche avere lo stesso nome di alcuni dei componenti qui descritti.
>I componenti core del modulo non sono correlati ad AEM Forms.

## Riferimenti per sviluppatori {#developer-resources}

Per informazioni tecniche sui componenti di base, consulta la documentazione per gli sviluppatori [Sviluppo di componenti](/help/developing/overview.md) di base.
