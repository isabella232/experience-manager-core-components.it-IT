---
title: Pannello a soffietto moduli adattivi
description: Utilizza il pannello a soffietto per organizzare e semplificare un modulo lungo o complesso suddividendolo in sezioni più piccole e gestibili.
role: Architect, Developer, Admin, User
exl-id: 0ed38eee-fc22-4708-82eb-3fb1839b1ff2
source-git-commit: 7888cfa0f1358ce8018fc1e3cc3b19eb66a82b9d
workflow-type: tm+mt
source-wordcount: '1950'
ht-degree: 91%

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


Il componente core per pannello a soffietto adattivo dei moduli adattivi è stato rilasciato a febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità con AEM e i collegamenti alla documentazione corrispondente:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile con<br>[versione 2.0.4](/help/versions.md) e successive | Compatibile | Compatibile |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md).

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente Pannello a soffietto, consulta la documentazione tecnica disponibile su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/accordion/v1/accordion). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del pannello a soffietto per i visitatori tramite la finestra di dialogo per la configurazione. È inoltre possibile definire elementi del pannello a soffietto, pannelli, comportamento e aspetto con facilità per un’esperienza utente semplice.

### Scheda Base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/acc-basic.png)

* **Nome**: è possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo**: con il relativo titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungi un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo**: seleziona l’opzione per nascondere il titolo del componente.

* **Racchiudi i dati in un oggetto**: scegli “Racchiudi i dati in un oggetto” per inserire i dati del campo dalla procedura guidata all’interno di un oggetto JSON. Se non viene scelto, l’invio dati JSON presenta una struttura piatta per i campi della procedura guidata.

* **Layout**: è possibile disporre di un layout fisso (semplice) o flessibile (griglia dinamica) per la procedura guidata. Il layout semplice mantiene tutto fisso in posizione, mentre la griglia dinamica consente di regolare la posizione dei componenti in base alle proprie esigenze. Ad esempio, utilizza la griglia dinamica per allineare “Nome”, “Secondo nome” e “Cognome” in un modulo in un’unica riga.

* **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, offrendo agli utenti un’esperienza utente semplice per la raccolta e la gestione dei dati.
* **Nascondi componente**: seleziona questa opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente**: seleziona questa opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

### Ripeti pannello a soffietto {#repeat-accordion}

![repeat-pannello a soffietto](/help/adaptive-forms/assets/repeat-accordion.png)

È possibile utilizzare le opzioni di ripetibilità per duplicare i pannelli Pannello a soffietto e i relativi componenti figlio, definire un conteggio di ripetizioni minimo e massimo e facilitare la replica di sezioni simili all’interno di un modulo. Quando si interagisce con il componente Pannello a soffietto e si accede alle relative impostazioni, vengono visualizzate le seguenti opzioni:

* **Rendi il pannello a soffietto ripetibile**: funzione di attivazione/disattivazione che consente agli utenti di abilitare o disabilitare la funzionalità di ripetibilità.
* **Numero minimo di ripetizioni**: stabilisce il numero minimo di volte in cui il pannello a soffietto può essere ripetuto. Il valore zero indica che il pannello Pannello a soffietto non è ripetuto; il valore predefinito è zero.
* **Numero massimo di ripetizioni**: imposta il numero massimo di ripetizioni del pannello a soffietto. Per impostazione predefinita, questo valore è illimitato.

Per gestire in modo efficace le sezioni ripetibili nel Pannello a soffietto, segui i passaggi descritti in [Creazione di moduli con sezioni ripetibili](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html) articolo.

### Scheda Elementi {#items-tab}

![Scheda Elementi](/help/adaptive-forms/assets/acc-items.png)

Il pulsante Aggiungi consente di selezionare un componente da aggiungere come pannello dalla finestra di selezione del componente. Dopo aver aggiunto il componente, puoi vedere le seguenti opzioni:

* **Icona**: l’icona identifica il componente del pannello nell’elenco. Passa il puntatore del mouse sull’icona per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione**: la descrizione utilizzata come testo del pannello. Per impostazione predefinita, il nome del componente è selezionato per il pannello.
* **Elimina**: tocca o fai clic per eliminare il pannello dal componente Pannello a soffietto.
* **Ridisponi**: tocca o fai clic e trascina per modificare l’ordine dei pannelli.

### Scheda Contenuto Guida {#help-content}

![Scheda Contenuto Guida](/help/adaptive-forms/assets/acc-helpcontent.png)

* **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

* **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility}

![Scheda Accessibilità](/help/adaptive-forms/assets/acc-accessisbilty.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette di [accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente. Sono disponibili varie opzioni per l’utilizzo del testo per l’assistente vocale:

* **Testo per utilità per la lettura dello schermo**: il testo per le utilità per la lettura dello schermo si riferisce al testo aggiuntivo destinato specificamente alla lettura da parte di tecnologie per l’accessibilità, come le utilità per la lettura dello schermo utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.


   * **Testo personalizzato**: seleziona questa opzione per utilizzare il testo personalizzato per le etichette di accessibilità ARIA. Selezionando questa opzione, viene visualizzata la finestra di dialogo Testo personalizzato. Puoi aggiungere informazioni rilevanti nella finestra di dialogo Testo personalizzato.
   * **Descrizione**: seleziona questa opzione per utilizzare la descrizione per le etichette di accessibilità ARIA.
   * **Titolo**: seleziona questa opzione per utilizzare il titolo per le etichette di accessibilità ARIA.
   * **Nome**: seleziona questa opzione per utilizzare il nome per le etichette di accessibilità ARIA.
   * **Nessuno**: seleziona questa opzione in caso tu non voglia aggiungere etichette di accessibilità ARIA.

<!--

### Properties Tab {#properties-tab}

![Properties tab of the edit dialog of the Accordion Component](/help/assets/accordion-edit-properties.png)

*   **Single item expansion** - When selected, this option forces a single accordion item to be expanded at a time. Expanding one item will then collapse all others.
*   **Expanded items** - This option defines the items that are expanded by default when the page is loaded.
    * When **Single item expansion** is selected, one panel must be selected. By default the first panel is selected.
    * When **Single item expansion** is not selected, this option is a multi-select and is optional.
*   **ID** - This option allows to control the unique identifier of the component in the HTML and in the [Data Layer](/help/developing/data-layer/overview.md).
    * If left blank, a unique ID is automatically generated for you and can be found by inspecting the resulting page.
    * If an ID is specified, it is the responsibility of the author to make sure that it is unique.
    * Changing the ID can have an impact on CSS, JS and Data Layer tracking.

## Select Panel Popover {#select-panel-popover}

The **Select Panel** option (![Select panel icon](/help/assets/select-panel-icon.png)) on the component toolbar enables content authors to modify the panels in an accordion with ease. By selecting this option, the author can switch to a different panel for editing and rearrange the order of the panels in the accordion. The configured panels will be displayed in a drop-down menu for the author to choose from. This feature optimizes the editing process and makes it user-friendly for content authors.

![Select panel popover](/help/assets/select-panel-popover.png)


* The panels are displayed in a numbered list, reflecting the assigned arrangement.
* Each panel is listed with its component type in bold, followed by a brief description in lighter font.
* By clicking or tapping on a panel in the drop-down, you can easily switch the view in the editor to that specific panel.
* To rearrange the panels, simply use the drag handles to move them into the desired order. -->

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

### Scheda Stili {#styles-tab}

La finestra di dialogo per la progettazione consente di definire e gestire gli stili CSS per un componente. Il componente core del pannello a soffietto dei moduli adattivi supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

**Classi CSS predefinite**: puoi fornire una classe CSS predefinita per il componente pannello a soffietto.

**Stili consentiti**: puoi definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di moduli adattivi. Per applicare uno stile, nell’editor dei moduli adattivi, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.


<!--- 

The design dialog allows the template author to define the options available to the content author who uses the Accordion Component and the defaults set when placing the Accordion Component.


### Properties Tab {#properties-tab-design}

![Design dialog properties tab](/help/assets/accordion-design-properties.png)

* **Allowed Heading Elements** - This multi-select drop-down defines the accordion item heading HTML elements that are allowed to be selected by an author.
* **Default Heading Element** - This drop-down defines the default accordion item heading HTML element.

### Allowed Components Tab {#allowed-components-tab}

The **Allowed Components** tab is used to define which components can be added as items to panels in the Accordion Component by the content author.

The Allowed Components tab functions in the same way as the tab of the same name when [defining the policy and properties of a Layout Container in the Template Editor.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-layout-template-author)

### Styles Tab {#styles-tab}

The Accordion Component supports the AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

The Accordion Component supports the [Adobe Client Data Layer.](/help/developing/data-layer/overview.md) 


-->

## Articolo correlato {#related-article}

* [Creare un modulo adattivo in una pagina o in un frammento di esperienza di AEM Sites](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)

* [Creare un modulo adattivo indipendente](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=it)

