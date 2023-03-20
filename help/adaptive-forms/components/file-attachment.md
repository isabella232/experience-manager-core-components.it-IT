---
title: Componente core Forms adattivo - Allegato file
description: Utilizzo o personalizzazione del componente core allegato file Forms adattivo.
role: Architect, Developer, Admin, User
exl-id: 64a54fc6-db52-481f-bf5a-60c05122004d
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '1508'
ht-degree: 1%

---

# Allegato file {#file-attachment-adaptive-forms-core-component}

Un componente file allegato in un modulo adattivo consente agli utenti di selezionare e caricare i file dal computer o dal dispositivo locale. Il componente File allegato può essere configurato per consentire tipi di file specifici, limiti di dimensione e allegati multipli.

**Esempio**

![](/help/adaptive-forms/assets/upload-image.png)


## Utilizzo {#reasons-to-use-file-attachment}

Ci sono diversi motivi per cui è utile includere un componente file allegato in un modulo adattivo, tra cui:

* **Raccolta di informazioni aggiuntive**: Un componente File allegato consente agli utenti di caricare documenti, immagini, video o altri tipi di file come parte dell’invio del modulo. Può essere utile per raccogliere informazioni aggiuntive, ad esempio riprese, portfolio o documentazione di supporto.

* **Condivisione semplice di file di grandi dimensioni**: Il componente File allegato consente agli utenti di condividere facilmente file di grandi dimensioni, senza dover ricorrere a servizi di condivisione file esterni.

* **Comodità**: Il componente File allegato consente agli utenti di caricare file dal computer locale senza dover spostarsi all’esterno del modulo o utilizzare altri strumenti.

* **Analisi dei dati**: Il componente File allegato può essere utilizzato per raccogliere i dati da varie sorgenti e analizzarli o utilizzarli come input per un’ulteriore elaborazione.

* **Esperienza utente**: Il componente File allegato può essere utilizzato per rendere il modulo più semplice da usare, fornendo agli utenti un modo chiaro e intuitivo per caricare i file.

## Versione e compatibilità {#version-and-compatibility}

Il componente core per pannello a soffietto adattivo di Forms è stato rilasciato a febbraio 2023 come parte dei componenti core 2.0.4 per Cloud Service e i componenti core 1.1.12 per Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM 6.5.16.0 Forms o versione successiva |
|---|---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successivi | Compatibile con<br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive ma inferiori a 2.0.0. |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/adaptive-forms/version.md) documento.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente di base File allegato Forms adattivo, consulta la documentazione tecnica disponibile in [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/fileinput/v1/fileinput). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza dell’allegato del file per i visitatori tramite la finestra di dialogo Configura . È inoltre possibile definire le opzioni di file allegato con facilità per un’esperienza utente diretta.

### Scheda di base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/fileattachement_basictab.png)

* **Nome** - È possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo** - Con il relativo Titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungete un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo** - Seleziona l’opzione per nascondere il titolo del componente.

* **Titolo pulsante** - Questa opzione viene utilizzata per impostare l’etichetta del pulsante visualizzato in un modulo adattivo.

* **Riferimento a un&#39;associazione** - Un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente semplice per la raccolta e la gestione dei dati.
* **Nascondi componente** - Selezionare l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente** - Seleziona l’opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.
* **Sola lettura** - Seleziona l’opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.
* **Consenti più allegati** - Selezionare questa opzione per caricare più allegati utilizzando **File allegato** pulsante .

### Scheda Convalida {#validation-tab}

![Scheda Convalida](/help/adaptive-forms/assets/fileattachment_validationtab.png)

* **Obbligatorio** - Selezionare questa opzione se si desidera visualizzare il componente in un modulo adattivo. Non è possibile selezionare la **Nascondi componente** o **Disattiva componente**  in **Base** quando questa opzione è selezionata.

* **Messaggio di errore** - Questa opzione consente di inserire un messaggio visualizzato se **Obbligatorio** è selezionata e il campo viene lasciato vuoto.

* **Messaggio di convalida script** - Questa opzione consente di inserire un messaggio da visualizzare in caso di errore di convalida dello script.

* **Messaggio di errore dei file minimi** - Questa opzione viene utilizzata per inserire un messaggio di errore visualizzato se si caricano file inferiori al numero minimo di file specificato.

* **Messaggio di errore massimo file** - Questa opzione viene utilizzata per inserire un messaggio di errore visualizzato se si caricano file superiori al numero massimo di file specificato.

* **Dimensione massima del file (MB)** - Questa opzione consente di specificare una dimensione massima del file. Le dimensioni dei file sono specificate in MB.

* **Messaggio di errore Dimensione massima file** - Questa opzione viene utilizzata per inserire un messaggio di errore visualizzato se si caricano file di dimensioni superiori a quelle specificate in **Dimensione massima del file (MB)** opzione .

* **Tipi di file consentiti** - Vari tipi di file che possono essere caricati utilizzando **File allegato** qui sono aggiunti i pulsanti . Consente inoltre di aggiungere un nuovo formato di file facendo clic sul pulsante **Aggiungi** pulsante . I formati di file supportati sono: audio, video, immagine, testo o PDF. È inoltre possibile eliminare o ridisporre i tipi di file consentiti utilizzando:
   * **Elimina** - Tocca o fai clic per rimuovere tipi di file specifici.
   * **Ridisponi** - Tocca o fai clic e trascina per riordinare l’ordine dei tipi di file consentiti.

* **Messaggio di errore del tipo di file** - Questa opzione consente di inserire un messaggio di errore visualizzato quando si caricano i formati di file diversi da quelli elencati in **Tipi di file consentiti** opzione .

### Scheda Contenuto dell’Aiuto {#help-content-tab}

![Scheda Contenuto della guida](/help/adaptive-forms/assets/fileattachement_helpcontenttab.png)

* **Breve descrizione** - Una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita la **Mostra sempre una breve descrizione** per visualizzarlo sotto il componente.

* **Mostra sempre una breve descrizione** - Abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo della Guida** - Il testo della Guida si riferisce a informazioni o indicazioni aggiuntive fornite all&#39;utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’Aiuto (i) posta accanto al componente. Il testo della Guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility-tab}


![Scheda Accessibilità](/help/adaptive-forms/assets/fileattachement_accessibilitytab.png)

* **Testo per assistenti vocali** - Il testo per gli assistenti vocali si riferisce al testo aggiuntivo destinato specificamente alla lettura da parte di tecnologie per l’accessibilità, come gli assistenti vocali, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome ed eventuali messaggi pertinenti del campo (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di tutti gli utenti, compresi quelli con problemi visivi, e di comprendere appieno il campo del modulo e i relativi requisiti.


## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per il componente File allegato.

### Scheda Stili {#styles-tab}

Il componente di base Adaptive Forms File Attachment supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

![Finestra di dialogo di progettazione degli allegati file](/help/adaptive-forms/assets/fileattachment_designdialog.png)

* **Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente core File Attachment di Forms adattivo.

* **Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.
