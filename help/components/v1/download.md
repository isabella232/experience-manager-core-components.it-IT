---
title: Componente Scarica (v1)
description: Il componente core Scarica consente di creare un’opzione di scaricamento su una pagina.
role: Architect, Developer, Admin, User
source-git-commit: f8aa86d58ba71ede3c3cd867c45aafff06923325
workflow-type: ht
source-wordcount: '644'
ht-degree: 100%

---


# Componente Scarica  (v1) {#download-component}

Il componente core Scarica consente di creare un’opzione di scaricamento su una pagina.

## Utilizzo {#usage}

Il componente core Scarica consente di includere in una pagina un’opzione di scaricamento e la relativa risorsa associata.

* Le proprietà dell’opzione Scarica possono essere selezionate nella finestra di dialogo [finestra di dialogo per configurazione](#configure-dialog).
* I valori predefiniti del componente Scarica possono essere definiti nella [finestra di dialogo per progettazione](#design-dialog).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Scarica, introdotto con la versione 2.5.0 dei componenti core a giugno 2019.

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Scarica.
>
>Per informazioni dettagliate sulla versione corrente del componente Scarica, vedi il documento [Componente Scarica](/help/components/download.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Scarica e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_download).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Scarica [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_download_v1).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuto di definire l’elemento Scarica e il suo comportamento e aspetto nei confronti di chi visita la pagina.

![Scheda Risorsa della finestra di dialogo per modifica del componente Scarica](/help/assets/download-edit-asset.png)

### Scheda Risorsa {#asset-tab}

La selezione di una risorsa da scaricare è molto simile alla funzionalità del [componente Immagine](image-v1.md) e allo stesso modo sfrutta il DAM di AEM.

* **Scarica risorsa**
   * Rilascia una risorsa dal [browser di risorse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=it) oppure tocca l’opzione **Sfoglia** per caricarla da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * Tocca o fai clic su **Modifica** per [gestire i rendering della risorsa](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=it) nell’editor risorse.

### Scheda Proprietà {#properties-tab}

![Scheda Proprietà della finestra di dialogo per modifica del componente Scarica](/help/assets/download-edit-properties.png)

* **Titolo**: viene visualizzato come titolo dell’elemento da scaricare
   * **Ottieni titolo da risorsa DAM**: se selezionata, viene inserito automaticamente il titolo della risorsa DAM.
* **Descrizione**: il sottotitolo descrittivo dell’elemento da scaricare
   * **Ottieni descrizione da risorsa DAM**: se selezionata, viene inserita automaticamente la descrizione della risorsa DAM.
* **Testo azione**: il testo dell’azione per l’elemento da scaricare
   * Questo campo è necessario per caricare una risorsa dal file system.
   * **Visualizza in linea**: se selezionata, il testo specificato in **Testo azione** viene visualizzato in linea.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore di contenuto che utilizza il componente Scarica.

### Scheda Proprietà {#properties-tab-design}

![Finestra di dialogo per progettazione del componente Scarica](/help/assets/download-design.png)

* **Consenti caricamento dal file system**: consente all’autore di contenuto di caricare una risorsa dal proprio file system locale come risorsa da scaricare.
   * Per impostazione predefinita, questa opzione è deselezionata.
* **Tipo di titolo**: l’elemento HTML utilizzato per il titolo del componente Scarica.
   * Se non specificato, il valore predefinito è H3.
* **Visualizza dimensione file**: se selezionata, la dimensione del file della risorsa viene visualizzata nel componente Scarica.
   * Per impostazione predefinita, questa opzione è selezionata.
* **Visualizza formato file**: se selezionata, il formato del file della risorsa viene visualizzato nel componente Scarica.
   * Per impostazione predefinita, questa opzione è selezionata.
* **Visualizza Nome file**: se selezionata, il nome del file della risorsa viene visualizzato nel componente Scarica.
   * Per impostazione predefinita, questa opzione è selezionata.

### Scheda Stili {#styles-tab}

Il componente Immagine supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
