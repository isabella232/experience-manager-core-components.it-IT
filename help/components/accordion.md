---
title: Componente Pannello a soffietto
description: Il componente core Pannello a soffietto consente di creare una raccolta di pannelli inclusi in un pannello a soffietto su una pagina.
role: Architect, Developer, Admin, User
exl-id: 1deb570a-3d8d-409e-805f-8460c49cf9bb
source-git-commit: e8b3e55a42b6be6262d6f51b9569c0be3e8ce6c3
workflow-type: tm+mt
source-wordcount: '1068'
ht-degree: 98%

---

# Componente Pannello a soffietto{#accordion-component}

Il componente core Pannello a soffietto consente di creare una raccolta di pannelli inclusi in un pannello a soffietto su una pagina.

## Utilizzo {#usage}

Il componente core Pannello a soffietto consente di creare una raccolta di componenti, composti come pannelli e inclusi in un Pannello a soffietto su una pagina, in modo simile al [componente Schede](tabs.md), ma con la possibilità di espandere e comprimere i pannelli.

* Le proprietà del Pannello a soffietto possono essere definite nella [finestra di dialogo per configurazione](#configure-dialog).
* L’ordine dei pannelli nel Pannello a soffietto può essere definito sia nella finestra di dialogo per configurazione che nella [finestra a comparsa seleziona pannello](#select-panel-popover).
* Le impostazioni predefinite del componente Pannello a soffietto, quando lo si aggiunge a una pagina, possono essere definite [nella finestra di dialogo per progettazione](#design-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pannello a soffietto è la v1, introdotta con la versione 2.5.0 dei Componenti core a giugno 2019, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile  con<br>[versione 2.17.4](/help/versions.md) e precedenti | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Pannello a soffietto e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_accordion_it).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pannello a soffietto [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_accordion_v1).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Collegamenti profondi a un pannello {#deep-linking}

Pannello a soffietto, [carosello,](carousel.md) e [Componenti Schede](tabs.md) supporta il collegamento diretto a un pannello all’interno del componente.

Per effettuare questo collegamento:

1. Visualizza la pagina del componente utilizzando l’opzione **[Visualizza come pubblicato](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=it#view-as-published)** nell’editor di pagine.
1. Esamina il contenuto della pagina e identifica l’ID del pannello.
   * Esempio `id="accordion-86196c94d3-item-ca319dbb0b"`
1. L’ID diventa l’ancoraggio che puoi aggiungere all’URL utilizzando un hash (`#`).
   * Esempio `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

Navigando all’URL con l’ID del pannello come ancoraggio, il browser scorre direttamente fino al componente specifico e lo visualizza. Se il pannello è configurato per non essere espanso per impostazione predefinita, viene espanso automaticamente.

## Finestra di dialogo per configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuto di definire l’elemento Pannello a soffietto, i relativi pannelli e il suo comportamento e aspetto nei confronti di chi visita la pagina.

### Scheda Elementi {#items-tab}

![Scheda Elementi della finestra di dialogo per modifica del componente Pannello a soffietto](/help/assets/accordion-edit-items.png)

Utilizza il pulsante **Aggiungi** per aprire il selettore di componenti e scegliere quale componente aggiungere come pannello. Una volta aggiunto, all’elenco viene aggiunta una voce che contiene le seguenti colonne:

* **Icona**: l’icona del tipo di componente del pannello per facilitarne l’identificazione nell’elenco. Passa il puntatore del mouse sulla voce per visualizzare il nome completo del componente sotto forma di descrizione comando.
* **Descrizione**: il testo descrittivo del pannello; per impostazione predefinita è il nome del componente selezionato come pannello.
* **Elimina**: tocca o fai clic per eliminare il pannello dal componente Pannello a soffietto.
* **Ridisponi**: tocca o fai clic e trascina per modificare l’ordine dei pannelli.

>[!TIP]
>
>Se il riquadro di visualizzazione della pagina viene ridotto in modo che la finestra di dialogo per modifica diventi a schermo intero, il pulsante **Aggiungi** sarà nascosto. I componenti possono comunque essere aggiunti al componente Pannello a soffietto [trascinandoli dal browser dei componenti e rilasciandoli sul componente Pannello a soffietto nell’editor di pagine](https://helpx.adobe.com/it/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent).

### Scheda Proprietà {#properties-tab}

![Scheda Proprietà della finestra di dialogo per modifica del componente Pannello a soffietto](/help/assets/accordion-edit-properties.png)

* **Espansione di un singolo elemento**: se selezionata, questa opzione consente di espandere un singolo elemento del Pannello a soffietto alla volta. L’espansione di un singolo elemento determinerà la compressione di tutti gli altri.
* **Elementi espansi**: questa opzione definisce gli elementi che vengono espansi per impostazione predefinita al caricamento della pagina.
   * Quando si seleziona **Espansione di un singolo elemento**, è necessario selezionare un pannello. Per impostazione predefinita, viene selezionato il primo pannello.
   * Quando **Espansione di un singolo elemento** non è selezionata, questa opzione è a selezione multipla ed è facoltativa.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

## Finestra a comparsa selezione pannello {#select-panel-popover}

L’autore di contenuto può utilizzare l’opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a un altro pannello da modificare e per modificare facilmente l’ordine dei pannelli nel Pannello a soffietto.

![Icona Seleziona pannello](/help/assets/select-panel-icon.png)

Dopo aver selezionato l’opzione **Seleziona pannello** nella barra degli strumenti del componente, i pannelli del Pannello a soffietto configurati vengono visualizzati come elenco a discesa.

![Finestra a comparsa selezione pannello](/help/assets/select-panel-popover.png)

* L’elenco viene ordinato in base alla disposizione assegnata ai pannelli, che si evidenzia nella numerazione.
* Il tipo di componente del pannello viene visualizzato per primo, seguito dalla descrizione del pannello in caratteri più chiari.
* Toccando o facendo clic su una voce nel menu a discesa, nell’editor viene visualizzato il pannello corrispondente.
* I pannelli possono essere riposizionati tramite le maniglie di trascinamento.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore di contenuto che utilizza il componente Pannello a soffietto e le impostazioni predefinite scelte al momento del posizionamento del Pannello a soffietto.

### Scheda Proprietà {#properties-tab-design}

![Scheda Proprietà della finestra di dialogo per progettazione](/help/assets/accordion-design-properties.png)

* **Elementi intestazione consentiti**: questo elenco a discesa a selezione multipla definisce gli elementi HTML per l’intestazione del Pannello a soffietto che possono essere selezionati da un autore.
* **Elemento intestazione predefinito**: questo elenco a discesa definisce l’elemento HTML predefinito per l’intestazione del Pannello a soffietto.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** viene utilizzata per definire quali componenti possono essere aggiunti come elementi al Pannello a soffietto dall’autore di contenuto.

La scheda Componenti consentiti funziona come la scheda con lo stesso nome utilizzata per [definire i criteri e le proprietà di un Contenitore layout nell’editor di modelli.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it#editing-a-template-layout-template-author)

### Scheda Stili {#styles-tab}

Il componente Pannello a soffietto supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

## Adobe Client Data Layer {#data-layer}

Il componente Pannello a soffietto supporta [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
