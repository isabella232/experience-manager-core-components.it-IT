---
title: Frammento di modulo adattivo
description: Utilizza i frammenti di modulo per creare segmenti di modulo o gruppi di campi e riutilizzarli in Adaptive Forms per migliorarne l’efficienza e la riutilizzabilità.
role: Architect, Developer, Admin, User
source-git-commit: 6f83e843b95689bad2cfb31bd53c20b135d789d5
workflow-type: tm+mt
source-wordcount: '1675'
ht-degree: 65%

---


# Componente Frammento modulo {#form-fragment-component-adaptive-forms-core-component}

Forms adattivo offre un modo pratico per creare segmenti di moduli, come pannelli o gruppi di campi, in modo che possano essere riutilizzati in diversi Forms adattivi. Questi segmenti riutilizzabili e autonomi sono denominati [Frammenti di moduli adattivi](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/adaptive-form-fragments-core-components.html).

È possibile [aggiungere più volte un frammento a un documento](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/adaptive-form-fragments-core-components.html#insert-a-fragment-in-an-adaptive-form) e utilizzare le proprietà di associazione dati dei relativi componenti per collegarli a diverse origini dati o schemi. Ad esempio, puoi utilizzare lo stesso frammento di indirizzo per un indirizzo permanente, di comunicazione e di fatturazione e collegarlo a campi diversi di un’origine dati o di uno schema.

![esempio](/help/adaptive-forms/assets/using-multiple-fragment-af.gif)


È inoltre possibile utilizzare [opzione di ripetibilità](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html?lang=it) per duplicare il componente frammento di modulo e i relativi componenti figlio, definisci un conteggio di ripetizioni minimo e massimo e semplifica la replica di sezioni simili all’interno di un modulo.

>[!NOTE]
>
> È possibile [creare un frammento di modulo adattivo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/adaptive-form-fragments-core-components.html#create-a-fragment) da zero o salva un pannello in un modulo adattivo esistente come frammento.

## Utilizzo {#usage}

- **Riutilizzabilità**: la possibilità di riutilizzare i frammenti di modulo su più Forms adattivi è il vantaggio principale dell’utilizzo dei frammenti di modulo. Aiuta a mantenere coerenza a livello di progettazione e funzionalità, in quanto le modifiche apportate a un frammento si riflettono in tutte le istanze in cui viene utilizzato.

- **Esperienza utente coerente**: l’utilizzo di frammenti di modulo per elementi comuni, ad esempio intestazioni o piè di pagina, garantisce un’esperienza utente coerente.

- **Manutenzione semplice**: le modifiche o le modifiche apportate a un frammento di modulo si riflettono in tutte le istanze in cui viene utilizzato. Semplifica la manutenzione e riduce le possibilità di errori.

- **Efficienza**: designer e sviluppatori risparmiano tempo creando e testando i frammenti di modulo una sola volta. I frammenti di modulo possono quindi essere facilmente incorporati in più Forms adattivi senza la necessità di un lavoro ridondante.

## Versione e compatibilità {#version-and-compatibility}

Il componente core Frammento Forms adattivo è stato rilasciato come parte dei Componenti core 2.0.50 per Cloud Service e Componenti core 1.1.26 per AEM 6.5.16.0 Forms o versione successiva. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM Forms 6.5.16.0 o versioni successive |
|---|---|---|
| v1 | Compatibile con <br>[versione 2.0.50](/help/adaptive-forms/version.md) e successive | Compatibile con<br>[versione 1.1.26](/help/adaptive-forms/version.md) e più tardi ma inferiore a 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente core Frammento adattivo di Forms, consulta la documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/fragment). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del frammento per i visitatori con la finestra di dialogo per configurazione. Puoi anche definire facilmente le proprietà dei frammenti per un’esperienza utente fluida.

### Scheda Base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/fragment-basictab.png)

- **Nome**: è possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

- **Titolo**: con il relativo titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungi un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

- **Nascondi titolo**: seleziona l’opzione per nascondere il titolo del componente.

- **Raggruppa dati dei componenti secondari all’invio del modulo (racchiudi dati nell’oggetto)**: quando questa opzione è selezionata, i dati dei relativi componenti secondari sono nidificati all’interno dell’oggetto JSON del componente principale. Tuttavia, se l’opzione non è selezionata, i dati JSON inviati hanno una struttura semplice, senza alcun oggetto per il componente principale. Ad esempio:

   - Quando l’opzione è selezionata, i dati dei componenti secondari (ad esempio, Via, Città e CAP) vengono nidificati all’interno del componente principale (Indirizzo) come oggetto JSON. In questo modo viene creata una struttura gerarchica e i dati vengono organizzati sotto il componente principale.

     Struttura dei dati inviati:

     ```JSON
     { "Address":
     
     { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     
     }
     ```

   - Quando l’opzione non è selezionata, i dati JSON inviati hanno una struttura semplice senza alcun oggetto per il componente principale (Indirizzo). Tutti i dati si trovano allo stesso livello, senza alcuna organizzazione gerarchica.


     Struttura dei dati inviati:

     ```JSON
        { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     ```

- **Riferimento frammento** - Un riferimento frammento è un riferimento a un frammento di modulo memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento frammento consente di associare dinamicamente il frammento di modulo a un modulo.

- **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, offrendo agli utenti un’esperienza utente semplice per la raccolta e la gestione dei dati.

- **Nascondi componente**: seleziona questa opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
- **Disattiva componente**: seleziona questa opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.
- **Sola lettura**: seleziona questa opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

### Scheda Ripeti frammento {#repeat-tab}

![Scheda Ripeti frammento](/help/adaptive-forms/assets/fragment-repeattab.png)

- **Rendi il frammento ripetibile**: funzione di attivazione/disattivazione che consente agli utenti di abilitare o disabilitare la funzionalità di ripetibilità.
- **Numero minimo di ripetizioni**: stabilisce il numero minimo di volte in cui il componente frammento può essere ripetuto. Il valore zero indica che il componente frammento non viene ripetuto; il valore predefinito è zero.
- **Numero massimo di ripetizioni**: imposta il numero massimo di ripetizioni del componente del frammento. Per impostazione predefinita, questo valore è illimitato.

### Scheda Contenuto Guida {#help-content}

![Scheda Contenuto Guida](/help/adaptive-forms/assets/fragment-helptab.png)

- **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

- **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

- **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Accessibilità {#accessibility}

![Scheda Accessibilità](/help/adaptive-forms/assets/fragment-accessibilitytab.png)

- **Testo per utilità per la lettura dello schermo**: il testo per le utilità per la lettura dello schermo si riferisce al testo aggiuntivo destinato specificamente ad essere letto da tecnologie di assistenza, come le utilità per la lettura dello schermo, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per progettazione viene utilizzata per definire e gestire gli stili CSS per il componente Frammento di modulo.

### Scheda Stili {#styles-tab}

Il componente core Frammento modulo adattivo supporta l’AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

![Finestra di dialogo per la progettazione](/help/adaptive-forms/assets/checkbox-style.png)

- **Classi CSS predefinite**: puoi fornire una classe CSS predefinita per il componente core Frammento modulo adattivo.

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






