---
title: 'Componente core Forms adattivo: schede verticali'
description: Utilizzo o personalizzazione del componente core Schede verticali di Forms adattivo.
role: Architect, Developer, Admin, User
exl-id: d5cd1c18-6840-4f2f-a767-a69b803e6075
source-git-commit: a567b5ad937d426abe16c34e039e19cd0b1af5b0
workflow-type: tm+mt
source-wordcount: '1927'
ht-degree: 65%

---

# Schede verticali {#vertical-tabs-adaptive-forms-core-component}

Le schede verticali in un modulo adattivo si riferiscono a un motivo di progettazione in cui più sezioni di un modulo sono raggruppate e visualizzate come schede separate, allineate verticalmente. L’utente può passare da una scheda all’altra per accedere a diverse sezioni del modulo. Ogni scheda funge da attivatore per mostrare e nascondere il relativo contenuto del modulo. Le schede verticali consentono di organizzare i moduli lunghi in sezioni gestibili e di migliorare l’esperienza di utilizzo. Le schede possono essere utili per rendere un modulo più accessibile agli utenti con disabilità, consentendo di passare da una sezione all’altra tramite la navigazione con tastiera.

Facendo clic su una scheda, il contenuto del modulo si aggiorna dinamicamente mostrando la sezione corrispondente.

![esempio](/help/adaptive-forms/assets/horizontal-example.png)

## Utilizzo {#reasons-to-use-vertical-tabs}

I motivi comuni per l’utilizzo di schede verticali in un modulo adattivo sono:

- **Maggiore fruibilità**: le schede verticali consentono agli utenti di spostarsi più facilmente all’interno del modulo, soprattutto se il modulo include più sezioni o un numero elevato di campi.

- **Gestione dello spazio**: le schede verticali consentono di risparmiare spazio sullo schermo raggruppando in schede le sezioni del modulo correlate e visualizzandone una sola alla volta.

- **Organizzazione migliore**: le schede forniscono una struttura chiara e organizzata per un modulo, semplificandone la comprensione e la compilazione.

- **Maggiore coinvolgimento degli utenti**: le schede verticali possono rendere un modulo più attraente e coinvolgente per gli utenti, migliorando così il tasso di completamento del modulo.

## Versione e compatibilità {#version-and-compatibility}

Il componente core Schede verticali di Forms adattivo è stato rilasciato come parte dei Componenti core 2.0.18. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla relativa documentazione:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile con<br>[versione 2.0.18](/help/versions.md) e successive | Compatibile | Compatibile |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md).

## Dettagli tecnici {#technical-details}

Scopri le informazioni più recenti sulle schede verticali del Forms adattivo Componente core nella documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/verticaltabs/v1/verticaltabs). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).


## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza con le schede Verticali per i visitatori con la finestra di dialogo per configurazione. Puoi anche definire le opzioni delle schede Verticali in modo semplice, per un’esperienza utente fluida.

### Scheda Base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/vertical-tab-basic.png)

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

- **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, offrendo agli utenti un’esperienza utente semplice per la raccolta e la gestione dei dati.
- **Nascondi componente**: seleziona questa opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
- **Disattiva componente**: seleziona questa opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

### Ripeti scheda verticale {#repeat-tabs-on-top}

![Scheda Ripeti](/help/adaptive-forms/assets/vertical-tab-repeat-vertical-tab.png)

È possibile utilizzare le opzioni di ripetibilità per duplicare il componente Schede verticali e i relativi componenti figlio, definire un conteggio di ripetizioni minimo e massimo e facilitare la replica di sezioni simili all&#39;interno di un modulo. Quando si interagisce con il componente Vertical-tabs e si accede alle relative impostazioni, vengono visualizzate le seguenti opzioni:

- **Rendi le tabulazioni verticali ripetibili**: funzione di attivazione/disattivazione che consente agli utenti di abilitare o disabilitare la funzionalità di ripetibilità.
- **Numero minimo di ripetizioni**: stabilisce il numero minimo di volte in cui il componente Schede verticali può essere ripetuto. Il valore zero indica che il componente Vertical-tabs non è ripetuto. Il valore predefinito è zero.
- **Numero massimo di ripetizioni**: imposta il numero massimo di ripetizioni del componente Schede verticali. Per impostazione predefinita, questo valore è illimitato.

Per gestire in modo efficace le sezioni ripetibili all’interno delle schede Verticali, segui i passaggi descritti in [Creazione di moduli con sezioni ripetibili](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html?lang=it) articolo.

### Scheda Elementi {#items-tab}

![Scheda Elementi](/help/adaptive-forms/assets/vertical-tab-items.png)

Il pulsante **Aggiungi** consente di selezionare un componente da aggiungere come pannello dalla finestra di selezione del componente. Dopo aver aggiunto il componente, puoi vedere le seguenti opzioni:

- **Icona**: l’icona identifica il componente del pannello nell’elenco. Passa il puntatore del mouse sull’icona per visualizzare il nome completo del componente come descrizione comando.
- **Descrizione**: descrizione utilizzata come testo del pannello. Per impostazione predefinita, il nome del componente selezionato per il pannello.
- **Elimina** - Tocca o fai clic per eliminare il pannello dal componente Schede verticali.
- **Ridisponi**: tocca o fai clic e trascina per modificare l’ordine dei pannelli.

### Scheda Contenuto Guida {#help-content}

![Scheda Contenuto Guida](/help/adaptive-forms/assets/vertical-tab-help.png)

- **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

- **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

- **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility}

![Scheda Accessibilità](/help/adaptive-forms/assets/vertical-tab-accessibility.png)

- **Testo per utilità per la lettura dello schermo**: il testo per le utilità per la lettura dello schermo si riferisce al testo aggiuntivo destinato specificamente ad essere letto da tecnologie di assistenza, come le utilità per la lettura dello schermo, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.

- **Ruolo di HTML per l’annuncio dell’assistente vocale**: il ruolo HTML è un attributo utilizzato per specificare lo scopo di un elemento HTML per tecnologie di assistenza come le utilità per la lettura dello schermo. L’attributo ruolo viene utilizzato per fornire ulteriore contesto e significato semantico a un elemento, facilitando l’interpretazione e la lettura del contenuto da parte delle utilità per la lettura dello schermo per l’utente. Ad esempio, in AEM Forms, l’etichetta di un campo modulo potrebbe avere il ruolo di “etichetta” e il relativo campo di input potrebbe avere il ruolo di “casella di testo”. Questo permette all’assistente vocale di comprendere la relazione tra l’etichetta e il campo di input, e di leggerli in modo corretto all’utente.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente ai creatori di modelli di controllare la modalità di visualizzazione predefinita degli elementi. Per il componente Schede verticali di Forms adattivo, potete impostare quanto segue:

- Componenti core che un creatore di moduli può aggiungere alle schede Verticali nell’editor di Forms adattivo
- Nomi semplici per gli stili (classi CSS) che possono essere applicati nella finestra di dialogo delle proprietà del componente Schede verticali nell’editor di Forms adattivo.

Questo permette di rendere il processo di creazione e personalizzazione dei moduli più semplice ed efficace.

### Scheda Componenti Consentiti {#allowed-components-tab}

![Scheda Componenti consentiti](/help/adaptive-forms/assets/tabs-allowed-component.png)

Il **Componenti consentiti** Questa scheda consente all’editor di modelli di impostare i componenti che possono essere aggiunti come elementi ai pannelli nel componente Schede verticali nell’editor di Forms adattivo.

### Scheda Stili {#styles-tab}

![Scheda Stili](/help/adaptive-forms/assets/tabs-styles-tab.png)

La finestra di dialogo per la progettazione consente di definire e gestire gli stili CSS per un componente. Il componente core Schede verticali del Forms adattivo supporta l’AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

- **Classi CSS predefinite**: puoi fornire una classe CSS predefinita per il componente core Schede verticali di Forms adattivo.

- **Stili consentiti**: è possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di moduli adattivi. Per applicare uno stile, nell’editor dei moduli adattivi, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

### Scheda Proprietà personalizzate

![Scheda Proprietà personalizzate](/help/adaptive-forms/assets/tabs-custom-properties.png)

Le proprietà personalizzate consentono di associare attributi personalizzati (coppie chiave-valore) a un componente core Modulo adattivo utilizzando il modello di modulo. Le proprietà personalizzate si riflettono nella sezione delle proprietà della rappresentazione headless del componente. Consente di creare un comportamento di modulo dinamico che si adatta in base ai valori degli attributi personalizzati. Ad esempio, gli sviluppatori possono progettare varie rappresentazioni di un componente Forms headless per piattaforme mobili, desktop o web, migliorando in modo significativo l’esperienza utente su un’ampia gamma di dispositivi.

- **Nome gruppo**: puoi fornire un nome per identificare il gruppo di proprietà personalizzato. È possibile aggiungere, eliminare o ridisporre più gruppi di proprietà personalizzate. Dopo aver aggiunto il gruppo di proprietà personalizzato, puoi visualizzare le seguenti opzioni:

   - **Coppie chiave-valore**: puoi aggiungere più nomi di proprietà personalizzate e valori di proprietà personalizzate facendo clic sul pulsante **Aggiungi** per ogni gruppo di proprietà personalizzate.

   - **Elimina**: tocca o fai clic per eliminare il nome e il valore della proprietà personalizzata.

   - **Ridisponi**: tocca o fai clic e trascina per modificare l’ordine del nome della proprietà personalizzata e del valore della proprietà personalizzata.

## Articoli correlati {#related-articles}

{{more-like-this}}

## Consulta anche {#see-also}

{{see-also}}
