---
title: Componente pulsante
description: Il componente Pulsante componente core consente di creare e visualizzare un pulsante.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 4%

---


# Componente pulsante{#button-component}

Il componente Pulsante componente di base consente la configurazione e la visualizzazione di un pulsante su una pagina.

## Utilizzo {#usage}

Il componente Pulsante componente di base consente di includere un pulsante in una pagina.

* Le proprietà del pulsante possono essere selezionate nella finestra di dialogo di [configurazione](#configure-dialog).
* Gli stili per il componente Pulsante possono essere definiti nella finestra di dialogo [progettazione](#design-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pulsante è v1, introdotto con la release 2.5.0 dei componenti core a giugno 2019, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente Pulsante ed esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library_button).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pulsante [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_button_v1).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il pulsante e il comportamento del visitatore e la sua visualizzazione sulla pagina.

### Scheda Proprietà {#properties-tab}

![scheda Proprietà della finestra di dialogo di modifica del componente Pulsante](/help/assets/button-edit-properties.png)

* **Testo**  - Testo da visualizzare sul pulsante
* **Collegamento** : collegamento a una pagina di contenuto all’interno di AEM, una risorsa esterna o un ancoraggio
   * Utilizzare la finestra di dialogo **Selezione** per scegliere un percorso all&#39;interno di AEM.
* **Icona**  - Identificatore per la visualizzazione di un&#39;icona nel pulsante
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità della finestra di dialogo di modifica del componente Pulsante](/help/assets/button-edit-accessibility.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette [Accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente.

* **Etichetta**  - Valore di un attributo etichetta ARIA per il componente

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Immagine supporta il AEM [Sistema di stile](/help/get-started/authoring.md#component-styling).
