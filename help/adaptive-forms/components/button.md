---
title: Componente core dei moduli adattivi - Pulsante
description: Utilizzo o personalizzazione del componente core del pulsante per moduli adattivi.
role: Architect, Developer, Admin, User
exl-id: cb75929b-8c86-49d1-b51a-368f5b80b1a9
source-git-commit: ad3e3bca5cb46f14e864e4704c90ac3b62779794
workflow-type: tm+mt
source-wordcount: '1479'
ht-degree: 99%

---

# Componente Pulsante {#button-component-adaptive-forms-core-component}

Un pulsante in un modulo adattivo è un elemento dell’interfaccia utente che consente agli utenti di avviare un’azione quando ci cliccano sopra. L’elemento pulsante può essere utilizzato per inviare un modulo, reimpostare un modulo o eseguire altre operazioni, ad esempio la navigazione a una pagina diversa o l’attivazione di codice personalizzato. Il pulsante può essere creato utilizzando il componente core Pulsante.

L’editor di regole per moduli adattivi consente agli utenti di impostare varie azioni per il componente pulsante. Queste azioni includono l’apertura di un sito web, la visualizzazione o l’eliminazione di componenti modulo, l’aggiunta di un’istanza di un pannello o di un componente, l’invio o la reimpostazione di un modulo e altro ancora.

I moduli adattivi presentano componenti separati per il [Pulsante Invia](/help/adaptive-forms/components/submit-button.md) e il [Pulsante Ripristina](/help/adaptive-forms/components/reset-button.md), che consentono agli utenti di inviare o ripristinare un modulo in modo opportuno. Il componente Pulsante può essere configurato in modo flessibile per eseguire queste azioni in base alle esigenze specifiche.

Gli utenti possono accedere all’elenco completo delle azioni supportate per il componente pulsante utilizzando l’editor di regole per moduli adattivi. L’editor di regole consente agli utenti di creare regole attivate da vari eventi, ad esempio quando si fa clic su un pulsante, quando si carica un modulo o si modifica il valore di un campo. Queste regole possono quindi essere utilizzate per eseguire varie azioni, ad esempio per mostrare o nascondere i componenti, impostare i valori dei campi o inviare il modulo.

## Utilizzo {#reasons-to-use-button}

Ci sono diversi motivi per cui è utile includere un pulsante in un modulo adattivo, tra cui:

* **Invio del modulo**: un pulsante viene in genere utilizzato per inviare un modulo, consentendo agli utenti di inviare i dati immessi sul server per l’elaborazione.

* **Ripristino del modulo**: i pulsanti possono essere utilizzati anche per reimpostare un modulo, cancellando tutti i dati immessi dall’utente.

* **Navigazione**: i pulsanti possono essere utilizzati per spostarsi tra diverse sezioni di un modulo o tra pagine diverse di un sito web.

* **Gestione degli eventi**: i pulsanti possono essere utilizzati per attivare eventi diversi come l’apertura di un sito web, l’esposizione o la visualizzazione di componenti, l’aggiunta di un’istanza di un pannello o di un componente al pulsante.

* **Interattività**: i pulsanti possono essere utilizzati per creare moduli interattivi. Ad esempio, un pulsante può essere utilizzato per aprire una finestra di dialogo modale o per attivare o disattivare una sezione del modulo.

## Versione e compatibilità {#version-and-compatibility}

Il componente core Pannello a soffietto moduli adattativi è stato rilasciato a febbraio 2023 come parte dei Componenti core 2.0.4 per Cloud Service e i Componenti core 1.1.12 per AEM Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM Forms 6.5.16.0 o versioni successive |
|---|---|---|
| v1 | Compatibile con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successive | Compatibile con <br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive, ma precedenti a 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente core pulsante per moduli adattivi, consulta la documentazione tecnica disponibile su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/button/v1/button). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del pulsante per i visitatori tramite la finestra di dialogo Configura. Puoi anche definire le proprietà del pulsante facilmente per un’esperienza utente semplice.

### Scheda Base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/button_basictab.png)

* **Nome**: è possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo**: con il relativo titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungi un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente fluida per la raccolta e la gestione dei dati.

* **Riferimento di binding del documento di record**: questa opzione consente di associare un campo di un modulo adattivo a un campo di un documento di record. Quando l’utente immette un valore in un campo collegato di un modulo adattivo, tale valore viene visualizzato anche nel campo collegato del corrispondente documento di record. Ad esempio, è possibile utilizzare un riferimento di binding del documento di record per visualizzare il nome e l’indirizzo dell’utente in un documento di record, in base all’ID cliente immesso nel modulo. In questo modo, AEM Forms consente di generare un documento di record e offre un’esperienza utente semplice per la raccolta e la gestione dei dati.

* **Nascondi componente**: seleziona questa opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente**: seleziona questa opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.
* **Sola lettura**: seleziona questa opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

### Scheda Contenuto Guida {#help-content}

![Scheda Contenuto Guida](/help/adaptive-forms/assets/button_helptab.png)

* **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

* **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Accessibilità {#accessibility}

![Scheda Accessibilità](/help/adaptive-forms/assets/button_accessibilitytab.png)


* **Testo per utilità per la lettura dello schermo**: il testo per le utilità per la lettura dello schermo si riferisce al testo aggiuntivo destinato specificamente ad essere letto da tecnologie di assistenza, come le utilità per la lettura dello schermo, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione viene utilizzata per definire e gestire gli stili CSS per il componente pulsante.

### Scheda Stili {#styles-tab}

Il componente core Pulsante per moduli adattivi supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

![Finestra di dialogo per la progettazione](/help/adaptive-forms/assets/button_designdialog.png)

* **Classi CSS predefinite**: è possibile fornire una classe CSS predefinita per il componente core pulsante moduli adattivi.

* **Stili consentiti**: è possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di moduli adattivi. Per applicare uno stile, nell’editor dei moduli adattivi, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

## Articolo correlato {#related-article}

* [Creare un modulo adattivo in una pagina AEM Sites o in un frammento di esperienza](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=it)

* [Creare un modulo adattivo indipendente](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=it)

## Vedi anche {#see-also}

* [Pannello a soffietto](/help/adaptive-forms/components/accordion.md)
* [Gruppo di caselle di selezione](/help/adaptive-forms/components/checkbox-group.md)
* [Selettore data](/help/adaptive-forms/components/date-picker.md)
* [Elenco a discesa](/help/adaptive-forms/components/drop-down.md)
* [Inserimento e-mail](/help/adaptive-forms/components/email-input.md)
* [Contenitore modulo](/help/adaptive-forms/components/form-container.md)
* [Allegato file](/help/adaptive-forms/components/file-attachment.md)
* [Piè di pagina](/help/adaptive-forms/components/footer.md)
* [Intestazione](/help/adaptive-forms/components/header.md)
* [Schede orizzontali](/help/adaptive-forms/components/horizontal-tabs.md)
* [Immagine](/help/adaptive-forms/components/image.md)
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

