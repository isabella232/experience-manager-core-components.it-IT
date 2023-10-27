---
title: Componente core moduli adattivi - Elenco a discesa
description: Utilizzo o personalizzazione del componente core dell’elenco a discesa dei moduli adattivi.
role: Architect, Developer, Admin, User
exl-id: 9d59d0d2-d38f-4ed5-8b43-984c45f26f27
source-git-commit: be630c4d0a10ebaa679b77419b901fac818addb1
workflow-type: ht
source-wordcount: '1731'
ht-degree: 100%

---

# Elenco a discesa {#drop-down-list-adaptive-forms-core-component}

Un elenco a discesa in un modulo adattivo consente agli utenti di selezionare una o più opzioni da un elenco di opzioni predefinite. Le opzioni possono essere di tipo stringa, numero o booleano. Inoltre, il componente elenco a discesa può essere configurato in modo da avere diversi valori predefiniti e di convalida.

**Esempio**
![](/help/adaptive-forms/assets/drop-down-list.png)

## Utilizzo {#reasons-to-use-drop-down-list}

Ci sono diversi motivi per cui è utile includere un elenco a discesa in un modulo adattivo, tra cui:

* **Elenco lungo di opzioni**: gli elenchi a discesa sono utili nelle situazioni in cui è disponibile un lungo elenco di opzioni per un campo. Occupano meno spazio sul modulo rispetto a un elenco di pulsanti di scelta o caselle di controllo e possono risultare meno pesanti per gli utenti.

* **Coerenza**: gli elenchi a discesa forniscono coerenza nella progettazione e nel layout del modulo, rendendo la navigazione più intuitiva e semplice per gli utenti.

* **Chiarezza**: gli elenchi a discesa possono rendere il modulo più chiaro e semplice da comprendere fornendo un elenco chiaro e conciso di opzioni.

* **Esperienza utente**: gli elenchi a discesa possono essere utilizzati per rendere il modulo più semplice da usare, fornendo agli utenti un modo chiaro e intuitivo di selezionare le opzioni.

* **Analisi dei dati**: gli elenchi a discesa possono essere utilizzati per raccogliere dati da varie sorgenti e analizzarli o utilizzarli come input per un’ulteriore elaborazione.


**Finestra di dialogo Proprietà**

![](/help/adaptive-forms/assets/drop-down-list-properties.png)

In questo esempio, l’elemento Opzioni viene utilizzato per definire gli elementi dell’elenco. L’elemento **Testo visualizzato** viene utilizzato per fornire un’etichetta per gli elementi dell’elenco e **Valore dati** viene utilizzato per specificare il valore inviato al server al momento dell’invio del modulo.

Ogni opzione dell’elenco a discesa ha un valore dati univoco e un attributo testo visualizzato. Se l’utente seleziona l’opzione “Rosso”, il valore dati corrispondente viene inviato al server al momento dell’invio del modulo. Questi dati possono quindi essere elaborati da uno script lato server per determinare quali opzioni sono state selezionate dall’utente e possono essere utilizzate per eseguire varie azioni, ad esempio l’aggiornamento di altri campi del modulo o l’invio dei dati del modulo a uno script lato server per un’ulteriore elaborazione.

Inoltre, l’elenco a discesa può essere configurato in modo da avere valori di elaborazione diversi per ciascuna opzione e questo può essere impostato utilizzando l’editor di regole di moduli adattivi.

## Versione e compatibilità {#version-and-compatibility}

Il componente core Pannello a soffietto moduli adattativi è stato rilasciato a febbraio 2023 come parte dei Componenti core 2.0.4 per Cloud Service e i Componenti core 1.1.12 per AEM Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM Forms 6.5.16.0 o versioni successive |
|---|---|---|
| v1 | Compatibile con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successive | Compatibile con <br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive, ma precedenti a 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Ottieni le informazioni più aggiornate sul componente core dell’elenco a discesa dei moduli adattivi nella documentazione tecnica di [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/dropdown/v1/dropdown). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza dell’elenco a discesa per i visitatori tramite la finestra di dialogo Configura. Puoi anche definire le opzioni dell’elenco a discesa in modo semplice per un’esperienza utente fluida.

![Scheda Base](/help/adaptive-forms/assets/dropdown_basictab.png)

* **Nome**: puoi identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo**: il titolo permette di identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungi un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo**: seleziona l’opzione per nascondere il titolo del componente.

* **Consenti selezione multipla**: seleziona questa opzione per selezionare più opzioni da un elenco a discesa.

* **Salva valore come**: questa opzione specifica il tipo di dati del valore inviato quando viene selezionata qualsiasi opzione. Se **Salva valore con nome** è impostato su `Number` e si aggiungono dati stringa a **Valore dati** sulla scheda **Opzioni**, viene visualizzato il messaggio di errore `Value type mismatch`.

  Nella scheda **Opzioni**, puoi aggiungere valori dati e visualizzare coppie di testo utilizzando il pulsante **Aggiungi**. Una volta aggiunta una nuova opzione, vengono eseguite le seguenti azioni:

   * **Valore dati**: questa opzione consente di inserire il contenuto da inviare quando viene selezionata un’opzione.
   * **Testo visualizzato**: questa opzione consente di inserire il contenuto da visualizzare in un modulo adattivo.
   * **Elimina**: tocca o fai clic per eliminare l’opzione di un menu a discesa.
   * **Ridisponi**: tocca o fai clic e trascina per ridisporre l’ordine per l’opzione di un menu a discesa.

* **Opzioni predefinite**: questa opzione consente di aggiungere valori predefiniti. Utilizza l’icona Elimina per rimuovere l’opzione aggiunta. Se **Salva valore con nome** è impostato su `Number` e si aggiungono dati stringa a **Opzioni predefinite**, viene visualizzato il messaggio di errore `Value type mismatch`.

* **Testo segnaposto**: il testo segnaposto in un componente del modulo si riferisce a un’etichetta o a un prompt breve che viene visualizzato all’interno di un campo di input come suggerimento per l’utente sul tipo di informazioni che si prevede vengano immesse in quel campo. Il testo segnaposto scompare quando l’utente inizia a digitare nel campo e viene visualizzato nuovamente se il campo viene lasciato vuoto. Fornisce un suggerimento visivo all’utente, ma non funge da etichetta o valore permanente per il campo.

* **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente fluida per la raccolta e la gestione dei dati.

* **Nascondi componente**: seleziona l’opzione per nascondere il componente del modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente**: seleziona questa opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.
* **Sola lettura**: seleziona questa opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

### Scheda Convalida {#validation-tab}

![Scheda Convalida](/help/adaptive-forms/assets/dropdown_validationtab.png)

* **Obbligatorio**: seleziona questa opzione se desideri visualizzare il componente in un modulo adattivo. Non è possibile selezionare **Nascondi componente** o **Disattiva componente** nella scheda **Base** quando questa opzione è selezionata.

* **Messaggio di errore**: questa opzione consente di inserire un messaggio visualizzato se la casella di controllo **Obbligatorio** è selezionata e il campo modulo viene lasciato vuoto.

* **Messaggio di convalida script**: questa opzione consente di inserire un messaggio da visualizzare in caso di mancata convalida dello script.

### Scheda Contenuto Guida {#help-content-tab}

![Scheda Contenuto Guida](/help/adaptive-forms/assets/dropdown_helptab.png)

* **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

* **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità](/help/adaptive-forms/assets/dropdown_accessibilitytab.png)


**Testo per utilità per la lettura dello schermo**: il testo per le utilità per la lettura dello schermo si riferisce al testo aggiuntivo destinato specificamente ad essere letto da tecnologie di assistenza, come le utilità per la lettura dello schermo, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.


## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente di definire e gestire gli stili CSS per il componente Elenco a discesa.

### Scheda Stili {#styles-tab}

La scheda è utilizzata per definire e gestire gli stili CSS per un componente. Il componente core del menù a discesa per moduli adattivi supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

![Finestra di dialogo a discesa](/help/adaptive-forms/assets/dropdown_designdialog.png)

* **Classi CSS predefinite**: è possibile fornire una classe CSS predefinita per il componente core dell’elenco a discesa per moduli adattivi.

* **Stili consentiti**: è possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di moduli adattivi. Per applicare uno stile, nell’editor dei moduli adattivi, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

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
>* [Titolo](/help/adaptive-forms/components/title.md)
>* [Procedura guidata](/help/adaptive-forms/components/wizard.md)


## Consulta anche {#see-also}

{{see-also}}