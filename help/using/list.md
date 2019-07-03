---
title: Elenca componente
seo-title: Elenca componente
description: 'null'
seo-description: Il componente Elenco componenti core consente di creare con facilità elenchi statici e statici.
uuid: 50 a 572 e 8-b 444-4 f 7 d -82 bc -5 a 93 ebb 4 be 95
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: 89053323-6221-46 ed -896 a -31 a 42 c 55282 e
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


# Elenca componente{#list-component}

Il componente Elenco componenti core consente di creare con facilità elenchi statici e statici.

## Utilizzo {#usage}

Il componente Elenco può essere utilizzato per creare, ad esempio, un elenco dinamico di pagine figlie o un elenco statico di elementi definiti arbitrariamente. The type of lists available and formatting options can be defined by the template author in the [design dialog](#design-dialog). The content editor can select from available list types and how to format the list elements in the [edit dialog](#edit-dialog).

## Version and Compatibility {#version-and-compatibility}

La versione corrente del componente Elenco è v 2, introdotta con la release 2.0.0 dei Componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](list-v1.md) | Compatibile | Compatibile | Compatibile |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the List Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/list.html).

### Technical Details {#technical-details}

The latest technical documentation about the List Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all&#39;autore del contenuto di configurare l&#39;elenco e gli elementi dell&#39;elenco.

### List Settings Tab {#list-settings-tab}

L&#39;elenco può essere creato in diversi modi.

* [Pagine figlie](#child-pages)
* [Elenco fisso](#fixed-list)
* [Ricerca](#search-options)
* [Tag](#tags)

Regardless of how the list is built, there are [Sort Options](#sort-options) that can always be configured.

![](assets/chlimage_1-38.png)

A seconda del modo in cui l&#39;autore del contenuto sceglie di creare l&#39;elenco, vengono modificate anche le opzioni di configurazione aggiuntive.

#### Pagine figlie {#child-pages}

L&#39;elenco può essere creato dalle pagine figlie della pagina corrente o di un&#39;altra pagina.

![](assets/chlimage_1-39.png)

* **Pagina padre**
   * Pagina le cui pagine figlie devono essere elencate
   * Lasciate vuoto per usare la pagina corrente

* **Profondità figlio**
Il numero di livelli in basso nella gerarchia

#### Fixed List {#fixed-list}

L&#39;elenco può essere creato utilizzando un elenco fisso di elementi.

![](assets/chlimage_1-40.png)

Tap or click the **Add** button to inset a new item to the list.

* Enter text for the item in the list or use the **Selection Dialog** to choose an item from AEM.
* Utilizzare la maniglia di trascinamento per ridisporre gli elementi nell&#39;elenco.
* Usate l&#39;icona del cestino per eliminare gli elementi nell&#39;elenco.

#### Ricerca {#search-options}

L&#39;elenco può essere creato utilizzando i risultati di una ricerca di contenuto AEM.

![](assets/chlimage_1-41.png)

* **Query
di ricerca** La stringa per la quale verrà eseguita una ricerca a testo intero per generare gli elementi dell&#39;elenco
* **Cerca in**
dove eseguire la ricerca
   * Use the **Selection Dialog** to choose the location in AEM
   * Usa pagina corrente se lasciata vuota

#### Tag {#tags}

L&#39;elenco può essere creato utilizzando pagine che corrispondono a determinati tag in una posizione specifica.

![](assets/chlimage_1-42.png)

* **Pagina
padre** in cui deve iniziare la corrispondenza dei tag
   * Use the **Selection Dialog** to choose the location in AEM
   * Usa pagina corrente se lasciata vuota
* **Tag**
corrispondenti ai tag corrispondenti
   * Use the **Browse** dialog to select the tags
* **Corrispondenza**
Consente di definire quale tipo di corrispondenza deve qualificare una pagina da includere nell&#39;elenco
   * **qualsiasi tag**
   * **tutti i tag**

#### Sort Options {#sort-options}

A prescindere dalla modalità di creazione dell&#39;elenco, alcune opzioni di ordinamento possono essere sempre definite.

![](assets/chlimage_1-43.png)

* **Ordina per**
modalità di ordinamento degli elementi
   * **Titolo**
   * **Data ultima modifica**
* **Ordina ordine**
L&#39;ordine in cui gli elementi devono essere ordinati
   * **crescente**
   * **decrescente**
* **Numero massimo elementi**
massimo visualizzati nell&#39;elenco.
   * Lasciate vuoto per restituire tutti gli elementi.

### Item Settings Tab {#item-settings-tab}

La scheda Impostazioni elemento consente di configurare la formattazione degli elementi dell&#39;elenco.

![](assets/chlimage_1-44.png)

* **Collegare elementi**
collegamento alla pagina corrispondente
* **Mostra descrizione**
Mostra le descrizioni della voce di collegamento
* **Mostra data di modifica** mostra data di modifica dell&#39;elemento di collegamento

## Design Dialog {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire quali tipi di elenchi consentire agli autori di contenuto e alle impostazioni degli elementi disponibili.

### Impostazioni elenco {#list-settings}

On the **List Settings** tab, the date format can be defined as well as what type of lists should be available in the component to the content authors.

![](assets/chlimage_1-45.png)

* **Formato formato** data da utilizzare per la visualizzazione dell&#39;ultima data di modifica
* **Disattiva elementi figlio**
Disattiva il tipo di elenco elementi figlio nel componente
* **Disattiva statica**
Disattiva il tipo di elenco statico nel componente
* **Disattiva ricerca**
Disattiva il tipo di elenco di ricerca nel componente
* **Disabilita tag**
di elenco tag nel componente

### Impostazioni elemento {#item-settings}

On the **Item Settings** tab, the formatting options for the individual list elements that should be available in the component for the content authors can be defined.

![](assets/chlimage_1-46.png)

* **Opzione Collega elementi**
link nella finestra di dialogo [di modifica degli elementi](#edit-dialog)
* **Mostra descrizioni**
descrizione Mostra le descrizioni nella finestra di dialogo [di modifica](#edit-dialog)
* **Opzione Mostra data**
mostra data nella finestra di [dialogo di modifica](#edit-dialog)

### Styles Tab {#styles-tab}

The Image Component supports the AEM [Style System](authoring.md#component-styling).