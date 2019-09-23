---
title: Componente elenco (v1)
seo-title: Componente elenco (v1)
description: 'null'
seo-description: Il componente Elenco componenti core consente di creare facilmente elenchi dinamici e statici.
uuid: 06658c9d-cbf2-4bfe-b425-d980d1181908
content-type: riferimento
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 7c130ccc-83ff-464d-b58f-d581f4365dbd
disttype: dist5
gnavtheme: chiaro
groupsectionnavitems: 'no'
hidemerchandisingbar: eredita
hidepromocomponent: eredita
modalsize: 426x240
noindex: vero
index: n
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# Componente elenco (v1){#list-component-v}

Il componente Elenco componenti core consente di creare facilmente elenchi dinamici e statici.

## Utilizzo {#usage}

Il componente Elenco può essere utilizzato per creare, ad esempio, un elenco dinamico di pagine figlie o un elenco statico di elementi definiti arbitrariamente.

Il tipo di elenchi disponibili e le opzioni di formattazione possono essere definite dall'autore del modello nella finestra di dialogo [della](list-v1.md#main-pars_title_1995166862)progettazione. L'editor dei contenuti può selezionare tra i tipi di elenco disponibili e come formattare gli elementi dell'elenco nella finestra di dialogo [di](list-v1.md#main-pars_title)modifica.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la v1 del componente Elenco, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

La tabella seguente elenca la compatibilità di v1 del componente Elenco.

| Versione di AEM | Componente elenco v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Elenco.
>
>Per informazioni dettagliate sulla versione corrente del componente Elenco, consultare il documento [Elenco componenti](list.md) .

## Output componente di esempio {#sample-component-output}

Esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/chlimage_1-47.png)

### HTML {#html}

```
<div class="cmp cmp-list aem-GridColumn aem-GridColumn--default--12">

<ul>
    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/arctic-surfing-in-lofoten.html">
            <span class="cmp-list--item-title">Arctic Surfing In Lofoten</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/summit-success-in-the-himalayas.html">
            <span class="cmp-list--item-title">Summit Success in the Himalayas</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/climbing-on-kalymnos-island--greece.html">
            <span class="cmp-list--item-title">Climbing on Kalymnos Island, Greece</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/running-at-the-great-wall-marathon.html">
            <span class="cmp-list--item-title">Running at the Great Wall Marathon</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/skiing-deep-powder-in-siberia.html">
            <span class="cmp-list--item-title">Skiing deep powder in Siberia</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/climbing-in-the-massif-du-mont-blanc.html">
            <span class="cmp-list--item-title">Climbing in the Massif du Mont Blanc</span>
            
        </a>
        
    </article>
</li>
</ul>

</div>
```

### JSON {#json}

```
"articles_list": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              ":type": "weretail/components/content/articleslist",
              "tagsMatch": "any",
              "displayAs": "teaser",
              "feedEnabled": "true",
              "listFrom": "children",
              "limit": "0",
              "orderBy": "cq:lastModified",
              "pageMax": "0"
            }
```

>[!NOTE]
>
>L’esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le informazioni sulla [compatibilità per i componenti core v1](versions.md#main-pars_title_236368006) .

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di configurare l’elenco e gli elementi dell’elenco.

### Impostazioni elenco {#list-settings}

L'elenco può essere creato in diversi modi.

* [Pagine figlie](list-v1.md#main-pars_title_1861279796)
* [Elenco fisso](list-v1.md#main-pars_title_1227896889)
* [Ricerca](list-v1.md#main-pars_title_1224003560)
* [Tag](list-v1.md#main-pars_title_700759533)

Indipendentemente dalla modalità di creazione dell'elenco, è sempre possibile configurare le opzioni [di](list-v1.md#main-pars_title_1568376452) ordinamento.

![](assets/chlimage_1-38.png)

A seconda di come l’autore del contenuto sceglie di generare l’elenco, le opzioni di configurazione aggiuntive cambieranno.

#### Pagine figlie {#child-pages}

È possibile creare l'elenco delle pagine figlie della pagina corrente o di un'altra pagina.

![](assets/chlimage_1-39.png)

* **Pagina padre**
   * Pagina di cui devono essere elencate le pagine figlie
   * Lascia vuoto per utilizzare la pagina corrente
* **Profondità** figlio - Quanti livelli della gerarchia devono essere utilizzati

#### Fixed List {#fixed-list}

L'elenco può essere creato utilizzando un elenco fisso di elementi.

![](assets/chlimage_1-40.png)

Toccate o fate clic sul pulsante **Aggiungi** per inserire un nuovo elemento nell’elenco.

* Immettete il testo per l’elemento nell’elenco o utilizzate la finestra di dialogo **di** selezione per scegliere un elemento da AEM.
* Usate la maniglia di trascinamento per ridisporre gli elementi nell’elenco.
* Utilizzate l'icona del cestino per eliminare gli elementi nell'elenco.

#### Ricerca {#search}

L'elenco può essere creato utilizzando i risultati di una ricerca di contenuto AEM.

![](assets/chlimage_1-41.png)

* **Query** di ricerca - Stringa per la quale verrà eseguita una ricerca full-text per generare gli elementi elenco
* **Cerca in** - Dove eseguire la ricerca
   * Utilizzare la finestra di dialogo **** Selezione per scegliere il percorso in AEM
   * Usa pagina corrente se lasciata vuota

#### Tag {#tags}

L'elenco può essere creato utilizzando pagine che corrispondono a determinati tag presenti in una determinata posizione.

![](assets/chlimage_1-42.png)

* **Pagina** padre - Punto di inizio della corrispondenza del tag
   * Utilizzare la finestra di dialogo **** Selezione per scegliere il percorso in AEM
   * Usa pagina corrente se lasciata vuota
* **Tag** - Quali tag devono corrispondere
   * Utilizzare la finestra di dialogo **Sfoglia** per selezionare i tag
* **Corrispondenza** : consente di definire il tipo di corrispondenza da applicare a una pagina da includere nell'elenco.
   * **qualsiasi tag**
   * **tutti i tag**

#### Opzioni di ordinamento {#sort-options}

Indipendentemente dalla modalità di creazione dell’elenco, è sempre possibile definire alcune opzioni di ordinamento.

![](assets/chlimage_1-43.png)

* **Ordina per** - Modalità di ordinamento degli elementi
   * **Titolo**
   * **Data ultima modifica**
* **Ordina ordine** - L'ordine in cui devono essere ordinati gli articoli
   * **crescente**
   * **decrescente**
* **Numero massimo elementi** - Numero massimo di elementi visualizzati nell'elenco.
   * Lasciate vuoto per restituire tutti gli elementi.

### Impostazioni elemento {#item-settings}

Utilizzando la scheda Impostazioni **** elemento, è possibile configurare la formattazione degli elementi dell'elenco.

![](assets/chlimage_1-44.png)

* **Collega elementi** Collega elementi alla pagina corrispondente
* **Mostra descrizione** Mostra descrizioni dell’elemento di collegamento
* **Mostra data** Mostra data modifica elemento collegamento

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire i tipi di elenchi da consentire agli autori dei contenuti e le impostazioni degli elementi disponibili.

### Impostazioni elenco {#list-settings-1}

Nella scheda Impostazioni **** elenco, è possibile definire il formato della data e il tipo di elenchi da rendere disponibili nel componente per gli autori del contenuto.

![](assets/chlimage_1-45.png)

* **Formato** data - Formato da utilizzare per la visualizzazione dell'ultima data di modifica
* **Disattiva elementi figlio** - Disattiva il tipo di elenco degli elementi figlio nel componente
* **Disattiva statico** - Disattiva il tipo di elenco statico nel componente
* **Disattiva ricerca** - Disattiva il tipo di elenco di ricerca nel componente
* **Disattiva tag** - Disattiva il tipo di elenco dei tag nel componente

### Impostazioni elemento {#item-settings-1}

Nella scheda Impostazioni **** elemento è possibile definire le opzioni di formattazione per i singoli elementi dell'elenco che dovrebbero essere disponibili nel componente per gli autori dei contenuti.

![](assets/chlimage_1-46.png)

* **Collega elementi** - Opzione Attiva collegamenti elementi nella finestra di dialogo di [modifica](list-v1.md#main-pars_title_550499279)
* **Mostra descrizioni** - Opzione Mostra descrizioni nella finestra di dialogo di [modifica](list-v1.md#main-pars_title_550499279)
* **Mostra data** - Abilita opzione Mostra data nella finestra di dialogo di [modifica](list-v1.md#main-pars_title_550499279)

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Elenco [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.
