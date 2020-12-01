---
title: Componente elenco (v1)
description: Il componente Elenco componenti core consente di creare facilmente elenchi dinamici e statici.
index: n
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 4%

---


# Componente elenco (v1) {#list-component-v}

Il componente Elenco componenti core consente di creare facilmente elenchi dinamici e statici.

## Utilizzo {#usage}

Il componente Elenco può essere utilizzato per creare, ad esempio, un elenco dinamico di pagine figlie o un elenco statico di elementi definiti arbitrariamente.

Il tipo di elenchi disponibili e le opzioni di formattazione possono essere definite dall&#39;autore del modello nella finestra di dialogo [progettazione](#design-dialog). L&#39;editor di contenuti può selezionare tra i tipi di elenco disponibili e come formattare gli elementi dell&#39;elenco nella finestra di dialogo di [modifica](#edit-dialog).

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
>Per informazioni dettagliate sulla versione corrente del componente Elenco, vedere il documento [Componente elenco](/help/components/list.md).

## Esempio di output del componente {#sample-component-output}

Esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](/help/assets/chlimage_1-47.png)

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
>L’esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, vedere le [informazioni sulla compatibilità per i componenti core v1](/help/versions.md).

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di configurare l’elenco e gli elementi dell’elenco.

### Impostazioni elenco {#list-settings}

L&#39;elenco può essere creato in diversi modi.

* [Pagine figlie](#child-pages)
* [Elenco fisso](#fixed-list)
* [Ricerca](#search-list)
* [Tag](#tags)

Indipendentemente dalla modalità di creazione dell&#39;elenco, è sempre possibile configurare [Opzioni di ordinamento](#sort-options).

![](/help/assets/chlimage_1-38.png)

A seconda di come l’autore del contenuto sceglie di generare l’elenco, le opzioni di configurazione aggiuntive cambieranno.

#### Pagine figlie {#child-pages}

È possibile creare l&#39;elenco delle pagine figlie della pagina corrente o di un&#39;altra pagina.

![](/help/assets/chlimage_1-39.png)

* **Pagina padre**
   * La pagina di cui devono essere elencate le pagine figlie
   * Lascia vuoto per utilizzare la pagina corrente
* **Profondità**  figlio - Quanti livelli della gerarchia devono essere utilizzati

#### Elenco fisso {#fixed-list}

L&#39;elenco può essere creato utilizzando un elenco fisso di elementi.

![](/help/assets/chlimage_1-40.png)

Toccate o fate clic sul pulsante **Aggiungi** per inserire un nuovo elemento nell&#39;elenco.

* Immettere il testo per l&#39;elemento nell&#39;elenco oppure utilizzare la finestra di dialogo **Selezione** per scegliere un elemento dal AEM.
* Usate la maniglia di trascinamento per ridisporre gli elementi nell’elenco.
* Utilizzate l&#39;icona del cestino per eliminare gli elementi nell&#39;elenco.

#### Ricerca {#search-list}

L&#39;elenco può essere creato utilizzando i risultati di una ricerca di AEM contenuto.

![](/help/assets/chlimage_1-41.png)

* **Query**  di ricerca - Stringa per la quale verrà eseguita una ricerca full-text per generare gli elementi dell&#39;elenco
* **Cerca in**  - Dove deve essere eseguita la ricerca
   * Utilizzare la finestra di dialogo **Selezione** per scegliere la posizione in AEM
   * Usa pagina corrente se lasciata vuota

#### Tag {#tags}

L&#39;elenco può essere creato utilizzando pagine che corrispondono a determinati tag presenti in una determinata posizione.

![](/help/assets/chlimage_1-42.png)

* **Pagina**  padre - Punto di inizio della corrispondenza del tag
   * Utilizzare la finestra di dialogo **Selezione** per scegliere la posizione in AEM
   * Usa pagina corrente se lasciata vuota
* **Tag**  - Quali tag devono corrispondere
   * Utilizzare la finestra di dialogo **Sfoglia** per selezionare i tag
* **Corrispondenza** : consente di definire il tipo di corrispondenza da applicare a una pagina da includere nell&#39;elenco.
   * **qualsiasi tag**
   * **tutti i tag**

#### Opzioni ordinamento {#sort-options}

Indipendentemente dalla modalità di creazione dell’elenco, è sempre possibile definire alcune opzioni di ordinamento.

![](/help/assets/chlimage_1-43.png)

* **Ordina per**  - Modalità di ordinamento degli elementi
   * **Titolo**
   * **Data ultima modifica**
* **Ordina ordine** : l&#39;ordine in cui gli articoli devono essere ordinati
   * **crescente**
   * **decrescente**
* **Numero massimo elementi**  - Numero massimo di elementi visualizzati nell&#39;elenco.
   * Lasciate vuoto per restituire tutti gli elementi.

### Impostazioni elemento {#item-settings}

Utilizzando la scheda **Impostazioni elemento**, è possibile configurare la formattazione degli elementi dell&#39;elenco.

![](/help/assets/chlimage_1-44.png)

* **Collega**
elementiCollega elementi alla pagina corrispondente
* **Mostra**
descrizioneMostra le descrizioni dell’elemento di collegamento
* **Mostra**
dataMostra la data di modifica dell’elemento del collegamento

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire i tipi di elenchi da consentire agli autori dei contenuti e le impostazioni degli elementi disponibili.

### Impostazioni elenco {#list-settings-1}

Nella scheda **Impostazioni elenco** è possibile definire il formato della data e il tipo di elenchi da rendere disponibili nel componente per gli autori del contenuto.

![](/help/assets/chlimage_1-45.png)

* **Formato**  data - Formato da utilizzare per la visualizzazione dell&#39;ultima data di modifica
* **Disabilita elementi figlio**  - Disattiva il tipo di elenco degli elementi figlio nel componente
* **Disabilita statica**  - Disattiva il tipo di elenco statico nel componente
* **Disabilita ricerca**  - Disattiva il tipo di elenco di ricerca nel componente
* **Disabilita tag**  - Disattiva il tipo di elenco dei tag nel componente

### Impostazioni elemento {#item-settings-1}

Nella scheda **Impostazioni elemento** è possibile definire le opzioni di formattazione per i singoli elementi dell&#39;elenco che dovrebbero essere disponibili nel componente per gli autori del contenuto.

![](/help/assets/chlimage_1-46.png)

* **Collega elementi**  - Opzione Attiva collegamenti elementi nella finestra di dialogo di  [modifica](#edit-dialog)
* **Mostra descrizioni**  - Opzione Mostra descrizioni nella finestra di dialogo di  [modifica](#edit-dialog)
* **Mostra data**  - Abilita opzione Mostra data nella finestra di dialogo di  [modifica](#edit-dialog)

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Elenco [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).
