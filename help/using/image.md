---
title: Componente immagine
seo-title: Componente immagine
description: Il componente Immagine componente core è una funzione di modifica locale delle funzioni dei componenti immagine.
seo-description: Il componente Immagine componente core è una funzione di modifica locale delle funzioni dei componenti immagine.
uuid: 1 a 229 d 42-2428-43 aa -895 a -9 b 7 c 1 bf 02834
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: d 4684 f 33-2 fb 5-4 f 32-866 f -7136 cf 1800 d 7
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Componente immagine{#image-component}

Il componente Immagine componente core è un componente immagine adattivo che funzioni in funzione di modifica locale.

## Utilizzo {#usage}

Il componente Immagine permette di posizionare facilmente risorse di immagini e offerte locali. Offre selezioni immagine adattive con caricamento lazy e ritaglio per l&#39;autore del contenuto.

The image widths as well as cropping and additional settings can be defined by the template author in the [design dialog](#design-dialog). The content editor can upload or select assets in the [configure dialog](#configure-dialog) and crop the image in the [edit dialog](#edit-dialog). Per maggiore praticità è disponibile anche una semplice modifica diretta dell&#39;immagine.

## Version and Compatibility {#version-and-compatibility}

La versione corrente del componente Immagine è v 2, introdotta con la release 2.0.0 dei Componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](image-v1.md) | Compatibile | Compatibile | Compatibile |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## SVG Support {#svg-support}

Il componente Immagine vettoriale scalabile (SVG) è supportato dal componente Immagine.

* È supportata la funzione di trascinamento di una risorsa SVG da DAM e il caricamento di un file SVG da un file system locale.
* Nei flussi immagine adattiva viene trasmesso il file SVG originale (le trasformazioni vengono ignorate).
* Per un&#39;immagine SVG, le «immagini sensibili» e le «dimensioni sensibili» sono impostate su un array vuoto nel modello di immagine.

### Protezione {#security}

Per motivi di sicurezza, il formato SVG originale non viene mai chiamato direttamente dall&#39;Editor immagini. `<img src=“path-to-component”>`Viene richiamata. Tale browser impedisce l&#39;esecuzione di script incorporati nel file SVG.

>[!CAUTION]
>
>SVG support requires release 2.1.0 of the Core Components or higher along with [service pack 2](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) for AEM 6.4 or [service pack 3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) for AEM 6.3 or higher to support [new image editor features](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/image-editor.html) within AEM.

## Sample Component Output {#sample-component-output}

To experience the Image Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/image.html).

### Technical Details {#technical-details}

The latest technical documentation about the Image Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/image/v2/image).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

>[!NOTE]
>
>As of Core Components release 2.1.0, the Image Component supports [schema.org microdata](https://schema.org).

## Configure Dialog {#configure-dialog}

In addition to the standard [edit dialog](#edit-dialog) and [design dialog](#design-dialog), the image component offers a configure dialog where the image itself is defined along with its description and basic properties.

### Asset Tab {#asset-tab}

![](assets/screen_shot_2018-01-08at114245.png)

* **Risorsa immagine**
   * Drop an asset from the [asset browser](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) or tap the **browse** option to upload from a local file system.
   * Tap or click **Clear** to de-select the currently selected image.
   * Tap or click **Edit** to [mange the renditions of the asset](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) in the asset editor.

### Metadata Tab {#metadata-tab}

![](assets/screen_shot_2018-01-08at114527.png)

* **L&#39;immagine è decorativa**
Se l&#39;immagine deve essere ignorata dalla tecnologia di accessibilità e quindi non richiede un testo alternativo. Ciò si applica solo alle immagini decorative.
* **Alternative**testuali alternative
rispetto al significato o alla funzione dell&#39;immagine, per i lettori ipovedenti.
   * Get alternative text from DAM - When checked the image&#39;s alternative text will be populated with the value of the `dc:description` metadata in DAM.

* **Didascalia**
Ulteriori informazioni sull&#39;immagine, visualizzate sotto l&#39;immagine per impostazione predefinita.
   * **Ottieni didascalia da DAM**
Quando questa opzione è selezionata, il testo della didascalia dell&#39;immagine verrà popolato con il valore dei `dc:title` metadati in DAM.
   * **Visualizza didascalia come a comparsa** Quando questa opzione è selezionata, la didascalia non viene visualizzata sotto l&#39;immagine, ma come pop-up visualizzato da alcuni browser quando si passa il mouse sull&#39;immagine.

* **Collegamento**
   * Collegate l&#39;immagine a un&#39;altra risorsa.
   * Utilizza la finestra di dialogo di selezione per collegare un&#39;altra risorsa AEM.
   * Se non collegate una risorsa AEM, immettete l&#39;URL assoluto. Gli URL non soliti verranno interpretati come relativi ad AEM.

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all&#39;autore del contenuto di ritagliare, modificare la mappa di lancio e applicare lo zoom all&#39;immagine.

![](assets/chlimage_1-8.png)

* Avvia ritaglio

   ![](assets/chlimage_1-9.png)

   Selezionando questa opzione si apre un menu a discesa per le proporzioni di ritaglio predefinite.

   * Choose the option **Free Hand** to define your own crop.
   * Choose the option **Remove Crop** to display the original asset.
   Una volta selezionata l&#39;opzione Ritaglio, usate le maniglie blu per ridimensionare il ritaglio sull&#39;immagine.

   ![](assets/chlimage_1-10.png)

* Ruota a destra

   ![](assets/chlimage_1-11.png)

   Utilizzare questa opzione per ruotare l&#39;immagine di 90 ° a destra (in senso orario).

* Rifletti in orizzontale

   ![](assets/screen_shot_2018-04-16at091404.png)

   Usate questa opzione per riflettere l&#39;immagine in orizzontale o ruotare l&#39;immagine di 180 ° lungo l&#39;asse y.

* Rifletti in verticale

   ![](assets/screen_shot_2018-04-16at091410.png)

   Utilizzate questa opzione per riflettere l&#39;immagine in verticale o ruotare l&#39;immagine di 180 ° lungo l&#39;asse x.

* Mappa lancio

   >[!CAUTION]
   >
   >The Launch Map feature requires release 2.1.0 of the Core Components or higher along with [service pack 2](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) for AEM 6.4 or [service pack 3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) for AEM 6.3 or higher to support [new image editor features](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/image-editor.html) within AEM.

   ![](assets/chlimage_1-12.png)

   Utilizzate questa opzione per applicare una mappa di lancio all&#39;immagine. Selezionate questa opzione per aprire una nuova finestra che consente all&#39;utente di selezionare la forma della mappa:

   * **Aggiungi mappa rettangolare**
   * **Aggiungi mappa circolare**
   * **Aggiungi mappa poligono**
      * Per impostazione predefinita, viene aggiunta una mappa triangolare. Fare doppio clic su una riga della forma per aggiungere una nuova maniglia di ridimensionamento blu su un nuovo lato.
   Una volta selezionata la forma della mappa, questa viene sovrapposta all&#39;immagine che consente il ridimensionamento. Trascinare e rilasciare le maniglie di ridimensionamento blu per regolare la forma.

   ![](assets/chlimage_1-13.png)

   Dopo aver ridimensionato la mappa di avvio, fare clic su di essa per aprire una barra degli strumenti mobile per definire il percorso del collegamento.

   * **Percorso**
      * Utilizzare l&#39;opzione Selettore percorso per selezionare un percorso in AEM
      * Se il percorso non è in AEM, usate l&#39;URL assoluto. I percorsi non assoluti verranno interpretati in base ad AEM.
   * **Testo**
Alt Descrizione alternativa della destinazione del percorso
   * **Destinazione**
      * **Stessa scheda**
      * **Nuova scheda**
      * **Frame principale**
      * **Frame superiore**
   Toccate o fate clic sulla spunta blu da salvare, sulla x nera da annullare e sul cestino rosso per eliminare la mappa.

   ![](assets/chlimage_1-14.png)

* Ripristina zoom

   ![](assets/chlimage_1-15.png)

   Se l&#39;immagine è già stata ingrandita, usate questa opzione per ripristinare il livello di zoom.

* Apri cursore zoom

   ![](assets/chlimage_1-16.png)

   Usate questa opzione per visualizzare un cursore per controllare il livello di zoom dell&#39;immagine.

   ![](assets/chlimage_1-17.png)

L&#39;editor locale può essere usato anche per modificare l&#39;immagine. A causa di limiti di spazio, sono disponibili solo le opzioni di base. Per le opzioni di modifica complete, utilizzate la modalità schermo intero.

![](assets/chlimage_1-18.png)

>[!NOTE]
>
>Le operazioni di modifica delle immagini (ritaglio, capovolgimento, rotazione) non sono supportate per le immagini GIF. Tutte le modifiche apportate in modalità di modifica a GIF non saranno persistenti.

## Design Dialog {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire il ritaglio, il caricamento e le opzioni di rotazione e caricamento che l&#39;autore del contenuto ha quando si utilizza questo componente.

### Main Tab {#main-tab}

On the **Main** tab you can define a list of widths in pixels for the image to automatically load the most appropriate width from the list.

Inoltre, è possibile definire quali opzioni generali vengono visualizzate o disattivate quando l&#39;autore aggiunge il componente a una pagina.

![](assets/screenshot_2018-10-19at102756.png)

* **Abilita caricamento
lazy** Definisce se l&#39;opzione di caricamento lazy viene attivata automaticamente quando si aggiunge il componente Immagine a una pagina.
* **L&#39;immagine è decorativa**
se l&#39;opzione Immagine decorativa viene attivata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Ottenete testo alternativo da DAM**
Definire se l&#39;opzione per recuperare il testo alternativo da DAM viene attivata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Ottenere didascalia da DAM**
Definire se l&#39;opzione per recuperare la didascalia dal DAM viene attivata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Visualizza didascalia come a comparsa** Definite se l&#39;opzione per visualizzare la didascalia immagine come pop-up viene attivata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Disabilita controllo tracciamento**
UUID per disattivare il tracciamento dell&#39;UUID della risorsa immagine.

* **Larghezze**
Consente di definire un elenco di larghezze in pixel affinché l&#39;immagine carichi automaticamente la larghezza più appropriata dall&#39;elenco.
   * Tap or click the **Add** button to add another size.
      * Utilizzare le maniglie di acquisizione per riordinare l&#39;ordine delle dimensioni.
      * Use the **Delete** icon to remove a width.
   * Per impostazione predefinita, il caricamento delle immagini viene eseguito fino a quando non diventa visibile.
      * Select the option **Disable lazy loading** to load the images upon page load.
* **Qualità**
JPEG Il fattore di qualità (in percentuale da 0 e 100) per le immagini JPEG trasformate (ad es. ridimensionate o ritagliate).

>[!CAUTION]
>
>L&#39;opzione Qualità JPEG è disponibile a partire dalla versione 2.2.0 dei componenti core.

>[!NOTE]
>
>As of release 2.2.0 of the Core Components, the Image Component adds the unique UUID attribute `data-asset-id` to the image asset to allow tracking and analysis of the number of views that individual assets receive.

### Features Tab {#features-tab}

On the **Features** tab you can define which options are available to the content authors when using the component including upload options, orientation, and cropping options.

* Origine

   ![](assets/chlimage_1-19.png)

   Select the option **Allow asset upload from file system** to allow content authors to upload images from his or her local computer. Per obbligare gli autori di contenuto a selezionare solo risorse da AEM, deselezionate questa opzione.

* Orientamento

   ![](assets/chlimage_1-20.png)

* **Rotazione**
Consente di utilizzare questa opzione per consentire all&#39;autore del contenuto di utilizzare l&#39;opzione **Ruota diritto.**
* **Rifletti**
Utilizzate questa opzione per consentire all&#39;autore del contenuto di utilizzare le opzioni **Rifletti in orizzontale** e **Rifletti in verticale** .

   >[!CAUTION]
   >
   >The **Flip** option is disabled by default. Enabling it will display the **Flip Vertically** and **Flip Horizontally** buttons in the edit dialog of the image component, however the feature is not currently supported by AEM and any changes made using these options will not be persisted.

<!-- 
Comment Type: remark
Last Modified By: Chris Bohnert (bohnert)
Last Modified Date: 2017-11-20T05:51:34.378-0500

<p>Added caution based on CQDOC-11457. Hid the flip options in the procedure using the <strong>Draft</strong> option so that when this feature is implemented in CQ-4221539, the <strong>Draft</strong> property can simply be removed along with the caution.</p>
 -->

* Ritaglio

   ![](assets/chlimage_1-21.png)

   Select the option **Allow crop** to allow the content author to crop the image in the component in the edit dialog.
   * Click **Add** to add a pre-defined crop aspect ratio.
   * Enter a descriptive name, which will be shown in the **Start Crop** dropdown.
   * Inserite il rapporto numerico dell&#39;aspetto.
   * Utilizzare le maniglie trascinate per riordinare l&#39;ordine delle proporzioni
   * Usate l&#39;icona del cestino per eliminare le proporzioni.
   >[!CAUTION]
   >
   >Note that in AEM, crop aspect ratios are defined as **height/width**. Ciò si differenzia dalla definizione convenzionale di larghezza/altezza e viene effettuata per motivi di compatibilità precedenti. Gli autori di contenuto non saranno a conoscenza di alcuna differenza purché sia indicato un nome chiaro del rapporto, in quanto il nome viene visualizzato nell&#39;interfaccia utente e non il rapporto stesso.

### Styles Tab {#styles-tab-1}

The Image Component supports the AEM [Style System](authoring.md#component-styling).