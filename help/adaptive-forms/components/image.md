---
title: Componente core Forms adattivo - Immagine
description: Utilizzo o personalizzazione del componente di base Immagine adattiva di Forms.
role: Architect, Developer, Admin, User
source-git-commit: 1e6460d318f4f9a5dfdcbb81723da01b51b72f3f
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 2%

---


# Immagine {#image-adaptive-forms-core-component}

Un componente Immagine in un Modulo adattivo consente di includere le immagini in un modulo. Queste immagini possono essere utilizzate per migliorare la struttura complessiva del modulo, fornire informazioni aggiuntive o per aiutare gli utenti a comprendere lo scopo del modulo. Il componente Immagine può essere utilizzato per aggiungere un logo, una foto o un elemento grafico nel modulo.

Per l’accessibilità, è importante specificare **Testo alternativo** all’immagine per fornire un testo alternativo breve e descrittivo per l’immagine, che descrive l’immagine per gli utenti che non possono visualizzarla.


**Esempio**

![](/help/adaptive-forms/assets/image.png)


## Utilizzo {#reasons-to-use-image-in-a-form}

Ci sono diversi motivi per cui è utile includere un componente Immagine in un Modulo adattivo, tra cui:

* **Branding**: Un’immagine può essere utilizzata per visualizzare il logo o il nome dell’organizzazione che ha creato il modulo, contribuendo a stabilire il riconoscimento e la credibilità del marchio.

* **Strumenti visivi**: Un’immagine può essere utile per fornire un ulteriore livello di informazioni agli utenti, fornendo un supporto visivo per aiutare gli utenti a comprendere lo scopo del modulo.

* **Decorazione**: Un’immagine può essere utilizzata per migliorare la struttura complessiva del modulo e renderlo più attraente dal punto di vista visivo.

* **Esperienza utente**: Un’immagine può essere utilizzata per rendere il modulo più semplice da usare, fornendo agli utenti un modo chiaro e intuitivo di accedere e compilare i campi del modulo.

## Versione e compatibilità {#version-and-compatibility}

Il componente di base per le immagini adattive di Forms è stato rilasciato nel febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente di base Immagine adattiva di Forms, consulta la documentazione tecnica disponibile in [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/image/v1/image). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).


## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza dell’immagine per i visitatori tramite la finestra di dialogo Configura . Puoi anche definire le opzioni immagine con facilità per un’esperienza utente fluida.

![Scheda Proprietà](/help/adaptive-forms/assets/image_properties.png)

* **Nome** - È possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo** - Con il relativo Titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungete un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Riferimento di binding del documento di record** - Questa opzione consente di associare un campo Modulo adattivo a un campo Documento di record. Quando l’utente immette un valore in un campo collegato di un modulo adattivo, tale valore viene visualizzato anche nel campo collegato del corrispondente documento di record. Ad esempio, è possibile utilizzare un riferimento di binding Documento di record per visualizzare il nome e l&#39;indirizzo di un cliente in un documento di record, in base all&#39;ID del cliente immesso nel modulo. In questo modo, AEM Forms consente di generare un documento di record e offre un’esperienza utente semplice per la raccolta e la gestione dei dati.

* **Descrizione** - Una descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di una specifica immagine.

* **Rilascia una risorsa qui o cerca un file da caricare** - Questa opzione consente di rilasciare una risorsa, ad esempio un’immagine, mediante trascinamento del mouse. È inoltre possibile caricare un file da un file system locale utilizzando **Sfoglia** pulsante . Dopo l’aggiunta di un’immagine, nella parte inferiore dell’immagine vengono visualizzati tre pulsanti:
   * **Modifica** - Tocca o fai clic su **Modifica** per gestire le rappresentazioni della risorsa nell’Editor risorse.
   * **Cancella** - Tocca o fai clic su **Cancella** per deselezionare l&#39;immagine attualmente selezionata.
   * **Selezione** - Tocca o fai clic su **Selezione**  per selezionare un’altra immagine dalla cartella Risorse.

* **Testo alternativo** - Questa opzione viene utilizzata per inserire il testo che fornisce un testo alternativo breve e descrittivo per l’immagine, che descrive l’immagine per gli utenti ipovedenti.

* **Nascondi componente** - Selezionare l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.

* **Sola lettura** - Seleziona l’opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo Progettazione viene utilizzata per definire e gestire gli stili CSS per il componente Immagine.

### Scheda Stili {#styles-tab}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per un componente. Il componente di base per l’immagine di Forms adattiva supporta l’AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

**Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente di base Immagine adattiva di Forms.

**Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.