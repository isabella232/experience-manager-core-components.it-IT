---
title: Componente core Forms adattivo - Intestazione
description: Utilizzo o personalizzazione del componente di base dell’intestazione di Forms adattiva.
role: Architect, Developer, Admin, User
source-git-commit: b378fbd5695f82b8fc9de3a2d53a8387099ae33b
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 7%

---


# Intestazione {#header-adaptive-forms-core-component}

Un componente Intestazione in un modulo adattivo è una sezione nella parte superiore del modulo che in genere include il titolo, il logo o il nome del modulo. L’intestazione può includere anche altre informazioni, ad esempio una breve descrizione dello scopo del modulo, il nome dell’organizzazione che ha creato il modulo o informazioni di contatto per assistenza sul modulo. L’intestazione viene utilizzata per fornire agli utenti una panoramica del modulo e fornire il contesto delle informazioni che stanno per compilare. Viene utilizzato per aiutare gli utenti a comprendere lo scopo del modulo e come compilarlo correttamente.

**Esempio**

![](/help/adaptive-forms/assets/header.png)

## Utilizzo {#reasons-to-use-header}

* **Branding**: Un’intestazione può essere utilizzata per visualizzare il logo o il nome dell’organizzazione che ha creato il modulo, contribuendo a stabilire il riconoscimento e la credibilità del marchio.

* **Contesto**: Un’intestazione può fornire una breve descrizione dello scopo del modulo, aiutando gli utenti a comprendere il contesto in cui il modulo viene utilizzato.

* **Navigazione**: Un’intestazione può includere collegamenti o pulsanti che consentono agli utenti di passare ad altre parti del sito web o dell’applicazione.

* **Informazioni**: Un’intestazione può includere informazioni di contatto o collegamenti alle risorse dell’Aiuto, facilitando agli utenti l’assistenza in caso di necessità.

* **Esperienza utente**: Un’intestazione può essere utilizzata per rendere il modulo più semplice da usare, fornendo agli utenti un modo chiaro e intuitivo di accedere e compilare i campi del modulo.

## Versione e compatibilità {#version-and-compatibility}

Il componente di base dell’intestazione di Forms adattiva è stato rilasciato nel febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |
Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente di base dell’intestazione di Forms adattiva, consulta la documentazione tecnica disponibile in [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageheader/v1/pageheader). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza di intestazione per i visitatori tramite la finestra di dialogo Configura . Puoi anche definire le opzioni di intestazione con facilità per un’esperienza utente diretta.

### Scheda Immagine {#image-tab}

Questa parte dell&#39;intestazione contiene il titolo dell&#39;intestazione e l&#39;immagine.

![Imagetab](/help/adaptive-forms/assets/header_image.png)

* **Risorsa immagine** - Questa opzione consente di rilasciare una risorsa, ad esempio un’immagine, mediante trascinamento del mouse. È inoltre possibile caricare un file da un file system locale utilizzando **Sfoglia** pulsante . Dopo l’aggiunta di un’immagine, nella parte inferiore dell’immagine vengono visualizzati tre pulsanti. Dopo l’aggiunta di un’immagine, nella parte inferiore dell’immagine vengono visualizzati tre pulsanti:
   * **Modifica** - Tocca o fai clic su **Modifica** per gestire le rappresentazioni della risorsa nell’Editor risorse.
   * **Cancella** - Tocca o fai clic su **Cancella** per deselezionare l&#39;immagine attualmente selezionata.
   * **Selezione** - Tocca o fai clic su **Selezione**  per selezionare un’altra immagine dalla cartella Risorse.

* **Titolo** - Questa opzione viene utilizzata per aggiungere l’intestazione all’intestazione. Il testo predefinito viene incluso nella finestra di dialogo e può essere modificato dall’utente.
* **Collega a** - Puoi collegare l’intestazione alla cartella utilizzando **Sfoglia** icona.
* **Descrizione** - Una descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di una specifica immagine.
* **Dimensioni (px)** - Consente di regolare la lunghezza e la larghezza dell&#39;immagine aumentando o diminuendo i pixel.

![scheda accessibilità](/help/adaptive-forms/assets/header_accessibility.png)

* **Testo alternativo** - Questa opzione viene utilizzata per inserire il testo che fornisce un testo alternativo breve e descrittivo per l’immagine, che descrive l’immagine per gli utenti ipovedenti.

* **L’immagine è decorativa**: controlla se l’immagine deve essere ignorata dalla tecnologia per l’accessibilità e quindi non richiede un testo alternativo. Questo vale solo per le immagini decorative.

### Scheda Testo {#text-tab}

Questa sezione consente di inserire il testo da includere nell’intestazione.



