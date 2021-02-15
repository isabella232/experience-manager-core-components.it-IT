---
title: Componente carosello
description: Il componente Carosello consente all’autore del contenuto di presentare il contenuto in un carosello a rotazione.
translation-type: tm+mt
source-git-commit: d3ebcea5fa1523c1a986841cd3d1a64e16e85f6d
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 1%

---


# Componente carosello{#carousel-component}

Il componente Carosello dei componenti core consente all’autore del contenuto di presentare il contenuto in un carosello navigabile.

## Utilizzo {#usage}

Con il componente Carosello, l’autore del contenuto organizza il contenuto in un carosello rotante di diapositive.

La [finestra di dialogo di modifica](#edit-dialog) consente all&#39;autore del contenuto di creare, assegnare un nome e ordinare più diapositive, nonché attivare la transizione automatica con ritardo. Utilizzando la finestra di dialogo [progettazione](#design-dialog), l&#39;autore del modello può definire quali componenti possono essere aggiunti al carosello, attivare o disattivare le transizioni automatiche e personalizzare gli stili.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Carosello è v1, introdotto con la release 2.2.0 dei componenti core a ottobre 2018, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente Carosello ed esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library_carousel).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Carosello [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_carousel_v1).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di aggiungere, rinominare e ridisporre le diapositive nonché di definire le impostazioni di transizione automatica.

### Scheda Articoli {#items-tab}

![Scheda Elementi della finestra di dialogo di modifica del componente Carosello](/help/assets/carousel-edit-items.png)

Utilizzate il pulsante **Aggiungi** per aprire il selettore dei componenti e scegliere quale componente aggiungere come scheda. Una volta aggiunta, una voce viene aggiunta all&#39;elenco, che contiene le seguenti colonne:

* **Icona**  - L&#39;icona del tipo di componente della scheda per facilitarne l&#39;identificazione nell&#39;elenco. Passate il puntatore del mouse sopra per visualizzare il nome completo del componente come una descrizione comando.
* **Descrizione**  - Descrizione utilizzata come testo della scheda, con impostazione predefinita sul nome del componente selezionato per la scheda.
* **Elimina**  - Toccate o fate clic per eliminare la scheda dal componente Tabulazioni.
* **Riordina**  - Toccate o fate clic e trascinate per ordinare le schede.

>[!TIP]
>
>Se la vista della pagina viene ridotta in modo che la finestra di dialogo di modifica diventi a schermo intero, il pulsante **Aggiungi** verrà nascosto. Per aggiungere i componenti al componente Carosello, [trascinare dal browser Componenti e rilasciare il componente Carosello nell&#39;editor pagina](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser).

### Scheda Proprietà {#properties-tab}

![scheda Proprietà della finestra di dialogo di modifica del componente Carosello](/help/assets/carousel-edit-properties.png)

Nella scheda **Proprietà**, l&#39;autore del contenuto può impostare le diapositive sulla transizione automatica.

* **Transizione automatica delle diapositive** : quando è attiva, il componente passa automaticamente alla diapositiva successiva dopo un ritardo specificato.
* **Ritardo**  transizione: quando è selezionata l&#39;opzione Transizione automatica diapositive, questo valore viene utilizzato per definire il ritardo tra le transizioni (in millisecondi).
* **Disattiva pausa automatica al passaggio del mouse** : quando è selezionata l&#39;opzione  **Transizione automatica** della diapositiva, la transizione del carosello si interrompe automaticamente ogni volta che il cursore passa sul carosello. Selezionate questa opzione per evitare che la transizione venga messa in pausa.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

>[!NOTE]
>
>I controlli di avanzamento delle diapositive non sono attivati in modalità **Modifica**. Utilizzate la modalità [**Anteprima**](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode) o l&#39;opzione **[Visualizza come pubblicato](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** per interagire con il carosello come lettore del contenuto pubblicato.
>
>La funzione di avanzamento automatico non è abilitata in modalità **Modifica**. Utilizzate l&#39;opzione **[Visualizza come pubblicato](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** per visualizzare la funzione di avanzamento automatico come lettore del contenuto pubblicato.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità della finestra di dialogo di modifica del componente Carosello](/help/assets/carousel-edit-accessibility.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette [Accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente.

* **Etichetta**  - Valore di un attributo etichetta ARIA per il componente

## Seleziona pannello {#select-panel}

L’autore del contenuto può utilizzare l’opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a un’altra diapositiva da modificare e per riordinare facilmente l’ordine delle diapositive.

![Seleziona l’icona del pannello](/help/assets/select-panel-icon.png)

Dopo aver selezionato l&#39;opzione **Seleziona pannello** nella barra degli strumenti del componente, le diapositive configurate vengono visualizzate come un elenco a discesa.

* L&#39;elenco è ordinato dalla disposizione assegnata delle diapositive e si riflette nella numerazione.
* Il tipo di componente della diapositiva viene visualizzato per primo, seguito dalla descrizione della diapositiva con il carattere più chiaro.

![Seleziona pannello](/help/assets/select-panel-popover.png)

* Toccando o facendo clic su una voce nel menu a discesa, passa alla diapositiva la vista nell’editor.
* La diapositiva può essere riordinata nella stessa posizione utilizzando le maniglie di trascinamento.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire quali componenti possono essere aggiunti al componente carosello come diapositive, nonché definire le impostazioni predefinite per la transizione automatica e quali stili personalizzati sono disponibili per l’autore del contenuto.

### Scheda Proprietà {#properties-tab-1}

La scheda **Proprietà** viene utilizzata per definire le impostazioni predefinite per le transizioni di diapositiva quando un autore di contenuto aggiunge il componente carosello a una pagina.

![Finestra di dialogo Progettazione del componente Carosello](/help/assets/carousel-design.png)

* **Transizione automatica diapositive**  - Definisce se per impostazione predefinita l’opzione per spostare automaticamente il carosello nella diapositiva successiva è abilitata quando l’autore del contenuto aggiunge il componente carosello a una pagina.
* **Ritardo**  transizione - Definisce il valore predefinito del ritardo di transizione tra le diapositive (in millisecondi) quando un autore di contenuto aggiunge il componente carosello a una pagina.
* **Disattiva pausa automatica al passaggio del mouse**  - Definisce se per impostazione predefinita l&#39;opzione per disattivare la pausa automatica delle diapositive è abilitata quando l&#39;autore del contenuto seleziona  **automaticamente** le diapositive di transizione.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** viene utilizzata per definire quali componenti possono essere aggiunti al componente Carosello dall&#39;autore del contenuto come diapositive.

La scheda Componenti consentiti funziona nello stesso modo della scheda con lo stesso nome quando si definisce il criterio e le proprietà di un Contenitore di layout nell&#39;Editor modelli.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)[

### Scheda Stili {#styles-tab}

Il componente Carosello supporta il AEM [Sistema di stile](/help/get-started/authoring.md#component-styling).

## Livello dati client  Adobe {#data-layer}

Il componente Carosello supporta il [ livello dati client Adobe.](/help/developing/data-layer/overview.md)
