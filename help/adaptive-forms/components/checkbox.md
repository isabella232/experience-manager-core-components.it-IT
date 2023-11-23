---
title: 'Componente core Forms adattivo: casella di controllo'
description: Utilizzo o personalizzazione del componente core Casella di controllo Forms adattivo.
role: Architect, Developer, Admin, User
hide: true
hidefromtoc: true
source-git-commit: ecc6ba79ba5e90bd6e759353d15ca85ce404d769
workflow-type: tm+mt
source-wordcount: '1708'
ht-degree: 53%

---


# Casella di selezione {#checkbox-component}

Una casella di controllo è un elemento dell&#39;interfaccia utente grafico comunemente utilizzato nelle applicazioni software e nei moduli per consentire agli utenti di effettuare una scelta binaria tra due opzioni: selezionata (selezionata) o deselezionata (deselezionata).

Una casella di controllo viene generalmente rappresentata come un piccolo quadratino che può essere attivato o disattivato facendo clic o toccando. Quando viene selezionata una casella di controllo, viene visualizzato un segno di spunta per indicare che l&#39;opzione o la funzionalità associata è attiva o abilitata.

**Esempio**

![gruppo di caselle di controllo](/help/adaptive-forms/assets/checkbox-example.png)

## Utilizzo {#reasons-to-use-checkbox}

I motivi comuni per cui si utilizza la casella di controllo in un modulo adattivo sono:

- **Facilità d&#39;uso**: le caselle di controllo sono chiare a livello visivo e forniscono un modo semplice per effettuare scelte binarie. Sono intuitivi e facili da comprendere, grazie alla facilità d&#39;uso.

- **Consenso e accordo**: le caselle di controllo vengono utilizzate per ottenere il consenso dell’utente per vari scopi, ad esempio accettare termini e condizioni, abbonarsi alle newsletter o confermare la verifica dell’età. Indicano chiaramente che l’utente accetta attivamente qualcosa.

- **Conferma visiva**: le caselle di controllo selezionate forniscono agli utenti una conferma visiva che la selezione è stata registrata. Questo feedback aiuta a prevenire gli errori degli utenti e garantisce che sappiano che le loro scelte sono state registrate.

- **Prevenzione degli errori**: le caselle di controllo riducono la probabilità di errori consentendo agli utenti di rivedere e confermare le scelte prima dell’invio del modulo.

## Versione e compatibilità {#version-and-compatibility}

Il componente core Casella di controllo Forms adattivo è stato rilasciato a febbraio 2023 come parte dei Componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla relativa documentazione:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile con<br>[versione 2.0.4](/help/versions.md) e successive | Compatibile | Compatibile |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md).

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente core Casella di controllo di Forms adattivo, consulta la documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/checkbox/v1/checkbox). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza con la Casella di controllo per i visitatori tramite la finestra di dialogo per configurazione. Puoi anche definire le opzioni della casella di controllo con facilità per un’esperienza utente fluida.

![Scheda Base](/help/adaptive-forms/assets/checkbox-basic.png)

- **Nome**: è possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

- **Titolo** - Con il relativo titolo, è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato accanto al componente. Se non aggiungi un titolo, il componente non viene visualizzato.

- **Nascondi titolo**: seleziona l’opzione per nascondere il titolo del componente.

- **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, offrendo agli utenti un’esperienza utente semplice per la raccolta e la gestione dei dati.

- **Contrassegna come elemento modulo non associato**: seleziona l’opzione per configurare un campo modulo non collegato ad alcun schema. Questa opzione consente di salvare i dati senza aggiornare l&#39;origine dati. Consente inoltre di gestire i dati in modo personalizzato, separato dall’integrazione standard del database.

- **Tipo di dati del valore inviato**: questa opzione specifica il tipo di dati del valore inviato quando viene selezionata un’opzione. Se il **tipo di dati del valore inviato** è impostato su `Number` e si aggiungono dati stringa al **Valore dati** nella scheda **Opzioni**, nella schermata viene visualizzato il messaggio di errore `Value type mismatch`.

- **Nascondi componente**: seleziona questa opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.

- **Disabilita componente** - Seleziona l’opzione per disabilitare o bloccare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.
- **Sola lettura**: seleziona questa opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.
- **Se questa opzione è selezionata, viene restituito un valore** -Selezionare questa opzione per specificare il valore da associare alla casella di controllo quando è selezionata o selezionata. Si tratta dell’azione che si verifica quando si contrassegna o si contrassegna la casella di controllo.
- **Abilita Deseleziona.**- Selezionare l&#39;opzione per abilitare o disabilitare la possibilità di deselezionare una casella di controllo precedentemente selezionata.
   - Se **Abilita Deseleziona** è abilitato o impostato su true, significa che l’utente può selezionare e deselezionare la casella di controllo a propria discrezione. Se necessario, può attivare e disattivare la casella di controllo.

   - Se **Abilita Deseleziona** è disabilitato o impostato su false, significa che una volta selezionata la casella di controllo, l’utente non può deselezionarla.
- **Se questa opzione è deselezionata, viene restituito un valore** : l’opzione ti consente di specificare il valore da associare alla casella di controllo quando si trova in uno stato non selezionato o deselezionato.

- **Valore predefinito**: questa opzione consente di aggiungere un valore predefinito in un campo modulo. Se sono selezionati il **Componente disabilitato** o il **Componente di sola lettura**, il valore predefinito viene visualizzato sullo schermo. Se l’utente non immette alcun valore nel campo modulo, questo valore viene inviato al momento dell’invio del modulo.

### Scheda Convalida {#validation-tab}

![Scheda Convalida](/help/adaptive-forms/assets/checkbox-validation.png)

- **Obbligatorio**: seleziona questa opzione se desideri visualizzare il componente in un modulo adattivo. Dopo aver selezionato l’opzione, è necessario effettuare una selezione prima di procedere con l’invio di un modulo. Non è possibile selezionare **Nascondi componente** o **Disattiva componente** nella scheda **Base** quando questa opzione è selezionata.

- **Messaggio di errore**: questa opzione consente di inserire un messaggio visualizzato se la casella di controllo **Obbligatorio** è selezionata e il campo modulo viene lasciato vuoto.

- **Messaggio di convalida script**: questa opzione consente di inserire un messaggio da visualizzare in caso di mancata convalida dello script.

### Scheda Contenuto Guida {#helpcontent-tab}

![Scheda Contenuto Guida](/help/adaptive-forms/assets/checkbox-help.png)

- **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

- **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

- **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità](/help/adaptive-forms/assets/checkbox-accessibility.png)

**Testo per utilità per la lettura dello schermo**: il testo per le utilità per la lettura dello schermo si riferisce al testo aggiuntivo destinato specificamente ad essere letto da tecnologie di assistenza, come le utilità per la lettura dello schermo, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per progettazione viene utilizzata per definire e gestire gli stili CSS per il componente Casella di controllo.

### Scheda Stili {#styles-tab}

Il componente core Casella di controllo Forms adattivo supporta l’AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

![Finestra di dialogo per la progettazione](/help/adaptive-forms/assets/checkbox-style.png)

- **Classi CSS predefinite**: puoi fornire una classe CSS predefinita per il componente core del gruppo di caselle di selezione dei moduli adattivi.

- **Stili consentiti**: puoi definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di moduli adattivi. Per applicare uno stile, nell’editor dei moduli adattivi, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

### Proprietà personalizzate

![Finestra di dialogo Proprietà personalizzate](/help/adaptive-forms/assets/checkbox-customproperties.png)

Le proprietà personalizzate consentono di associare attributi personalizzati (coppie chiave-valore) a un componente core Modulo adattivo utilizzando il modello di modulo. Le proprietà personalizzate si riflettono nella sezione delle proprietà della rappresentazione headless del componente. Consente di creare un comportamento di modulo dinamico che si adatta in base ai valori degli attributi personalizzati. Ad esempio, gli sviluppatori possono progettare varie rappresentazioni di un componente Forms headless per piattaforme mobili, desktop o web, migliorando in modo significativo l’esperienza utente su un’ampia gamma di dispositivi.

- **Nome gruppo**: puoi fornire un nome per identificare il gruppo di proprietà personalizzato. È possibile aggiungere, eliminare o ridisporre più gruppi di proprietà personalizzate. Dopo aver aggiunto il gruppo di proprietà personalizzato, puoi visualizzare le seguenti opzioni:

   - **Coppie chiave-valore**: puoi aggiungere più nomi di proprietà personalizzate e valori di proprietà personalizzate facendo clic sul pulsante **Aggiungi** per ogni gruppo di proprietà personalizzate.

   - **Elimina**: tocca o fai clic per eliminare il nome e il valore della proprietà personalizzata.

   - **Ridisponi**: tocca o fai clic e trascina per modificare l’ordine del nome della proprietà personalizzata e del valore della proprietà personalizzata.

## Articoli correlati {#related-articles}

{{more-like-this}}

## Consulta anche {#see-also}

{{see-also}}


