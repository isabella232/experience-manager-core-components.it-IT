---
title: Componente Schede
description: Il componente Tabulazioni consente di creare più schede per disporre il contenuto su una pagina.
translation-type: tm+mt
source-git-commit: 65f900ad6759206a13f2bda6169900f62d968d8d

---


# Componente Schede

Il componente core Tabs Component consente l&#39;organizzazione del contenuto su più schede.

## Utilizzo {#usage}

Il componente Tabulazioni consente all’autore del contenuto di organizzare il contenuto della pagina all’interno di più schede.

La finestra di dialogo [di](#edit-dialog) modifica consente all’autore del contenuto di definire più schede e di impostare la scheda attiva. Utilizzando la finestra di dialogo [di](#design-dialog)progettazione, l&#39;autore del modello può definire quali componenti possono essere aggiunti alle schede e personalizzare gli stili.

>[!NOTE]
>
>Sono supportati i componenti scheda nidificati (schede all’interno delle schede).
>
>È possibile individuare/selezionare componenti scheda semplici (non nidificati) utilizzando la struttura [del](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html#content-tree)contenuto, ma non è possibile utilizzare schede nidificate.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Tabs è v1, introdotto con la release 2.2.0 dei componenti core a ottobre 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM come servizio cloud |
|--- |--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Tabs e per vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visita la Libreria [](https://adobe.com/go/aem_cmp_library_tabs)Componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Tabs [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_tabs_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di creare, rinominare e ridisporre le schede, nonché definire la scheda attiva.

### Scheda Articoli {#items-tab}

![](assets/screen-shot-2019-08-29-12.28.16.png)

Usate il pulsante **Aggiungi** per aprire il selettore dei componenti e scegliere quale componente aggiungere come scheda. Una volta aggiunta, una voce viene aggiunta all&#39;elenco, che contiene le seguenti colonne:

* **Icona** - L&#39;icona del tipo di componente della scheda per una facile identificazione nell&#39;elenco. Passate il puntatore del mouse sopra per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione** - Descrizione utilizzata come testo della scheda, con impostazione predefinita sul nome del componente selezionato per la scheda.
* **Elimina** - Toccate o fate clic per eliminare la scheda dal componente scheda.
* **Ridisponi** - Toccate o fate clic e trascinate per riordinare l&#39;ordine delle schede.

>[!TIP]
>
>Se la vista della pagina viene ridotta e la finestra di dialogo di modifica diventa a schermo intero, il pulsante **Aggiungi** viene nascosto. Per aggiungere i componenti al componente Tabulazioni, [trascinateli dal Browser componenti e trascinateli sul componente Tabulazioni nell’editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component)di pagina.

### Scheda Proprietà {#properties-tab}

![](assets/screen-shot-2019-08-29-12.28.32.png)

Nella scheda **Proprietà** , l&#39;autore del contenuto può definire quale scheda è attiva al caricamento della pagina. Con l&#39;opzione **Predefinito** , verrà selezionata la prima scheda.

### Scheda Accessibilità {#accessibility-tab}

![](assets/screen-shot-2019-08-29-12.28.40.png)

Nella scheda **Accessibilità** , è possibile impostare i valori per le etichette di accessibilità [](https://www.w3.org/WAI/standards-guidelines/aria/) ARIA per il componente.

* **Etichetta** - Valore di un attributo etichetta ARIA per il componente

## Select Panel {#select-panel}

L’autore del contenuto può usare l’opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a un altro pannello e riordinare facilmente l’ordine delle schede.

![](assets/screenshot_2018-10-11at165417.png)

Dopo aver selezionato l’opzione **Seleziona pannello** nella barra degli strumenti del componente, le schede configurate vengono visualizzate come un elenco a discesa.

* L&#39;elenco è ordinato dalla disposizione assegnata delle schede e si riflette nella numerazione.
* Il tipo di componente della scheda viene visualizzato per primo, seguito dalla descrizione della scheda con un carattere più chiaro.

![](assets/screenshot_2018-10-11at165154.png)

* Toccando o facendo clic su una voce nel menu a discesa, la vista nell’editor passa a tale scheda.
* Le schede possono essere ridisposte in posizione utilizzando le maniglie di trascinamento.

>[!NOTE]
>
>Le schede non sono selezionabili dall&#39;autore in modalità **Modifica** . Utilizzate la modalità **[Anteprima](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)**o l&#39;opzione**[ Visualizza come pubblicato](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** per interagire con le schede come lettori del contenuto pubblicato.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire quali componenti possono essere aggiunti al componente Tabulazioni, nonché definire quali stili personalizzati sono disponibili per l&#39;autore del contenuto.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda Componenti **** consentiti viene utilizzata per definire quali componenti possono essere aggiunti al componente Tabulazioni dall&#39;autore del contenuto come elementi.

La scheda Componenti consentiti funziona nello stesso modo della scheda con lo stesso nome quando si [definisce il criterio e le proprietà di un Contenitore di layout nell&#39;Editor modelli.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Scheda Stili {#styles-tab}

Il componente Tabs supporta AEM [Style System](authoring.md#component-styling).
