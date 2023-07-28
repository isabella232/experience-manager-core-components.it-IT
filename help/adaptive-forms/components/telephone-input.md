---
title: Componente core moduli adattivi - Inserimento numero di telefono
description: Utilizzo o personalizzazione del componente core per l’inserimento del numero di telefono nei moduli adattivi.
role: Architect, Developer, Admin, User
exl-id: d06179ac-04bd-4af4-b6ac-c4c78086058c
source-git-commit: 7888cfa0f1358ce8018fc1e3cc3b19eb66a82b9d
workflow-type: ht
source-wordcount: '1757'
ht-degree: 100%

---

# Inserimento telefono {#telephone-input-adaptive-forms-core-component}

Il componente core per l’inserimento del numero di telefono in un modulo adattivo consente agli utenti di inserire un numero di telefono. Nel campo del numero di telefono, se utilizziamo dispositivi mobili, sono visualizzate le tastiere per inserire il numero di telefono. Il campo può essere personalizzato con attributi aggiuntivi quali “pattern” e “segnaposto” per specificare il formato e la descrizione del numero di telefono.

Il campo del numero di telefono viene comunemente utilizzato nei moduli di contatto, nei moduli di registrazione e in altri moduli in cui è richiesto un numero telefonico come mezzo di contatto. Il campo del numero di telefono può essere utilizzato anche per garantire che l’utente immetta un numero di telefono valido, in quanto il browser può applicare determinati vincoli, come la lunghezza e il formato del numero di telefono, in base all’attributo “pattern”.

## Utilizzo {#reasons-to-use-telephone-input}

I motivi comuni per cui si utilizza un campo per il numero di telefono in un modulo adattivo sono i seguenti:

* **Informazioni di contatto**: un campo per il numero di telefono viene comunemente utilizzato per memorizzare il numero di telefono di un utente come mezzo di contatto.

* **Maggiore accuratezza dei dati**: utilizzando un campo per il numero di telefono, il modulo può imporre determinati vincoli al formato del numero di telefono, il che può contribuire a garantire che i dati immessi siano accurati e completi.

* **Esperienza utente migliorata**: un campo per il numero di telefono offre agli utenti un modo chiaro e intuitivo di inserire il proprio numero di telefono e può migliorare l’esperienza dell’utente consentendo agli utenti di inserire rapidamente e facilmente le informazioni di contatto.

## Versione e compatibilità {#version-and-compatibility}

Il componente core Pannello a soffietto moduli adattativi è stato rilasciato a febbraio 2023 come parte dei Componenti core 2.0.4 per Cloud Service e i Componenti core 1.1.12 per AEM Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM Forms 6.5.16.0 o versioni successive |
|---|---|---|
| v1 | Compatibile con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successive | Compatibile con <br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive, ma precedenti a 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente core per l’immissione del numero di telefono nei moduli adattivi, consulta la documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/telephoneinput/v1/telephoneinput). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza di immissione del numero di telefono dei visitatori tramite la finestra di dialogo per la configurazione. È inoltre possibile definire le opzioni di immissione del numero di telefono in modo semplice per un’esperienza utente perfetta.

![Scheda Base](/help/adaptive-forms/assets/telephoneinput_basictab.png)

* **Nome**: è possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo**: con il relativo titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungi un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo**: seleziona l’opzione per nascondere il titolo del componente.

* **Testo segnaposto**: il testo segnaposto in un componente modulo si riferisce a un’etichetta o a un prompt brevi che vengono visualizzati all’interno di un campo di inserimento come suggerimento per l’utente sul tipo di informazioni che ci si aspetta venga immesso in quel campo. Il testo segnaposto scompare quando l’utente inizia a digitare nel campo e viene visualizzato nuovamente se il campo viene lasciato vuoto. Fornisce un suggerimento visivo all’utente, ma non funge da etichetta o valore permanente per il campo.

* **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente fluida per la raccolta e la gestione dei dati.

* **Nascondi componente**: seleziona l’opzione per nascondere il componente del modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.

* **Disattiva componente**: seleziona questa opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

* **Sola lettura**: seleziona questa opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

* **Valore predefinito** - questa opzione consente di aggiungere un valore predefinito in un campo modulo. Se **Componente disabilitato** o **Componente di sola lettura** è selezionato, il valore predefinito viene visualizzato sullo schermo. Se l’utente non immette alcun valore nel campo modulo, questo valore viene inviato al momento dell’invio del modulo.

### Scheda Convalida {#validation-tab}

![Scheda Convalida](/help/adaptive-forms/assets/telephoneinput_validationtab.png)

* **Obbligatorio**: seleziona questa opzione se desideri visualizzare il componente in un modulo adattivo. Non è possibile selezionare **Nascondi componente** o **Disattiva componente** nella scheda **Base** quando questa opzione è selezionata.

* **Messaggio di errore**: questa opzione consente di inserire un messaggio visualizzato se la casella di controllo **Obbligatorio** è selezionata e il campo viene lasciato vuoto.

* **Messaggio di convalida script**: questa opzione consente di inserire un messaggio da visualizzare in caso di errore di convalida dello script.

* **Numero massimo di caratteri**: questa opzione consente di specificare il numero massimo di caratteri consentiti nel componente. Se immetti più caratteri del valore specificato in **Numero massimo di caratteri**, sullo schermo viene visualizzato un messaggio di errore. La finestra di dialogo **Messaggio di errore relativo al numero massimo di caratteri** consente di aggiungere un messaggio di errore personalizzato.

* **Messaggio di errore relativo al numero massimo di caratteri**: la finestra di dialogo **Messaggio di errore relativo al numero massimo di caratteri** ti permette di aggiungere un messaggio di errore personalizzato se si immettono caratteri superiori al valore specificato nell’opzione **Numero massimo di caratteri**.

* **Numero minimo di caratteri**: questa opzione ti consente di specificare il numero minimo di caratteri consentiti nel campo. Se immetti caratteri inferiori al valore specificato in **Numero minimo di caratteri**, sullo schermo viene visualizzato un messaggio di errore. La finestra di testo **Messaggio di errore relativo al numero minimo caratteri** consente di aggiungere un messaggio di errore personalizzato.

* *Messaggio di errore relativo al numero minimo dei caratteri**: la finestra di dialogo **Messaggio di errore relativo al numero minimo dei caratteri** consente di aggiungere un messaggio di errore personalizzato se inserisci meno caratteri rispetto al valore specificato nell’opzione **Numero minimo di caratteri**.

L’opzione **Pattern di convalida** consente di inserire un pattern per convalidare il numero di telefono inserito. Il numero di telefono inserito viene convalidato in base al valore inserito nell’opzione **Pattern**. Nel caso in cui il numero di telefono non venga convalidato con il valore inserito nell’opzione **Pattern**, il messaggio di errore viene visualizzato sullo schermo.

* **Pattern**: questa opzione consente di inserire i pattern di verifica consentiti per il numero di telefono. Sono consentite anche espressioni regolari.

* **Messaggio di errore**: questa opzione consente di inserire un messaggio visualizzato sullo schermo se il numero di telefono inserito non viene convalidato con il valore inserito nell’opzione **Pattern**.

### Scheda Contenuto Guida {#help-content-tab}

![Scheda Contenuto Guida](/help/adaptive-forms/assets/telephoneinput_helptab.png)

* **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

* **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità](/help/adaptive-forms/assets/telephoneinput_accessibilitytab.png)

**Testo per utilità per la lettura dello schermo**: il testo per le utilità per la lettura dello schermo si riferisce al testo aggiuntivo destinato specificamente ad essere letto da tecnologie di assistenza, come le utilità per la lettura dello schermo, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente di definire e gestire gli stili CSS per il componente di inserimento del numero di telefono.

### Scheda Stili {#styles-tab}

La scheda è utilizzata per definire e gestire gli stili CSS per un componente. Il componente core per l’inserimento del numero di telefono nei moduli adattivi supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

![Finestra di dialogo per la progettazione](/help/adaptive-forms/assets/telephoneinput_designdialog.png)

* **Classi CSS predefinite**: è possibile fornire una classe CSS predefinita per il componente core di inserimento del numero di telefono nei moduli adattivi.

* **Stili consentiti**: è possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di moduli adattivi. Per applicare uno stile, nell’editor dei moduli adattivi, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

### Scheda Formati {#format-tab}

La scheda dei formati consente di specificare i formati numerici predefiniti e personalizzati.

![Scheda Formato](/help/adaptive-forms/assets/telephoneinput_format.png)

## Articolo correlato {#related-article}

* [Creare un modulo adattivo in una pagina AEM Sites o in un frammento di esperienza](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=it)

* [Creare un modulo adattivo indipendente](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=it)
