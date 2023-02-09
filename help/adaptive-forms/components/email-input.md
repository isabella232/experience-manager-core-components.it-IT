---
title: Componente core Forms adattivo - Ingresso e-mail
description: Utilizzo o personalizzazione del componente di base per l’input e-mail di Forms adattivo.
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '1776'
ht-degree: 1%

---


# Ingresso e-mail {#Email-input-adaptive-forms-core-component}

Il componente di base per l’immissione di e-mail per modulo adattivo viene utilizzato per raccogliere gli indirizzi e-mail degli utenti. Il campo di immissione e-mail consente al browser di verificare che i dati immessi siano in un formato di indirizzo e-mail valido. In genere è rappresentata come casella di testo e presenta convalide dei pattern per accettare solo indirizzi e-mail validi. Il campo di input e-mail può essere ulteriormente personalizzato con attributi aggiuntivi come &quot;required&quot;, &quot;segnaposto&quot; e &quot;pattern&quot; per impostare le convalide per i dati di input.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

Ci sono diversi motivi per cui è utile includere un componente di input e-mail in un modulo adattivo, tra cui:

* **Comodità dell&#39;utente**: Un input e-mail facilita l’immissione dei propri indirizzi e-mail da parte degli utenti, in quanto fornisce un’indicazione chiara dei dati previsti nel campo .

* **Comunicazione personalizzata**: La raccolta degli indirizzi e-mail degli utenti tramite un modulo consente comunicazioni personalizzate, ad esempio l’invio di e-mail di conferma o newsletter.

* **Generazione di lead**: Raccogliendo gli indirizzi e-mail tramite un modulo, le aziende possono creare il proprio elenco e-mail e utilizzarlo per la generazione di lead.

* **Autenticazione utente**: Gli indirizzi e-mail possono essere utilizzati come mezzo di autenticazione per accedere a contenuti o servizi soggetti a restrizioni.

* **Raccolta di feedback**: Un input e-mail in un modulo di feedback consente all&#39;azienda di comunicare con l&#39;utente per un follow-up o un chiarimento sul suo feedback.

## Versione e compatibilità {#version-and-compatibility}

Il componente core per input e-mail adattivo di Forms è stato rilasciato a febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente core per l’input e-mail di Forms adattivo, consulta la documentazione tecnica disponibile in [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/emailinput/v1/emailinput). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente la tua esperienza di input e-mail per i visitatori tramite la finestra di dialogo Configura . Puoi anche definire le opzioni di input e-mail con facilità per un’esperienza utente senza soluzione di continuità.

### Scheda di base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/email_basictab.png)

* **Nome** - Il nome identifica in modo univoco il componente nell&#39;editor delle regole.Le stringhe di nome non consentono l&#39;uso di caratteri e spazi speciali.

* **Titolo** - Con il relativo Titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungete un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo** - Seleziona l’opzione per nascondere il titolo del componente.

* **Testo segnaposto** - Il testo segnaposto in un componente modulo si riferisce a un’etichetta o a un prompt breve che viene visualizzato all’interno di un campo di input come suggerimento per l’utente sul tipo di informazioni che ci si aspetta venga immesso in quel campo. Il testo segnaposto scompare quando l’utente inizia a digitare nel campo e viene visualizzato nuovamente se il campo viene lasciato vuoto. Fornisce un segnale visivo all’utente, ma non agisce come etichetta o valore permanente per il campo.

* **Riferimento a un&#39;associazione** - Un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente semplice per la raccolta e la gestione dei dati.
* **Nascondi componente** - Selezionare l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente** - Seleziona l’opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.
* **Sola lettura** - Seleziona l’opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.

* **Valore predefinito** - Questa opzione consente di aggiungere un valore predefinito in un campo modulo. Se **Componente disabilitato** o **Componente di sola lettura** è selezionato, il valore predefinito viene visualizzato sullo schermo. Se l’utente non immette alcun valore nel campo modulo, questo valore viene inviato al momento dell’invio del modulo


### Scheda Convalida {#validation-tab}

![Scheda Convalida](/help/adaptive-forms/assets/email_validationtab.png)

* **Obbligatorio** - Selezionare questa opzione se si desidera visualizzare il componente in un modulo adattivo. Non è possibile selezionare la **Nascondi componente** o **Disattiva componente**  in **Base** quando questa opzione è selezionata.

* **Messaggio di errore** - Questa opzione consente di inserire un messaggio visualizzato se **Obbligatorio** è selezionata e il campo modulo viene lasciato vuoto.

* **Messaggio di convalida script** - Questa opzione consente di inserire un messaggio da visualizzare in caso di errore di convalida dello script.

* **Numero massimo di caratteri** - Questa opzione consente di specificare il numero massimo di caratteri consentiti nel campo. Se immetti caratteri maggiori del valore specificato in **Numero massimo di caratteri**, sullo schermo viene visualizzato un messaggio di errore. La **Messaggio di errore relativo al numero massimo di caratteri** consente di aggiungere un messaggio di errore personalizzato.

* **Messaggio di errore relativo al numero massimo di caratteri** - **Messaggio di errore relativo al numero massimo di caratteri** se si immettono caratteri superiori al valore specificato nella **Numero massimo di caratteri** opzione .

* **Numero minimo di caratteri** - Questa opzione consente di specificare il numero minimo di caratteri consentiti nel campo. Se immetti caratteri inferiori al valore specificato in **Numero minimo di caratteri**, sullo schermo viene visualizzato un messaggio di errore. La **Messaggio di errore minimo caratteri** consente di aggiungere un messaggio di errore personalizzato.

* **Messaggio di errore minimo caratteri** - **Messaggio di errore minimo caratteri** consente di aggiungere un messaggio di errore personalizzato se si immettono caratteri inferiori al valore specificato nel **Numero minimo di caratteri** opzione .

<br>

    L’opzione **Pattern convalida** ti consente di inserire un pattern per convalidare l’ID e-mail immesso. Se l’ID e-mail non viene convalidato con il valore inserito nell’opzione **Pattern** , sullo schermo viene visualizzato il messaggio di errore.
    * **Pattern** - Questa opzione ti consente di inserire i pattern di verifica consentiti per le e-mail. Sono consentite anche espressioni regolari.
    * **Messaggio di errore** - Questa opzione ti consente di inserire un messaggio che viene visualizzato sullo schermo se l’ID e-mail non riesce a convalidare con il valore immesso nell’opzione **Pattern**

### Scheda Contenuto dell’Aiuto {#help-content-tab}

![Scheda Contenuto della guida](/help/adaptive-forms/assets/email_helptab.png)

* **Breve descrizione** - Una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita la **Mostra sempre una breve descrizione** per visualizzarlo sotto il componente.

* **Mostra sempre una breve descrizione** - Abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo della Guida** - Il testo della Guida si riferisce a informazioni o indicazioni aggiuntive fornite all&#39;utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’Aiuto (i) posta accanto al componente. Il testo della Guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità](/help/adaptive-forms/assets/email_accessibilitytab.png)

Sulla **Accessibilità** scheda , valori impostati per [Accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) etichette per il componente. Sono disponibili varie opzioni per l’utilizzo del testo per l’assistente vocale:

* **Testo per assistenti vocali** - Il testo per gli assistenti vocali si riferisce al testo aggiuntivo destinato specificamente alla lettura da parte di tecnologie per l’accessibilità, come gli assistenti vocali, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome ed eventuali messaggi pertinenti del campo (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di tutti gli utenti, compresi quelli con problemi visivi, e di comprendere appieno il campo del modulo e i relativi requisiti.


   * **Testo personalizzato**: Selezionare questa opzione per utilizzare il testo personalizzato per le etichette di accessibilità ARIA. Selezionando questa opzione viene visualizzata la finestra di dialogo Testo personalizzato. È possibile aggiungere informazioni rilevanti nella finestra di dialogo Testo personalizzato.
   * **Descrizione**: Selezionare questa opzione per utilizzare la descrizione per le etichette di accessibilità ARIA.
   * **Titolo**: Selezionare questa opzione per utilizzare il titolo per le etichette di accessibilità ARIA.
   * **Nome**: Selezionare questa opzione per utilizzare il nome per le etichette di accessibilità ARIA.
   * **Nessuno**: Selezionare questa opzione se non si desidera aggiungere etichette di accessibilità ARIA.


## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo Progettazione viene utilizzata per definire e gestire gli stili CSS per il componente di input E-mail.


### Scheda Stili {#styles-tab}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per un componente. Il componente di base per l’input e-mail di Forms adattivo supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

**Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente core di input e-mail di Forms adattivo.

**Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

### Scheda Formati {#format-tab}

La scheda Formati consente di specificare i formati di data predefiniti e personalizzati.
