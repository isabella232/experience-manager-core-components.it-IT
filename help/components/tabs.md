---
title: Componente Tabulazioni
description: Il componente Tabulazioni consente di creare più schede per disporre il contenuto su una pagina.
translation-type: tm+mt
source-git-commit: 2926c51c2ab97b50b9ec4942cd5415c15a1411b6
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 2%

---


# Componente scheda {#tabs-component}

Il componente core Tabs Component consente l&#39;organizzazione del contenuto su più schede.

## Utilizzo {#usage}

Il componente Tabulazioni consente all’autore del contenuto di organizzare il contenuto della pagina all’interno di più schede.

La [finestra di dialogo di modifica](#edit-dialog) consente all&#39;autore del contenuto di definire più schede e di impostare la scheda attiva. Utilizzando la finestra di dialogo [progettazione](#design-dialog), l&#39;autore del modello può definire quali componenti possono essere aggiunti alle schede e personalizzare gli stili.

>[!TIP]
>
>Sono supportati i componenti scheda nidificati (schede all’interno delle schede).
>
>È possibile individuare/selezionare componenti scheda semplici (non nidificati) utilizzando la struttura [contenuto](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html#content-tree), ma non è possibile utilizzare schede nidificate.

## Collegamento diretto a un pannello {#deep-linking}

Le schede e i [componenti Accordion](accordion.md) supportano il collegamento diretto a un pannello all&#39;interno del componente.

Per effettuare ciò:

1. Visualizzare la pagina con il componente utilizzando l&#39;opzione **[Visualizza come pubblicato](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** nell&#39;editor di pagina.
1.  Inspect il contenuto della pagina e identificare l’ID del pannello.
   * Esempio `id="accordion-86196c94d3-item-ca319dbb0b"`
1. L&#39;ID diventa l&#39;ancoraggio che potete aggiungere all&#39;URL utilizzando un hash (`#`).
   * Esempio `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

Passando all’URL con l’ID del pannello come ancoraggio, il browser scorre direttamente fino al componente specifico e visualizza il pannello specificato. Se il pannello non è configurato per impostazione predefinita, viene espanso automaticamente.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Tabs è v1, introdotto con la release 2.2.0 dei componenti core a ottobre 2018, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente Tabs e vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library_tabs).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Tabs [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_tabs_v1).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di creare, rinominare e ridisporre le schede, nonché definire la scheda attiva.

### Scheda Articoli {#items-tab}

![Scheda Elementi della finestra di dialogo di modifica del componente](/help/assets/tabs-edit-items.png)

Utilizzate il pulsante **Aggiungi** per aprire il selettore di componenti e scegliere quale componente aggiungere come scheda. Una volta aggiunta, una voce viene aggiunta all&#39;elenco, che contiene le seguenti colonne:

* **Icona**  - L&#39;icona del tipo di componente della scheda per facilitarne l&#39;identificazione nell&#39;elenco. Passate il puntatore del mouse sopra per visualizzare il nome completo del componente come una descrizione comando.
* **Descrizione**  - Descrizione utilizzata come testo della scheda, con impostazione predefinita sul nome del componente selezionato per la scheda.
* **Elimina**  - Toccate o fate clic per eliminare la scheda dal componente scheda.
* **Ridisponi**  - Toccate o fate clic e trascinate per riordinare l&#39;ordine delle schede.

>[!TIP]
>
>Se la vista della pagina viene ridotta in modo che la finestra di dialogo di modifica diventi a schermo intero, il pulsante **Aggiungi** verrà nascosto. I componenti possono essere aggiunti al componente Tabs trascinando dal browser Componenti e rilasciando il componente Tabs nell&#39;editor pagina[.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component)

### Scheda Proprietà {#properties-tab}

![Scheda Proprietà della finestra di dialogo di modifica del componente](/help/assets/tabs-edit-properties.png)

* **Elemento**  attivo: l&#39;autore del contenuto può definire quale scheda è attiva al caricamento della pagina.
   * Con l&#39;opzione **Default**, verrà selezionata la prima scheda.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità della finestra di dialogo di modifica del componente](/help/assets/tabs-edit-accessibility.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette [Accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente.

* **Etichetta**  - Valore di un attributo etichetta ARIA per il componente

## Seleziona pannello {#select-panel}

L&#39;autore del contenuto può utilizzare l&#39;opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a un altro pannello per la modifica e per riordinare facilmente l&#39;ordine delle schede.

![Seleziona l’icona del pannello](/help/assets/select-panel-icon.png)

Dopo aver selezionato l&#39;opzione **Seleziona pannello** nella barra degli strumenti del componente, le schede configurate vengono visualizzate come un elenco a discesa.

* L&#39;elenco è ordinato dalla disposizione assegnata delle schede e si riflette nella numerazione.
* Il tipo di componente della scheda viene visualizzato per primo, seguito dalla descrizione della scheda con un carattere più chiaro.

![Selezione del puntatore del pannello](/help/assets/select-panel-popover.png)

* Toccando o facendo clic su una voce nel menu a discesa, la vista nell’editor passa a tale scheda.
* Le schede possono essere ridisposte in posizione utilizzando le maniglie di trascinamento.

>[!NOTE]
>
>Le schede non sono selezionabili dall&#39;autore in modalità **Modifica**. Utilizzate la modalità **[Anteprima](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)** o l&#39;opzione **[Visualizza come pubblicato](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** per interagire con le schede come lettore del contenuto pubblicato.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire quali componenti possono essere aggiunti al componente Tabulazioni, nonché definire quali stili personalizzati sono disponibili per l&#39;autore del contenuto.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** viene utilizzata per definire quali componenti possono essere aggiunti al componente Tabulazioni dall&#39;autore del contenuto come elementi.

La scheda Componenti consentiti funziona nello stesso modo della scheda con lo stesso nome quando si definisce il criterio e le proprietà di un Contenitore di layout nell&#39;Editor modelli.[](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Scheda Stili {#styles-tab}

Il componente Tabs supporta il AEM [Sistema di stile](/help/get-started/authoring.md#component-styling).
