---
title: Componente Schede
seo-title: Componente Schede
description: Il componente Schede consente di creare più schede per disporre il contenuto in una pagina.
seo-description: Il componente Schede consente di creare più schede per disporre il contenuto in una pagina.
uuid: 46 f 71233-8 b 12-4887-a 0 c 6-ad 24 dc 469 cb 1
content-type: riferimento
topic-tags: componenti core
discoiquuid: 966 d 47 fb-d 35 d -4103-b 29 d -4 ef 0 aa 739 f 24
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Componente Schede

Il componente Tabella componenti core consente di organizzare il contenuto su più schede.

## Utilizzo {#usage}

Il componente Schede consente all&#39;autore del contenuto di organizzare il contenuto della pagina all&#39;interno di più schede.

The [edit dialog](#edit-dialog) allows the content author to define multiple tabs as well as set the active tab. Using the [design dialog](#design-dialog), the template author can define which components can be added to tabs and customize the styles.

>[!NOTE]
>
>Sono supportati i componenti di schede nidificati (schede all&#39;interno delle schede).
>
>Simple (non-nested) tab components can be located/selected using the [content tree](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html), however nested tabs can not be.

## Version and Compatibility {#version-and-compatibility}

La versione corrente del componente Tabs è v 1, introdotta con la release 2.2.0 dei componenti core a ottobre 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | Compatibile | Compatibile | Compatibile |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Tabs Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/tabs.html).

### Technical Details {#technical-details}

The latest technical documentation about the Tabs Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all&#39;autore del contenuto di creare, rinominare e ridisporre le schede e definire la scheda attiva.

### Items Tab {#items-tab}

![](assets/screenshot_2018-10-11at153557.png)

Use the **Add** button to open the component selector to choose which component to add as a tab. Una volta aggiunta, all&#39;elenco viene aggiunta una voce contenente le colonne seguenti:

* **Icona** : l&#39;icona del tipo di componente della scheda per facilitarne l&#39;identificazione. Passate il mouse per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione** : descrizione utilizzata come testo della scheda, in base al nome del componente selezionato per la scheda.
* **Elimina** : toccate o fate clic per eliminare la scheda dal componente di tabulazione.
* **Ridisponi** : tocca o fai clic e trascina per riordinare l&#39;ordine delle schede.

### Properties Tab {#properties-tab}

![](assets/screenshot_2018-10-19at140646.png)

On the **Properties** tab, the content author can define which tab is active when the page is loaded. With the **Default** option, the first tab will be selected.

## Select Panel {#select-panel}

The content author can use the **Select Panel** option on the component toolbar to change to a different panel for editing as well as to easily rearrange the order of the tabs.

![](assets/screenshot_2018-10-11at165417.png)

Once selecting the **Select Panel** option in the component toolbar, the configured tabs are displayed as a drop-down.

* L&#39;elenco è ordinato dalla disposizione assegnata delle schede e si riflette nella numerazione.
* Il tipo di componente della scheda viene visualizzato per primo, seguita dalla descrizione della scheda in font più chiaro.

![](assets/screenshot_2018-10-11at165154.png)

* Toccando o facendo clic su una voce nel menu a discesa, passa alla scheda nell&#39;editor.
* Le schede possono essere ridisposte in posizione utilizzando le maniglie di trascinamento.

>[!NOTE]
>
>Tabs are not selectable by the author when in **Edit** mode. Use [**Preview** mode](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) or the **[View as Published](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** option to interact with the tabs as a reader of the published content would.

## Design Dialog {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire quali componenti aggiungere come elementi al componente Schede e quali stili personalizzati sono disponibili per l&#39;autore del contenuto.

### Allowed Components Tab {#allowed-components-tab}

The **Allowed Components** tab is used to define which components can be added as items to the tabs component by the content author.

The Allowed Components tab functions in the same way as the tab of the same name when [defining the policy and properties of a Layout Container in the Template Editor.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Styles Tab {#styles-tab}

The Tabs Component supports the AEM [Style System](authoring.md#component-styling).