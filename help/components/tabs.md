---
title: Componente Schede
description: Il componente Schede consente di creare più schede per disporre il contenuto di una pagina.
role: Architect, Developer, Admin, User
exl-id: 0031c5f3-447c-4932-898f-2f453801e492
source-git-commit: d435e82d5950336c66997399829e3baf23f170c0
workflow-type: ht
source-wordcount: '1028'
ht-degree: 100%

---

# Componente Schede {#tabs-component}

Il componente core Schede consente di organizzare il contenuto in più schede.

## Utilizzo {#usage}

Il componente Schede consente all’autore di contenuto di organizzare il contenuto della pagina in più schede.

La [finestra di dialogo per modifica](#edit-dialog) consente all’autore di contenuto di definire più schede e di impostare la scheda attiva. Utilizzando la [finestra di dialogo per progettazione](#design-dialog), l’autore del modello può definire quali componenti possono essere aggiunti alle schede e personalizzarne gli stili.

>[!TIP]
>
>Sono supportati i componenti Schede nidificati (schede all’interno di schede).
>
>I componenti Schede semplici (non nidificati) possono essere posizionati/selezionati utilizzando la [struttura del contenuto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=it#content-tree), ma non è possibile utilizzare le schede nidificate.

## Collegamenti profondi a un pannello {#deep-linking}

I componenti Schede e [Pannello a soffietto](accordion.md) supportano il collegamento diretto a un pannello all’interno del componente.

Per effettuare questo collegamento:

1. Visualizza la pagina del componente utilizzando l’opzione **[Visualizza come pubblicato](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=it#view-as-published)** nell’editor di pagine.
1. Esamina il contenuto della pagina e identifica l’ID del pannello.
   * Esempio `id="accordion-86196c94d3-item-ca319dbb0b"`
1. L’ID diventa l’ancoraggio che puoi aggiungere all’URL utilizzando un hash (`#`).
   * Esempio `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

Navigando all’URL con l’ID del pannello come ancoraggio, il browser scorre direttamente fino al componente specifico e lo visualizza. Se il pannello è configurato per non essere espanso per impostazione predefinita, viene espanso automaticamente.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Schede è la v1, introdotta con la versione 2.2.0 dei Componenti core a ottobre 2018, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Schede e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_tabs_it).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Schede [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_tabs_v1_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per modifica {#edit-dialog}

La finestra di dialogo per modifica consente all’autore di contenuto di aggiungere, rinominare e ridisporre le schede e di definire la scheda attiva.

### Scheda Elementi {#items-tab}

![Scheda Elementi della finestra di dialogo per modifica del componente Schede](/help/assets/tabs-edit-items.png)

Utilizza il pulsante **Aggiungi** per aprire il selettore di componenti e scegliere quale componente aggiungere come scheda. Una volta aggiunto, all’elenco viene aggiunta una voce che contiene le seguenti colonne:

* **Icona**: l’icona del tipo di componente della scheda per una facile identificazione nell’elenco. Passa il puntatore del mouse sulla voce per visualizzare il nome completo del componente sotto forma di descrizione comando.
* **Descrizione**: la descrizione utilizzata come testo della scheda; per impostazione predefinita è il nome del componente selezionato per la scheda.
* **Elimina**: tocca o fai clic per eliminare la scheda dal componente Schede.
* **Ridisponi**: tocca o fai clic e trascina per modificare l’ordine delle schede.

>[!TIP]
>
>Se il riquadro di visualizzazione della pagina viene ridotto in modo che la finestra di dialogo per modifica diventi a schermo intero, il pulsante **Aggiungi** sarà nascosto. I componenti possono comunque essere aggiunti al componente Schede [trascinandoli dal browser dei componenti e rilasciandoli sul componente Schede nell’editor di pagine](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=it#inserting-a-component).

### Scheda Proprietà {#properties-tab}

![Scheda Proprietà della finestra di dialogo per modifica del componente Schede](/help/assets/tabs-edit-properties.png)

* **Elemento attivo**: l’autore di contenuto può definire quale scheda è attiva al caricamento della pagina.
   * Con l’opzione **Impostazione predefinita**, viene selezionata la prima scheda.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità della finestra di dialogo per modifica del componente Schede](/help/assets/tabs-edit-accessibility.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette di [accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente.

* **Etichetta**: il valore di un attributo dell’etichetta ARIA del componente

## Seleziona pannello {#select-panel}

L’autore di contenuto può utilizzare l’opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a un pannello diverso da modificare e per cambiare facilmente l’ordine delle schede.

![Icona Seleziona pannello](/help/assets/select-panel-icon.png)

Dopo aver selezionato l’opzione **Seleziona pannello** nella barra degli strumenti del componente, le schede configurate vengono visualizzate come un elenco a discesa.

* L’elenco viene ordinato in base alla disposizione assegnata alle schede, che si evidenzia nella numerazione.
* Il tipo di componente della scheda viene visualizzato per primo, seguito dalla descrizione della scheda in caratteri più chiari.

![Finestra a comparsa selezione pannello](/help/assets/select-panel-popover.png)

* Toccando o facendo clic su una voce nel menu a discesa, nell’editor viene visualizzata la scheda corrispondente.
* Le schede possono essere riposizionate tramite le maniglie di trascinamento.

>[!NOTE]
>
>Le schede non sono selezionabili dall’autore in modalità **Modifica**. Utilizza la modalità **[Anteprima](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=it#preview-mode)** oppure l’opzione **[Visualizza come pubblicato](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=it#view-as-published)** per interagire con le schede come farebbe un normale lettore del contenuto pubblicato.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire quali componenti possono essere aggiunti come elementi al componente Schede e quali stili personalizzati sono disponibili per l’autore di contenuto.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** viene utilizzata per definire quali componenti possono essere aggiunti come elementi del componente Schede dall’autore di contenuto.

La scheda Componenti consentiti funziona come la scheda con lo stesso nome utilizzata per [definire i criteri e le proprietà di un Contenitore layout nell’editor di modelli.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it)

### Scheda Stili {#styles-tab}

Il componente Schede supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

## Adobe Client Data Layer {#data-layer}

Il componente Schede supporta [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
