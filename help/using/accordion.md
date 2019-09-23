---
title: Componente Accordion
seo-title: Componente Accordion
description: 'null'
seo-description: Il componente Core Component Accordion consente di creare una raccolta di pannelli disposti in un pannello a soffietto su una pagina.
uuid: ec807de9-f76c-4850-9ece-c3e439a1d626
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: f093f58e-9755-4a4f-803a-ab93a50e6870
translation-type: tm+mt
source-git-commit: bbd54d433cbeee5395dc8b90bc47f9b44747e25b

---


# Componente Accordion{#accordion-component}

Il componente Core Component Accordion consente di creare una raccolta di pannelli disposti in un pannello a soffietto su una pagina.

## Utilizzo {#usage}

Il componente Core Component Accordion consente di creare una raccolta di componenti, composti come pannelli, e disposti in un pannello a soffietto su una pagina, simile al componente [](tabs.md)Tabulazioni, ma consente di espandere e comprimere i pannelli.

* Le proprietà del pannello di controllo possono essere definite nella finestra di dialogo [di](#configure-dialog)configurazione.
* L’ordine dei pannelli del pannello a soffietto può essere definito nella finestra di dialogo di configurazione e nel contenitore del pannello di [selezione](#select-planel.md).
* I valori predefiniti per il componente Accordion quando viene aggiunto a una pagina possono essere definiti nella finestra di dialogo [](#design-dialog)della progettazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Accordion è v1, introdotto con la release 2.5.0 dei componenti core a giugno 2019, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Accordion e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](http://opensource.adobe.com/aem-core-wcm-components/library/accordion.html)componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Accordion [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/accordion/v1/accordion).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire l’elemento Accordion, i relativi pannelli e come si presenterà e come verrà visualizzato da un visitatore alla pagina.

### Scheda Articoli {#items-tab}

![](assets/screen-shot-2019-06-21-08.26.38.png)

Usate il pulsante **Aggiungi** per aprire il selettore di componenti e scegliere quale componente aggiungere come pannello. Una volta aggiunta, una voce viene aggiunta all'elenco, che contiene le seguenti colonne:

* **Icona** - L'icona del tipo di componente del pannello per una facile identificazione nell'elenco. Passate il puntatore del mouse sopra per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione** - Descrizione utilizzata come testo del pannello, con impostazione predefinita sul nome del componente selezionato per il pannello.
* **Elimina** - Toccate o fate clic per eliminare il pannello dal componente Accordion.
* **Ridisponi** - Toccate o fate clic e trascinate per riordinare i pannelli.

### Scheda Proprietà {#properties-tab}

![](assets/screen-shot-2019-06-21-08.26.53.png)

* **Espansione** elemento singolo - Se selezionata, questa opzione forza l'espansione di un singolo elemento a soffietto alla volta. Se si espande un elemento, verranno compressi tutti gli altri.
* **Elementi** espansi - Questa opzione definisce gli elementi che vengono espansi per impostazione predefinita quando la pagina viene caricata.
   * Quando è selezionata l’espansione **di un elemento** singolo, è necessario selezionare un pannello. Per impostazione predefinita, è selezionato il primo pannello.
   * Se l'espansione **di un elemento** singolo non è selezionata, questa opzione è una selezione multipla ed è facoltativa.

## Selezione del puntatore del pannello {#seelct-panel-popover}

L’autore del contenuto può usare l’opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a un altro pannello e ridisporre facilmente l’ordine dei pannelli all’interno della struttura di navigazione.

![](assets/screen-shot-2019-06-21-08.49.36.png)

Dopo aver selezionato l’opzione **Seleziona pannello** nella barra degli strumenti del componente, i pannelli a soffietto configurati vengono visualizzati come un elenco a discesa.

![](assets/screen-shot-2019-06-21-08.52.14.png)

* L'elenco è ordinato in base alla disposizione assegnata dei pannelli e si riflette nella numerazione.
* Il tipo di componente del pannello viene visualizzato per primo, seguito dalla descrizione del pannello con un carattere più chiaro.
* Toccando o facendo clic su una voce nel menu a discesa, la vista nell’editor viene sostituita da tale pannello.
* I pannelli possono essere ridisposti in posizione mediante le maniglie di trascinamento.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all'autore del modello di definire le opzioni disponibili per l'autore del contenuto che utilizza il componente Accordion e le impostazioni predefinite al momento del posizionamento del componente Accordion.

### Scheda Proprietà {#properties-tab-design}

![](assets/screen-shot-2019-06-21-08.58.11.png)

* **Elementi** titolo consentiti - Questo elenco a discesa con più selezioni definisce l'intestazione dell'elemento Accordion gli elementi HTML che possono essere selezionati da un autore.
* **Elemento** titolo predefinito - Questo elenco a discesa definisce l'elemento Accordion predefinito dell'elemento HTML.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda Componenti **** consentiti viene utilizzata per definire quali componenti possono essere aggiunti ai pannelli del componente Accordion dall’autore del contenuto come elementi.

La scheda Componenti consentiti funziona nello stesso modo della scheda con lo stesso nome quando si [definisce il criterio e le proprietà di un Contenitore di layout nell'Editor modelli.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Scheda Stili {#styles-tab}

Il componente Accordion supporta AEM [Style System](authoring.md#component-styling).
