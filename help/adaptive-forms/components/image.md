---
title: Componente core moduli adattivi - Immagine
description: Utilizzo o personalizzazione del componente core immagine dei moduli adattivi.
role: Architect, Developer, Admin, User
exl-id: 9ee42d5d-16e3-4973-8364-5bc512ebe72e
source-git-commit: ad3e3bca5cb46f14e864e4704c90ac3b62779794
workflow-type: ht
source-wordcount: '1051'
ht-degree: 100%

---

# Immagine {#image-adaptive-forms-core-component}

Un componente Immagine in un modulo adattivo consente di includere le immagini in un modulo. Queste immagini possono essere utilizzate per migliorare la struttura complessiva del modulo, fornire informazioni aggiuntive o servire come aiuto visivo per favorire la comprensione dello scopo del modulo. Il componente Immagine può essere utilizzato per aggiungere un logo, una foto o un elemento grafico nel modulo.

Per l’accessibilità, è importante specificare un **Testo alternativo** all’immagine per fornire un testo alternativo breve e descrittivo per l’immagine, la quale viene descritta agli utenti che non possono visualizzarla.


**Esempio**

![](/help/adaptive-forms/assets/image.png)


## Utilizzo {#reasons-to-use-image-in-a-form}

Ci sono diversi motivi per cui è utile includere un componente Immagine in un modulo adattivo, tra cui:

* **Branding**: un’immagine può essere utilizzata per visualizzare il logo o il nome dell’organizzazione che ha creato il modulo, contribuendo a stabilire il riconoscimento e la credibilità del marchio.

* **Strumenti visivi**: un’immagine può essere utile per fornire un ulteriore livello di informazioni agli utenti, fornendo un supporto visivo per aiutarli a comprendere lo scopo del modulo.

* **Decorazione**: un’immagine può essere utilizzata per migliorare la struttura complessiva del modulo e renderlo più attraente dal punto di vista visivo.

* **Esperienza utente**: un’immagine può essere utilizzata per rendere il modulo più semplice da usare, fornendo agli utenti un modo chiaro e intuitivo di accedere e compilarne i campi.

## Versione e compatibilità {#version-and-compatibility}

Il componente core Pannello a soffietto moduli adattativi è stato rilasciato a febbraio 2023 come parte dei Componenti core 2.0.4 per Cloud Service e i Componenti core 1.1.12 per AEM Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM Forms 6.5.16.0 o versioni successive |
|---|---|---|
| v1 | Compatibile con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successive | Compatibile con <br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive, ma precedenti a 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Ottieni informazioni aggiornate sul componente core Immagine per moduli adattivi nella documentazione tecnica in [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/image/v1/image). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).


## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza dell’immagine per i visitatori tramite la finestra di dialogo Configura. Puoi anche definire le opzioni dell’immagine con facilità per un’esperienza utente semplice.

![Scheda Proprietà](/help/adaptive-forms/assets/image_properties.png)

* **Nome**: puoi identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo**: con il relativo titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungi un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Riferimento di binding del documento di record**: questa opzione consente di associare un campo di un modulo adattivo a un campo di un documento di record. Quando l’utente immette un valore in un campo collegato di un modulo adattivo, tale valore viene visualizzato anche nel campo collegato del corrispondente documento di record. Ad esempio, è possibile utilizzare un riferimento di binding del documento di record per visualizzare il nome e l’indirizzo dell’utente in un documento di record, in base all’ID cliente immesso nel modulo. In questo modo, AEM Forms consente di generare un documento di record e offre un’esperienza utente semplice per la raccolta e la gestione dei dati.

* **Descrizione**: una descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di una specifica immagine.

* **Rilascia una risorsa qui o cerca un file da caricare**: questa opzione consente di rilasciare una risorsa, ad esempio un’immagine, mediante trascinamento del mouse. È inoltre possibile caricare un file da un sistema di file locale utilizzando il pulsante **Sfoglia**. Dopo l’aggiunta di un’immagine, nella sua parte inferiore vengono visualizzati tre pulsanti:
   * **Modifica**: tocca o fai clic su **Modifica** per gestire i rendering della risorsa nell’editor delle risorse.
   * **Cancella**: tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * **Scegli**: tocca o fai clic sull’opzione **Scegli** per selezionare un’altra immagine dalla cartella risorse.

* **Testo alternativo**: questa opzione viene utilizzata per inserire un testo breve e descrittivo alternativo all’immagine, che descrive l’immagine per gli utenti ipovedenti.

* **Nascondi componente**: seleziona l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.

* **Sola lettura**: seleziona l’opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione viene utilizzata per definire e gestire gli stili CSS per il componente Immagine.

### Scheda Stili {#styles-tab}

La scheda è utilizzata per definire e gestire gli stili CSS per un componente. Il componente core immagine dei moduli adattivi supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

![Finestra di dialogo per la progettazione](/help/adaptive-forms/assets/image_designdialog.png)

**Classi CSS predefinite**: puoi fornire una classe CSS predefinita per il componente core immagine dei moduli adattivi.

**Stili consentiti**: puoi definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di moduli adattivi. Per applicare uno stile, nell’editor dei moduli adattivi, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

## Articolo correlato {#related-article}

* [Creare un modulo adattivo in una pagina AEM Sites o in un frammento di esperienza](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=it)

* [Creare un modulo adattivo indipendente](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=it)


## Consulta anche {#see-also}

* [Pannello a soffietto](/help/adaptive-forms/components/accordion.md)
* [Pulsante](/help/adaptive-forms/components/button.md)
* [Gruppo di caselle di selezione](/help/adaptive-forms/components/checkbox-group.md)
* [Selettore data](/help/adaptive-forms/components/date-picker.md)
* [Elenco a discesa](/help/adaptive-forms/components/drop-down.md)
* [Inserimento e-mail](/help/adaptive-forms/components/email-input.md)
* [Contenitore modulo](/help/adaptive-forms/components/form-container.md)
* [Allegato file](/help/adaptive-forms/components/file-attachment.md)
* [Piè di pagina](/help/adaptive-forms/components/footer.md)
* [Intestazione](/help/adaptive-forms/components/header.md)
* [Schede orizzontali](/help/adaptive-forms/components/horizontal-tabs.md)
* [Inserimento numero](/help/adaptive-forms/components/number-input.md)
* [Contenitore pannelli](/help/adaptive-forms/components/panel-container.md)
* [Pulsante di scelta](/help/adaptive-forms/components/radio-button.md)
* [Pulsante Ripristina](/help/adaptive-forms/components/reset-button.md)
* [Pulsante Invia](/help/adaptive-forms/components/submit-button.md)
* [Inserimento telefono](/help/adaptive-forms/components/telephone-input.md)
* [Inserimento testo](/help/adaptive-forms/components/text-input.md)
* [Testo](/help/adaptive-forms/components/text.md)
* [Titolo](/help/adaptive-forms/components/title.md)
* [Procedura guidata](/help/adaptive-forms/components/wizard.md)