---
title: Scarica componente
seo-title: Scarica componente
description: 'null'
seo-description: Il componente Download componente core consente di creare un'opzione di download su una pagina.
uuid: ec 807 de 9-f 76 c -4850-9 ece-c 3 e 439 a 1 d 626
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: f 093 f 58 e -9755-4 a 4 f -803 a-ab 93 a 50 e 6870
translation-type: tm+mt
source-git-commit: 88bc68b60e5de247fe800ac041ffefdf9238cce1

---


# Download Component{#download-component}

Il componente Download componente core consente di creare un&#39;opzione di download su una pagina.

## Utilizzo {#usage}

Il componente Download componente core consente di includere un&#39;opzione di download e la relativa risorsa associata su una pagina.

* The download option&#39;s properties can be selected in the [configure dialog](#configure-dialog).
* Defaults for the download component can be defined in the [design dialog](#design-dialog).

## Version and Compatibility {#version-and-compatibility}

La versione corrente del componente Download è v 1, introdotta con la release 2.5.0 dei Componenti core a giugno 2019, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Download Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/download.html).

## Technical Details {#technical-details}

The latest technical documentation about the Download Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/download/v1/download).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Configure Dialog {#configure-dialog}

La finestra di dialogo Configura consente all&#39;autore del contenuto di definire l&#39;elemento di download e di verificare come si presenterà e si presenterà per un visitatore alla pagina.

![](assets/screen-shot-2019-06-17-09.49.14.png)

### Asset Tab {#asset-tab}

The selection of a download asset is very similar to the functionality of the [Image Component](image.md) and likewise leverages AEM&#39;s DAM.

* **Scarica risorsa**
   * Drop an asset from the [asset browser](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) or tap the **browse** option to upload from a local file system.
   * Tap or click **Clear** to de-select the currently selected image.
   * Tap or click **Edit** to [mange the renditions of the asset](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) in the asset editor.

### Properties Tab {#properties-tab}

![](assets/screen-shot-2019-06-17-09.49.51.png)

* **Titolo** : viene visualizzato come intestazione per l&#39;elemento di download
   * **Ottenere il titolo dalla risorsa** DAM - Se selezionato, il titolo viene automaticamente popolato con il titolo della risorsa DAM.
* **Descrizione** : viene visualizzato come sottotitoli descrittivi dell&#39;elemento di download
   * **Ottieni descrizione dalla risorsa** DAM - Se selezionata, la descrizione viene compilata automaticamente con la descrizione della risorsa DAM.
* **Testo** azione: visualizzato come testo dell&#39;azione per l&#39;elemento download
   * Questo campo è richiesto quando si carica una risorsa dal file system.
   * **Visualizza in linea** : quando viene selezionato il testo **dell&#39;azione fornito** verrà visualizzato in linea.

## Design Dialog {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire le opzioni disponibili per l&#39;autore di contenuto che utilizza il componente Scarica.

### Properties Tab {#properties-tab-design}

![](assets/screen-shot-2019-06-17-10.04.31.png)

* **Testo azione predefinito** - Definisce il testo **azione predefinito** fornito quando un autore aggiunge il componente Scarica componente a una pagina.
* **Consenti caricamento dal file system** - Consente all&#39;autore del contenuto di caricare una risorsa dal proprio file system locale come risorsa di download.
   * Il valore predefinito è deselezionato.
* **Tipo titolo** - L&#39;elemento HTML utilizzato per il titolo del componente Scarica.
   * Se non è selezionato alcun valore, il valore predefinito è H 3.
* **Visualizza dimensione** file: quando selezionate la dimensione del file, verrà visualizzata nel componente di download.
   * Il valore predefinito è selezionato.
* **Visualizza formato file** - Quando selezionate il formato di file della risorsa, verrà visualizzato nel componente Download.
   * Il valore predefinito è selezionato.
* **Visualizza nome file** : quando viene selezionato il nome file della risorsa, verrà visualizzato nel componente Download.
   * Il valore predefinito è selezionato.

### Styles Tab {#styles-tab}

The Image Component supports the AEM [Style System](authoring.md#component-styling).
