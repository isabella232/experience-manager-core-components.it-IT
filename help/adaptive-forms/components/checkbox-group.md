---
title: Componente core dei moduli adattivi - Gruppo di caselle di controllo
description: Utilizzo o personalizzazione del componente core del gruppo di caselle di controllo nei moduli adattivi.
role: Architect, Developer, Admin, User
exl-id: 2ced0223-e664-470b-a400-b6865d3a67c9
source-git-commit: ad3e3bca5cb46f14e864e4704c90ac3b62779794
workflow-type: ht
source-wordcount: '1699'
ht-degree: 100%

---

# Gruppo di caselle di controllo {#button-component-adaptive-forms-core-component}

Un gruppo di caselle di controllo in un modulo adattivo è un insieme di caselle di controllo correlate che consentono agli utenti di selezionare una o più opzioni da un elenco. Ciascuna casella di controllo è rappresentata da un valore dati (valore utilizzato per elaborare gli elementi di un gruppo di caselle di controllo) e dal valore visualizzato (etichetta per ogni elemento della casella di controllo che ne descrive lo scopo)

**Esempio**

![](/help/adaptive-forms/assets/checkbox-group.png)

**Finestra di dialogo Proprietà**

![](/help/adaptive-forms/assets/checkbox-group-properties.png)

In questo esempio, l’elemento Opzioni viene utilizzato per raggruppare le caselle di controllo. L’elemento **Testo visualizzato** viene utilizzato per fornire un’etichetta per un elemento e **Valore dati** viene utilizzato per specificare il valore inoltrato al server al momento dell’invio del modulo.

Ogni opzione/elemento della casella di controllo ha un valore dati univoco e un attributo Testo visualizzato. Se l’utente seleziona le caselle di controllo “Figlio” e “Figlia”, il valore dati corrispondente viene inviato al server al momento dell’invio del modulo. Questi dati possono quindi essere elaborati da uno script lato server per determinare quali opzioni sono state selezionate dall’utente e possono essere utilizzate per eseguire varie azioni, ad esempio l’aggiornamento di altri campi del modulo o l’invio dei dati del modulo a uno script lato server per un’ulteriore elaborazione.

Inoltre, il gruppo di caselle di controllo può essere configurato in modo da avere valori di elaborazione diversi per ciascuna opzione, e questo può essere impostato utilizzando l’editor di regole dei moduli adattivi.

## Utilizzo {#reasons-to-use-check-box-group}

Ci sono diversi motivi per cui è utile includere un gruppo di caselle di controllo in un modulo adattivo, tra cui:

* **Selezioni multiple**: un gruppo di caselle di controllo consente agli utenti di selezionare più opzioni da un elenco, il che può essere utile in situazioni in cui sono consentite o richieste selezioni multiple.

* **Esperienza utente**: un gruppo di caselle di controllo può essere utilizzato per rendere il modulo più semplice da usare, poiché fornisce agli utenti un modo chiaro e intuitivo per selezionare più opzioni.

* **Analisi dei dati**: un gruppo di caselle di controllo può essere utilizzato per raccogliere dati di origine diversa e analizzarli o utilizzarli come input per un’ulteriore elaborazione.

* **Sondaggi**: un gruppo caselle di controllo può essere utilizzato nei sondaggi per selezionare più opzioni per una domanda.

* **Preferenze utente**: un gruppo di caselle di controllo può essere utilizzato per registrare le preferenze dell’utente tra diverse opzioni.

* **Valore dati**: un gruppo di caselle di controllo può essere utilizzato anche per elaborare gli elementi di un gruppo di caselle di controllo.

## Versione e compatibilità {#version-and-compatibility}

Il componente core Pannello a soffietto moduli adattativi è stato rilasciato a febbraio 2023 come parte dei Componenti core 2.0.4 per Cloud Service e i Componenti core 1.1.12 per AEM Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM Forms 6.5.16.0 o versioni successive |
|---|---|---|
| v1 | Compatibile con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successive | Compatibile con <br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive, ma precedenti a 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Puoi trovare le informazioni più recenti sul componente core di un gruppo di caselle di controllo nei moduli adattivi nella documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/checkboxgroup/v1/checkboxgroup). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente la tua esperienza con le caselle di controllo per i visitatori tramite la finestra di dialogo Configura. Puoi anche definire le opzioni delle caselle di controllo con facilità per un’esperienza utente ottimale.


### Scheda Base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/checkbox_basictab.png)

* **Nome**: il nome identifica in modo univoco il componente nell’editor delle regole. Le stringhe di nome non consentono l’uso di caratteri e spazi speciali.

* **Titolo**: con il relativo titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungi un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo**: seleziona l’opzione per nascondere il Titolo del componente.

* **Opzioni**: è possibile aggiungere valori dati e visualizzare coppie di testo utilizzando il pulsante **Aggiungi**. Una volta aggiunta una nuova opzione, è possibile eseguire le azioni seguenti:

   * **Valore Dati**: questa opzione consente di immettere il contenuto da inviare quando viene selezionata un’opzione.
   * **Testo visualizzato**: questa opzione consente di inserire il contenuto da visualizzare in un modulo adattivo.
   * **Elimina**: tocca o fai clic per eliminare l’opzione di una casella di controllo.
   * **Ridisponi**: tocca o fai clic e trascina per modificare l’ordine dei pannelli.

* **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente fluida per la raccolta e la gestione dei dati.

* **Tipo di dati del valore inviato** - questa opzione specifica il tipo di dati del valore inviato quando viene selezionata un’opzione. Se il **tipo di dati del valore inviato** è impostato su `Number` e si aggiungono dati della stringa a **Valore dati** nella scheda **Opzioni**, nella schermata viene visualizzato un messaggio di errore `Value type mismatch`.

* **Opzioni visualizzate**: questa opzione viene utilizzata per impostare l’allineamento visivo delle caselle di controllo in un modulo adattivo. Le due opzioni supportate sono:
   * **Orizzontale**: quando questa opzione è selezionata, le caselle di controllo vengono visualizzate da sinistra a destra in un modulo adattivo.
   * **Verticale**: quando questa opzione è selezionata, le caselle di controllo vengono visualizzate dall’alto verso il basso in un modulo adattivo.

* **Opzioni predefinite**: questa opzione consente di aggiungere valori predefiniti preselezionati al caricamento del modulo. Utilizza l’icona Elimina per rimuovere le opzioni aggiunte. Se il **tipo di dati del valore inviato** è impostato su `Number` e aggiungi una stringa di dati a **Opzioni predefinite**, la schermata mostra un messaggio di errore `Value type mismatch`.
* **Nascondi componente**: seleziona l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente**: seleziona questa opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.
* **Sola lettura**: seleziona questa opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

### Scheda Convalida {#validation-tab}

![Scheda Convalida](/help/adaptive-forms/assets/checkbox_validationtab.png)

* **Obbligatorio**: seleziona questa opzione se desideri visualizzare il componente in un modulo adattivo. Non è possibile selezionare **Nascondi componente** o **Disattiva componente** nella scheda **Base** quando questa opzione è selezionata.

* **Messaggio di errore**: questa opzione consente di inserire un messaggio visualizzato se la casella di controllo **Obbligatorio** è selezionata e il campo modulo viene lasciato vuoto.

* **Messaggio di convalida script**: questa opzione consente di inserire un messaggio da visualizzare in caso di mancata convalida dello script.

### Scheda Contenuto Guida {#helpcontent-tab}

![Scheda Contenuto Guida](/help/adaptive-forms/assets/checkbox_helptab.png)

* **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

* **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità](/help/adaptive-forms/assets/checkbox_accessibility.png)

**Testo per utilità per la lettura dello schermo**: il testo per le utilità per la lettura dello schermo si riferisce al testo aggiuntivo destinato specificamente ad essere letto da tecnologie di assistenza, come le utilità per la lettura dello schermo, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.

    ## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione si usa per definire e gestire gli stili CSS per il componente Gruppo di caselle di selezione.

### Scheda Stili {#styles-tab}

Il componente core Gruppo di caselle di controllo dei moduli adattivi supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) AEM.

![Finestra di dialogo per la progettazione](/help/adaptive-forms/assets/checkbox_designdialog.png)

* **Classi CSS predefinite**: puoi fornire una classe CSS predefinita per il componente core del gruppo di caselle di selezione dei moduli adattivi.

* **Stili consentiti**: puoi definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di moduli adattivi. Per applicare uno stile, nell’editor dei moduli adattivi, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

## Articolo correlato {#related-article}

* [Creare un modulo adattivo in una pagina AEM Sites o in un frammento di esperienza](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=it)

* [Creare un modulo adattivo indipendente](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=it)

## Consulta anche {#see-also}

* [Pannello a soffietto](/help/adaptive-forms/components/accordion.md)
* [Pulsante](/help/adaptive-forms/components/button.md)
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