---
title: Componente Contenitore
seo-title: Componente Contenitore
description: 'null'
seo-description: Il componente Contenitore di componenti core consente la creazione di un contenitore per più componenti aggiuntivi su una pagina.
uuid: ec 807 de 9-f 76 c -4850-9 ece-c 3 e 439 a 1 d 626
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: f 093 f 58 e -9755-4 a 4 f -803 a-ab 93 a 50 e 6870
translation-type: tm+mt
source-git-commit: 3e2e7a297c6ee1d6c8d092c619df8febdc900e25

---


# Container Component{#container-component}

Il componente Contenitore di componenti core consente la creazione di un contenitore per più componenti aggiuntivi su una pagina.

## Utilizzo {#usage}

Il componente Contenitore di componenti core consente la creazione di un contenitore per più componenti aggiuntivi su una pagina e può essere utilizzato per raggruppare altri componenti e applicare uno stile o layout comune.

* The container&#39;s properties can be selected in the [configure dialog](#configure-dialog).
* Defaults for the Container Component when adding it to a page can be defined in the [design dialog](#design-dialog).

## Version and Compatibility {#version-and-compatibility}

La versione corrente del componente Contenitore è v 1, introdotta con la release 2.5.0 dei componenti core a giugno 2019, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Container Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/container.html).

## Technical Details {#technical-details}

The latest technical documentation about the Container Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/container/v1/container).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Configure Dialog {#configure-dialog}

La finestra di dialogo Configura consente all&#39;autore del contenuto di definire l&#39;elemento contenitore e di comprenderne il funzionamento e il relativo aspetto.

![](assets/screen-shot-2019-06-21-13.59.26.png)

* **Layout** : questa opzione definisce il comportamento o il comportamento del layout del componente Contenitore.
   * **Semplice** - Definisce un contenitore come semplice raccolta di componenti
   * **Griglia** reattiva: definisce un contenitore come griglia reattiva [AEM](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/responsive-layout.html)
* **ID** - Utilizzate questa opzione per definire l&#39;attributo ID HTML da applicare al componente.
* **Colore di sfondo** - Definibile come valori RGB a mano libera o utilizzando il selettore colore, [a seconda della configurazione](#background-tab)
* **Immagine di sfondo** - Definisce un colore di sfondo per il contenitore, [a seconda della configurazione](#background-tab)

## Design Dialog {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire le opzioni disponibili per l&#39;autore di contenuto che utilizza il componente Contenitore.

### Allowed Components Tab {#allowed-components-tab}

The **Allowed Components** tab is used to define which components can be added as items to the Container Component by the content author.

The Allowed Components tab functions in the same way as the tab of the same name when [defining the policy and properties of a Layout Container in the Template Editor.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Default Components Tab {#default-components-tab}

The Default Components tab is used to define which component is added to the component when a particular asset type is dropped on the container, similar to [how default components are defined on the page template](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html#EditingTemplatesTemplateAuthors).

### Responsive Settings Tab {#responsive-settings-tab}

![](assets/screen-shot-2019-06-21-09.33.03.png)

* **Colonne** : definisce il numero di colonne nella griglia del contenitore risultante.

### Background Tab {#background-tab}

![](assets/screen-shot-2019-06-21-09.42.42.png)

* **Immagine di sfondo**
   * **Abilita immagine** di sfondo: selezionate questa opzione per consentire all&#39;autore del contenuto di definire un&#39;immagine di sfondo per il contenitore.
* **Colore di sfondo**
   * **Abilita colore** di sfondo: selezionate questa opzione per consentire all&#39;autore del contenuto di definire un colore di sfondo per il contenitore.
   * **Solo** campioni: selezionate questa opzione per consentire all&#39;autore del contenuto di selezionare solo i campioni di colore predefiniti per il colore dello sfondo del contenitore.
      * Only available when **Enable background color** is selected
* **Campioni consentiti** - Definire colori predefiniti da cui l&#39;autore del contenuto può selezionare il colore dello sfondo del contenitore
   * Use the **Add** button to add a pre-defined color swatch. Una volta aggiunta, all&#39;elenco viene aggiunta una voce contenente le colonne seguenti:
   * **Valore** - Definite manualmente il colore tramite i valori RGB
      * Toccate o fate clic sul selettore colore per selezionare più facilmente un colore regolando i singoli valori RGB o definendo un valore esadecimale.
   * **Elimina** : toccate o fate clic per eliminare un campione.
   * **Ridisponete** : toccate o fate clic e trascinate per riordinare l&#39;ordine dei campioni.

### Styles Tab {#styles-tab}

The Container Component supports the AEM [Style System](authoring.md#component-styling).
