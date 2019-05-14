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
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# Elenca componente{#list-component}

Il componente Elenco componenti core consente di creare con facilità elenchi statici e statici.

## Utilizzo {#usage}

Il componente Elenco può essere utilizzato per creare, ad esempio, un elenco dinamico di pagine figlie o un elenco statico di elementi definiti arbitrariamente. Il tipo di elenchi disponibili e le opzioni di formattazione possono essere definite dall&#39;autore del modello nella finestra di dialogo [di progettazione](#design-dialog). L&#39;Editor contenuto può selezionare i tipi di elenchi disponibili e formattare gli elementi dell&#39;elenco nella finestra di dialogo [di modifica](#edit-dialog).

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Elenco è v 2, introdotta con la release 2.0.0 dei Componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](list-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/screen_shot_2018-01-12at105924.png)

### Libreria componenti

Per provare il componente Elenco e vedere alcuni esempi delle opzioni di configurazione e l&#39;output HTML e JSON, visitare la [Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library/list.html).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente [Elenco è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Finestra di dialogo di modifica {#edit-dialog}

La finestra di dialogo di modifica consente all&#39;autore del contenuto di configurare l&#39;elenco e gli elementi dell&#39;elenco.

### Scheda Impostazioni elenco {#list-settings-tab}

L&#39;elenco può essere creato in diversi modi.

* [Pagine figlie](#child-pages)
* [Elenco fisso](#fixed-list)
* [Ricerca](#search-options)
* [Tag](#tags)

A prescindere dalla modalità di creazione dell&#39;elenco, [sono disponibili Opzioni](#sort-options) di ordinamento.

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

#### Elenco fisso {#fixed-list}

L&#39;elenco può essere creato utilizzando un elenco fisso di elementi.

![](assets/chlimage_1-40.png)

Toccate o fate clic sul **pulsante Aggiungi** per inserire un nuovo elemento nell&#39;elenco.

* Immettete il testo per l&#39;elemento nell&#39;elenco o utilizzate la **finestra di dialogo di selezione** per scegliere un elemento da AEM.
* Utilizzare la maniglia di trascinamento per ridisporre gli elementi nell&#39;elenco.
* Usate l&#39;icona del cestino per eliminare gli elementi nell&#39;elenco.

#### Ricerca {#search-options}

L&#39;elenco può essere creato utilizzando i risultati di una ricerca di contenuto AEM.

![](assets/chlimage_1-41.png)

* **Query
di ricerca** La stringa per la quale verrà eseguita una ricerca a testo intero per generare gli elementi dell&#39;elenco
* **Cerca in**
dove eseguire la ricerca
   * Utilizzare la **finestra di dialogo** di selezione per scegliere la posizione in AEM
   * Usa pagina corrente se lasciata vuota

#### Tag {#tags}

L&#39;elenco può essere creato utilizzando pagine che corrispondono a determinati tag in una posizione specifica.

![](assets/chlimage_1-42.png)

* **Pagina
padre** in cui deve iniziare la corrispondenza dei tag
   * Utilizzare la **finestra di dialogo** di selezione per scegliere la posizione in AEM
   * Usa pagina corrente se lasciata vuota
* **Tag**
corrispondenti ai tag corrispondenti
   * Utilizzare la **finestra di** dialogo Sfoglia per selezionare i tag
* **Corrispondenza**
Consente di definire quale tipo di corrispondenza deve qualificare una pagina da includere nell&#39;elenco
   * **qualsiasi tag**
   * **tutti i tag**

#### Opzioni ordinamento {#sort-options}

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

### Scheda Impostazioni elemento {#item-settings-tab}

La scheda Impostazioni elemento consente di configurare la formattazione degli elementi dell&#39;elenco.

![](assets/chlimage_1-44.png)

* **Collegare elementi**
collegamento alla pagina corrispondente
* **Mostra descrizione**
Mostra le descrizioni della voce di collegamento
* **Mostra data di modifica** mostra data di modifica dell&#39;elemento di collegamento

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire quali tipi di elenchi consentire agli autori di contenuto e alle impostazioni degli elementi disponibili.

### Impostazioni elenco {#list-settings}

Nella **scheda Impostazioni** elenco, è possibile definire il formato della data e il tipo di elenchi disponibili nel componente agli autori di contenuto.

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

Nella **scheda Impostazioni** elemento, le opzioni di formattazione per i singoli elementi dell&#39;elenco che dovrebbero essere disponibili nel componente per gli autori di contenuto possono essere definite.

![](assets/chlimage_1-46.png)

* **Opzione Collega elementi**
link nella finestra di dialogo [di modifica degli elementi](#edit-dialog)
* **Mostra descrizioni**
descrizione Mostra le descrizioni nella finestra di dialogo [di modifica](#edit-dialog)
* **Opzione Mostra data**
mostra data nella finestra di [dialogo di modifica](#edit-dialog)

### Scheda Stili {#styles-tab}

Il componente Immagine supporta il sistema [di stile AEM](authoring.md#component-styling).