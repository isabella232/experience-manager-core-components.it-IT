---
title: Pannello a soffietto per moduli adattivi
description: Utilizzare il pannello a soffietto per organizzare e semplificare un modulo lungo o complesso suddividendolo in sezioni più piccole e gestibili.
role: Architect, Developer, Admin, User
source-git-commit: 0e4fb8454b7ef84eb5b1b73b01c982a2f9c12381
workflow-type: tm+mt
source-wordcount: '1652'
ht-degree: 3%

---

# Componente Pannello a soffietto {#accordion-component-adaptive-forms-core-component}

Il componente di base per pannello a soffietto consente agli utenti di creare sezioni espandibili e comprimibili in un modulo adattivo. Viene spesso utilizzato per organizzare e semplificare moduli lunghi o complessi suddividendoli in sezioni più piccole e gestibili. Ogni sezione di un pannello a soffietto è in genere rappresentata da un’intestazione, su cui l’utente può fare clic per espandere o comprimere il contenuto corrispondente. Il contenuto può essere qualsiasi componente di base.

## Utilizzo {#usage}

Ci sono diversi motivi per cui è utile includere un pannello a soffietto in un modulo adattivo, tra cui:

* **Salvataggio dello spazio**: Un pannello a soffietto consente agli utenti di espandere e comprimere le sezioni di un modulo, riducendo la quantità di spazio necessario per visualizzare tutti i campi del modulo contemporaneamente.

* **Navigazione**: Un pannello a soffietto può essere utilizzato per creare una struttura di navigazione gerarchica, facilitando agli utenti la ricerca dei campi modulo necessari.

* **Esperienza utente**: Il pannello a soffietto può essere utilizzato per rendere il modulo più semplice da usare, fornendo agli utenti un modo chiaro e intuitivo di accedere ai campi del modulo e compilarli.

* **Long Forms**: Il pannello a soffietto è un componente ideale per gestire le forme lunghe, in quanto consente agli utenti di concentrarsi su una sezione alla volta, anziché cercare di elaborare molte informazioni contemporaneamente.

Puoi utilizzare:

* La [finestra di dialogo configura](#configure-dialog) per specificare le proprietà del componente a soffietto.

* La [Selezione pover del pannello](#select-panel-popover)  definire l&#39;ordine dei pannelli del pannello a soffietto. Questo consente all’autore di disporre i pannelli nell’ordine in cui dovrebbero essere visualizzati.

* Opzioni dell’autore di un modulo per abilitare o disabilitare determinate funzioni nel [finestra di dialogo di progettazione](#design-dialog). Ad esempio, un autore può scegliere di disattivare alcuni campi o sezioni di un modulo. Queste opzioni consentono all’autore di avere un maggiore controllo sulla struttura e sulle funzionalità del modulo, facilitando la creazione di moduli personalizzati in base alle esigenze specifiche dell’organizzazione.

La finestra di dialogo di configurazione, l’opzione Selezione pannello e la finestra di dialogo Progettazione fanno parte dei componenti core creati per semplificare la creazione dei moduli e fornire un modo efficiente per creare moduli complessi.

## Versione e compatibilità {#version-and-compatibility}


Il componente core per pannello a soffietto adattivo di Forms è stato rilasciato a febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente Pannello a soffietto, consulta la documentazione tecnica disponibile in [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/accordion/v1/accordion). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del pannello a soffietto per i visitatori tramite la finestra di dialogo Configura . È inoltre possibile definire elementi a soffietto, pannelli, comportamento e aspetto con facilità per un’esperienza utente diretta.

### Scheda di base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/accordion_basictab.png)

* **Nome** - È possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo** - Con il relativo Titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungete un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo** - Seleziona l’opzione per nascondere il titolo del componente.

* **Racchiudi i dati in un oggetto** - Scegliere &quot;Racchiudi i dati in un oggetto&quot; per inserire i dati del campo dalla procedura guidata all&#39;interno di un oggetto JSON. Se non viene selezionato, i dati di invio JSON presentano una struttura piatta per i campi della procedura guidata.

* **Layout** - È possibile disporre di un layout fisso (semplice) o flessibile (griglia reattiva) per la procedura guidata. Il layout Semplice mantiene tutto fisso nella posizione, mentre la griglia reattiva consente di regolare la posizione dei componenti in base alle proprie esigenze. Ad esempio, utilizza Griglia reattiva per allineare &quot;Nome&quot;, &quot;Nome intermedio&quot; e &quot;Cognome&quot; in un modulo in un’unica riga.

* **Riferimento a un&#39;associazione** - Un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente semplice per la raccolta e la gestione dei dati.
* **Nascondi componente** - Selezionare l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente** - Seleziona l’opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.

### Scheda Elementi {#items-tab}

![Scheda Elementi](/help/adaptive-forms/assets/accordion_itemstab.png)

Il pulsante Aggiungi consente di selezionare un componente da aggiungere come pannello dalla finestra di selezione del componente. Dopo aver aggiunto il componente, puoi vedere le seguenti opzioni:

* **Icona** - L’icona identifica il componente del pannello nell’elenco. Passa il puntatore del mouse sull’icona per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione** - Descrizione utilizzata come testo del pannello. Per impostazione predefinita, per il pannello è selezionato il nome del componente.
* **Elimina**: tocca o fai clic per eliminare il pannello dal componente Pannello a soffietto.
* **Ridisponi**: tocca o fai clic e trascina per modificare l’ordine dei pannelli.

### Scheda Contenuto dell’Aiuto {#help-content}

![Scheda Contenuto della guida](/help/adaptive-forms/assets/accordion_helpcontent.png)

* **Breve descrizione** - Una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita la **Mostra sempre una breve descrizione** per visualizzarlo sotto il componente.

* **Mostra sempre una breve descrizione** - Abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo della Guida** - Il testo della Guida si riferisce a informazioni o indicazioni aggiuntive fornite all&#39;utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’Aiuto (i) posta accanto al componente. Il testo della Guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility}

![Scheda Accessibilità](/help/adaptive-forms/assets/accordion_accessibility.png)

* **Testo per assistenti vocali** - Il testo per gli assistenti vocali si riferisce al testo aggiuntivo destinato specificamente alla lettura da parte di tecnologie per l’accessibilità, come gli assistenti vocali, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome ed eventuali messaggi pertinenti del campo (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di tutti gli utenti, compresi quelli con problemi visivi, e di comprendere appieno il campo del modulo e i relativi requisiti.

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

La finestra di dialogo Progettazione consente ai creatori di modelli di controllare la modalità di visualizzazione predefinita degli elementi. Per il componente per pannello a soffietto di Forms adattivo, puoi impostare quanto segue:

* Tipo di elementi di intestazione di HTML consentiti e impostati come predefiniti (ad esempio H1, H2, H3, ecc.)
* Componenti core che un creatore di moduli può aggiungere al pannello a soffietto nell’editor di Forms adattivo
* Nomi semplici per gli stili (classi CSS) che possono essere applicati nella finestra di dialogo delle proprietà del componente a soffietto nell’editor di Forms adattivo.

Questo consente di semplificare e personalizzare i moduli.

### Scheda Proprietà {#properties-tab-design}

La scheda Proprietà consente agli autori dei modelli di impostare gli elementi di intestazione HTML predefiniti e consentiti per gli autori dei moduli:

![Scheda Proprietà della finestra di dialogo per progettazione](/help/assets/accordion-design-properties.png)

* **Elementi di intestazione consentiti**: Un elenco a discesa con più opzioni che consente all’autore del modello di scegliere quali elementi di intestazione può essere utilizzato dall’autore per il pannello a soffietto.

* **Elemento di intestazione predefinito**: Un elenco a discesa imposta l’elemento Titolo predefinito per il componente a soffietto.

### Scheda Componenti consentiti {#allowed-components-tab}

La **Componenti consentiti** scheda consente all’editor modelli di impostare i componenti che possono essere aggiunti come elementi ai pannelli nel componente Pannello a soffietto nell’editor di Forms adattivo.

### Scheda Stili {#styles-tab}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per un componente. Il componente di base per pannello a soffietto adattivo di Forms supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

**Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente a soffietto.

**Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.


<!-- 

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




