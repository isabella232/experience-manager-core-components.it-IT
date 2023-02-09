---
title: Componente core Forms adattivo - Ingresso telefonico
description: Utilizzo o personalizzazione del componente di base per l’input telefonico di Forms adattivo.
role: Architect, Developer, Admin, User
source-git-commit: 0e4fb8454b7ef84eb5b1b73b01c982a2f9c12381
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 1%

---


# Ingresso telefonico {#telephone-input-adaptive-forms-core-component}

Il componente di base per l’immissione di un telefono per modulo adattivo consente agli utenti di inserire un numero di telefono. Il campo di ingresso del telefono visualizza le tastiere nei dispositivi mobili pertinenti ai numeri di telefono. Può essere personalizzato con attributi aggiuntivi quali &quot;pattern&quot; e &quot;segnaposto&quot; per specificare il formato e la descrizione del numero di telefono.

Il campo di immissione telefonica viene comunemente utilizzato nei moduli di contatto, nei moduli di registrazione e in altri moduli in cui è richiesto un numero telefonico come mezzo di contatto. Il campo di input telefonico può essere utilizzato anche per garantire che l&#39;utente immetta un numero di telefono valido, in quanto il browser può applicare determinati vincoli, come la lunghezza e il formato del numero di telefono, in base all&#39;attributo &quot;pattern&quot;.

## Utilizzo {#reasons-to-use-telephone-input}

I motivi comuni per utilizzare un campo di immissione telefonica in un modulo adattivo sono i seguenti:

* **Informazioni di contatto**: Un campo di input telefonico viene comunemente utilizzato per raccogliere il numero di telefono di un utente come mezzo di contatto.

* **Precisione dei dati migliorata**: Utilizzando un campo di input telefonico, il modulo può imporre determinati vincoli al formato del numero di telefono, il che può contribuire a garantire che i dati immessi siano accurati e completi.

* **Migliore esperienza utente**: Un campo di ingresso telefonico offre agli utenti un modo chiaro e intuitivo di inserire il proprio numero di telefono e può migliorare l&#39;esperienza dell&#39;utente consentendo agli utenti di inserire rapidamente e facilmente le informazioni di contatto.

## Versione e compatibilità {#version-and-compatibility}

Il componente di base per l’input per telefono adattivo di Forms è stato rilasciato nel febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente di base per l’input per telefono adattivo di Forms, consulta la documentazione tecnica disponibile in [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/telephoneinput/v1/telephoneinput). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza di input del telefono per i visitatori tramite la finestra di dialogo Configura . È inoltre possibile definire le opzioni di input per telefono in modo semplice e intuitivo.

![Scheda di base](/help/adaptive-forms/assets/telephoneinput_basictab.png)

* **Nome** - È possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo** - Con il relativo Titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungete un titolo, al posto del testo del titolo viene visualizzato il nome del componente.
* **Nascondi titolo** - Seleziona l’opzione per nascondere il titolo del componente.

* **Testo segnaposto** - Il testo segnaposto in un componente modulo si riferisce a un’etichetta o a un prompt breve che viene visualizzato all’interno di un campo di input come suggerimento per l’utente sul tipo di informazioni che ci si aspetta venga immesso in quel campo. Il testo segnaposto scompare quando l’utente inizia a digitare nel campo e viene visualizzato nuovamente se il campo viene lasciato vuoto. Fornisce un segnale visivo all’utente, ma non agisce come etichetta o valore permanente per il campo.
* **Riferimento a un&#39;associazione** - Un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente semplice per la raccolta e la gestione dei dati.
* **Nascondi componente** - Selezionare l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente** - Seleziona l’opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.
* **Sola lettura** - Seleziona l’opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.
* **Valore predefinito** - Questa opzione consente di aggiungere un valore predefinito in un campo modulo. Se **Componente disabilitato** o **Componente di sola lettura** è selezionato, il valore predefinito viene visualizzato sullo schermo. Se l’utente non immette alcun valore nel campo modulo, questo valore viene inviato al momento dell’invio del modulo

### Scheda Convalida {#validation-tab}

![Scheda Convalida](/help/adaptive-forms/assets/telephoneinput_validationtab.png)

* **Obbligatorio** - Selezionare questa opzione se si desidera visualizzare il componente in un modulo adattivo. Non è possibile selezionare la **Nascondi componente** o **Disattiva componente**  in **Base** quando questa opzione è selezionata.

* **Messaggio di errore** - Questa opzione consente di inserire un messaggio visualizzato se **Obbligatorio** è selezionata e il campo viene lasciato vuoto.

* **Messaggio di convalida script** - Questa opzione consente di inserire un messaggio da visualizzare in caso di errore di convalida dello script.

* **Numero massimo di caratteri** - Questa opzione consente di specificare il numero massimo di caratteri consentiti nel componente. Se immetti caratteri maggiori del valore specificato in **Numero massimo di caratteri**, sullo schermo viene visualizzato un messaggio di errore. La **Messaggio di errore relativo al numero massimo di caratteri** consente di aggiungere un messaggio di errore personalizzato.

* **Messaggio di errore relativo al numero massimo di caratteri** - **Messaggio di errore relativo al numero massimo di caratteri** se si immettono caratteri superiori al valore specificato nella **Numero massimo di caratteri** opzione .

* **Numero minimo di caratteri** - Questa opzione consente di specificare il numero minimo di caratteri consentiti nel campo. Se immetti caratteri inferiori al valore specificato in **Numero minimo di caratteri**, sullo schermo viene visualizzato un messaggio di errore. La **Messaggio di errore minimo caratteri** consente di aggiungere un messaggio di errore personalizzato.

* **Messaggio di errore minimo caratteri** - **Messaggio di errore minimo caratteri** consente di aggiungere un messaggio di errore personalizzato se si immettono caratteri inferiori al valore specificato nel **Numero minimo di caratteri** opzione .

La **Pattern di convalida** consente di inserire un pattern per convalidare il numero di telefono immesso. Il numero di telefono immesso viene convalidato in base al valore immesso nel **Pattern** opzione . Nel caso in cui il numero di telefono non sia convalidato con il valore inserito in **Pattern** il messaggio di errore viene visualizzato sullo schermo.
* **Pattern** - Questa opzione consente di inserire i pattern di verifica consentiti per il numero di telefono. Sono consentite anche espressioni regolari.
* **Messaggio di errore** - Questa opzione consente di inserire un messaggio visualizzato sullo schermo se il numero di telefono immesso non viene convalidato con il valore immesso nel campo **Pattern** opzione

### Scheda Contenuto dell’Aiuto {#help-content-tab}

![Scheda Contenuto della guida](/help/adaptive-forms/assets/telephoneinput_helptab.png)

* **Breve descrizione** - Una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita la **Mostra sempre una breve descrizione** per visualizzarlo sotto il componente.

* **Mostra sempre una breve descrizione** - Abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo della Guida** - Il testo della Guida si riferisce a informazioni o indicazioni aggiuntive fornite all&#39;utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’Aiuto (i) posta accanto al componente. Il testo della Guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità](/help/adaptive-forms/assets/telephoneinput_accessibilitytab.png)

* **Testo per assistenti vocali** - Il testo per gli assistenti vocali si riferisce al testo aggiuntivo destinato specificamente alla lettura da parte di tecnologie per l’accessibilità, come gli assistenti vocali, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome ed eventuali messaggi pertinenti del campo (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di tutti gli utenti, compresi quelli con problemi visivi, e di comprendere appieno il campo del modulo e i relativi requisiti.


## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per il componente di input Telephone.

### Scheda Stili {#styles-tab}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per un componente. Il componente di base per l’input telefonico di Forms adattivo supporta l’AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

**Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente core di input per telefono adattivo di Forms.

**Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

### Scheda Formati {#format-tab}

La scheda Formati consente di specificare i formati numerici predefiniti e personalizzati.