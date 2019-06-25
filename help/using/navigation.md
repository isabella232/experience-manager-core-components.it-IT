---
title: Componente di navigazione
seo-title: Componente di navigazione
description: 'null'
seo-description: Il componente Navigazione consente agli utenti di navigare facilmente in una struttura del sito globalizzata.
uuid: 616 c 03 fb -39 b 3-402 a-b 990-f 56 c 87 bc 6 df 4
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: da 8 d 67 d 7-b 65 e -4041-bc 0 e-e 998 f 24 a 68 f 9
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


# Navigation Component{#navigation-component}

Il componente Navigazione consente agli utenti di navigare facilmente in una struttura del sito globalizzata.

## Utilizzo {#usage}

Il componente di navigazione consente una gerarchia di navigazione che può essere integrata dalle copie live di un blueprint, dalle copie in lingua di una lingua originale o da una semplice struttura ad albero delle pagine. Consente agli utenti della pagina di navigare facilmente in una struttura del sito.

The [edit dialog](#edit-dialog) allows the content author to define the navigation root page along with the depth of navigation. The [design dialog](#design-dialog) allows the template author to define default values for the navigation root and depth.

## Version and Compatibility {#version-and-compatibility}

La versione corrente del componente di navigazione è v 1, introdotta con la release 2.0.0 dei componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | Compatibile | Compatibile | Compatibile |


For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Navigation Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/navigation.html).

## Technical Details {#technical-details}

The latest technical documentation about the Navigation Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/navigation/v1/navigation).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md.

>[!NOTE]
>
>As of Core Components release 2.1.0, the Navigation Component supports [schema.org microdata](https://schema.org).

## Edit Dialog {#edit-dialog}

Nella finestra di dialogo di modifica, l&#39;autore del contenuto può definire la pagina principale per la navigazione e la profondità della struttura di navigazione.

![](assets/screen_shot_2018-04-03at112055.png)

* **Radice
di navigazione** La pagina principale, che verrà utilizzata per generare la struttura di navigazione.
* **Escludi principale
di navigazione** Escludi la radice di navigazione nella struttura ad albero risultante, includi solo i relativi discendenti.
* **Raccolta di tutte le pagine**
figlie Raccoglie tutte le pagine che sono discendenti della radice di navigazione.
* **Profondità
struttura di navigazione** Definisce quanti livelli ridurre la struttura di navigazione, il componente dovrebbe essere visualizzato rispetto alla radice di navigazione (disponibile solo quando **l&#39;opzione Raccoglie tutte le pagine** figlie non è selezionata).

## Design Dialog {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di impostare i valori predefiniti per la pagina di navigazione e la profondità di navigazione presentati agli autori di contenuto.

### Properties Tab {#properties-tab}

![](assets/screen_shot_2018-04-03at112357.png)

* **Radice**
di navigazione Il valore predefinito della pagina principale della struttura di navigazione, che verrà utilizzata per generare la struttura di navigazione e per impostazione predefinita quando l&#39;autore del contenuto aggiunge il componente alla pagina.
* **Escludi radice
di navigazione** Il valore predefinito dell&#39;opzione per escludere la radice di navigazione nella struttura ad albero risultante.
* **Raccolta di pagine
figlie** Il valore predefinito dell&#39;opzione per raccogliere tutte le pagine discendenti della radice di navigazione.
* **Profondità**
struttura di navigazione Il valore predefinito della profondità della struttura di navigazione.

### Styles Tab {#styles-tab}

The Navigation Component supports the AEM [Style System](authoring.md#component-styling).