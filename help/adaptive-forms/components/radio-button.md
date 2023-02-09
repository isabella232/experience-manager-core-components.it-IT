---
title: Componente core Forms adattivo - Pulsante di scelta
description: Utilizzo o personalizzazione del componente core del pulsante di scelta adattivo Forms.
role: Architect, Developer, Admin, User
source-git-commit: 1e6460d318f4f9a5dfdcbb81723da01b51b72f3f
workflow-type: tm+mt
source-wordcount: '1645'
ht-degree: 1%

---


# Pulsante di scelta {#radio-button-adaptive-forms-core-component}

Un pulsante di scelta in un modulo adattivo è un tipo di elemento di input che consente all’utente di selezionare una opzione da un gruppo di opzioni correlate. È rappresentato da un piccolo pulsante circolare riempito o vuoto per indicare se l’opzione è selezionata o meno. Quando un utente seleziona un pulsante di scelta, gli altri nel gruppo vengono deselezionati. I pulsanti di scelta vengono generalmente utilizzati quando sono presenti più opzioni reciprocamente esclusive e se ne può selezionare una sola alla volta.

**Esempio**

![](/help/adaptive-forms/assets/radio-button.png)

**Finestra di dialogo Proprietà**

![](/help/adaptive-forms/assets/radio-button-properties.png)

In questo esempio, l’elemento Options viene utilizzato per raggruppare i pulsanti di scelta. La **Testo visualizzato** viene utilizzato per fornire un’etichetta per un elemento e **Valore dati** viene utilizzato per specificare il valore inviato al server al momento dell’invio del modulo.

Ogni opzione del pulsante di scelta ha un valore Dati univoco e un attributo Testo visualizzato . Se un utente seleziona &quot;1-10&quot;, il valore dati corrispondente viene inviato al server quando il modulo viene inviato. Questi dati possono quindi essere elaborati da uno script sul lato server per determinare quali opzioni sono state selezionate dall’utente e possono essere utilizzati per eseguire varie azioni, ad esempio l’aggiornamento di altri campi del modulo o l’invio dei dati del modulo a uno script sul lato server per un’ulteriore elaborazione.

Inoltre, ogni pulsante di scelta può essere configurato in modo da avere valori di elaborazione diversi per ciascuna opzione, e questo può essere impostato utilizzando l’Editor di regole di Forms adattivo

## Utilizzo {#reasons-to-use-radio-button}

Esistono diversi motivi per utilizzare i pulsanti di scelta in un modulo, tra cui:

* **Scelte limitate**: I pulsanti di scelta vengono utilizzati per fornire un elenco di opzioni predefinite tra le quali l’utente può scegliere, e una sola opzione alla volta può essere selezionata. Questa funzione è utile quando il numero di opzioni è limitato e si escludono a vicenda.

* **Cancella rappresentazione**: I pulsanti di scelta sono chiari e facili da comprendere, rendendo più semplice per gli utenti sapere cosa stanno selezionando.

* **Coerenza**: L’utilizzo dei pulsanti di scelta garantisce agli utenti un modo uniforme e standardizzato di presentare le opzioni, facilitando loro la comprensione e l’interazione con il modulo.

* **Facile da usare**: I pulsanti di scelta sono facili da usare, in particolare per gli utenti che non hanno familiarità con la tecnologia o che hanno una mobilità limitata.

## Versione e compatibilità {#version-and-compatibility}

Il componente core per pulsanti di scelta adattativo di Forms è stato rilasciato nel febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente core del pulsante di scelta Adattivo Forms, consulta la documentazione tecnica disponibile in [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/radiobutton/v1/radiobutton). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del pulsante di scelta per i visitatori tramite la finestra di dialogo Configura . Puoi anche definire le opzioni dei pulsanti di scelta con facilità per un’esperienza utente fluida.

![Scheda Base](/help/adaptive-forms/assets/radiobutton_basictab.png)

* **Nome** - È possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo** - Con il relativo Titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungete un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo** - Seleziona l’opzione per nascondere il titolo del componente.

   In **Opzioni** è possibile aggiungere valori di dati e visualizzare coppie di testo utilizzando **Aggiungi** pulsante . Una volta aggiunta una nuova opzione, è possibile eseguire le azioni seguenti:

   * **Valore dati** - Questa opzione consente di immettere il contenuto da inviare quando viene selezionata un’opzione.
   * **Testo visualizzato** - Questa opzione consente di inserire il contenuto da visualizzare in un modulo adattivo.
   * **Elimina** - Tocca o fai clic per eliminare l’opzione di un pulsante di scelta .
   * **Ridisponi** - Tocca o fai clic e trascina per ridisporre l’ordine delle opzioni.

* **Riferimento a un&#39;associazione** - Un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente semplice per la raccolta e la gestione dei dati.

* **Tipo di dati del valore inviato** - Questa opzione specifica il tipo di dati del valore inviato quando viene selezionata un’opzione. Se la **tipo di dati del valore inviato** è impostato su `Number` e si aggiungono dati stringa a **Valore dati** &#x200B; &#x200B; **Opzioni** nella schermata viene visualizzato un `Value type mismatch` messaggio di errore.
* **Opzioni predefinite** - Questa opzione consente di aggiungere valori predefiniti preselezionati al caricamento del modulo. Se la **tipo di dati del valore inviato** è impostato su `Number` e si aggiungono dati stringa a **Opzioni predefinite**, nella schermata viene visualizzato un `Value type mismatch` messaggio di errore.

* **Opzioni di visualizzazione** - Questa opzione viene utilizzata per impostare l’allineamento visivo dei pulsanti di scelta in un modulo adattivo. Le due opzioni supportate sono:
   * **Orizzontale** - Quando questa opzione è selezionata, i pulsanti di scelta vengono visualizzati da sinistra a destra in un modulo adattivo.
   * **Verticale** - Quando questa opzione è selezionata, i pulsanti di scelta vengono visualizzati dall’alto verso il basso in un modulo adattivo.
* **Nascondi componente** - Selezionare l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente** - Seleziona l’opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.
* **Sola lettura** - Seleziona l’opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.

### Scheda Convalida {#validation-tab}

![Scheda Convalida](/help/adaptive-forms/assets/radiobutton_validationtab.png)

* **Obbligatorio** - Selezionare questa opzione se si desidera visualizzare il componente in un modulo adattivo. Non è possibile selezionare la **Nascondi componente** o **Disattiva componente**  in **Base** quando questa opzione è selezionata.

* **Messaggio di errore** - Questa opzione consente di inserire un messaggio visualizzato se **Obbligatorio** è selezionata e il campo modulo viene lasciato vuoto.

* **Messaggio di convalida script** - Questa opzione consente di inserire un messaggio da visualizzare in caso di errore di convalida dello script.

### Scheda Contenuto dell’Aiuto {#helpcontent-tab}

![Scheda Contenuto della guida](/help/adaptive-forms/assets/radiobutton_helptab.png)

* **Breve descrizione** - Una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita la **Mostra sempre una breve descrizione** per visualizzarlo sotto il componente.

* **Mostra sempre una breve descrizione** - Abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo della Guida** - Il testo della Guida si riferisce a informazioni o indicazioni aggiuntive fornite all&#39;utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’Aiuto (i) posta accanto al componente. Il testo della Guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità](/help/adaptive-forms/assets/radiobutton_accessibilitytab.png)

* **Testo per assistenti vocali** - Il testo per gli assistenti vocali si riferisce al testo aggiuntivo destinato specificamente alla lettura da parte di tecnologie per l’accessibilità, come gli assistenti vocali, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome ed eventuali messaggi pertinenti del campo (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di tutti gli utenti, compresi quelli con problemi visivi, e di comprendere appieno il campo del modulo e i relativi requisiti.


## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per il componente Pulsante di scelta.


### Scheda Stili {#styles-tab}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per un componente. Il componente core del pulsante di scelta adattivo Forms supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

**Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente core del pulsante di scelta Adattivo Forms.

**Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.