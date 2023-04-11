---
title: Componente core di moduli adattivi - Intestazione
description: Utilizzo o personalizzazione del componente core dell’ntestazione dei moduli adattivi.
role: Architect, Developer, Admin, User
exl-id: aa18def9-0bec-4475-8dde-213860621ef5
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 92%

---

# Intestazione {#header-adaptive-forms-core-component}

Un componente intestazione in un modulo adattivo è una sezione nella parte superiore del modulo che in genere include il titolo, il logo o il nome del modulo. L’intestazione può includere anche altre informazioni, ad esempio una breve descrizione dello scopo del modulo, il nome dell’organizzazione che ha creato il modulo o informazioni di contatto per assistenza sul modulo. L’intestazione viene utilizzata per fornire agli utenti una panoramica del modulo e fornire il contesto delle informazioni che stanno per compilare. Viene utilizzato per aiutare gli utenti a comprendere lo scopo del modulo e come compilarlo correttamente.

**Esempio**

![](/help/adaptive-forms/assets/header.png)

## Utilizzo {#reasons-to-use-header}

* **Branding**: un’intestazione può essere utilizzata per visualizzare il logo o il nome dell’organizzazione che ha creato il modulo, contribuendo a stabilire il riconoscimento e la credibilità del marchio.

* **Contesto**: un’intestazione può fornire una breve descrizione dello scopo del modulo, aiutando gli utenti a comprendere il contesto in cui il modulo viene utilizzato.

* **Navigazione**: un’intestazione può includere collegamenti o pulsanti che consentono agli utenti di passare ad altre parti del sito web o dell’applicazione.

* **Informazioni**: un’intestazione può includere informazioni di contatto o collegamenti alle risorse di supporto, facilitando agli utenti l’assistenza in caso di necessità.

* **Esperienza utente**: un’intestazione può essere utilizzata per rendere il modulo più semplice da usare, fornendo agli utenti un modo chiaro e intuitivo di accedere e compilare i campi del modulo.

## Versione e compatibilità {#version-and-compatibility}

Il componente core per pannello a soffietto adattivo di Forms è stato rilasciato a febbraio 2023 come parte dei componenti core 2.0.4 per Cloud Service e i componenti core 1.1.12 per Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM 6.5.16.0 Forms o versione successiva |
|---|---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successive | Compatibile con<br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive ma inferiori a 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente core intestazione dei moduli adattivi, consulta la documentazione tecnica disponibile su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageheader/v1/pageheader). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza con l’intestazione per i visitatori tramite la finestra di dialogo per la configurazione. Puoi anche definire le opzioni di intestazione con facilità per un’esperienza utente diretta.

### Scheda Immagine {#image-tab}

Questa parte dell’intestazione contiene il titolo dell’intestazione e l’immagine.

![Scheda Immagine](/help/adaptive-forms/assets/header_image.png)

* **Risorsa immagine**: questa opzione consente di rilasciare una risorsa, ad esempio un’immagine, mediante trascinamento del mouse. È inoltre possibile caricare un file da un file system locale utilizzando il pulsante **Sfoglia**. Dopo l’aggiunta di un’immagine, nella parte inferiore della stessa vengono visualizzati tre pulsanti. Dopo l’aggiunta di un’immagine, nella sua parte inferiore vengono visualizzati tre pulsanti:
   * **Modifica**: tocca o fai clic su **Modifica** per gestire i rendering della risorsa nell’editor delle risorse.
   * **Cancella**: tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * **Seleziona**: tocca o fai clic su **Seleziona** per selezionare un’altra immagine dalla cartella Risorse.

* **Titolo**: questa opzione viene utilizzata per aggiungere l’intestazione all’intestazione. Il testo predefinito viene incluso nella finestra di dialogo e può essere modificato dall’utente.
* **Collega a**: puoi collegare l’intestazione alla cartella utilizzando l’icona **Sfoglia**.
* **Descrizione**: una descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di una specifica immagine.
* **Dimensioni (px)**: consente di regolare la lunghezza e la larghezza dell’immagine aumentando o diminuendo i pixel.

![Scheda Accessibilità](/help/adaptive-forms/assets/header_accessibility.png)

* **Testo alternativo**: questa opzione viene utilizzata per inserire il testo che fornisce un testo alternativo breve e descrittivo per l’immagine. La descrizione dell’immagine sarà di aiuto agli utenti ipovedenti.

* **L’immagine è decorativa**: controlla se l’immagine deve essere ignorata dalla tecnologia per l’accessibilità e quindi non richiede un testo alternativo. Questo vale solo per le immagini decorative.

### Scheda Testo {#text-tab}

Questa sezione consente di inserire il testo da includere nell’intestazione.

