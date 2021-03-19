---
title: Componente Schede
description: Il componente Tabulazioni consente di creare più schede per disporre il contenuto di una pagina.
role: Architetto, Sviluppatore, Amministratore, Business Practices
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 2%

---


# Componente Schede {#tabs-component}

Il componente Schede componenti core consente l’organizzazione del contenuto su più schede.

## Utilizzo {#usage}

Il componente Tabulazioni consente all’autore del contenuto di organizzare il contenuto della pagina all’interno di più schede.

La [finestra di dialogo di modifica](#edit-dialog) consente all’autore del contenuto di definire più schede e di impostare la scheda attiva. Utilizzando la finestra di dialogo [progettazione](#design-dialog), l’autore del modello può definire quali componenti possono essere aggiunti alle schede e personalizzare gli stili.

>[!TIP]
>
>Sono supportati i componenti scheda nidificati (schede all’interno delle schede).
>
>I componenti scheda semplici (non nidificati) possono essere posizionati/selezionati utilizzando la [struttura contenuto](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html#content-tree), ma non è possibile utilizzare le schede nidificate.

## Collegamenti profondi a un pannello {#deep-linking}

Le schede e i [Componenti pannello a soffietto](accordion.md) supportano il collegamento diretto a un pannello all’interno del componente.

Per effettuare ciò:

1. Visualizza la pagina con il componente utilizzando l&#39;opzione **[Visualizza come pubblicato](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** nell&#39;editor di pagine.
1. Inspect il contenuto della pagina e identifica l’ID del pannello.
   * Esempio `id="accordion-86196c94d3-item-ca319dbb0b"`
1. L’ID diventa l’ancoraggio che puoi aggiungere all’URL utilizzando un hash (`#`).
   * Esempio `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

Navigando all’URL con l’ID del pannello come ancoraggio, il browser scorre direttamente fino al componente specifico e visualizza il pannello specificato. Se il pannello è configurato per non essere espanso per impostazione predefinita, viene espanso automaticamente.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Tabs è la v1, introdotta con la versione 2.2.0 dei componenti core a ottobre 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente Tabs e dell’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_tabs) .

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Tabs [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_tabs_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di creare, rinominare e ridisporre le schede e di definire la scheda attiva.

### Scheda Elementi {#items-tab}

![Scheda della finestra di dialogo Modifica elementi del componente Schede](/help/assets/tabs-edit-items.png)

Utilizza il pulsante **Aggiungi** per aprire il selettore dei componenti e scegliere quale componente aggiungere come scheda. Una volta aggiunta, una voce viene aggiunta all’elenco, che contiene le colonne seguenti:

* **Icona** : l’icona del tipo di componente della scheda per una facile identificazione nell’elenco. Passa il puntatore del mouse per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione** : descrizione utilizzata come testo della scheda, con impostazione predefinita sul nome del componente selezionato per la scheda.
* **Elimina** : tocca o fai clic per eliminare la scheda dal componente scheda.
* **Ridisponi** : tocca o fai clic e trascina per riordinare l’ordine delle schede.

>[!TIP]
>
>Se la finestra di visualizzazione della pagina viene ridotta in modo che la finestra di dialogo di modifica diventi a schermo intero, il pulsante **Aggiungi** sarà nascosto. I componenti possono ancora essere aggiunti al componente Tabs trascinando dal browser Componenti e rilasciando il componente Tabs nell&#39;editor pagina](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component).[

### Scheda Proprietà {#properties-tab}

![Scheda delle proprietà della finestra di dialogo di modifica del componente Tabs](/help/assets/tabs-edit-properties.png)

* **Elemento attivo** : l’autore del contenuto può definire quale scheda è attiva al caricamento della pagina.
   * Con l’opzione **Predefinito**, viene selezionata la prima scheda.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

### Scheda Accessibilità {#accessibility-tab}

![Scheda della finestra di dialogo di accesso facilitato del componente Tabs](/help/assets/tabs-edit-accessibility.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette [Accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente.

* **Etichetta**  - Valore di un attributo dell’etichetta ARIA per il componente

## Seleziona il pannello {#select-panel}

L’autore del contenuto può utilizzare l’opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a un altro pannello per la modifica e per ridisporre facilmente l’ordine delle schede.

![Icona Seleziona pannello](/help/assets/select-panel-icon.png)

Dopo aver selezionato l&#39;opzione **Seleziona pannello** nella barra degli strumenti del componente, le schede configurate vengono visualizzate come un elenco a discesa.

* L&#39;elenco è ordinato dalla disposizione assegnata delle schede e si riflette nella numerazione.
* Il tipo di componente della scheda viene visualizzato per primo, seguito dalla descrizione della scheda con font più chiaro.

![Selezione pover del pannello](/help/assets/select-panel-popover.png)

* Toccando o facendo clic su una voce nel menu a discesa, la visualizzazione nell’editor passa a tale scheda.
* Le linguette possono essere ridisposte in posizione utilizzando le maniglie di trascinamento.

>[!NOTE]
>
>Le schede non sono selezionabili dall&#39;autore in modalità **Modifica**. Utilizza la modalità **[Anteprima](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)** o l&#39;opzione **[Visualizza come pubblicato](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** per interagire con le schede come lettore del contenuto pubblicato.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire quali componenti possono essere aggiunti come elementi al componente tab e di definire quali stili personalizzati sono disponibili per l’autore del contenuto.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** viene utilizzata per definire quali componenti possono essere aggiunti dall’autore del contenuto al componente delle schede come elementi.

La scheda Componenti consentiti funziona allo stesso modo della scheda dello stesso nome quando [definisci i criteri e le proprietà di un contenitore di layout nell’Editor modelli.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Scheda Stili {#styles-tab}

Il componente Tabs supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

## Livello dati client di Adobe {#data-layer}

Il componente Tabs supporta [Livello dati client di Adobe.](/help/developing/data-layer/overview.md)
