---
title: Componente core Forms adattivo - Selezione data
description: Utilizzo o personalizzazione del componente core del selettore data adattivo di Forms.
role: Architect, Developer, Admin, User
source-git-commit: 0e4fb8454b7ef84eb5b1b73b01c982a2f9c12381
workflow-type: tm+mt
source-wordcount: '1760'
ht-degree: 2%

---


# Selettore data {#date-picker-adaptive-forms-core-component}

Un componente del selettore data in un modulo adattivo è un elemento dell’interfaccia utente che consente agli utenti di selezionare una data da un calendario o immettendo manualmente una data in un formato specifico. Il componente Selezione data può essere configurato in modo da avere diversi valori di formattazione, convalida e impostazione predefinita.

**Esempio**

![](/help/adaptive-forms/assets/date-picker.png)

## Utilizzo {#reasons-to-use-drop-date-picker}

Ci sono diversi motivi per cui è utile includere un selettore data in un modulo adattivo, tra cui:

* **Comodità**: Un componente Selezione data consente agli utenti di selezionare facilmente una data da un calendario senza dover inserire manualmente la data in un campo di testo. In questo modo è possibile risparmiare tempo e ridurre gli errori.

* **Esperienza utente**: Il componente Selezione data può essere utilizzato per rendere il modulo più semplice da usare, fornendo agli utenti un modo chiaro e intuitivo per selezionare la data.

* **Analisi dei dati**: Il componente Selezione data può essere utilizzato per raccogliere dati da varie sorgenti e analizzarli, oppure per utilizzarli come input per un’ulteriore elaborazione.

* **Gestione eventi**: Il componente Selezione data può essere utilizzato nei siti web di gestione eventi per selezionare la data dell’evento.

* **Prenotazione e prenotazione**: Il componente Selezione data può essere utilizzato nei siti web di prenotazione e prenotazione per selezionare le date di check-in e check-out.

* **Formato data**: Il componente Selezione data può essere utilizzato per correggere il formato in cui la data viene visualizzata e immessa. Assicurati che il formato della data sia coerente in tutto il modulo per garantire un’esperienza utente coerente.

## Versione e compatibilità {#version-and-compatibility}

Il componente core del selettore data adattivo di Forms è stato rilasciato a febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## Dettagli tecnici {#technical-details}

Scarica le informazioni più recenti sul componente core del selettore data adattivo di Forms nella documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/datepicker/v1/datepicker). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del selettore data per i visitatori tramite la finestra di dialogo Configura . Puoi anche definire le opzioni del selettore data con facilità per un’esperienza utente senza soluzione di continuità.

### Scheda di base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/datepicker_basictab.png)

* **Nome** - Il nome identifica il componente in modo univoco nell’editor di regole. I caratteri speciali e gli spazi non sono consentiti nelle stringhe dei nomi.

* **Titolo** - Il titolo è una stringa che viene visualizzata nella parte superiore di un componente in un modulo adattivo. Il titolo identifica in modo univoco il componente nella struttura ad albero di un modulo adattivo. Se non aggiungete un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo** - Selezionare questa opzione per nascondere il titolo del tipo di componente in un modulo adattivo.

* **Testo segnaposto** - Il testo segnaposto in un componente modulo si riferisce a un’etichetta o a un prompt breve che viene visualizzato all’interno di un campo di input come suggerimento per l’utente sul tipo di informazioni che ci si aspetta venga immesso in quel campo. Il testo segnaposto scompare quando l’utente inizia a digitare nel campo e viene visualizzato nuovamente se il campo viene lasciato vuoto. Fornisce un segnale visivo all’utente, ma non agisce come etichetta o valore permanente per il campo.

* **Nascondi componente** - Selezionare l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente** - Seleziona l’opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.
* **Sola lettura** - Seleziona l’opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.
* **Data predefinita** - Questa opzione consente di aggiungere una data al campo del modulo. La data immessa viene visualizzata per impostazione predefinita nella posizione del componente. Se l’utente non immette alcuna data, questo valore viene inviato al momento dell’invio del modulo. Nel caso **Componente disabilitato** o **Componente di sola lettura** viene selezionata, la data predefinita viene visualizzata sullo schermo e inviata al momento dell’invio del modulo.


### Scheda Convalida {#validation-tab}

![Scheda Convalida](/help/adaptive-forms/assets/datepicker_validation.png)

* **Obbligatorio** - Selezionare questa opzione se si desidera visualizzare il componente in un modulo adattivo. Non è possibile selezionare la **Nascondi componente** o **Disattiva componente** in **Base** quando questa opzione è selezionata.

* **Messaggio di errore** - Questa opzione consente di inserire un messaggio visualizzato se **Obbligatorio** è selezionata e il campo modulo viene lasciato vuoto.

* **Messaggio di convalida script** - Questa opzione consente di inserire un messaggio da visualizzare in caso di errore di convalida dello script.

* **Data minima** - Questa opzione consente di inserire la data minima richiesta. Se immetti una data precedente alla data specificata in Data minima, sullo schermo viene visualizzato un messaggio di errore. La **Messaggio di errore minimo** consente di aggiungere un messaggio di errore personalizzato.

* **Messaggio di errore minimo** - **Messaggio di errore minimo** Se si immette una data precedente alla data specificata nella finestra di dialogo, è possibile aggiungere un messaggio di errore personalizzato da visualizzare **Data minima** opzione .

* **Data massima** - Questa opzione consente di inserire la data massima richiesta. Se immetti una data successiva alla data specificata in Data massima, sullo schermo viene visualizzato un messaggio di errore. La **Messaggio di errore massimo** consente di aggiungere un messaggio di errore personalizzato.

* **Messaggio di errore massimo** - **Messaggio di errore massimo** consente di aggiungere un messaggio di errore personalizzato da visualizzare, se si immette una data successiva alla data specificata in **Data massima** opzione .


### Scheda Contenuto dell’Aiuto {#help-content-tab}

![Scheda Contenuto della guida](/help/adaptive-forms/assets/datepicker_helptab.png)

* **Breve descrizione** - Una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita la **Mostra sempre una breve descrizione** per visualizzarlo sotto il componente.

* **Mostra sempre una breve descrizione**- Abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo della Guida** - Il testo della Guida si riferisce a informazioni o indicazioni aggiuntive fornite all&#39;utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’Aiuto (i) posta accanto al componente. Il testo della Guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.


### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità](/help/adaptive-forms/assets/datepicker_accessibilitytab.png)

**Testo per assistenti vocali** - Il testo per gli assistenti vocali si riferisce al testo aggiuntivo destinato specificamente alla lettura da parte di tecnologie per l’accessibilità, come gli assistenti vocali, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome ed eventuali messaggi pertinenti del campo (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di tutti gli utenti, compresi quelli con problemi visivi, e di comprendere appieno il campo del modulo e i relativi requisiti.

Sulla **Accessibilità** scheda , valori impostati per [Accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) etichette per il componente. Sono disponibili varie opzioni per l’utilizzo del testo per l’assistente vocale:

* **Testo personalizzato**: Selezionare questa opzione per utilizzare il testo personalizzato per le etichette di accessibilità ARIA. Selezionando questa opzione viene visualizzata la finestra di dialogo Testo personalizzato. È possibile aggiungere informazioni rilevanti nella finestra di dialogo Testo personalizzato.
* **Descrizione**: Selezionare questa opzione per utilizzare la descrizione per le etichette di accessibilità ARIA.
* **Titolo**: Selezionare questa opzione per utilizzare il titolo per le etichette di accessibilità ARIA.
* **Nome**: Selezionare questa opzione per utilizzare il nome per le etichette di accessibilità ARIA.
* **Nessuno**: Selezionare questa opzione se non si desidera aggiungere etichette di accessibilità ARIA.


### Scheda Formati {#format-tab}

![Scheda Formati](/help/adaptive-forms/assets/datepicker_formattab.png)

* **Formato di visualizzazione** - Rappresenta il formato della data visualizzato all&#39;utente. La **Tipo** consente all’utente di selezionare il formato della data. È inoltre possibile personalizzare il formato della data utilizzando **Personalizzato** in **Tipo** menu a discesa.

* **Modifica formato** - Rappresenta un formato di data in cui l’utente può modificare la data. La **Tipo** consente all’utente di selezionare il formato della data. È inoltre possibile personalizzare il formato della data utilizzando **Personalizzato** in **Tipo** menu a discesa.

* **Formato di visualizzazione** - Rappresenta il formato della data visualizzato all&#39;utente. L’opzione Tipo consente all’utente di selezionare il formato della data. È inoltre possibile personalizzare il formato della data utilizzando **Personalizzato** in **Tipo** menu a discesa.

* **Modifica formato** - Rappresenta un formato di data in cui l’utente modifica la data. L’opzione Tipo consente all’utente di selezionare il formato della data. È inoltre possibile personalizzare il formato della data utilizzando **Personalizzato** in **Tipo** menu a discesa.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per il componente Selezione data .


### Scheda Stili {#styles-tab}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per un componente. Il componente di base per il selettore data adattivo di Forms supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

**Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente core del selettore data adattivo di Forms.

**Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

### Scheda Formati {#formats-tab}

La scheda Formati consente di specificare i formati di data predefiniti e personalizzati.