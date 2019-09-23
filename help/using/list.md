---
title: Elenca componente
seo-title: Elenca componente
description: 'null'
seo-description: Il componente Elenco componenti core consente di creare facilmente elenchi dinamici e statici.
uuid: 50a572e8-b444-4f7d-82bc-5a93ebb4be95
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 89053323-6221-46ed-896a-31a42c55282e
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

Il componente Elenco componenti core consente di creare facilmente elenchi dinamici e statici.

## Utilizzo {#usage}

Il componente Elenco può essere utilizzato per creare, ad esempio, un elenco dinamico di pagine figlie o un elenco statico di elementi definiti arbitrariamente. Il tipo di elenchi disponibili e le opzioni di formattazione possono essere definite dall'autore del modello nella finestra di dialogo [della](#design-dialog)progettazione. L'editor dei contenuti può selezionare tra i tipi di elenco disponibili e come formattare gli elementi dell'elenco nella finestra di dialogo [di](#edit-dialog)modifica.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Elenco è v2, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](list-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Elenco e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](http://opensource.adobe.com/aem-core-wcm-components/library/list.html)componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Elenco [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di configurare l’elenco e gli elementi dell’elenco.

### Scheda Impostazioni elenco {#list-settings-tab}

L'elenco può essere creato in diversi modi.

* [Pagine figlie](#child-pages)
* [Elenco fisso](#fixed-list)
* [Ricerca](#search-options)
* [Tag](#tags)

Indipendentemente dalla modalità di creazione dell'elenco, è sempre possibile configurare le opzioni [di](#sort-options) ordinamento.

![](assets/chlimage_1-38.png)

A seconda di come l’autore del contenuto sceglie di generare l’elenco, le opzioni di configurazione aggiuntive cambieranno.

#### Pagine figlie {#child-pages}

È possibile creare l'elenco delle pagine figlie della pagina corrente o di un'altra pagina.

![](assets/chlimage_1-39.png)

* **Pagina padre**
   * Pagina di cui devono essere elencate le pagine figlie
   * Lascia vuoto per utilizzare la pagina corrente

* **Profondità figlio** Quanti livelli della gerarchia devono essere utilizzati

#### Fixed List {#fixed-list}

L'elenco può essere creato utilizzando un elenco fisso di elementi.

![](assets/chlimage_1-40.png)

Toccate o fate clic sul pulsante **Aggiungi** per inserire un nuovo elemento nell’elenco.

* Immettete il testo per l’elemento nell’elenco o utilizzate la finestra di dialogo **di** selezione per scegliere un elemento da AEM.
* Usate la maniglia di trascinamento per ridisporre gli elementi nell’elenco.
* Utilizzate l'icona del cestino per eliminare gli elementi nell'elenco.

#### Ricerca {#search-options}

L'elenco può essere creato utilizzando i risultati di una ricerca di contenuto AEM.

![](assets/chlimage_1-41.png)

* **Query** di ricerca Stringa per la quale verrà eseguita una ricerca full-text per generare gli elementi elenco
* **Cerca nella** posizione in cui eseguire la ricerca
   * Utilizzare la finestra di dialogo **** Selezione per scegliere il percorso in AEM
   * Usa pagina corrente se lasciata vuota

#### Tag {#tags}

L'elenco può essere creato utilizzando pagine che corrispondono a determinati tag presenti in una determinata posizione.

![](assets/chlimage_1-42.png)

* **Pagina** padre da cui deve iniziare la corrispondenza del tag
   * Utilizzare la finestra di dialogo **** Selezione per scegliere il percorso in AEM
   * Usa pagina corrente se lasciata vuota
* **Tag** per i tag da associare
   * Utilizzare la finestra di dialogo **Sfoglia** per selezionare i tag
* **Corrispondenza** Consente di definire il tipo di corrispondenza da applicare alla pagina da includere nell'elenco.
   * **qualsiasi tag**
   * **tutti i tag**

#### Opzioni di ordinamento {#sort-options}

Indipendentemente dalla modalità di creazione dell’elenco, è sempre possibile definire alcune opzioni di ordinamento.

![](assets/chlimage_1-43.png)

* **Ordina per** modalità di ordinamento degli elementi
   * **Titolo**
   * **Data ultima modifica**
* **Ordina ordine** L'ordine in cui devono essere ordinati gli articoli
   * **crescente**
   * **decrescente**
* **Numero massimo elementi** Numero massimo di elementi visualizzati nell'elenco.
   * Lasciate vuoto per restituire tutti gli elementi.

### Scheda Impostazioni elemento {#item-settings-tab}

Utilizzando la scheda Impostazioni elemento, è possibile configurare la formattazione degli elementi dell'elenco.

![](assets/chlimage_1-44.png)

* **Collega elementi** Collega elementi alla pagina corrispondente
* **Mostra descrizione** Mostra descrizioni dell’elemento di collegamento
* **Mostra data** Mostra data modifica elemento collegamento

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire i tipi di elenchi da consentire agli autori dei contenuti e le impostazioni degli elementi disponibili.

### Impostazioni elenco {#list-settings}

Nella scheda Impostazioni **** elenco, è possibile definire il formato della data e il tipo di elenchi da rendere disponibili nel componente per gli autori del contenuto.

![](assets/chlimage_1-45.png)

* **Formato** data Formato da utilizzare per la visualizzazione dell'ultima data di modifica
* **Disabilita elementi figlio** Disattiva il tipo di elenco figli nel componente
* **Disabilita statica** Disattiva il tipo di elenco statico nel componente
* **Disattiva ricerca** Disattiva il tipo di elenco di ricerca nel componente
* **Disabilita tag** Disattiva il tipo di elenco dei tag nel componente

### Impostazioni elemento {#item-settings}

Nella scheda Impostazioni **** elemento è possibile definire le opzioni di formattazione per i singoli elementi dell'elenco che dovrebbero essere disponibili nel componente per gli autori dei contenuti.

![](assets/chlimage_1-46.png)

* **Collega elementi** Abilita collegamenti elementi nella finestra di dialogo di [modifica](#edit-dialog)
* **Mostra descrizioni** Abilita Mostra descrizioni opzione nella finestra di dialogo di [modifica](#edit-dialog)
* **Mostra data** Abilita data opzione Mostra data nella finestra di dialogo di [modifica](#edit-dialog)

### Scheda Stili {#styles-tab}

Il componente Immagine supporta AEM [Style System](authoring.md#component-styling).