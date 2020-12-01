---
title: Scarica componente
description: Il componente per il download dei componenti core consente di creare un’opzione di download su una pagina.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 2%

---


# Scarica componente{#download-component}

Il componente per il download dei componenti core consente di creare un’opzione di download su una pagina.

## Utilizzo {#usage}

Il componente Download del componente core consente di includere in una pagina un’opzione di download e la risorsa associata.

* Le proprietà dell&#39;opzione di download possono essere selezionate nella finestra di dialogo [configura](#configure-dialog).
* I valori predefiniti per il componente di download possono essere definiti nella finestra di dialogo di progettazione [](#design-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Download è v1, introdotto con la release 2.5.0 dei componenti core a giugno 2019, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente Download ed esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visita la [Libreria componenti](https://adobe.com/go/aem_cmp_library_download).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Download [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_download_v1).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire l’elemento da scaricare e il suo funzionamento e la sua visualizzazione sulla pagina da parte di un visitatore.

![Scheda Risorsa della finestra di dialogo di modifica del componente Download](/help/assets/download-edit-asset.png)

### Scheda Risorsa {#asset-tab}

La selezione di una risorsa di download è molto simile alla funzionalità del [componente immagine](image.md) e utilizza AEM DAM.

* **Scarica risorsa**
   * Rilasciate una risorsa dal [browser delle risorse](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) o toccate l&#39;opzione **Browse** per caricarla da un file system locale.
   * Toccate o fate clic su **Cancella** per deselezionare l&#39;immagine attualmente selezionata.
   * Toccate o fate clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) nell&#39;editor risorse.

### Scheda Proprietà {#properties-tab}

![scheda Proprietà della finestra di dialogo di modifica del componente Download](/help/assets/download-edit-properties.png)

* **Titolo**  - Visualizzato come titolo per l’elemento di download
   * **Ottieni titolo da risorsa**  DAM: se questa opzione è selezionata, il titolo viene popolato automaticamente con il titolo della risorsa DAM.
* **Descrizione**  - Visualizzato come sottotitolo descrittivo dell&#39;elemento di download
   * **Ottieni una descrizione dalla risorsa**  DAM: se questa opzione è selezionata, la descrizione della risorsa DAM viene compilata automaticamente con la relativa descrizione.
* **Testo**  azione: viene visualizzato come testo di azione per l’elemento di download
   * Questo campo è richiesto quando si carica una risorsa dal file system.
   * **Visualizza in linea**  - Se selezionato, il testo dell&#39; **azione fornito verrà** visualizzato in linea.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore del contenuto che utilizza il componente Download.

### Scheda Proprietà {#properties-tab-design}

![Finestra di dialogo Progettazione del componente Download](/help/assets/download-design.png)

* **Consenti caricamento dal file system** : consente all&#39;autore del contenuto di caricare una risorsa dal file system locale come risorsa da scaricare.
   * Il valore predefinito è deselezionato.
* **Tipo**  titolo - L&#39;elemento HTML utilizzato per il titolo del componente Download.
   * Se non è selezionato alcun valore, il valore predefinito è H3.
* **Visualizza dimensioni**  file: se è selezionata, la dimensione del file della risorsa verrà visualizzata nel componente Download.
   * Il valore predefinito è selezionato.
* **Formato**  file di visualizzazione: se è selezionata questa opzione, il formato del file della risorsa verrà visualizzato nel componente di download.
   * Il valore predefinito è selezionato.
* **Nome**  file visualizzato: se selezionato, il nome del file della risorsa verrà visualizzato nel componente Download.
   * Il valore predefinito è selezionato.

### Scheda Stili {#styles-tab}

Il componente Immagine supporta il AEM [Sistema di stile](/help/get-started/authoring.md#component-styling).
