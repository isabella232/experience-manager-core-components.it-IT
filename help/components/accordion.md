---
title: Componente a soffietto
description: Il componente pannello a soffietto dei componenti core consente di creare una raccolta di pannelli disposti in un pannello a soffietto su una pagina.
role: Architetto, Sviluppatore, Amministratore, Business Practices
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 1%

---


# Componente per pannello a soffietto{#accordion-component}

Il componente pannello a soffietto dei componenti core consente di creare una raccolta di pannelli disposti in un pannello a soffietto su una pagina.

## Utilizzo {#usage}

Il componente Pannello a soffietto del componente core consente di creare una raccolta di componenti, composti come pannelli e disposti in un pannello a soffietto su una pagina, simile al [Componente schede](tabs.md), ma consente di espandere e comprimere i pannelli.

* Le proprietà del pannello a soffietto possono essere definite nella finestra di dialogo [configura](#configure-dialog).
* L&#39;ordine dei pannelli del pannello a soffietto può essere definito nella finestra di dialogo di configurazione e nel [selettore pannello](#select-panel-popover).
* Le impostazioni predefinite per il componente per pannello a soffietto quando lo si aggiunge a una pagina possono essere definite nella finestra di dialogo [progettazione](#design-dialog).

## Collegamenti profondi a un pannello {#deep-linking}

I componenti per pannello a soffietto e [schede](tabs.md) supportano il collegamento diretto a un pannello all’interno del componente.

Per effettuare ciò:

1. Visualizza la pagina con il componente utilizzando l&#39;opzione **[Visualizza come pubblicato](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** nell&#39;editor di pagine.
1. Inspect il contenuto della pagina e identifica l’ID del pannello.
   * Esempio `id="accordion-86196c94d3-item-ca319dbb0b"`
1. L’ID diventa l’ancoraggio che puoi aggiungere all’URL utilizzando un hash (`#`).
   * Esempio `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

Navigando all’URL con l’ID del pannello come ancoraggio, il browser scorre direttamente fino al componente specifico e visualizza il pannello specificato. Se il pannello è configurato per non essere espanso per impostazione predefinita, viene espanso automaticamente.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente per pannello a soffietto è la v1, introdotta con la versione 2.5.0 dei componenti core a giugno 2019, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per provare il componente per pannello a soffietto e visualizzare esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_accordion).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente per pannello a soffietto [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_accordion_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire l’elemento a soffietto, i relativi pannelli e il comportamento di un visitatore sulla pagina.

### Scheda Elementi {#items-tab}

![Scheda Elementi della finestra di dialogo di modifica del componente per pannello a soffietto](/help/assets/accordion-edit-items.png)

Utilizza il pulsante **Aggiungi** per aprire il selettore dei componenti e scegliere quale componente aggiungere come pannello. Una volta aggiunta, una voce viene aggiunta all’elenco, che contiene le colonne seguenti:

* **Icona** : l’icona del tipo di componente del pannello per facilitarne l’identificazione nell’elenco. Passa il puntatore del mouse per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione** : descrizione utilizzata come testo del pannello, con impostazione predefinita sul nome del componente selezionato per il pannello.
* **Elimina** : tocca o fai clic per eliminare il pannello dal componente a soffietto.
* **Ridisponi**  - Tocca o fai clic e trascina per ridisporre l’ordine dei pannelli.

>[!TIP]
>
>Se la finestra di visualizzazione della pagina viene ridotta in modo che la finestra di dialogo di modifica diventi a schermo intero, il pulsante **Aggiungi** sarà nascosto. I componenti possono ancora essere aggiunti al componente per pannello a soffietto trascinandoli dal browser Componenti e rilasciandoli sul componente per pannello a soffietto nell’ editor pagina](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent).[

### Scheda Proprietà {#properties-tab}

![Scheda Proprietà della finestra di dialogo di modifica del componente per pannello a soffietto](/help/assets/accordion-edit-properties.png)

* **Espansione di un singolo elemento** : se selezionata, questa opzione consente di espandere un singolo elemento a soffietto alla volta. Espandi un elemento per comprimere tutti gli altri.
* **Elementi espansi** : questa opzione definisce gli elementi che vengono espansi per impostazione predefinita al caricamento della pagina.
   * Quando si seleziona **Espansione elemento singolo**, è necessario selezionare un pannello. Per impostazione predefinita, è selezionato il primo pannello.
   * Quando **L&#39;espansione di un singolo elemento** non è selezionata, questa opzione è una selezione multipla ed è facoltativa.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

## Seleziona il puntatore del pannello {#select-panel-popover}

L’autore del contenuto può utilizzare l’opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a un altro pannello da modificare e per ridisporre facilmente l’ordine dei pannelli nel pannello a soffietto.

![Icona Seleziona pannello](/help/assets/select-panel-icon.png)

Dopo aver selezionato l’opzione **Seleziona pannello** nella barra degli strumenti del componente, i pannelli a soffietto configurati vengono visualizzati come un elenco a discesa.

![Selezione pover del pannello](/help/assets/select-panel-popover.png)

* L&#39;elenco è ordinato dalla disposizione assegnata dei pannelli e si riflette nella numerazione.
* Il tipo di componente del pannello viene visualizzato per primo, seguito dalla descrizione del pannello in caratteri più chiari.
* Toccando o facendo clic su una voce nel menu a discesa, la visualizzazione nell’editor passa a tale pannello.
* I pannelli possono essere ridisposti in posizione mediante le maniglie di trascinamento.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore del contenuto che utilizza il componente per pannello a soffietto e le impostazioni predefinite al momento del posizionamento del componente per pannello a soffietto.

### Scheda Proprietà {#properties-tab-design}

![Scheda delle proprietà della finestra di dialogo Progettazione](/help/assets/accordion-design-properties.png)

* **Elementi titolo consentiti**  - Questo elenco a discesa con più selezioni definisce l’intestazione di elemento a soffietto elementi HTML che possono essere selezionati da un autore.
* **Elemento intestazione predefinito** : questo elenco a discesa definisce l’elemento HTML predefinito dell’intestazione di pannello a soffietto.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** viene utilizzata per definire quali componenti possono essere aggiunti come elementi ai pannelli nel componente per pannello a soffietto dall’autore del contenuto.

La scheda Componenti consentiti funziona allo stesso modo della scheda dello stesso nome quando [definisci i criteri e le proprietà di un contenitore di layout nell’Editor modelli.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-layout-template-author)

### Scheda Stili {#styles-tab}

Il componente per pannello a soffietto supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

## Livello dati client di Adobe {#data-layer}

Il componente per pannello a soffietto supporta [Livello dati client di Adobe.](/help/developing/data-layer/overview.md)
