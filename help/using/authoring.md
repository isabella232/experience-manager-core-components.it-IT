---
title: Authoring con i componenti core
seo-title: Authoring con i componenti core
description: In AEM, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine create - Componenti core offrono funzionalità di authoring flessibili e ricche di funzionalità.
seo-description: In AEM, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine create - Componenti core offrono funzionalità di authoring flessibili e ricche di funzionalità.
uuid: 4 a 54 cd 4 c -3 d 89-4683-8301-bf 1 e 634736 e 3
content-type: riferimento
topic-tags: authoring
discoiquuid: 8751 e 490-d 427-44 f 2-b 767-51935 afda 988
translation-type: tm+mt
source-git-commit: b6fbef1cff2908533df6573cd3a92266857ba93f

---


# Autore con componenti core

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create.

I componenti core offrono funzionalità di authoring flessibili e avanzate. The [We.Retail reference site](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) illustrates how the core components can be used.

Per provare i componenti core e vedere esempi di opzioni di configurazione e output HTML e JSON, visita la [Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html).

Per un'introduzione dettagliata agli sviluppatori per l'implementazione dei componenti core su un progetto AEM, [consulta l'esercitazione WKND.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

>[!NOTE]
>
>Core Components are not immediately available to authors, the [development team must first integrate them to your environment](using.md). Once integrated, they may be made available and pre-configured via the [template editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html).

>[!CAUTION]
>
>I componenti core [richiedono AEM 6.3 o versione successiva](versions.md) e richiedono l'uso di [modelli modificabili](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html). Non funzionano con l'interfaccia classica né con i modelli statici.

## Authoring con i componenti core {#authoring-with-core-components}

In qualità di autore noterete diversi vantaggi dei componenti core, tra cui:

* Simple to use and well-integrated with the [page editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)

* Funzionalità avanzate per contenere molti casi d'uso [come illustrato in We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) e nella libreria [Componenti](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)

* [Preconfigurabile](#pre-configuring-core-components) per definire quali funzioni sono disponibili per gli autori di pagine tramite l'editor [modelli](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

* Built around [accessibility guidelines](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

* Built to support [responsive layout](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/responsive-layout.html)

* Creato per supportare [facilmente la localizzazione](localization.md)

Components are available on the **Components** tab of the side panel of the page editor when [editing a page](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html).

I componenti sono raggruppati in base alle categorie denominate gruppi di componenti per organizzare e filtrare i componenti in modo semplice. Il nome del gruppo di componenti viene visualizzato con il componente nel browser [Componenti](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) ed è anche possibile filtrare per gruppo per trovare facilmente il componente giusto.

>[!NOTE]
>
>I componenti core sono per impostazione predefinita parte di un gruppo nascosto e non sono visibili nel browser Componenti.
>
>Aggiungete i componenti richiesti a un gruppo visibile o personalizzateli affinché siano disponibili per gli autori.

## Preconfigurazione dei componenti core {#pre-configuring-core-components}

Configuring Foundation Components was the job of a developer. Tuttavia, con i componenti core, l'autore di un modello ora può configurare una serie di funzionalità tramite l'editor modelli.

Ad esempio, se un componente immagine non consente il caricamento di immagini dal file system o se un componente di testo consenti solo determinate formattazioni, queste funzioni possono essere attivate o disattivate con un semplice clic.

Per ulteriori informazioni, consultate [Creazione di modelli](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) di pagina.

### Modifica e progettazione di finestre di dialogo {#edit-and-design-dialogs}

Poiché i componenti core possono essere preconfigurati dagli autori dei modelli per definire le opzioni consentite come parte di un modello e quindi configurate dall'autore della pagina per definire il contenuto effettivo della pagina, ogni componente può avere opzioni in due finestre di dialogo diverse.

|  | Descrizione | Controlli | Esempi |
|--- |--- |--- |--- |
| **Finestra di dialogo di modifica** | Opzioni che possono essere modificate dall **'autore** di una pagina durante la modifica normale delle pagine per i componenti inseriti | Contenuto visualizzato dal componente e aspetto finale sulla pagina. | Formattazione del testo del contenuto, rotazione di un'immagine su una pagina |
| **Finestra di dialogo Progettazione** | Opzioni che possono essere modificate da un **autore** di modelli durante la configurazione di un modello di pagina. | Opzioni disponibili nell'autore della pagina per la modifica del componente | Opzioni di formattazione del testo disponibili, opzioni disponibili per l'immagine |

### Attribuzione stile dei componenti {#component-styling}

Gli stili della maggior parte dei componenti core possono essere definiti mediante il sistema di stile AEM.

* Un autore può definire gli stili disponibili per un particolare componente nella finestra di dialogo Progettazione di tale componente.
* L'autore del contenuto può quindi scegliere gli stili da applicare quando si aggiunge il componente e si crea un contenuto.

Per ulteriori dettagli, consultate [la documentazione di Sistema](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/style-system.html) di stile.

>[!NOTE]
>
>In AEM 6.3, service pack 2 (6.3.2.0) o più recente è richiesto per abilitare la funzionalità del sistema di stile.

## Elenco dei componenti core disponibili {#list-of-core-components-available}

Di seguito è riportato un elenco dei componenti core disponibili collegati alle pagine che descrivono in dettaglio le capacità della finestra di dialogo di modifica e progettazione.

La versione corrente dei componenti core presenta i seguenti componenti.

* [Accordion](accordion.md)
* [Breadcrumb](breadcrumb.md)
* [Pulsante](button.md)
* [Contenitore](container.md)
* [Carosello](carousel.md)
* [Frammento di contenuto](content-fragment-component.md)
* [Elenco frammenti di contenuto](content-fragment-list.md)
* [Scarica](download.md)
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
>Per ulteriori informazioni, consultate la pagina di aiuto (collegata a nell'elenco precedente) per il componente specifico per informazioni sulla compatibilità o fate riferimento al [documento Versioni](versions.md) componenti principali.

>[!NOTE]
>
>A seconda dell’istanza corrente è possibile che siano presenti componenti personalizzati sviluppati esplicitamente per le tue esigenze. Questi possono anche avere lo stesso nome di alcuni dei componenti qui descritti.
>I componenti core del modulo non sono correlati ad AEM Forms.

## Riferimenti per sviluppatori {#developer-resources}

Per informazioni tecniche sui componenti core, consultate [la documentazione sullo](developing.md) sviluppo dei componenti core Sviluppo.
