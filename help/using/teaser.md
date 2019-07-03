---
title: Componente teaser
seo-title: Componente teaser
description: Il componente teaser può mostrare un'immagine, un titolo, rich text ed eventualmente un collegamento a un altro contenuto.
seo-description: Il componente teaser può mostrare un'immagine, un titolo, rich text ed eventualmente un collegamento a un altro contenuto.
uuid: 46989314-df 37-448 b -8562-c 707043 f 2160
contentOwner: bohnert
content-type: riferimento
topic-tags: componenti core
discoiquuid: e 597 c 18 e -3643-41 be -9878-4 a 7872 f 1 ab 90
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Teaser Component{#teaser-component}

Il componente Teaser componente core può mostrare un&#39;immagine, un titolo, rich text ed eventualmente un collegamento a un altro contenuto.

## Utilizzo {#usage}

Il componente Teaser consente all&#39;autore del contenuto di creare facilmente un teaser con un&#39;immagine, un titolo o un testo RTF e il collegamento a un altro contenuto o ad altre azioni.

The template author can use the [design dialog](#design-dialog) to define if the options to create call-to-actions and add links are available as well as disabling various display options. The content author can use the [configure dialog](#configure-dialog) to set an image, define CTAs, set titles and descriptions, and configure links to the individual teaser. The [edit dialog](image.md#edit-dialog) of the [Image Component](image.md) can be accessed to modify the teaser image.

## Version and Compatibility {#version-and-compatibility}

La versione corrente del componente Teaser è v 1, introdotta con la release 2.1.0 dei Componenti core a luglio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v1 | Compatibile | Compatibile | Compatibile |

## Sample Component Output {#sample-component-output}

To experience the Teaser Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/teaser.html).

### Technical Details {#technical-details}

The latest technical documentation about the Teaser Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Configure Dialog {#configure-dialog}

L&#39;autore del contenuto può utilizzare la finestra di dialogo Configura per definire le proprietà del singolo teaser. There is also an [edit dialog](#edit-dialog) to modify the teaser image if one is selected.

### Immagine {#image}

![](assets/screen_shot_2018-07-03at104125.png)

* **Risorsa immagine**
   * Drop an asset from the [asset browser](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) or tap the **browse** option to upload from a local file system.
   * Tap or click **Clear** to de-select the currently selected image.
   * Tap or click **Edit** to [mange the renditions of the asset](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) in the asset editor.

### Testo {#text}

![](assets/screen_shot_2018-07-03at104138.png)

* **Titolo**
Definisce un titolo da visualizzare come intestazione del teaser.
* **Ottieni titolo dalla pagina
collegata** Quando questa opzione è selezionata, il titolo verrà popolato con il titolo della pagina collegata.
* **Descrizione**
Definisce una descrizione da visualizzare come sottoinsieme del teaser.
* **Ottieni descrizione dalla pagina
collegata** Quando questa opzione è selezionata, la descrizione verrà compilata con la descrizione della pagina collegata.

### Links &amp; Actions {#links-actions}

![](assets/screen_shot_2018-07-03at104146.png)

* **** Collegamento collegamento applicato al teaser. Utilizzate il browser Percorsi per selezionare la destinazione del collegamento.
* **Abilita chiamata-azioni** quando questa opzione è selezionata, abilita la definizione di Call-to-Actions. Il primo collegamento Call-to-Action nell&#39;elenco viene usato come collegamento per altri elementi teaser.

## Edit Dialog {#edit-dialog}

The Teaser Component delegates image rendering to the [Image Component](image.md). Therefore the [edit dialog](image.md#edit-dialog of the Image Component is available to the content author to manipulate the teaser image.

## Design Dialog {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire le opzioni teaser che l&#39;autore del contenuto ha quando si utilizza questo componente.

### Teaser Tab {#teaser-tab}

![](assets/screen_shot_2018-07-03at105958.png)

* **Inviti all&#39;azione**
   * **Disable Call-to-Actions**
Hide the **Call-to-Actions** option for content authors
* **Elementi**
   * **Nascondi titolo**
      * Hides the **Title** option for content authors
      * When selected the **Title Type** is hidden
   * **Nascondi descrizione**
Nasconde l&#39;opzione **Descrizione** per gli autori di contenuto
* **Tipo
titolo** Definisce il tag H da utilizzare dal titolo del teaser.
* **Collegamenti**
   * **Non collegare l&#39;immagine**
Quando selezionata, l&#39;immagine teaser non è collegata
   * **Non collegare il titolo**
quando selezionato, il titolo del teaser non è collegato

### Styles Tab {#styles-tab}

The Teaser Component supports the AEM [Style System](authoring.md#component-styling).
