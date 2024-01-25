---
title: 'Componente core Forms adattivo: componente switch'
description: Utilizzo o personalizzazione del componente core Switch Forms adattivo.
role: Architect, Developer, Admin, User
hide: true
hidefromToC: true
source-git-commit: d172e019c5621d950a94cbdd8d27e4834dbabe3b
workflow-type: tm+mt
source-wordcount: '1689'
ht-degree: 67%

---


# Cambia componente{#switch-adaptive-forms-core-component}

Il componente switch è un’interfaccia utente grafica utilizzata nei moduli che consente agli utenti di scegliere tra due opzioni. In genere si tratta di un interruttore a due stati che consente agli utenti di scegliere tra due stati, abilitando o disabilitando una funzione, un&#39;impostazione o una funzionalità. Il componente switch è progettato per rappresentare visivamente lo stato corrente e indicare se una particolare funzione è attivata o disattivata.

Il componente switch è un elemento di controllo booleano che imposta il valore su true o false. Ad esempio, viene utilizzato per attivare o disattivare una funzione, ad esempio l&#39;audio disattivato o disattivato, o per abilitare o disabilitare Bluetooth o WiFi.

![Esempio di switch component](/help/adaptive-forms/assets/switch-example.png)

## Utilizzo {#reasons-to-use-switch}

I motivi comuni per utilizzare il passaggio in un modulo adattivo sono:

- **Interazione dell’utente**: gli utenti possono interagire con il componente switch facendo clic o toccando su di esso.

- **Stati**: il componente switch ha due stati: ON e OFF. Lo stato iniziale del componente switch dipende dall&#39;impostazione di default o dallo stato corrente della feature che controlla.

- **Rappresentazione visiva**: il componente switch riflette visivamente il suo stato corrente cambiando il colore o la posizione.

- **Funzionalità di controllo**: il componente switch viene utilizzato per abilitare o disabilitare funzionalità specifiche in un modulo AEM. Ad esempio, consente agli utenti di attivare o disattivare una funzione.

## Versione e compatibilità {#version-and-compatibility}

Il componente core Switch Forms adattivo è stato rilasciato come parte dei Componenti core 2.0.64. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla relativa documentazione:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile con <br>[versione 2.0.64](/help/adaptive-forms/version.md) e successive | Compatibile | Compatibile |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente core per switch Forms adattivo, consulta la documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/switch/v1/switch). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente di personalizzare facilmente l’esperienza del componente Switch per i visitatori. È inoltre possibile definire facilmente le opzioni dei componenti Switch per garantire un&#39;esperienza utente ottimale.

### Scheda Base

![Scheda Base](/help/adaptive-forms/assets/switch-basic.png)

- **Nome**: è possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

- **Titolo**: puoi identificare facilmente un componente in un modulo con il suo nome e, per impostazione predefinita, il titolo viene visualizzato accanto al componente. Se non aggiungi un titolo, il componente non viene visualizzato.

- **Nascondi titolo**: seleziona l’opzione per nascondere il titolo del componente.

- **Mantieni valore stato deselezionato** - Selezionando questa opzione è possibile specificare il valore da restituire quando il componente switch non è selezionato.
- **Opzioni** : specifica il valore dei dati e visualizza il testo per ciascuna opzione.
   - **Su valore dati** - Specifica il valore da inviare quando il passaggio è abilitato in un modulo adattivo.
   - **Testo visualizzato** - Specificare il testo da visualizzare come etichetta quando il parametro è abilitato in un modulo adattivo.
   - **Valore dati disattivato** - Specifica il valore da inviare quando il passaggio non è abilitato in un modulo adattivo. Questa opzione è visibile solo se **Mantieni valore stato deselezionato** è attivato.
   - **Testo non visualizzato** - Specificare il testo da visualizzare come etichetta quando il parametro non è abilitato in un modulo adattivo. Questa opzione è visibile solo se **Mantieni valore stato deselezionato** è attivato.

- **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, offrendo agli utenti un’esperienza utente semplice per la raccolta e la gestione dei dati.
- **Contrassegna come elemento modulo non associato**: seleziona l’opzione per configurare un campo modulo non collegato ad alcun schema. Questa opzione consente di salvare i dati senza aggiornare l’origine dati. Consente inoltre di gestire i dati in modo personalizzato, separato dall’integrazione standard del database.

- **Tipo di dati del valore inviato**: questa opzione specifica il tipo di dati del valore inviato quando viene selezionata un’opzione. Se il **tipo di dati del valore inviato** è impostato su `Number` e si aggiungono dati stringa al **Valore dati** nella scheda **Opzioni**, nella schermata viene visualizzato il messaggio di errore `Value type mismatch`.
- **Nascondi componente**: seleziona questa opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.

- **Disattiva componente**: seleziona l’opzione per disabilitare o bloccare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

- **Valore predefinito**: questa opzione consente di aggiungere un valore predefinito in un campo del modulo. Se sono selezionati il **Componente disabilitato** o il **Componente di sola lettura**, il valore predefinito viene visualizzato sullo schermo. Se l’utente non immette alcun valore nel campo modulo, questo valore viene inviato al momento dell’invio del modulo.

### Scheda Convalida {#validation-tab}

![Scheda Convalida](/help/adaptive-forms/assets/switch-validation.png)

- **Obbligatorio**: seleziona questa opzione se desideri visualizzare il componente in un modulo adattivo. Dopo aver selezionato l’opzione, è necessario effettuare una selezione prima di procedere con l’invio di un modulo. Non è possibile selezionare **Nascondi componente** o **Disattiva componente** nella scheda **Base** quando questa opzione è selezionata.

- **Messaggio di errore**: questa opzione consente di inserire un messaggio visualizzato se la casella di controllo **Obbligatorio** è selezionata e il campo modulo viene lasciato vuoto.

- **Messaggio di convalida script**: questa opzione consente di inserire un messaggio da visualizzare in caso di mancata convalida dello script.

### Scheda Contenuto Guida {#helpcontent-tab}

![Scheda Contenuto Guida](/help/adaptive-forms/assets/switch-help.png)

- **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

- **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

- **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità](/help/adaptive-forms/assets/switch-accessibility.png)

**Testo per utilità per la lettura dello schermo**: il testo per le utilità per la lettura dello schermo indica il testo aggiuntivo destinato alla lettura da parte di tecnologie per l’accessibilità, come le utilità per la lettura dello schermo, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.

### Scheda Stili {#styles-tab}

![Scheda Stili](/help/adaptive-forms/assets/switch-styles.png)

- **Nascondi etichette** - Selezionare questa opzione per nascondere le etichette del componente switch.

- **Mostra etichette** - Selezionare questa opzione per visualizzare le etichette del componente switch.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per progettazione viene utilizzata per definire e gestire gli stili CSS per il componente Switch.

### Scheda Stili {#styles-design-tab}

Il componente core Switch Forms adattivo supporta l’AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

![Finestra di dialogo per la progettazione](/help/adaptive-forms/assets/checkbox-style.png)

- **Classi CSS predefinite**: puoi fornire una classe CSS predefinita per il componente core gruppo di switch Forms adattivo.

- **Stili consentiti**: è possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di moduli adattivi. Per applicare uno stile, nell’editor dei moduli adattivi, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

### Proprietà personalizzate

![Finestra di dialogo Proprietà personalizzate](/help/adaptive-forms/assets/checkbox-customproperties.png)

Le proprietà personalizzate consentono di associare attributi personalizzati (coppie chiave-valore) a un componente core Modulo adattivo utilizzando il modello di modulo. Le proprietà personalizzate vengono riflesse nella sezione delle proprietà della rappresentazione headless del componente. Consentono di creare un comportamento di modulo dinamico che si adatta in base ai valori degli attributi personalizzati. Ad esempio, gli sviluppatori possono progettare diverse rappresentazioni di un componente moduli headless su piattaforme mobili, desktop o web, migliorando in modo significativo l’esperienza utente su un’ampia gamma di dispositivi.

- **Nome gruppo**: puoi fornire un nome per identificare il gruppo di proprietà personalizzate. È possibile aggiungere, eliminare o ridisporre più gruppi di proprietà personalizzate. Dopo aver aggiunto il gruppo di proprietà personalizzate, puoi visualizzare le seguenti opzioni:

   - **Coppie chiave-valore**: puoi aggiungere più nomi e valori della proprietà personalizzata facendo clic sul pulsante **Aggiungi** per ogni gruppo di proprietà personalizzate.

   - **Elimina**: tocca o fai clic per eliminare il nome e il valore della proprietà personalizzata.

   - **Ridisponi**: tocca o fai clic e trascina per modificare il nome della proprietà personalizzata e il valore della proprietà personalizzata.

## Articoli correlati {#related-articles}

{{more-like-this}}

## Consulta anche {#see-also}

{{see-also}}









