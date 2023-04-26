---
title: Pannello a soffietto moduli adattivi
description: Utilizza il pannello a soffietto per organizzare e semplificare un modulo lungo o complesso suddividendolo in sezioni più piccole e gestibili.
role: Architect, Developer, Admin, User
exl-id: 0ed38eee-fc22-4708-82eb-3fb1839b1ff2
source-git-commit: 0cfdc56fe5508e156eee2ae818be311748af7247
workflow-type: ht
source-wordcount: '1677'
ht-degree: 100%

---

# Componente pannello a soffietto {#accordion-component-adaptive-forms-core-component}

Il componente core per pannello a soffietto consente agli utenti di creare sezioni espandibili e comprimibili in un modulo adattivo. Viene spesso utilizzato per organizzare e semplificare moduli lunghi o complessi suddividendoli in sezioni più piccole e gestibili. Ogni sezione di un pannello a soffietto è in genere rappresentata da un’intestazione, su cui l’utente può fare clic per espandere o comprimere il contenuto corrispondente. Il contenuto può essere qualsiasi componente core.

## Utilizzo {#usage}

Ci sono diversi motivi per cui è utile includere un pannello a soffietto in un modulo adattivo, tra cui:

* **Risparmio di spazio**: un pannello a soffietto consente agli utenti di espandere e comprimere le sezioni di un modulo, riducendo la quantità di spazio necessaria per visualizzare tutti i campi del modulo contemporaneamente.

* **Navigazione**: un pannello a soffietto può essere utilizzato per creare una struttura di navigazione gerarchica, facilitando agli utenti la ricerca dei campi modulo necessari.

* **Esperienza utente**: il pannello a soffietto può essere utilizzato per rendere il modulo più semplice da usare, fornendo agli utenti un modo chiaro e intuitivo di accedere ai campi del modulo e compilarli.

* **Moduli lunghi**: il pannello a soffietto è un componente ideale per gestire i moduli lunghi, in quanto consente agli utenti di concentrarsi su una sezione alla volta, anziché cercare di elaborare molte informazioni contemporaneamente.

Puoi utilizzare:

* La [finestra di dialogo per la configurazione](#configure-dialog) specifica le proprietà del componente pannello a soffietto.

* La [Finestra popover Seleziona pannello](#select-panel-popover) definisce l’ordine dei pannelli del pannello a soffietto. Questo consente all’autore di disporre i pannelli nell’ordine in cui dovrebbero essere visualizzati.

* Opzioni dell’autore di un modulo per abilitare o disabilitare determinate funzioni nella [finestra di dialogo di progettazione](#design-dialog). Ad esempio, un autore può scegliere di disattivare alcuni campi o sezioni di un modulo. Queste opzioni consentono all’autore di avere un maggiore controllo sulla struttura e sulle funzionalità del modulo, facilitando la creazione di moduli personalizzati in base alle esigenze specifiche dell’organizzazione.

La finestra di dialogo per la configurazione, la finestra di dialogo per la progettazione e la finestra popover seleziona pannello fanno parte dei componenti core creati per semplificare la creazione dei moduli e fornire un modo efficiente per creare moduli complessi.

## Versione e compatibilità {#version-and-compatibility}

Il componente core Pannello a soffietto moduli adattativi è stato rilasciato a febbraio 2023 come parte dei Componenti core 2.0.4 per Cloud Service e i Componenti core 1.1.12 per AEM Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM Forms 6.5.16.0 o versioni successive |
|---|---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successive | Compatibile con la <br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive ma precedenti alla 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente Pannello a soffietto, consulta la documentazione tecnica disponibile su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/accordion/v1/accordion). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del pannello a soffietto per i visitatori tramite la finestra di dialogo per la configurazione. È inoltre possibile definire elementi del pannello a soffietto, pannelli, comportamento e aspetto con facilità per un’esperienza utente semplice.

### Scheda Base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/accordion_basictab.png)

* **Nome**: è possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo**: con il relativo titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungi un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo**: seleziona l’opzione per nascondere il titolo del componente.

* **Racchiudi i dati in un oggetto**: scegli “Racchiudi i dati in un oggetto” per inserire i dati del campo dalla procedura guidata all’interno di un oggetto JSON. Se non viene scelto, l’invio dati JSON presenta una struttura piatta per i campi della procedura guidata.

* **Layout**: è possibile disporre di un layout fisso (semplice) o flessibile (griglia dinamica) per la procedura guidata. Il layout semplice mantiene tutto fisso in posizione, mentre la griglia dinamica consente di regolare la posizione dei componenti in base alle proprie esigenze. Ad esempio, utilizza la griglia dinamica per allineare “Nome”, “Secondo nome” e “Cognome” in un modulo in un’unica riga.

* **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente fluida per la raccolta e la gestione dei dati.
* **Nascondi componente**: seleziona l’opzione per nascondere il componente del modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente**: seleziona questa opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

### Scheda Elementi {#items-tab}

![Scheda Elementi](/help/adaptive-forms/assets/accordion_itemstab.png)

Il pulsante Aggiungi consente di selezionare un componente da aggiungere come pannello dalla finestra di selezione del componente. Dopo aver aggiunto il componente, puoi vedere le seguenti opzioni:

* **Icona**: l’icona identifica il componente del pannello nell’elenco. Passa il puntatore del mouse sull’icona per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione**: la descrizione utilizzata come testo del pannello. Per impostazione predefinita, il nome del componente è selezionato per il pannello.
* **Elimina**: tocca o fai clic per eliminare il pannello dal componente Pannello a soffietto.
* **Ridisponi**: tocca o fai clic e trascina per modificare l’ordine dei pannelli.

### Scheda Contenuto Guida {#help-content}

![Scheda Contenuto Guida](/help/adaptive-forms/assets/accordion_helpcontent.png)

* **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

* **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility}

![Scheda Accessibilità](/help/adaptive-forms/assets/accordion_accessibility.png)

**Testo per utilità per la lettura dello schermo**: il testo per le utilità per la lettura dello schermo si riferisce al testo aggiuntivo destinato specificamente ad essere letto da tecnologie di assistenza, come le utilità per la lettura dello schermo, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente ai creatori di modelli di controllare la modalità di visualizzazione predefinita degli elementi. Per il componente pannello a soffietto dei moduli adattivi, puoi impostare gli elementi seguenti:

* Tipo di elementi di intestazione HTML consentiti e impostati come predefiniti (ad esempio H1, H2, H3, ecc.)
* I componenti core che un creatore di moduli può aggiungere al pannello a soffietto nell’editor di moduli adattivi
* Nomi semplici per gli stili (classi CSS) che possono essere applicati nella finestra di dialogo delle proprietà del componente pannello a soffietto nell’editor di moduli adattivi.

Questo permette di rendere il processo di creazione e personalizzazione dei moduli più semplice ed efficace.

### Scheda Proprietà {#properties-tab-design}

La scheda Proprietà consente agli autori del modello di impostare gli elementi di intestazione HTML predefiniti e consentiti per gli autori del modulo:

![Scheda proprietà della finestra di dialogo per la progettazione](/help/assets/accordion-design-properties.png)

* **Elementi di intestazione consentiti**: un elenco a discesa con più opzioni che consente all’autore del modello di scegliere gli elementi di intestazione del modulo da utilizzare per il pannello a soffietto.

* **Elemento di intestazione predefinito**: un elenco a discesa imposta l’elemento intestazione predefinito per il componente a soffietto.

### Scheda Componenti Consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** consente all’editor dei modelli di impostare i componenti che possono essere aggiunti come elementi ai pannelli nel componente Pannello a soffietto nell’editor dei moduli adattivi.

![Scheda Componenti consentiti](/help/adaptive-forms/assets/accordion_allowedcomponents.png)

### Scheda Stili {#styles-tab}

La scheda è utilizzata per definire e gestire gli stili CSS per un componente. Il componente core del pannello a soffietto dei moduli adattivi supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

![Scheda Stile](/help/adaptive-forms/assets/accordion_style.png)

* **Classi CSS predefinite**: puoi fornire una classe CSS predefinita per il componente pannello a soffietto.

* **Stili consentiti**: puoi definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di moduli adattivi. Per applicare uno stile, nell’editor dei moduli adattivi, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

