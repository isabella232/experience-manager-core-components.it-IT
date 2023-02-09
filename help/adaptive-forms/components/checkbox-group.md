---
title: Componente core Forms adattivo - Gruppo di caselle di selezione
description: Utilizzo o personalizzazione del componente core del gruppo di caselle di controllo Forms adattivo.
role: Architect, Developer, Admin, User
source-git-commit: 0e4fb8454b7ef84eb5b1b73b01c982a2f9c12381
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 2%

---


# Gruppo di caselle di selezione {#button-component-adaptive-forms-core-component}

Un gruppo di caselle di controllo in un modulo adattivo è un insieme di caselle di controllo correlate che consentono agli utenti di selezionare una o più opzioni da un elenco. Ciascuna casella di controllo è rappresentata da un valore dati (valore utilizzato per elaborare gli elementi di un gruppo di caselle di controllo) e dal valore di visualizzazione (etichetta per ogni elemento di casella di controllo che ne descrive lo scopo)

**Esempio**

![](/help/adaptive-forms/assets/checkbox-group.png)

**Finestra di dialogo Proprietà**

![](/help/adaptive-forms/assets/checkbox-group-properties.png)

In questo esempio, l’elemento Options viene utilizzato per raggruppare le caselle di controllo. La **Testo visualizzato** viene utilizzato per fornire un’etichetta per un elemento e **Valore dati** viene utilizzato per specificare il valore inviato al server al momento dell’invio del modulo.

Ogni opzione/elemento della casella di controllo ha un valore Dati univoco e un attributo Testo visualizzato . Se un utente seleziona le caselle di controllo &quot;Figlio&quot; e &quot;Figlia&quot;, il valore dati corrispondente viene inviato al server al momento dell’invio del modulo. Questi dati possono quindi essere elaborati da uno script sul lato server per determinare quali opzioni sono state selezionate dall’utente e possono essere utilizzati per eseguire varie azioni, ad esempio l’aggiornamento di altri campi del modulo o l’invio dei dati del modulo a uno script sul lato server per un’ulteriore elaborazione.

Inoltre, il gruppo di caselle di controllo può essere configurato in modo da avere valori di elaborazione diversi per ciascuna opzione, e questo può essere impostato utilizzando l’Editor di regole di Forms adattivo.

## Utilizzo {#reasons-to-use-check-box-group}

Ci sono diversi motivi per cui è utile includere un gruppo di caselle di controllo in un modulo adattivo, tra cui:

* **Selezioni multiple**: Un gruppo di caselle di controllo consente agli utenti di selezionare più opzioni da un elenco, il che può essere utile in situazioni in cui sono consentite o richieste selezioni multiple.

* **Esperienza utente**: Il gruppo di caselle di controllo può essere utilizzato per rendere il modulo più semplice da usare, fornendo agli utenti un modo chiaro e intuitivo per selezionare più opzioni.

* **Analisi dei dati**: Il gruppo di caselle di controllo può essere utilizzato per raccogliere dati da varie sorgenti e analizzarli o utilizzarli come input per un&#39;ulteriore elaborazione.

* **Indagini**: Il gruppo di caselle di controllo può essere utilizzato nei sondaggi per selezionare più opzioni per una domanda.

* **Preferenze utente**: Il gruppo casella di controllo può essere utilizzato per raccogliere le preferenze dell&#39;utente per diverse opzioni.

* **Valore dati**: Il gruppo casella di controllo può essere utilizzato anche per elaborare gli elementi di un gruppo di caselle di controllo.

## Versione e compatibilità {#version-and-compatibility}

Il componente di base Adaptive Forms Checkbox Group è stato rilasciato nel febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Ottieni le informazioni più recenti sul componente core del gruppo di controllo adattivo Forms nella documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/checkboxgroup/v1/checkboxgroup). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente la tua esperienza con le caselle di controllo per i visitatori tramite la finestra di dialogo Configura . Puoi anche definire le opzioni delle caselle di controllo con facilità per un’esperienza utente diretta.


### Scheda di base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/checkbox_basictab.png)

* **Nome** - Il nome identifica in modo univoco il componente nell&#39;editor delle regole.Le stringhe di nome non consentono l&#39;uso di caratteri e spazi speciali.

* **Titolo** - Con il relativo Titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungete un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo** - Seleziona l’opzione per nascondere il titolo del componente.

* **Opzioni** - È possibile aggiungere valori di dati e visualizzare coppie di testo utilizzando **Aggiungi** pulsante . Una volta aggiunta una nuova opzione, è possibile eseguire le azioni seguenti:

   * **Valore dati** - Questa opzione consente di immettere il contenuto da inviare quando viene selezionata un’opzione.
   * **Testo visualizzato** - Questa opzione consente di inserire il contenuto da visualizzare in un modulo adattivo.
   * **Elimina** - Tocca o fai clic per eliminare l’opzione di una casella di controllo .
   * **Ridisponi**: tocca o fai clic e trascina per modificare l’ordine dei pannelli.

* **Riferimento a un&#39;associazione** - Un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente semplice per la raccolta e la gestione dei dati.

* **Tipo di dati del valore inviato** - Questa opzione specifica il tipo di dati del valore inviato quando viene selezionata un’opzione. Se la **tipo di dati del valore inviato** è impostato su `Number` e si aggiungono dati stringa a **Valore dati** &#x200B; &#x200B; **Opzioni** nella schermata viene visualizzato un `Value type mismatch` messaggio di errore.

* **Opzioni di visualizzazione** - Questa opzione viene utilizzata per impostare l’allineamento visivo delle caselle di controllo in un modulo adattivo. Le due opzioni supportate sono:
   * **Orizzontale** - Quando questa opzione è selezionata, le caselle di controllo vengono visualizzate da sinistra a destra in un modulo adattivo.
   * **Verticale** - Quando questa opzione è selezionata, le caselle di controllo vengono visualizzate dall’alto verso il basso in un modulo adattivo.

* **Opzioni predefinite** - Questa opzione consente di aggiungere valori predefiniti preselezionati al caricamento del modulo. Utilizza l’icona Elimina per rimuovere le opzioni aggiunte. Se la **tipo di dati del valore inviato** è impostato su `Number` e si aggiungono dati stringa a **Opzioni predefinite**, nella schermata viene visualizzato un `Value type mismatch` messaggio di errore.
* **Nascondi componente** - Selezionare l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente** - Seleziona l’opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.
* **Sola lettura** - Seleziona l’opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.

### Scheda Convalida {#validation-tab}

![Scheda Convalida](/help/adaptive-forms/assets/checkbox_validationtab.png)

* **Obbligatorio** - Selezionare questa opzione se si desidera visualizzare il componente in un modulo adattivo. Non è possibile selezionare la **Nascondi componente** o **Disattiva componente**  in **Base** quando questa opzione è selezionata.

* **Messaggio di errore** - Questa opzione consente di inserire un messaggio visualizzato se **Obbligatorio** è selezionata e il campo modulo viene lasciato vuoto.

* **Messaggio di convalida script** - Questa opzione consente di inserire un messaggio da visualizzare in caso di errore di convalida dello script.

### Scheda Contenuto dell’Aiuto {#helpcontent-tab}

![Scheda Contenuto della guida](/help/adaptive-forms/assets/checkbox_helptab.png)

* **Breve descrizione** - Una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita la **Mostra sempre una breve descrizione** per visualizzarlo sotto il componente.

* **Mostra sempre una breve descrizione** - Abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo della Guida** - Il testo della Guida si riferisce a informazioni o indicazioni aggiuntive fornite all&#39;utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’Aiuto (i) posta accanto al componente. Il testo della Guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità](/help/adaptive-forms/assets/checkbox_accessibility.png)

* **Testo per assistenti vocali** - Il testo per gli assistenti vocali si riferisce al testo aggiuntivo destinato specificamente alla lettura da parte di tecnologie per l’accessibilità, come gli assistenti vocali, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome ed eventuali messaggi pertinenti del campo (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di tutti gli utenti, compresi quelli con problemi visivi, e di comprendere appieno il campo del modulo e i relativi requisiti.

   Sulla **Accessibilità** scheda , valori impostati per [Accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) etichette per il componente. Sono disponibili varie opzioni per l’utilizzo del testo per l’assistente vocale:

* **Testo personalizzato**: Selezionare questa opzione per utilizzare il testo personalizzato per le etichette di accessibilità ARIA. Selezionando questa opzione viene visualizzata la finestra di dialogo Testo personalizzato. È possibile aggiungere informazioni rilevanti nella finestra di dialogo Testo personalizzato.

* **Titolo**: Selezionare questa opzione per utilizzare il titolo per le etichette di accessibilità ARIA.


## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo Progettazione viene utilizzata per definire e gestire gli stili CSS per il componente Gruppo di caselle di controllo.

### Scheda Stili {#styles-tab}

Il componente di base Gruppo di caselle di controllo Forms adattivo supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

**Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente core Gruppo di caselle di controllo adattivo Forms.

**Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

