---
title: Componente core Forms adattivo - Elenco a discesa
description: Utilizzo o personalizzazione del componente di base dell’elenco a discesa di Forms adattivo.
role: Architect, Developer, Admin, User
source-git-commit: 1e6460d318f4f9a5dfdcbb81723da01b51b72f3f
workflow-type: tm+mt
source-wordcount: '1673'
ht-degree: 1%

---


# Elenco a discesa {#drop-down-list-adaptive-forms-core-component}

Un elenco a discesa in un modulo adattivo consente agli utenti di selezionare una o più opzioni da un elenco di opzioni predefinite. Le opzioni possono essere di tipo String, Number o Boolean. Inoltre, il componente elenco a discesa può essere configurato in modo da avere diversi valori di convalida e di default.

**Esempio**
![](/help/adaptive-forms/assets/drop-down-list.png)

## Utilizzo {#reasons-to-use-drop-down-list}

Ci sono diversi motivi per cui è utile includere un elenco a discesa in un modulo adattivo, tra cui:

* **Elenco lungo di opzioni**: Gli elenchi a discesa sono utili nelle situazioni in cui è disponibile un lungo elenco di opzioni per un campo. occupano meno spazio sul modulo rispetto a un elenco di pulsanti di scelta o caselle di controllo e possono risultare meno onerosi per gli utenti.

* **Coerenza**: Gli elenchi a discesa forniscono coerenza nella progettazione e nel layout del modulo, facilitando la navigazione agli utenti.

* **Chiarezza**: Gli elenchi a discesa possono rendere il modulo più chiaro e semplice da comprendere fornendo un elenco chiaro e conciso di opzioni.

* **Esperienza utente**: Gli elenchi a discesa possono essere utilizzati per rendere il modulo più semplice da usare, fornendo agli utenti un modo chiaro e intuitivo di selezionare le opzioni.

* **Analisi dei dati**: Gli elenchi a discesa possono essere utilizzati per raccogliere dati da varie sorgenti e analizzarli o utilizzarli come input per un’ulteriore elaborazione.


**Finestra di dialogo Proprietà**

![](/help/adaptive-forms/assets/drop-down-list-properties.png)

In questo esempio, l’elemento Options viene utilizzato per definire gli elementi dell’elenco. La **Testo visualizzato** viene utilizzato per fornire un’etichetta per gli elementi dell’elenco e **Valore dati** viene utilizzato per specificare il valore inviato al server al momento dell’invio del modulo.

Ogni opzione dell’elenco a discesa ha un valore Dati univoco e un attributo Testo visualizzato . Se un utente seleziona l’opzione &quot;Rosso&quot;, il valore dati corrispondente viene inviato al server al momento dell’invio del modulo. Questi dati possono quindi essere elaborati da uno script sul lato server per determinare quali opzioni sono state selezionate dall’utente e possono essere utilizzati per eseguire varie azioni, ad esempio l’aggiornamento di altri campi del modulo o l’invio dei dati del modulo a uno script sul lato server per un’ulteriore elaborazione.

Inoltre, l’elenco a discesa può essere configurato in modo da avere valori di elaborazione diversi per ciascuna opzione, e questo può essere impostato utilizzando l’Editor di regole di Forms adattive.

## Versione e compatibilità {#version-and-compatibility}

L’elenco a discesa Adattivo Forms Componente principale è stato rilasciato nel febbraio 2023 come parte dei Componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sull’elenco a discesa Adaptive Forms Componente principale nella documentazione tecnica di [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/dropdown/v1/dropdown). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza dell’elenco a discesa per i visitatori tramite la finestra di dialogo Configura . Puoi anche definire le opzioni dell’elenco a discesa in modo semplice per un’esperienza utente fluida.

![Scheda Base](/help/adaptive-forms/assets/dropdown_basictab.png)

* **Nome** - È possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo** - Con il relativo Titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungete un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo** - Seleziona l’opzione per nascondere il titolo del componente.

* **Consenti selezione multipla** - Selezionare questa opzione per selezionare più opzioni da un elenco a discesa.

* **Salva valore con nome** - Questa opzione specifica il tipo di dati del valore inviato quando viene selezionata un’opzione. Se la **Salva valore con nome** è impostato su `Number` e si aggiungono dati stringa a **Valore dati** &#x200B; &#x200B; **Opzioni** nella schermata viene visualizzato un `Value type mismatch` messaggio di errore.

   In **Opzioni** è possibile aggiungere valori di dati e visualizzare coppie di testo utilizzando **Aggiungi** pulsante . Una volta aggiunta una nuova opzione, vengono eseguite le azioni seguenti:

   * **Valore dati** - Questa opzione consente di immettere il contenuto da inviare quando viene selezionata un’opzione.
   * **Testo visualizzato** - Questa opzione consente di inserire il contenuto da visualizzare in un modulo adattivo.
   * **Elimina** - Tocca o fai clic per eliminare l’opzione di un menu a discesa .
   * **Ridisponi** - Tocca o fai clic e trascina per ridisporre l’ordine di opzione di un menu a discesa.

* **Opzioni predefinite** - Questa opzione consente di aggiungere valori predefiniti. Utilizza l’icona Elimina per rimuovere l’opzione aggiunta. Se la **Salva valore con nome** è impostato su `Number` e si aggiungono dati stringa a **Opzioni predefinite**, nella schermata viene visualizzato un `Value type mismatch` messaggio di errore.

* **Testo segnaposto** - Il testo segnaposto in un componente modulo si riferisce a un’etichetta o a un prompt breve che viene visualizzato all’interno di un campo di input come suggerimento per l’utente sul tipo di informazioni che ci si aspetta venga immesso in quel campo. Il testo segnaposto scompare quando l’utente inizia a digitare nel campo e viene visualizzato nuovamente se il campo viene lasciato vuoto. Fornisce un segnale visivo all’utente, ma non agisce come etichetta o valore permanente per il campo.

* **Riferimento a un&#39;associazione** - Un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente semplice per la raccolta e la gestione dei dati.

* **Nascondi componente** - Selezionare l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente** - Seleziona l’opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.
* **Sola lettura** - Seleziona l’opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.

### Scheda Convalida {#validation-tab}

![Scheda Convalida](/help/adaptive-forms/assets/dropdown_validationtab.png)

* **Obbligatorio** - Selezionare questa opzione se si desidera visualizzare il componente in un modulo adattivo. Non è possibile selezionare la **Nascondi componente** o **Disattiva componente**  in **Base** quando questa opzione è selezionata.

* **Messaggio di errore** - Questa opzione consente di inserire un messaggio visualizzato se **Obbligatorio** è selezionata e il campo modulo viene lasciato vuoto.

* **Messaggio di convalida script** - Questa opzione consente di inserire un messaggio da visualizzare in caso di errore di convalida dello script.

### Scheda Contenuto dell’Aiuto {#help-content-tab}

![Scheda Contenuto della guida](/help/adaptive-forms/assets/dropdown_helptab.png)

* **Breve descrizione** - Una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita la **Mostra sempre una breve descrizione** per visualizzarlo sotto il componente.

* **Mostra sempre una breve descrizione** - Abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo della Guida** - Il testo della Guida si riferisce a informazioni o indicazioni aggiuntive fornite all&#39;utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’Aiuto (i) posta accanto al componente. Il testo della Guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità](/help/adaptive-forms/assets/dropdown_accessibilitytab.png)

* **Testo per assistenti vocali** - Il testo per gli assistenti vocali si riferisce al testo aggiuntivo destinato specificamente alla lettura da parte di tecnologie per l’accessibilità, come gli assistenti vocali, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome ed eventuali messaggi pertinenti del campo (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di tutti gli utenti, compresi quelli con problemi visivi, e di comprendere appieno il campo del modulo e i relativi requisiti.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per il componente Elenco a discesa.


### Scheda Stili {#styles-tab}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per un componente. L’elenco a discesa Forms adattivo Componenti core supporta l’AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

**Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente core dell’elenco a discesa Forms adattivo.

**Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.


