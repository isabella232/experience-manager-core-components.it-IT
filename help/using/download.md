---
title: Scarica componente
seo-title: Scarica componente
description: 'null'
seo-description: Il componente per il download dei componenti core consente di creare un’opzione di download su una pagina.
uuid: ec807de9-f76c-4850-9ece-c3e439a1d626
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: f093f58e-9755-4a4f-803a-ab93a50e6870
translation-type: tm+mt
source-git-commit: 88bc68b60e5de247fe800ac041ffefdf9238cce1

---


# Scarica componente{#download-component}

Il componente per il download dei componenti core consente di creare un’opzione di download su una pagina.

## Utilizzo {#usage}

Il componente Download del componente core consente di includere in una pagina un’opzione di download e la risorsa associata.

* Le proprietà dell'opzione di download possono essere selezionate nella finestra di dialogo [di](#configure-dialog)configurazione.
* I valori predefiniti per il componente Download possono essere definiti nella finestra di dialogo [](#design-dialog)della progettazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Download è v1, introdotto con la release 2.5.0 dei componenti core a giugno 2019, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Download ed esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la libreria [dei](http://opensource.adobe.com/aem-core-wcm-components/library/download.html)componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Download [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/download/v1/download).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire l’elemento da scaricare e come si presenterà e come verrà visualizzato da un visitatore alla pagina.

![](assets/screen-shot-2019-06-17-09.49.14.png)

### Scheda Risorsa {#asset-tab}

La selezione di una risorsa per il download è molto simile alla funzionalità del componente [](image.md) immagine e sfrutta allo stesso modo DAM di AEM.

* **Scarica risorsa**
   * Trascinate una risorsa dal browser [delle](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) risorse o toccate l'opzione **Sfoglia** per caricarla da un file system locale.
   * Toccate o fate clic su **Cancella** per deselezionare l'immagine attualmente selezionata.
   * Toccate o fate clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) nell’editor risorse.

### Scheda Proprietà {#properties-tab}

![](assets/screen-shot-2019-06-17-09.49.51.png)

* **Titolo** - Visualizzato come titolo per l’elemento di download
   * **Ottieni titolo dalla risorsa** DAM: se questa opzione è selezionata, il titolo viene popolato automaticamente con il titolo della risorsa DAM.
* **Descrizione** - Visualizzato come sottotitolo descrittivo dell'elemento di download
   * **Ottieni una descrizione dalla risorsa** DAM: se questa opzione è selezionata, la descrizione della risorsa DAM viene compilata automaticamente con la relativa descrizione.
* **Testo** azione - Visualizzato come testo di azione per l'elemento di download
   * Questo campo è richiesto quando si carica una risorsa dal file system.
   * **Visualizza in linea** - Se selezionata, il testo **dell'** azione fornito verrà visualizzato in linea.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore del contenuto che utilizza il componente Download.

### Scheda Proprietà {#properties-tab-design}

![](assets/screen-shot-2019-06-17-10.04.31.png)

* **Testo** azione predefinito - Definisce il testo **predefinito per le** azioni fornito quando un autore aggiunge il componente Download a una pagina.
* **Consenti caricamento dal file system** - Consente all'autore del contenuto di caricare una risorsa dal file system locale come risorsa da scaricare.
   * Il valore predefinito è deselezionato.
* **Tipo** titolo - L'elemento HTML utilizzato per il titolo del componente Download.
   * Se non è selezionato alcun valore, il valore predefinito è H3.
* **Visualizza dimensioni** file: se è selezionata, le dimensioni del file della risorsa vengono visualizzate nel componente Download.
   * Il valore predefinito è selezionato.
* **Visualizza formato** file: quando viene selezionato, il formato file della risorsa verrà visualizzato nel componente Download.
   * Il valore predefinito è selezionato.
* **Nome** file visualizzato: se selezionato, il nome del file della risorsa verrà visualizzato nel componente Download.
   * Il valore predefinito è selezionato.

### Scheda Stili {#styles-tab}

Il componente Immagine supporta AEM [Style System](authoring.md#component-styling).
