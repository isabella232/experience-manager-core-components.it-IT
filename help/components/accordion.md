---
title: Componente Accordion
description: Il componente Core Component Accordion consente di creare una raccolta di pannelli disposti in un pannello a soffietto su una pagina.
translation-type: tm+mt
source-git-commit: 2926c51c2ab97b50b9ec4942cd5415c15a1411b6
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 1%

---


# Componente Accordion{#accordion-component}

Il componente Core Component Accordion consente di creare una raccolta di pannelli disposti in un pannello a soffietto su una pagina.

## Utilizzo {#usage}

Il componente Core Component Accordion consente la creazione di una raccolta di componenti, composti come pannelli, e disposti in un pannello a soffietto su una pagina, simile al [Componente Tabs](tabs.md), ma consente l&#39;espansione e il comprimere dei pannelli.

* Le proprietà del pannello di controllo possono essere definite nella finestra di dialogo [configura](#configure-dialog).
* L&#39;ordine dei pannelli del pannello a soffietto può essere definito nella finestra di dialogo di configurazione e nel [selettore del pannello ](#select-panel-popover).
* I valori predefiniti per il componente Accordion quando viene aggiunto a una pagina possono essere definiti nella finestra di dialogo di progettazione [a1/>.](#design-dialog)

## Collegamento diretto a un pannello {#deep-linking}

Le schede [Componenti Accordion e &lt;a0/>Tabs](tabs.md) supportano il collegamento diretto a un pannello all&#39;interno del componente.

Per effettuare ciò:

1. Visualizzare la pagina con il componente utilizzando l&#39;opzione **[Visualizza come pubblicato](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** nell&#39;editor di pagina.
1.  Inspect il contenuto della pagina e identificare l’ID del pannello.
   * Esempio `id="accordion-86196c94d3-item-ca319dbb0b"`
1. L&#39;ID diventa l&#39;ancoraggio che potete aggiungere all&#39;URL utilizzando un hash (`#`).
   * Esempio `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

Passando all’URL con l’ID del pannello come ancoraggio, il browser scorre direttamente fino al componente specifico e visualizza il pannello specificato. Se il pannello non è configurato per impostazione predefinita, viene espanso automaticamente.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Accordion è v1, introdotto con la release 2.5.0 dei componenti core a giugno 2019, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente Accordion e vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library_accordion).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Accordion [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_accordion_v1).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire l’elemento Accordion, i relativi pannelli e come si presenterà e come verrà visualizzato da un visitatore alla pagina.

### Scheda Articoli {#items-tab}

![scheda Elementi della finestra di dialogo di modifica del componente Accordion](/help/assets/accordion-edit-items.png)

Utilizzate il pulsante **Aggiungi** per aprire il selettore di componenti e scegliere quale componente aggiungere come pannello. Una volta aggiunta, una voce viene aggiunta all&#39;elenco, che contiene le seguenti colonne:

* **Icona**  - Icona del tipo di componente del pannello per una facile identificazione nell’elenco. Passate il puntatore del mouse sopra per visualizzare il nome completo del componente come una descrizione comando.
* **Descrizione**  - Descrizione utilizzata come testo del pannello, con impostazione predefinita sul nome del componente selezionato per il pannello.
* **Elimina**  - Toccate o fate clic per eliminare il pannello dal componente Accordion.
* **Ridisponi**  - Toccate o fate clic e trascinate per riordinare i pannelli.

>[!TIP]
>
>Se la vista della pagina viene ridotta in modo che la finestra di dialogo di modifica diventi a schermo intero, il pulsante **Aggiungi** verrà nascosto. Per aggiungere i componenti al componente Accordion, [trascinare dal browser Componenti e rilasciare il componente Accordion nell&#39;editor pagina](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent).

### Scheda Proprietà {#properties-tab}

![scheda Proprietà della finestra di dialogo di modifica del componente Accordion](/help/assets/accordion-edit-properties.png)

* **Espansione**  elemento singolo: se selezionata, questa opzione forza l&#39;espansione di un singolo elemento a soffietto alla volta. Se si espande un elemento, verranno compressi tutti gli altri.
* **Elementi**  espansi - Questa opzione definisce gli elementi che vengono espansi per impostazione predefinita quando la pagina viene caricata.
   * Quando si seleziona **Espansione elemento singolo**, è necessario selezionare un pannello. Per impostazione predefinita, è selezionato il primo pannello.
   * Se **Espansione elemento singolo** non è selezionata, questa opzione è una selezione multipla ed è facoltativa.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Selezione del puntatore del pannello {#select-panel-popover}

L&#39;autore del contenuto può utilizzare l&#39;opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a un altro pannello per la modifica e per ridisporre facilmente l&#39;ordine dei pannelli all&#39;interno della struttura di navigazione.

![Seleziona l’icona del pannello](/help/assets/select-panel-icon.png)

Dopo aver selezionato l&#39;opzione **Seleziona pannello** nella barra degli strumenti del componente, i pannelli a soffietto configurati vengono visualizzati come un elenco a discesa.

![Selezione del puntatore del pannello](/help/assets/select-panel-popover.png)

* L&#39;elenco è ordinato in base alla disposizione assegnata dei pannelli e si riflette nella numerazione.
* Il tipo di componente del pannello viene visualizzato per primo, seguito dalla descrizione del pannello con un carattere più chiaro.
* Toccando o facendo clic su una voce nel menu a discesa, la vista nell’editor viene sostituita da tale pannello.
* I pannelli possono essere ridisposti in posizione mediante le maniglie di trascinamento.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire le opzioni disponibili per l&#39;autore del contenuto che utilizza il componente Accordion e le impostazioni predefinite al momento del posizionamento del componente Accordion.

### Scheda Proprietà {#properties-tab-design}

![scheda Proprietà della finestra di dialogo Progettazione](/help/assets/accordion-design-properties.png)

* **Elementi**  titolo consentiti - Questo elenco a discesa con più selezioni definisce l&#39;intestazione dell&#39;elemento Accordion gli elementi HTML che possono essere selezionati da un autore.
* **Elemento**  titolo predefinito - Questo elenco a discesa definisce l&#39;elemento Accordion predefinito dell&#39;elemento HTML.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** viene utilizzata per definire quali componenti possono essere aggiunti come elementi ai pannelli nel componente Accordion dall&#39;autore del contenuto.

La scheda Componenti consentiti funziona nello stesso modo della scheda con lo stesso nome quando si definisce il criterio e le proprietà di un Contenitore di layout nell&#39;Editor modelli.[](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-layout-template-author)

### Scheda Stili {#styles-tab}

Il componente Accordion supporta il AEM [Style System](/help/get-started/authoring.md#component-styling).
