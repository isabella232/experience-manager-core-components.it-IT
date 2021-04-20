---
title: Scarica componente
description: Il componente Download del componente core consente di creare un’opzione di download su una pagina.
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 2%

---


# Scarica componente{#download-component}

Il componente Download del componente core consente di creare un’opzione di download su una pagina.

## Utilizzo {#usage}

Il componente Download del componente core consente di includere in una pagina un’opzione di download e la relativa risorsa associata.

* Le proprietà dell&#39;opzione di download possono essere selezionate nella finestra di dialogo [configura](#configure-dialog).
* I valori predefiniti per il componente download possono essere definiti nella finestra di dialogo [progettazione](#design-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Download è la v1, introdotta con la versione 2.5.0 dei componenti core a giugno 2019, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione e dell’output HTML e JSON del componente Download, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_download) .

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Download [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_download_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire l’elemento da scaricare e come si comporterà e apparirà per un visitatore alla pagina.

![Scheda Risorsa della finestra di dialogo di modifica del componente Download](/help/assets/download-edit-asset.png)

### Scheda Risorsa {#asset-tab}

La selezione di una risorsa da scaricare è molto simile alla funzionalità del [componente immagine](image.md) e sfrutta anche AEM DAM.

* **Scarica risorsa**
   * Rilascia una risorsa dal [browser Risorse](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) o tocca l’opzione **Sfoglia** per caricarla da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * Tocca o fai clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) nell’editor risorse.

### Scheda Proprietà {#properties-tab}

![Scheda Proprietà della finestra di dialogo di modifica del componente Download](/help/assets/download-edit-properties.png)

* **Titolo** : viene visualizzato come titolo dell’elemento da scaricare
   * **Ottieni titolo da risorsa**  DAM: se selezionato, il titolo viene compilato automaticamente con il titolo della risorsa DAM.
* **Descrizione**  - Visualizza come sottotitolo descrittivo dell&#39;elemento di download
   * **Ottieni descrizione da DAM asset** : se selezionata, la descrizione viene compilata automaticamente con la descrizione della risorsa DAM.
* **Testo azione** : viene visualizzato come testo dell’azione per l’elemento scaricato
   * Questo campo è necessario per caricare una risorsa dal file system.
   * **Visualizza in linea** : quando è selezionata l’opzione Testo  **azione** fornita, viene visualizzato in linea.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore del contenuto che utilizza il componente Scarica .

### Scheda Proprietà {#properties-tab-design}

![Finestra di dialogo Progettazione del componente Scarica](/help/assets/download-design.png)

* **Consenti caricamento dal file system** : consente all’autore del contenuto di caricare una risorsa dal proprio file system locale come risorsa da scaricare.
   * Il valore predefinito è deselezionato.
* **Tipo di titolo** : l’elemento HTML utilizzato per il titolo del componente di download.
   * Se non è selezionato alcun valore, il valore predefinito è H3.
* **Dimensioni file di visualizzazione** : quando è selezionata la dimensione del file della risorsa, questa viene visualizzata nel componente di download.
   * Il valore predefinito è selezionato.
* **Formato del file di visualizzazione** : se selezionato, il formato del file della risorsa verrà visualizzato nel componente di download.
   * Il valore predefinito è selezionato.
* **Nome file visualizzato** : se selezionato, il nome del file della risorsa verrà visualizzato nel componente di download.
   * Il valore predefinito è selezionato.

### Scheda Stili {#styles-tab}

Il componente Immagine supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).
