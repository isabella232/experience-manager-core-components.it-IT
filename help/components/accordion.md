---
title: Componente Accordion
description: Il componente Core Component Accordion consente di creare una raccolta di pannelli disposti in un pannello a soffietto su una pagina.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '1051'
ht-degree: 1%

---


# Componente Accordion{#accordion-component}

Il componente Core Component Accordion consente di creare una raccolta di pannelli disposti in un pannello a soffietto su una pagina.

## Utilizzo {#usage}

Il componente Core Component Accordion consente di creare una raccolta di componenti, composti come pannelli, e disposti in un pannello a soffietto su una pagina, simile al componente [](tabs.md)Tabulazioni, ma consente di espandere e comprimere i pannelli.

* Le proprietà del pannello di controllo possono essere definite nella finestra di dialogo [di](#configure-dialog)configurazione.
* L’ordine dei pannelli del pannello a soffietto può essere definito nella finestra di dialogo di configurazione e nel contenitore del pannello di [selezione](#select-panel-popover).
* I valori predefiniti per il componente Accordion quando viene aggiunto a una pagina possono essere definiti nella finestra di dialogo [](#design-dialog)della progettazione.

## Collegamento diretto a un pannello {#deep-linking}

I componenti [Accordion e](tabs.md) Tabs supportano il collegamento diretto a un pannello all’interno del componente.

Per effettuare ciò:

1. Visualizzare la pagina con il componente utilizzando l’opzione **[Visualizza come pubblicato](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/authoring/editing-content.html#view-as-published)**nell’editor pagina.
1. Esaminate il contenuto della pagina e identificate l’ID del pannello.
   * Esempio `id="accordion-86196c94d3-item-ca319dbb0b"`
1. L’ID diventa l’ancoraggio che potete aggiungere all’URL utilizzando un hash (`#`).
   * Esempio `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

Passando all’URL con l’ID del pannello come ancoraggio, il browser scorre direttamente fino al componente specifico e visualizza il pannello specificato. Se il pannello non è configurato per impostazione predefinita, viene espanso automaticamente.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Accordion è v1, introdotto con la release 2.5.0 dei componenti core a giugno 2019, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Accordion e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](https://adobe.com/go/aem_cmp_library_accordion)componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Accordion [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_accordion_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire l’elemento Accordion, i relativi pannelli e come si presenterà e come verrà visualizzato da un visitatore alla pagina.

### Scheda Articoli {#items-tab}

![scheda Elementi della finestra di dialogo di modifica del componente Accordion](/help/assets/accordion-edit-items.png)

Usate il pulsante **Aggiungi** per aprire il selettore di componenti e scegliere quale componente aggiungere come pannello. Una volta aggiunta, una voce viene aggiunta all&#39;elenco, che contiene le seguenti colonne:

* **Icona** - L&#39;icona del tipo di componente del pannello per una facile identificazione nell&#39;elenco. Passate il puntatore del mouse sopra per visualizzare il nome completo del componente come una descrizione comando.
* **Descrizione** - Descrizione utilizzata come testo del pannello, con impostazione predefinita sul nome del componente selezionato per il pannello.
* **Elimina** - Toccate o fate clic per eliminare il pannello dal componente Accordion.
* **Ridisponi** - Toccate o fate clic e trascinate per riordinare i pannelli.

>[!TIP]
>
>Se la vista della pagina viene ridotta e la finestra di dialogo di modifica diventa a schermo intero, il pulsante **Aggiungi** viene nascosto. Per aggiungere i componenti al componente Accordion, [trascinateli dal Browser componenti e trascinateli sul componente Accordion nell’editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent)di pagina.

### Scheda Proprietà {#properties-tab}

![scheda Proprietà della finestra di dialogo di modifica del componente Accordion](/help/assets/accordion-edit-properties.png)

* **Espansione** elemento singolo - Se selezionata, questa opzione forza l&#39;espansione di un singolo elemento a soffietto alla volta. Se si espande un elemento, verranno compressi tutti gli altri.
* **Elementi** espansi - Questa opzione definisce gli elementi che vengono espansi per impostazione predefinita quando la pagina viene caricata.
   * Quando è selezionata l’espansione **di un elemento** singolo, è necessario selezionare un pannello. Per impostazione predefinita, è selezionato il primo pannello.
   * Se l&#39;espansione **di un elemento** singolo non è selezionata, questa opzione è una selezione multipla ed è facoltativa.
* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Selezione del puntatore del pannello {#select-panel-popover}

L’autore del contenuto può usare l’opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a un altro pannello e ridisporre facilmente l’ordine dei pannelli all’interno della struttura di navigazione.

![Seleziona l’icona del pannello](/help/assets/select-panel-icon.png)

Dopo aver selezionato l’opzione **Seleziona pannello** nella barra degli strumenti del componente, i pannelli a soffietto configurati vengono visualizzati come un elenco a discesa.

![Selezione del puntatore del pannello](/help/assets/select-panel-popover.png)

* L&#39;elenco è ordinato in base alla disposizione assegnata dei pannelli e si riflette nella numerazione.
* Il tipo di componente del pannello viene visualizzato per primo, seguito dalla descrizione del pannello con un carattere più chiaro.
* Toccando o facendo clic su una voce nel menu a discesa, la vista nell’editor viene sostituita da tale pannello.
* I pannelli possono essere ridisposti in posizione mediante le maniglie di trascinamento.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire le opzioni disponibili per l&#39;autore del contenuto che utilizza il componente Accordion e le impostazioni predefinite al momento del posizionamento del componente Accordion.

### Scheda Proprietà {#properties-tab-design}

![scheda Proprietà della finestra di dialogo Progettazione](/help/assets/accordion-design-properties.png)

* **Elementi** titolo consentiti - Questo elenco a discesa con più selezioni definisce l&#39;intestazione dell&#39;elemento Accordion gli elementi HTML che possono essere selezionati da un autore.
* **Elemento** titolo predefinito - Questo elenco a discesa definisce l&#39;elemento Accordion predefinito dell&#39;elemento HTML.

### Allowed Components Tab {#allowed-components-tab}

La scheda Componenti **** consentiti viene utilizzata per definire quali componenti possono essere aggiunti ai pannelli del componente Accordion dall’autore del contenuto come elementi.

La scheda Componenti consentiti funziona nello stesso modo della scheda con lo stesso nome quando si [definisce il criterio e le proprietà di un Contenitore di layout nell&#39;Editor modelli.](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/templates.html)

### Scheda Stili {#styles-tab}

Il componente Accordion supporta AEM [Style System](/help/get-started/authoring.md#component-styling).
