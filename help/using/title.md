---
title: Componente titolo
seo-title: Componente titolo
description: 'null'
seo-description: Il componente Titolo componente core è un componente di intestazione della sezione che offre funzioni di modifica locale.
uuid: cf 190861-e 5 cd -42 b 8-9193-842 b 8 df 8 c 5 c 6
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: 243 efc 75-fcf 9-427 d -9303-9642 b 0602991
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Componente titolo{#title-component}

Il componente Titolo componente core è un componente di intestazione della sezione che offre funzioni di modifica locale.

## Utilizzo {#usage}

Il componente Titolo deve essere usato come titolo o intestazione di una sezione di contenuto. The available heading levels can be defined by the template author in the [design dialog](#design-dialog). The content editor can select from available headings levels in the [edit dialog](#edit-dialog). Per maggiore praticità, è disponibile anche una semplice modifica diretta del testo dell&#39;intestazione.

## Version and Compatibility {#version-and-compatibility}

La versione corrente del componente Titolo è v 2, introdotta con la release 2.0.0 dei Componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](title-v1.md) | Compatibile | Compatibile | Compatibile |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Title Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/title.html).

### Technical Details {#technical-details}

The latest technical documentation about the Title Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/title/v2/title).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all&#39;autore del contenuto di definire il testo del titolo e di selezionare il livello di intestazione.

* **Titolo** : se vuoto, verrà utilizzato il titolo della pagina
* **Tipo/Dimensione** : definisce il livello di intestazione del titolo
* **Collegamento** : definisce il contenuto a cui verrà collegato il titolo. Può essere un percorso a una pagina di contenuto, un URL esterno o un ancoraggio di pagina.

![](assets/screenshot_2018-10-19at110055.png)

>[!CAUTION]
>
>La capacità di definire un collegamento per il titolo è stata introdotta con la release 2.2.0 dei componenti core.

L&#39;editor locale può essere usato anche per modificare il testo del componente Titolo.

![](assets/chlimage_1-37.png)

## Design Dialog {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire il livello di intestazione predefinito che i componenti titolo avranno quando creati dagli autori dei contenuti.

### Sizes Tab {#sizes-tab}

![](assets/screenshot_2018-10-19at110120.png)

* **Tipi/dimensioni consentiti per autori** - Abilita o disabilita i tipi di intestazione che saranno disponibili per gli autori di contenuto quando utilizzano il componente Titolo.
* **Tipo/Dimensione predefinito**: definisce il tipo di intestazione che verrà assegnato automaticamente quando un autore aggiunge il componente Titolo a una pagina.
* **Disattiva collegamento**: disabilitate il supporto per i collegamenti nel componente Titolo per impedire agli autori di contenuto di collegarsi dai titoli.

>[!CAUTION]
>
>La capacità di definire un collegamento per il titolo è stata introdotta con la release 2.2.0 dei componenti core.

### Styles Tab {#styles-tab}

The Title Component supports the AEM [Style System](authoring.md#component-styling).