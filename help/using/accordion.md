---
title: Componente Accordion
seo-title: Componente Accordion
description: 'null'
seo-description: Il componente Accordion componente core consente la creazione di un insieme di pannelli disposti in una struttura di navigazione su una pagina.
uuid: ec 807 de 9-f 76 c -4850-9 ece-c 3 e 439 a 1 d 626
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: f 093 f 58 e -9755-4 a 4 f -803 a-ab 93 a 50 e 6870
translation-type: tm+mt
source-git-commit: bbd54d433cbeee5395dc8b90bc47f9b44747e25b

---


# Accordion Component{#accordion-component}

Il componente Accordion componente core consente la creazione di un insieme di pannelli disposti in una struttura di navigazione su una pagina.

## Utilizzo {#usage}

The Core Component Accordion component allows for the creation of a collection of components, composed as panels, and arranged in an accordion on a page, similar to the [Tabs Component](tabs.md), but allows for expanding and collapsing of the panels.

* The accordion&#39;s properties can be defined in the [configure dialog](#configure-dialog).
* The order of the panels of the accordion can be defined in the configure dialog as well as the [select panel popover](#select-planel.md).
* Defaults for the Accordion Component when adding it to a page can be defined in the [design dialog](#design-dialog).

## Version and Compatibility {#version-and-compatibility}

La versione corrente del componente Accordion è v 1, introdotta con la release 2.5.0 dei componenti core a giugno 2019, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/accordion.html).

## Technical Details {#technical-details}

The latest technical documentation about the Accordion Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/accordion/v1/accordion).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Configure Dialog {#configure-dialog}

La finestra di dialogo Configura consente all&#39;autore del contenuto di definire l&#39;elemento Accordion, i pannelli e l&#39;aspetto che avrà per un visitatore della pagina.

### Items Tab {#items-tab}

![](assets/screen-shot-2019-06-21-08.26.38.png)

Use the **Add** button to open the component selector to choose which component to add as a panel. Una volta aggiunta, all&#39;elenco viene aggiunta una voce contenente le colonne seguenti:

* **Icona** : l&#39;icona del tipo di componente del pannello per facilitarne l&#39;identificazione. Passate il mouse per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione** : descrizione utilizzata come testo del pannello, in base al nome del componente selezionato per il pannello.
* **Elimina** : toccate o fate clic per eliminare il pannello dal componente Accordion.
* **Ridisponi** : tocca o fai clic e trascina per riordinare l&#39;ordine dei pannelli.

### Properties Tab {#properties-tab}

![](assets/screen-shot-2019-06-21-08.26.53.png)

* **Espansione singola degli elementi** - Se selezionato, questa opzione forza l&#39;espansione di un singolo elemento Accordion alla volta. L&#39;espansione di un elemento ne determina la compressione.
* **Elementi** espansi: questa opzione definisce gli elementi che sono espansi per impostazione predefinita quando la pagina viene caricata.
   * When **Single item expansion** is selected, one panel must be selected. Per impostazione predefinita, è selezionato il primo pannello.
   * When **Single item expansion** is not selected, this option is a multi-select and is optional.

## Select Panel Popover {#seelct-panel-popover}

The content author can use the **Select Panel** option on the component toolbar to change to a different panel for editing as well as to easily rearrange the order of the panels within the accordion.

![](assets/screen-shot-2019-06-21-08.49.36.png)

Once selecting the **Select Panel** option in the component toolbar, the configured accordion panels are displayed as a drop-down.

![](assets/screen-shot-2019-06-21-08.52.14.png)

* L&#39;elenco è ordinato dalla disposizione assegnata dei pannelli e si riflette nella numerazione.
* Il tipo di componente del pannello viene visualizzato per primo, seguita dalla descrizione del pannello in font più chiaro.
* Toccando o facendo clic su una voce nel menu a discesa, viene attivata la visualizzazione nell&#39;editor in quel pannello.
* I pannelli possono essere riorganizzati in locale mediante le maniglie di trascinamento.

## Design Dialog {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire le opzioni disponibili per l&#39;autore di contenuto che utilizza il componente Accordion e le impostazioni predefinite durante l&#39;inserimento del componente Accordion.

### Properties Tab {#properties-tab-design}

![](assets/screen-shot-2019-06-21-08.58.11.png)

* **Elementi** di intestazione consentiti: questo menu a discesa con più selezioni definisce gli elementi HTML della voce Accordion che possono essere selezionati da un autore.
* **Elemento** intestazione predefinito: questo elenco a discesa definisce l&#39;elemento HTML di intestazione predefinito dell&#39;elemento Accordion.

### Allowed Components Tab {#allowed-components-tab}

The **Allowed Components** tab is used to define which components can be added as items to panels in the Accordion Component by the content author.

The Allowed Components tab functions in the same way as the tab of the same name when [defining the policy and properties of a Layout Container in the Template Editor.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Styles Tab {#styles-tab}

The Accordion Component supports the AEM [Style System](authoring.md#component-styling).
