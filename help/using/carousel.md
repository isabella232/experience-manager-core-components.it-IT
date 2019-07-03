---
title: Componente Carosello
seo-title: Componente Carosello
description: 'null'
seo-description: Il componente Carosello consente all'autore del contenuto di presentare il contenuto in un carosello rotante.
uuid: 34934491-bd 85-4 f 1 e-ae 22-bb 48 ed 4 dbd 5 c
content-type: riferimento
topic-tags: componenti core
discoiquuid: 3510812 b -9 d 3 e -40 fe-b 986-0 f 15 d 40 b 42 ad
disttype: dist5
gnavtheme: chiaro
groupsectionnavitems: 'no'
hidemerchandisingbar: eredita
hidepromocomponent: eredita
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Carousel Component{#carousel-component}

Il componente Carosello componente core consente all&#39;autore del contenuto di presentare il contenuto in un carosello navigabile.

## Utilizzo {#usage}

Utilizzo del componente Carosello, l&#39;autore del contenuto per organizzare il contenuto in un carosello di diapositive.

The [edit dialog](#edit-dialog) allows the content author to create, name, and order multiple slides as well as enable auto-transition with delay. Using the [design dialog](#design-dialog), the template author can define which components can be added to the carousel, enable or disable automatic transitions, and customize the styles.

## Version and Compatibility {#version-and-compatibility}

La versione corrente del componente Carosello è v 1, introdotta con la release 2.2.0 dei componenti core a ottobre 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | Compatibile | Compatibile | Compatibile |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Carousel Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/carousel.html).

### Technical Details {#technical-details}

The latest technical documentation about the Carousel Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all&#39;autore del contenuto di aggiungere, rinominare e ridisporre le diapositive e definire le impostazioni di transizione automatica.

### Items Tab {#items-tab}

![](assets/screenshot_2018-10-12at102451.png)

Use the **Add** button to open the component selector to choose which component to add as a tab. Una volta aggiunta, all&#39;elenco viene aggiunta una voce contenente le colonne seguenti:

* **Icona** : l&#39;icona del tipo di componente della scheda per facilitarne l&#39;identificazione. Passate il mouse per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione** : descrizione utilizzata come testo della scheda, in base al nome del componente selezionato per la scheda.
* **Elimina** : toccate o fate clic per eliminare la scheda dal componente Schede.
* **Riordina** : toccate o fate clic e trascinate per ordinare le schede.

### Properties Tab {#properties-tab}

![](assets/screenshot_2018-11-28at141054.png)

On the **Properties** tab, the content author can set the slides to automatically transition.

* **Transizione automatica delle diapositive** : quando è attiva, il componente avanza automaticamente alla diapositiva successiva dopo un ritardo specificato.
* **Ritardo transizione -** Quando si seleziona automaticamente le diapositive, questo valore viene usato per definire il ritardo tra transizioni (in millisecondi).
* **Disattiva la pausa automatica al passaggio del mouse** : quando **sono selezionate automaticamente le diapositive** , la transizione carosello si interrompe automaticamente ogni volta che il cursore passa sopra il carosello. Selezionate questa opzione per evitare pause.

>[!NOTE]
>
>The slide advance controls are not enabled when in **Edit** mode. Use [**Preview** mode](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) or the **[View as Published](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** option to interact with the carousel as a reader of the published content would.
>
>The auto-advance feature is not enabled when in **Edit** mode. Use **[View as Published](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** option to see the auto-advance feature as a reader of the published content would.

## Select Panel {#select-panel}

The content author can use the **Select Panel** option on the component toolbar to change to a different slide for editing as well as to easily rearrange the order of the slides.

![](assets/screenshot_2018-10-11at165417.png)

Once selecting the **Select Panel** option in the component toolbar, the configured slides are displayed as a drop-down.

* L&#39;elenco è ordinato dalla disposizione assegnata delle diapositive e si riflette nella numerazione.
* Il tipo di componente della diapositiva viene visualizzato per primo, seguita dalla descrizione della diapositiva in font più chiaro.

![](assets/opera_snapshot_2018-11-28141537localhost.png)

* Toccando o facendo clic su una voce nel menu a discesa, viene attivata la visualizzazione nell&#39;editor a quella diapositiva.
* La diapositiva può essere riorganizzata in locale utilizzando le maniglie di trascinamento.

## Design Dialog {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire quali componenti aggiungere come diapositive al componente carosello, nonché definire i valori predefiniti di transizione automatica e gli stili personalizzati disponibili per l&#39;autore del contenuto.

### Properties Tab {#properties-tab-1}

The **Properties** tab is used to define the default settings for the slide transitions when a content author adds the carousel component to a page.

![](assets/screenshot_2018-11-28at141824.png)

* **Scorrimento automatico delle diapositive** - Definisce se per impostazione predefinita l&#39;opzione di avanzamento automatico della sequenza alla diapositiva successiva viene attivata quando l&#39;autore del contenuto aggiunge il componente carosello a una pagina.
* **Ritardo transizione** - Definisce il valore predefinito del ritardo di transizione tra le diapositive (in millisecondi) quando un autore aggiunge il componente carosello a una pagina.
* **Disattiva pausa automatica al passaggio del mouse** - Definisce se per impostazione predefinita l&#39;opzione Disattiva la pausa automatica delle diapositive è abilitata quando **l&#39;autore del contenuto seleziona automaticamente le diapositive** .

### Allowed Components Tab {#allowed-components-tab}

The **Allowed Components** tab is used to define which components can be added as slides to the Carousel Component by the content author.

The Allowed Components tab functions in the same way as the tab of the same name when [defining the policy and properties of a Layout Container in the Template Editor.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Styles Tab {#styles-tab}

The Carousel Component supports the AEM [Style System](authoring.md#component-styling).