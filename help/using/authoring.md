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
source-git-commit: 600aefa49d6247c290b8fb9f6acf5548126b3f61

---


# Autore con componenti core

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine che vengono create. Questa sezione descrive i componenti core, che forniscono tipi di contenuto essenziali per la creazione di pagine.

I componenti core offrono funzionalità di authoring flessibili e avanzate. Il sito di riferimento [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) illustra come possono essere utilizzati i componenti core.

>[!NOTE]
>
>I componenti core non sono immediatamente disponibili per gli autori, il team [di sviluppo deve prima integrarli nell&#39;ambiente](using.md). Una volta integrati, possono essere resi disponibili e pre-configurati tramite l&#39;editor [modelli](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) o in modalità [progettazione](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-designmode.html).

>[!CAUTION]
>
>I componenti core [richiedono AEM 6.3 o versione successiva](versions.md) e non funzionano con l&#39;interfaccia classica.

## Authoring con i componenti core {#authoring-with-core-components}

Per comprendere i componenti core, consulta la [Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library.html), che mostra i componenti core e fornisce esempi di utilizzo.

In qualità di autore noterete diversi vantaggi dei componenti core, tra cui:

* Semplice utilizzo e perfettamente integrato con l&#39;editor [pagina](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)
* Funzionalità avanzate per contenere molti casi d&#39;uso [come illustrato in We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)
* [Preconfigurabile](#pre-configuring-core-components) per definire quali funzioni sono disponibili per gli autori delle pagine
   * Tramite l&#39;editor [modelli](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) per [modelli modificabili](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/page-templates-editable.html)
   * Modalità [di progettazione](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-designmode.html) per [modelli statici](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/page-templates-static.html)

* Basato sulle [linee guida per l&#39;accessibilità](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

* Progettato per supportare [il layout reattivo](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/responsive-layout.html)

I componenti sono disponibili nella scheda **Componenti** del pannello laterale dell&#39;editor pagina quando [si modifica una pagina](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html).

I componenti sono raggruppati in base alle categorie denominate gruppi di componenti per organizzare e filtrare i componenti in modo semplice. Il nome del gruppo di componenti viene visualizzato con il componente nel browser [Componenti](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) ed è anche possibile filtrare per gruppo per trovare facilmente il componente giusto.

>[!NOTE]
>
>I componenti core sono per impostazione predefinita parte di un gruppo nascosto e non sono visibili nel browser Componenti.
>
>Aggiungete i componenti richiesti a un gruppo visibile o personalizzateli affinché siano disponibili per gli autori.

## Preconfigurazione dei componenti core {#pre-configuring-core-components}

Configuring Foundation Components was the job of a developer. Tuttavia, con i componenti core, l&#39;autore di un modello può configurare una serie di funzionalità tramite l&#39;editor modelli o in modalità progettazione.

Ad esempio, se un componente immagine non consente il caricamento di immagini dal file system o se un componente di testo consenti solo determinate formattazioni, queste funzioni possono essere attivate o disattivate con un semplice clic.

Per ulteriori informazioni, consultate [Creazione di modelli](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) di pagina.

### Modifica e progettazione di finestre di dialogo {#edit-and-design-dialogs}

Poiché i componenti core possono essere preconfigurati dagli autori dei modelli per definire le opzioni consentite come parte di un modello e quindi configurate dall&#39;autore della pagina per definire il contenuto effettivo della pagina, ogni componente può avere opzioni in due finestre di dialogo diverse.

|  | Descrizione | Controlli | Esempi |
|--- |--- |--- |--- |
| **Finestra di dialogo di modifica** | Opzioni che possono essere modificate dall **&#39;autore** di una pagina durante la modifica normale delle pagine per i componenti inseriti | Contenuto visualizzato dal componente e aspetto finale sulla pagina. | Formattazione del testo del contenuto, rotazione di un&#39;immagine su una pagina |
| **Finestra di dialogo Progettazione** | Opzioni che possono essere modificate da un **autore** di modelli durante la configurazione di un modello di pagina. | Opzioni disponibili nell&#39;autore della pagina per la modifica del componente | Opzioni di formattazione del testo disponibili, opzioni disponibili per l&#39;immagine |

### Attribuzione stile dei componenti {#component-styling}

Gli stili della maggior parte dei componenti core possono essere definiti mediante il sistema di stile AEM.

* Un autore può definire gli stili disponibili per un particolare componente nella finestra di dialogo Progettazione di tale componente.
* L&#39;autore del contenuto può quindi scegliere gli stili da applicare quando si aggiunge il componente e si crea un contenuto.

Per ulteriori dettagli, consultate [la documentazione di Sistema](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/style-system.html) di stile.

>[!NOTE]
>
>In AEM 6.3, service pack 2 (6.3.2.0) o più recente è richiesto per abilitare la funzionalità del sistema di stile.

## Elenco dei componenti core disponibili {#list-of-core-components-available}

Di seguito è riportato un elenco dei componenti core disponibili collegati alle pagine che descrivono in dettaglio le capacità della finestra di dialogo di modifica e progettazione.

La versione corrente dei componenti core presenta i seguenti componenti.

* [Breadcrumb](breadcrumb.md)
* [Pulsante modulo](form-button.md)
* [Carosello](carousel.md)
* [Contenitore modulo](form-container.md)
* [Frammento di contenuto](content-fragment-component.md)
* [Elenco frammenti di contenuto](content-fragment-list.md)
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
* [Teaser](teaser.md)
* [Testo](text.md)
* [Titolo](title.md)

>[!CAUTION]
>
>Alcune versioni di singoli componenti core possono essere compatibili solo con determinate versioni di AEM.
>
>Per ulteriori informazioni, consultate la pagina di aiuto (collegata a nell&#39;elenco precedente) per il componente specifico per informazioni sulla compatibilità o fate riferimento al [documento Versioni](versions.md) componenti principali.

>[!NOTE]
>
>A seconda dell’istanza corrente è possibile che siano presenti componenti personalizzati sviluppati esplicitamente per le tue esigenze. Questi possono anche avere lo stesso nome di alcuni dei componenti qui descritti.
>I componenti core del modulo non sono correlati ad AEM Forms.

## Riferimenti per sviluppatori {#developer-resources}

Per informazioni tecniche sui componenti core, consultate [la documentazione sullo](developing.md) sviluppo dei componenti core Sviluppo.
