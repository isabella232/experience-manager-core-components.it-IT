---
title: Elenca componente
description: Il componente Elenco componenti core consente di creare facilmente elenchi dinamici e statici.
translation-type: tm+mt
source-git-commit: d3ebcea5fa1523c1a986841cd3d1a64e16e85f6d
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 4%

---


# Elenca componente{#list-component}

Il componente Elenco componenti core consente di creare facilmente elenchi dinamici e statici.

## Utilizzo {#usage}

Il componente Elenco può essere utilizzato per creare, ad esempio, un elenco dinamico di pagine figlie o un elenco statico di elementi definiti arbitrariamente. Il tipo di elenchi disponibili e le opzioni di formattazione possono essere definite dall&#39;autore del modello nella finestra di dialogo [progettazione](#design-dialog). L&#39;editor di contenuti può selezionare tra i tipi di elenco disponibili e come formattare gli elementi dell&#39;elenco nella finestra di dialogo di [modifica](#edit-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Elenco è v2, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](v1/list-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente Elenco e vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library_list).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Elenco [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_list_v2).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di configurare l’elenco e gli elementi dell’elenco.

### Scheda Impostazioni elenco {#list-settings-tab}

L&#39;elenco può essere creato in diversi modi.

* [Pagine figlie](#child-pages)
* [Elenco fisso](#fixed-list)
* [Ricerca](#search-options)
* [Tag](#tags)

Indipendentemente dalla modalità di creazione dell&#39;elenco, è sempre possibile configurare [Opzioni di ordinamento e ID](#sort-options).

![Finestra di dialogo di modifica del componente Elenco](/help/assets/list-edit.png)

A seconda di come l’autore del contenuto sceglie di generare l’elenco, le opzioni di configurazione aggiuntive cambieranno.

#### Pagine figlie {#child-pages}

È possibile creare l&#39;elenco delle pagine figlie della pagina corrente o di un&#39;altra pagina.

![Opzioni pagina figlia](/help/assets/list-edit-child-pages.png)

* **Pagina padre**
   * La pagina di cui devono essere elencate le pagine figlie
   * Lascia vuoto per utilizzare la pagina corrente

* **Child-**
DepthQuanti livelli della gerarchia devono essere utilizzati

#### Elenco fisso {#fixed-list}

L&#39;elenco può essere creato utilizzando un elenco fisso di elementi.

![Opzioni elenco fisso](/help/assets/list-edit-fixed.png)

Toccate o fate clic sul pulsante **Aggiungi** per inserire un nuovo elemento nell&#39;elenco.

* Immettere il testo per l&#39;elemento nell&#39;elenco oppure utilizzare la finestra di dialogo **Selezione** per scegliere un elemento dal AEM.
* Usate la maniglia di trascinamento per ridisporre gli elementi nell’elenco.
* Utilizzate l&#39;icona del cestino per eliminare gli elementi nell&#39;elenco.

#### Ricerca {#search-options}

L&#39;elenco può essere creato utilizzando i risultati di una ricerca di AEM contenuto.

![Opzioni elenco di ricerca](/help/assets/list-edit-search.png)

* **Query**
di ricerca: stringa per la quale verrà eseguita una ricerca full-text per generare gli elementi dell&#39;elenco
* **Ricerca**
inDove eseguire la ricerca
   * Utilizzare la finestra di dialogo **Selezione** per scegliere la posizione in AEM
   * Usa pagina corrente se lasciata vuota

#### Tag {#tags}

L&#39;elenco può essere creato utilizzando pagine che corrispondono a determinati tag presenti in una determinata posizione.

![Opzioni elenco dei tag](/help/assets/list-edit-tags.png)

* **Pagina**
padrePunto iniziale della corrispondenza del tag
   * Utilizzare la finestra di dialogo **Selezione** per scegliere la posizione in AEM
   * Usa pagina corrente se lasciata vuota
* ****
TagsQuali tag devono essere associati
   * Utilizzare la finestra di dialogo **Sfoglia** per selezionare i tag
* ****
Corrispondenza: consente di definire il tipo di corrispondenza da applicare a una pagina da includere nell&#39;elenco.
   * **qualsiasi tag**
   * **tutti i tag**

#### Opzioni ordinamento {#sort-options}

Indipendentemente dalla modalità di creazione dell’elenco, è sempre possibile definire alcune opzioni di ordinamento.

![Opzioni di ordinamento](/help/assets/list-edit-sort-options.png)

* **Ordina**
perModalità di ordinamento degli elementi
   * **Titolo**
   * **Data ultima modifica**
* **Ordina**
ordineOrdine di ordinamento degli articoli
   * **crescente**
   * **decrescente**
* **Numero massimo**
elementiNumero massimo di elementi visualizzati nell&#39;elenco.
   * Lasciate vuoto per restituire tutti gli elementi.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

### Scheda Impostazioni elemento {#item-settings-tab}

Utilizzando la scheda Impostazioni elemento, è possibile configurare la formattazione degli elementi dell&#39;elenco.

![Impostazioni degli elementi](/help/assets/list-edit-items.png)

* **Collega**
elementiCollega elementi alla pagina corrispondente
* **Mostra**
descrizioneMostra le descrizioni dell’elemento di collegamento
* **Mostra**
dataMostra la data di modifica dell’elemento del collegamento

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire i tipi di elenchi da consentire agli autori dei contenuti e le impostazioni degli elementi disponibili.

### Impostazioni elenco {#list-settings}

Nella scheda **Impostazioni elenco** è possibile definire il formato della data e il tipo di elenchi da rendere disponibili nel componente per gli autori del contenuto.

![Elenca le impostazioni dell&#39;elenco delle finestre di dialogo del componente](/help/assets/list-design-list-settings.png)

* **Formato data**
da utilizzare per la visualizzazione dell&#39;ultima data di modifica
* **Disabilita**
elementi figlioDisattiva il tipo di elenco figli nel componente
* **Disabilita**
staticaDisattiva il tipo di elenco statico nel componente
* **Disattiva**
ricercaDisattiva il tipo di elenco di ricerca nel componente
* **Disattiva**
tagDisattiva il tipo di elenco dei tag nel componente

### Impostazioni elemento {#item-settings}

Nella scheda **Impostazioni elemento** è possibile definire le opzioni di formattazione per i singoli elementi dell&#39;elenco che dovrebbero essere disponibili nel componente per gli autori del contenuto.

![Elenca le impostazioni della finestra di dialogo del componente](/help/assets/list-design-item-settings.png)

* **Collega**
elementiOpzione Abilita collegamenti elementi nella finestra di dialogo di  [modifica](#edit-dialog)
* **Mostra**
descrizioniOpzione Mostra descrizioni nella finestra di dialogo di  [modifica](#edit-dialog)
* **Mostra**
dataAbilita data nella finestra di dialogo di  [modifica](#edit-dialog)

### Scheda Stili {#styles-tab}

Il componente Immagine supporta il AEM [Sistema di stile](/help/get-started/authoring.md#component-styling).

## Livello dati client  Adobe {#data-layer}

Il componente Elenco supporta il [ livello dati client Adobe.](/help/developing/data-layer/overview.md)
