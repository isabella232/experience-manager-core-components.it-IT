---
title: Componente core moduli adattivi - Titolo
description: Utilizzo o personalizzazione del componente core del titolo dei moduli adattivi.
role: Architect, Developer, Admin, User
exl-id: 33eac885-8d66-4a5c-9a32-0ba11e6de293
source-git-commit: 59cd9d65bf4c1be6ab2eaf15bbb747b532863fdd
workflow-type: tm+mt
source-wordcount: '899'
ht-degree: 100%

---

# Titolo {#title-input-adaptive-forms-core-component}

In un modulo adattivo, per “titolo” si intende il testo visualizzato nella parte superiore del modulo, in genere sotto l’intestazione. Il titolo viene specificato utilizzando il componente Titolo. Questo componente può essere aggiunto al layout del modulo e il relativo testo può essere modificato in base allo scopo o all’argomento del modulo. Il titolo funge da etichetta o breve descrizione del modulo per l’utente e consente di distinguere il modulo dagli altri.

**Esempio**

![](/help/adaptive-forms/assets/title.png)

## Utilizzo {#reasons-to-use-title-in-an-adaptive-form}

Utilizzare un titolo in un modulo è consigliabile per diversi motivi:

* **Chiarezza**: un titolo identifica chiaramente lo scopo del modulo, facilitando agli utenti la comprensione di quali informazioni devono fornire.

* **Organizzazione**: un titolo può essere utile per organizzare i moduli in base all’argomento o allo scopo, facilitando agli utenti la ricerca del modulo di cui hanno bisogno.

* **Accessibilità**: un titolo è un elemento chiave per gli utenti con esigenze di accessibilità, in quanto viene letto ad alta voce dalle utilità per la lettura dello schermo, per aiutare gli utenti a comprendere il contesto del modulo.

* **Branding**: un titolo può essere utilizzato anche per visualizzare il nome di un’azienda o di un’organizzazione, il che contribuisce a creare un senso di fiducia e familiarità con l’utente.

* **Navigazione**: un titolo può anche essere utile per spostarsi all’interno del modulo, soprattutto se è lungo o complesso.

* **Search Engine Optimization (SEO)**: l’utilizzo di un titolo del modulo è utile anche nella SEO, in quanto i motori di ricerca utilizzano il titolo per determinare la rilevanza di una pagina web per una query di ricerca.

Nel complesso, il titolo di un modulo è un aspetto importante dell’esperienza utente e dovrebbe essere utilizzato per fornire un’etichetta chiara e concisa per il modulo, in modo da consentire agli utenti di comprendere il contesto e lo scopo del modulo.

## Versione e compatibilità {#version-and-compatibility}

Il componente core Pannello a soffietto moduli adattativi è stato rilasciato a febbraio 2023 come parte dei Componenti core 2.0.4 per Cloud Service e i Componenti core 1.1.12 per AEM Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM Forms 6.5.16.0 o versioni successive |
|---|---|---|
| v1 | Compatibile con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successive | Compatibile con <br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive, ma precedenti a 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente core del titolo per moduli adattivi, consulta la documentazione tecnica disponibile su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/title/v1/title). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del titolo per i visitatori tramite la finestra di dialogo Configura. Puoi anche definire le opzioni titolo con facilità per un’esperienza utente semplice.

![Scheda Base](/help/adaptive-forms/assets/title_properties.png)

La finestra di dialogo per modifica consente all’autore di contenuto di definire il testo del titolo e selezionare il livello dell’intestazione.

* **Titolo**: puoi identificare facilmente un componente in un modulo con il suo nome e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungi un titolo, al posto del testo del titolo viene visualizzato il nome del componente.
* **Tipo/Dimensione**: definisce il livello di intestazione del titolo.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e nel livello dati.
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente di definire e gestire gli stili CSS per il componente Selettore data.

### Titolo

La scheda Titolo consente agli autori dei modelli di impostare elementi di intestazione HTML predefiniti e consentiti per gli autori dei moduli:

![Scheda titolo della finestra di dialogo per progettazione](/help/adaptive-forms/assets/title_heading.png)

* **Elementi di intestazione consentiti**: un elenco con più opzioni che consente all’autore del modello di scegliere gli elementi di intestazione utilizzabili dall’autore del modulo per il titolo.

* **Elemento di intestazione predefinito**: elenco a discesa che imposta l’elemento Intestazione predefinito per il componente Titolo.

### Scheda Stili {#styles-tab}

La scheda è utilizzata per definire e gestire gli stili CSS per un componente. Il componente core selettore data dei moduli adattivi supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

![Scheda titolo della finestra di dialogo per la progettazione](/help/adaptive-forms/assets/title_styles.png)

* **Classi CSS predefinite**: è possibile fornire una classe CSS predefinita per il componente core selettore data dei moduli adattivi.

* **Stili consentiti**: è possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di moduli adattivi. Per applicare uno stile, nell’editor dei moduli adattivi, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

### Scheda Formati {#format-tab}

La scheda dei formati consente di specificare i formati di data predefiniti e personalizzati.

![Scheda Formato](/help/adaptive-forms/assets/title_styles.png)

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->


>[!MORELIKETHIS]
>
>* [Pannello a soffietto](/help/adaptive-forms/components/accordion.md)
>* [Pulsante](/help/adaptive-forms/components/button.md)
>* [Gruppo di caselle di selezione](/help/adaptive-forms/components/checkbox-group.md)
>* [Selettore data](/help/adaptive-forms/components/date-picker.md)
>* [Elenco a discesa](/help/adaptive-forms/components/drop-down.md)
>* [Inserimento e-mail](/help/adaptive-forms/components/email-input.md)
>* [Contenitore modulo](/help/adaptive-forms/components/form-container.md)
>* [Allegato file](/help/adaptive-forms/components/file-attachment.md)
>* [Piè di pagina](/help/adaptive-forms/components/footer.md)
>* [Intestazione](/help/adaptive-forms/components/header.md)
>* [Schede orizzontali](/help/adaptive-forms/components/horizontal-tabs.md)
>* [Immagine](/help/adaptive-forms/components/image.md)
>* [Inserimento numero](/help/adaptive-forms/components/number-input.md)
>* [Contenitore pannelli](/help/adaptive-forms/components/panel-container.md)
>* [Pulsante di scelta](/help/adaptive-forms/components/radio-button.md)
>* [Pulsante Ripristina](/help/adaptive-forms/components/reset-button.md)
>* [Pulsante Invia](/help/adaptive-forms/components/submit-button.md)
>* [Inserimento telefono](/help/adaptive-forms/components/telephone-input.md)
>* [Inserimento testo](/help/adaptive-forms/components/text-input.md)
>* [Testo](/help/adaptive-forms/components/text.md)
>* [Procedura guidata](/help/adaptive-forms/components/wizard.md)

## Consulta anche {#see-also}

{{see-also}}