---
title: Componente testo modulo
description: Il componente Testo modulo componente principale consente l’immissione di testo del modulo per l’invio.
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 7%

---


# Componente testo modulo{#form-text-component}

Il componente Testo modulo componente principale consente l’immissione di testo del modulo per l’invio.

## Utilizzo {#usage}

Il componente Testo modulo consente l’invio di diversi tipi di testo e deve essere utilizzato insieme al componente contenitore [modulo](form-container.md). Il tipo di convalida del testo, etichette e messaggi della guida può essere definito dall&#39;editor di contenuti nella finestra di dialogo [configura](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Testo modulo è v2, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-text-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente Testo modulo e per vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library_form_text).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Testo modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_text_v2).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il tipo di testo da inserire, nonché i valori e le etichette predefiniti.

### Scheda Proprietà {#properties-tab}

![scheda Proprietà](/help/assets/form-text-edit-properties.png)

* **Vincolo** : il tipo di testo da inserire e su cui verrà convalidato il comando
   * **Testo**
   * **Area testo**
   * **E-mail**
   * **Tel.**
   * **Data**
   * **Numero**
   * **Password**
* **Righe**  di testo - Numero di righe da visualizzare nell&#39;area di testo (visualizzate solo se  **** Limite è impostata su Area **di** testo)
* **Etichetta**  - Etichetta che verrà visualizzata per il campo
* **Nascondere l&#39;etichetta per la visualizzazione**  - Necessario se l&#39;etichetta è necessaria solo a scopo di accessibilità e non invia ulteriori informazioni visive sul campo
* **Nome**  elemento: il nome del campo inviato con i dati del modulo
* **Valore**  - Valore predefinito precompilato nel campo
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

### Informazioni sulla scheda {#about-tab}

![Scheda Informazioni](/help/assets/form-text-edit-about.png)

* **Messaggio**  della Guida: un suggerimento per l&#39;utente sulle informazioni che è possibile immettere nel campo
* **Visualizza messaggio di aiuto come segnaposto** : per visualizzare il messaggio di aiuto all&#39;interno del modulo di input quando è vuoto e non è attivo

### Scheda Vincoli {#constraints-tab}

![Scheda Vincoli](/help/assets/form-text-edit-constraints.png)

* **Messaggio vincolo**
   * Messaggio visualizzato come descrizione comando quando si invia il modulo, se il valore non convalida il tipo scelto
   * Non visualizzato per i tipi di vincolo **Testo** e **Area di testo**
* **Obbligatorio** : se selezionato, l&#39;utente deve compilare un valore prima di inviare il modulo
   * **Messaggio**  richiesto - Messaggio visualizzato come suggerimento se il campo viene lasciato vuoto
* **Rendi sola**  lettura - Se selezionato, l&#39;utente non può modificare il valore del campo

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Testo modulo supporta il AEM [Sistema di stile](/help/get-started/authoring.md#component-styling).
