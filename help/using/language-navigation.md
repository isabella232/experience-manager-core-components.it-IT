---
title: Componente di navigazione lingua
seo-title: Componente di navigazione lingua
description: 'null'
seo-description: Il componente di navigazione lingua fornisce una navigazione lingua/paese per un sito, in modo che i visitatori possano passare alla stessa pagina con un'altra lingua.
uuid: ce 736458-9 cdf -4 bc 2-b 90 f -9 c 5 a 62 fe 1 ca 0
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: 8 f 232 eb 0-65 d 5-4075-8668-75 f 1366882 c 8
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
source-git-commit: c58826c133eb112b305fa4facbe2a81e577eb896

---


# Language Navigation Component{#language-navigation-component}

Il componente Navigazione lingua fornisce una navigazione lingua/paese per un sito, in modo che i visitatori possano passare alla stessa pagina con un&#39;altra lingua.

## Utilizzo {#usage}

Spesso i siti Web sono forniti in più lingue per diverse aree. Il componente di navigazione lingua consente a un visitatore di visualizzare la stessa pagina in lingue/lingue diverse.

The [edit dialog](#edit-dialog) allows the definition of the global site navigation root as well as how deep into the structure the navigation should go. Using the [design dialog](#design-dialog), the template author can set the default values for the same options.

## Version and Compatibility {#version-and-compatibility}

La versione corrente del componente di navigazione lingua è v 1, introdotta con la release 2.0.0 dei componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | Compatibile | Compatibile | Compatibile |


For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Language Navigation Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/languagenavigation.html).

## Technical Details {#technical-details}

The latest technical documentation about the Language Navigation Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente di definire la directory principale di navigazione globale del sito e di analizzare la struttura della navigazione.

![](assets/screen_shot_2018-01-12at133353.png)

* **Radice
di navigazione** Definisce la pagina principale della struttura di navigazione.
   * Use the **Open Selection Dialog** button to easily navigate the content structure and select the root.
* **Profondità profondità** struttura della struttura globale della lingua rispetto alla radice di navigazione.

## Design Dialog {#design-dialog}

Mediante la finestra di dialogo di progettazione, l&#39;autore del modello può impostare i valori predefiniti per le stesse opzioni disponibili nella finestra di dialogo di modifica.

### Properties Tab {#properties-tab}

![](assets/screen_shot_2018-01-12at133642.png)

* **Valore predefinito di**navigazione della
cartella principale di navigazione quando un autore inserisce il componente Commutatore lingua in una pagina di contenuto
* **Valore predefinito Struttura**lingua Valore predefinito della
struttura della struttura quando un autore di contenuto posiziona il componente Commutatore lingua in una pagina di contenuto

### Styles Tab {#styles-tab}

The Language Navigation Component supports the AEM [Style System](authoring.md#component-styling).