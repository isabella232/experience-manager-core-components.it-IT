---
title: Elenca componente
description: Il componente Elenco dei componenti core consente di creare facilmente elenchi dinamici e statici.
role: Architect, Developer, Admin, User
exl-id: 662ab508-0253-4d28-b95c-8c4cde8173bd
source-git-commit: eea159ad494150c3f132166d48f624605eb92e64
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 4%

---

# Elenca componente{#list-component}

Il componente Elenco dei componenti core consente di creare facilmente elenchi dinamici e statici.

## Utilizzo {#usage}

Il componente Elenco può essere utilizzato per creare, ad esempio, un elenco dinamico di pagine figlie o un elenco statico di elementi definiti arbitrariamente. Il tipo di elenchi disponibili e le opzioni di formattazione possono essere definite dall&#39;autore del modello nella finestra di dialogo [progettazione](#design-dialog). L&#39;editor dei contenuti può scegliere tra i tipi di elenco disponibili e come formattare gli elementi dell&#39;elenco nella finestra di dialogo [modifica](#edit-dialog).

## Reindirizzamenti negli elenchi {#redirects}

Quando una pagina dispone di una destinazione di reindirizzamento (indipendentemente dal fatto che punti a un URL esterno o a un&#39;altra pagina AEM), allora un elenco che contiene i collegamenti a tale punto direttamente all&#39;URL della destinazione di reindirizzamento.

### Esempio {#redirect-example}

* Crea una pagina A che reindirizza alla pagina B.
* Crea una pagina C che reindirizza a `https://aemcomponents.dev`
* In una pagina D, inserisci un componente elenco che contiene le pagine A e C
* I rispettivi collegamenti generati puntano direttamente alle pagine B e `https://aemcomponents.dev`

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Elenco è v2, introdotta con la versione 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](v1/list-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione e dell’output HTML e JSON del componente Elenco , visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_list) .

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Elenco [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_list_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di configurare l’elenco e gli elementi dell’elenco.

### Scheda Impostazioni elenco {#list-settings-tab}

L’elenco può essere creato in diversi modi.

* [Pagine figlie](#child-pages)
* [Elenco fisso](#fixed-list)
* [Ricerca](#search-options)
* [Tag](#tags)

Indipendentemente dalla modalità di creazione dell’elenco, è sempre possibile configurare le opzioni di ordinamento e ID ](#sort-options).[

![Finestra di dialogo di modifica del componente Elenco](/help/assets/list-edit.png)

A seconda di come l’autore del contenuto sceglie di creare l’elenco, le opzioni di configurazione aggiuntive cambieranno.

#### Pagine figlie {#child-pages}

L’elenco può essere costituito dalle pagine figlie della pagina corrente o di un’altra pagina.

![Opzioni pagina figlia](/help/assets/list-edit-child-pages.png)

* **Pagina padre**
   * Pagina di cui creare l’elenco le pagine figlie
   * Lascia vuoto per utilizzare la pagina corrente

* **Secondaria-**
ProfonditàQuanti livelli della gerarchia devono essere utilizzati

#### Elenco fisso {#fixed-list}

L’elenco può essere creato utilizzando un elenco fisso di elementi.

![Opzioni elenco fisse](/help/assets/list-edit-fixed.png)

Tocca o fai clic sul pulsante **Aggiungi** per inserire un nuovo elemento nell’elenco.

* Inserisci il testo per l&#39;elemento nell&#39;elenco o utilizza la **finestra di dialogo di selezione** per scegliere un elemento da AEM.
* Utilizzare la maniglia di trascinamento per ridisporre gli elementi nell’elenco.
* Utilizza l’icona del cestino per eliminare gli elementi dall’elenco.

#### Ricerca {#search-options}

L’elenco può essere creato utilizzando i risultati di una ricerca di contenuto AEM.

![Opzioni dell’elenco di ricerca](/help/assets/list-edit-search.png)

* **Ricerca**
queryStringa per la quale verrà eseguita una ricerca full-text per generare gli elementi dell’elenco
* **Ricerca**
inDove eseguire la ricerca
   * Utilizza la **finestra di dialogo di selezione** per scegliere la posizione in AEM
   * Usa pagina corrente se lasciato vuoto

#### Tag {#tags}

L’elenco può essere creato utilizzando pagine che corrispondono a determinati tag presenti in una posizione specifica.

![Opzioni dell’elenco dei tag](/help/assets/list-edit-tags.png)

* **Pagina**
padreDa cui deve iniziare la corrispondenza del tag
   * Utilizza la **finestra di dialogo di selezione** per scegliere la posizione in AEM
   * Usa pagina corrente se lasciato vuoto
* ****
Tag: a quali tag deve corrispondere?
   * Utilizza la finestra di dialogo **Sfoglia** per selezionare i tag
* ****
MatchDefine quale tipo di corrispondenza deve qualificare una pagina da includere nell’elenco
   * **qualsiasi tag**
   * **tutti i tag**

#### Opzioni di ordinamento {#sort-options}

Indipendentemente dalla modalità di creazione dell’elenco, è sempre possibile definire alcune opzioni di ordinamento.

![Opzioni di ordinamento](/help/assets/list-edit-sort-options.png)

* **Ordina**
perCome ordinare gli elementi
   * **Titolo**
   * **Data ultima modifica**
* **Ordina**
ordineOrdine in cui gli articoli devono essere ordinati
   * **crescente**
   * **decrescente**
* **Numero massimo**
elementiNumero massimo di elementi visualizzati nell&#39;elenco.
   * Lascia vuoto per restituire tutti gli elementi.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

### Scheda Impostazioni elemento {#item-settings-tab}

Utilizzando la scheda Impostazioni elemento è possibile configurare la formattazione degli elementi dell’elenco.

![Impostazioni elemento](/help/assets/list-edit-items.png)

* **Collega**
elementiCollega elementi alla pagina corrispondente
* **Mostra**
descrizioneMostra descrizioni dell&#39;elemento di collegamento
* **Mostra**
dataMostra data di modifica dell&#39;elemento di collegamento

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire i tipi di elenchi da consentire agli autori dei contenuti e le impostazioni degli elementi disponibili.

### Impostazioni elenco {#list-settings}

Nella scheda **Impostazioni elenco** , è possibile definire il formato della data e il tipo di elenchi da rendere disponibili nel componente agli autori dei contenuti.

![Impostazione della finestra di dialogo di progettazione del componente Elenco](/help/assets/list-design-list-settings.png)

* **Formato data**
da utilizzare per la visualizzazione dell&#39;ultima data di modifica
* **Disabilita**
elementi figlioDisabilita il tipo di elenco figlio nel componente
* **Disattiva**
staticoDisabilita il tipo di elenco statico nel componente
* **Disattiva**
ricercaDisattiva il tipo di elenco di ricerca nel componente
* **Disattiva**
tagDisabilita il tipo di elenco dei tag nel componente

### Impostazioni elemento {#item-settings}

Nella scheda **Impostazioni elemento** è possibile definire le opzioni di formattazione per i singoli elementi dell’elenco che devono essere disponibili nel componente per gli autori di contenuti.

![Impostazioni della finestra di dialogo di progettazione del componente elenco](/help/assets/list-design-item-settings.png)

* **Collega**
elementiOpzione Abilita elementi di collegamento nella finestra di dialogo di  [modifica](#edit-dialog)
* **Mostra**
descrizioniAbilita opzione Mostra descrizioni nella finestra di dialogo di  [modifica](#edit-dialog)
* **Mostra opzione**
dataAttiva data nella finestra di dialogo di  [modifica](#edit-dialog)

### Scheda Stili {#styles-tab}

Il componente Immagine supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

## Livello dati client di Adobe {#data-layer}

Il componente Elenco supporta il [Livello dati client Adobe.](/help/developing/data-layer/overview.md)
