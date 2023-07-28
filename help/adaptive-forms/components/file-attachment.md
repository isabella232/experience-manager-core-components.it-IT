---
title: Componente core moduli adattivi - Allegato file
description: Utilizzo o personalizzazione del componente core allegato file dei moduli adattivi.
role: Architect, Developer, Admin, User
exl-id: 64a54fc6-db52-481f-bf5a-60c05122004d
source-git-commit: 7888cfa0f1358ce8018fc1e3cc3b19eb66a82b9d
workflow-type: ht
source-wordcount: '1544'
ht-degree: 100%

---

# Allegato file {#file-attachment-adaptive-forms-core-component}

Un componente allegato file in un modulo adattivo consente agli utenti di selezionare e caricare i file dal computer o dal dispositivo locale. Il componente allegato file può essere configurato per consentire tipi di file specifici, limiti di dimensione e allegati multipli.

**Esempio**

![](/help/adaptive-forms/assets/upload-image.png)


## Utilizzo {#reasons-to-use-file-attachment}

Ci sono diversi motivi per cui è utile includere un componente allegato file in un modulo adattivo, tra cui:

* **Raccolta di informazioni aggiuntive**: un componente file allegato consente agli utenti di caricare documenti, immagini, video o altri tipi di file come parte dell’invio del modulo. Può essere utile per raccogliere informazioni aggiuntive, ad esempio curriculum, portfolio o documentazione di supporto.

* **Condivisione semplice di file di grandi dimensioni**: il componente file allegato consente agli utenti di condividere facilmente file di grandi dimensioni, senza dover ricorrere a servizi di condivisione di file esterni.

* **Comodità**: il componente file allegato consente agli utenti di caricare file dal computer locale senza dover spostarsi all’esterno del modulo o utilizzare altri strumenti.

* **Analisi dei dati**: il componente file allegato può essere utilizzato per raccogliere i dati da varie sorgenti e analizzarli o utilizzarli come input per un’ulteriore elaborazione.

* **Esperienza utente**: il componente file allegato può essere utilizzato per rendere il modulo più semplice da usare, fornendo agli utenti un modo chiaro e intuitivo per caricare i file.

## Versione e compatibilità {#version-and-compatibility}

Il componente core Pannello a soffietto moduli adattativi è stato rilasciato a febbraio 2023 come parte dei Componenti core 2.0.4 per Cloud Service e i Componenti core 1.1.12 per AEM Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM Forms 6.5.16.0 o versioni successive |
|---|---|---|
| v1 | Compatibile con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successive | Compatibile con <br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive, ma precedenti a 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente core allegato file dei moduli adattivi, consulta la documentazione tecnica disponibile su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/fileinput/v1/fileinput). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza dell’allegato file per i visitatori tramite la finestra di dialogo Configura. È inoltre possibile definire le opzioni dell’allegato file con facilità per un’esperienza utente diretta.

### Scheda Base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/fileattachement_basictab.png)

* **Nome**: è possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo**: con il relativo titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungi un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo**: seleziona l’opzione per nascondere il titolo del componente.

* **Titolo pulsante**: questa opzione viene utilizzata per impostare l’etichetta del pulsante visualizzato in un modulo adattivo.

* **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente fluida per la raccolta e la gestione dei dati.
* **Nascondi componente**: seleziona l’opzione per nascondere il componente del modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente**: seleziona questa opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.
* **Sola lettura**: seleziona questa opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.
* **Consenti più allegati**: seleziona questa opzione per caricare più allegati utilizzando il pulsante **Allegato file**.

### Scheda Convalida {#validation-tab}

![Scheda Convalida](/help/adaptive-forms/assets/fileattachment_validationtab.png)

* **Obbligatorio**: seleziona questa opzione se desideri visualizzare il componente in un modulo adattivo. Non è possibile selezionare **Nascondi componente** o **Disattiva componente** nella scheda **Base** quando questa opzione è selezionata.

* **Messaggio di errore**: questa opzione consente di inserire un messaggio visualizzato se la casella di controllo **Obbligatorio** è selezionata e il campo viene lasciato vuoto.

* **Messaggio di convalida script**: questa opzione consente di inserire un messaggio da visualizzare in caso di errore di convalida dello script.

* **Messaggio di errore numero minimo di file**: questa opzione viene utilizzata per inserire un messaggio di errore visualizzato se si caricano un numero di file inferiore al numero minimo specificato.

* **Messaggio di errore numero massimo di file**: questa opzione viene utilizzata per inserire un messaggio di errore visualizzato se si carica un numero di file superiore al numero massimo specificato.

* **Dimensione massima del file (MB)**: questa opzione consente di specificare una dimensione massima del file. Le dimensioni dei file sono specificate in MB.

* **Messaggio di errore dimensione massima file**: questa opzione viene utilizzata per inserire un messaggio di errore visualizzato se si caricano file di dimensioni superiori a quelle specificate nell’opzione **Dimensione massima del file (MB)**.

* **Tipi di file consentiti**: vari tipi di file caricabili utilizzando il pulsante **Allegato file** sono aggiunti qui. Consente inoltre di aggiungere un nuovo formato di file facendo clic sul pulsante **Aggiungi**. I formati di file supportati sono: audio, video, immagine, testo o PDF. Puoi anche eliminare o ridisporre i tipi di file consentiti utilizzando:
   * **Elimina**: tocca o fai clic per rimuovere tipi di file specifici.
   * **Ridisponi**: tocca o fai clic e trascina per modificare l’ordine dei tipi di file consentiti.

* **Messaggio di errore tipo di file**: questa opzione consente di inserire un messaggio di errore visualizzato quando si caricano i formati di file diversi da quelli elencati nell’opzione **Tipi di file consentiti**.

### Scheda Contenuto Guida {#help-content-tab}

![Scheda Contenuto Guida](/help/adaptive-forms/assets/fileattachement_helpcontenttab.png)

* **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

* **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility-tab}


![Scheda Accessibilità](/help/adaptive-forms/assets/fileattachement_accessibilitytab.png)

* **Testo per utilità per la lettura dello schermo**: il testo per le utilità per la lettura dello schermo si riferisce al testo aggiuntivo destinato specificamente ad essere letto da tecnologie di assistenza, come le utilità per la lettura dello schermo, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.


## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente di definire e gestire gli stili CSS per il componente Allegato file.

### Scheda Stili {#styles-tab}

Il componente core Allegato file dei moduli adattivi supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

![Finestra di dialogo per la progettazione dei file allegati](/help/adaptive-forms/assets/fileattachment_designdialog.png)

* **Classi CSS predefinite**: puoi fornire una classe CSS predefinita per il componente core Allegato file dei moduli adattivi.

* **Stili consentiti**: puoi definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di moduli adattivi. Per applicare uno stile, nell’editor dei moduli adattivi, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

## Articolo correlato {#related-article}

* [Creare un modulo adattivo in una pagina AEM Sites o in un frammento di esperienza](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=it)

* [Creare un modulo adattivo indipendente](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=it)
