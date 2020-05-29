---
title: Componente testo modulo
description: Il componente Testo modulo componente principale consente l’immissione di testo del modulo per l’invio.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 7%

---


# Componente testo modulo{#form-text-component}

Il componente Testo modulo componente principale consente l’immissione di testo del modulo per l’invio.

## Utilizzo {#usage}

Il componente Testo modulo consente l’invio di diversi tipi di testo e deve essere utilizzato insieme al componente [Contenitore di](form-container.md)moduli. Il tipo di convalida del testo, etichette e messaggi di aiuto può essere definito dall&#39;editor di contenuti nella finestra di dialogo [di](#configure-dialog)configurazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Testo modulo è v2, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | - | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-text-v1.md) | Compatibile | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Testo modulo e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visitare la Libreria [](https://adobe.com/go/aem_cmp_library_form_text)componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Testo modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_text_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il tipo di testo da inserire, nonché i valori e le etichette predefiniti.

### Scheda Proprietà {#properties-tab}

![scheda Proprietà](/help/assets/form-text-edit-properties.png)

* **Vincolo** - Il tipo di testo da inserire e su cui verrà convalidato il comando
   * **Testo**
   * **Area testo**
   * **E-mail**
   * **Tel.**
   * **Data**
   * **Numero**
   * **Password**
* **Righe** di testo - Numero di righe da visualizzare nell&#39;area di testo (solo se **Vincolo** è impostato su **Area** di testo)
* **Etichetta** - Etichetta che verrà visualizzata per il campo
* **Nascondere l&#39;etichetta per la visualizzazione** - Necessario se l&#39;etichetta è necessaria solo a scopo di accessibilità e non immette ulteriori informazioni visive sul campo
* **Nome** elemento - Il nome del campo inviato con i dati del modulo
* **Valore** - Valore predefinito precompilato nel campo
* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

### Scheda {#about-tab}

![Scheda Informazioni](/help/assets/form-text-edit-about.png)

* **Messaggio** della Guida - Suggerimento per l&#39;utente di ciò che può essere immesso nel campo
* **Visualizza messaggio di aiuto come segnaposto** - Per visualizzare il messaggio di aiuto all&#39;interno del modulo di input quando è vuoto e non è attivo

### Scheda Vincoli {#constraints-tab}

![Scheda Vincoli](/help/assets/form-text-edit-constraints.png)

* **Messaggio vincolo**
   * Messaggio visualizzato come descrizione comando quando si invia il modulo, se il valore non convalida il tipo scelto
   * Non visualizzato per i tipi di vincolo **Testo** e Area **di** testo
* **Obbligatorio** - Se selezionato, l&#39;utente deve compilare un valore prima di inviare il modulo
   * **Messaggio** richiesto - Messaggio visualizzato come suggerimento se il campo viene lasciato vuoto
* **Rendi sola** lettura - Se selezionato, l&#39;utente non può modificare il valore del campo

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Testo modulo supporta AEM [Style System](/help/get-started/authoring.md#component-styling).
