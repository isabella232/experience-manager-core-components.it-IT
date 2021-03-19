---
title: Componente elenco (v1)
description: Il componente Elenco dei componenti core consente di creare facilmente elenchi dinamici e statici.
index: n
role: Architetto, Sviluppatore, Amministratore, Business Practices
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 4%

---


# Componente elenco (v1) {#list-component-v}

Il componente Elenco dei componenti core consente di creare facilmente elenchi dinamici e statici.

## Utilizzo {#usage}

Il componente Elenco può essere utilizzato per creare, ad esempio, un elenco dinamico di pagine figlie o un elenco statico di elementi definiti arbitrariamente.

Il tipo di elenchi disponibili e le opzioni di formattazione possono essere definite dall&#39;autore del modello nella finestra di dialogo [progettazione](#design-dialog). L&#39;editor dei contenuti può scegliere tra i tipi di elenco disponibili e come formattare gli elementi dell&#39;elenco nella finestra di dialogo [modifica](#edit-dialog).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Elenco, originariamente introdotto con la versione 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità della versione v1 del componente Elenco.

| Versione di AEM | Componente elenco v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Elenco.
>
>Per informazioni dettagliate sulla versione corrente del componente Elenco, consultare il documento [Componente elenco](/help/components/list.md) .

## Output componente di esempio {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>L’esportazione JSON dai componenti core richiede la versione 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le [informazioni sulla compatibilità per i componenti core v1](/help/versions.md) .

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di configurare l’elenco e gli elementi dell’elenco.

### Impostazioni elenco {#list-settings}

L’elenco può essere creato in diversi modi.

* [Pagine figlie](#child-pages)
* [Elenco fisso](#fixed-list)
* [Ricerca](#search-list)
* [Tag](#tags)

Indipendentemente dalla modalità di creazione dell’elenco, è sempre possibile configurare le [Opzioni di ordinamento](#sort-options).

![](/help/assets/chlimage_1-38.png)

A seconda di come l’autore del contenuto sceglie di creare l’elenco, le opzioni di configurazione aggiuntive cambieranno.

#### Pagine figlie {#child-pages}

L’elenco può essere costituito dalle pagine figlie della pagina corrente o di un’altra pagina.

![](/help/assets/chlimage_1-39.png)

* **Pagina padre**
   * Pagina di cui creare l’elenco le pagine figlie
   * Lascia vuoto per utilizzare la pagina corrente
* **Profondità figlio** : quanti livelli della gerarchia devono essere utilizzati

#### Elenco fisso {#fixed-list}

L’elenco può essere creato utilizzando un elenco fisso di elementi.

![](/help/assets/chlimage_1-40.png)

Tocca o fai clic sul pulsante **Aggiungi** per inserire un nuovo elemento nell’elenco.

* Inserisci il testo per l&#39;elemento nell&#39;elenco o utilizza la **finestra di dialogo di selezione** per scegliere un elemento da AEM.
* Utilizzare la maniglia di trascinamento per ridisporre gli elementi nell’elenco.
* Utilizza l’icona del cestino per eliminare gli elementi dall’elenco.

#### Ricerca {#search-list}

L’elenco può essere creato utilizzando i risultati di una ricerca di contenuto AEM.

![](/help/assets/chlimage_1-41.png)

* **Query di ricerca**  - Stringa per la quale verrà eseguita una ricerca full-text per generare gli elementi dell’elenco
* **Ricerca in** : dove deve essere eseguita la ricerca
   * Utilizza la **finestra di dialogo di selezione** per scegliere la posizione in AEM
   * Usa pagina corrente se lasciato vuoto

#### Tag {#tags}

L’elenco può essere creato utilizzando pagine che corrispondono a determinati tag presenti in una posizione specifica.

![](/help/assets/chlimage_1-42.png)

* **Pagina**  padre: inizio della corrispondenza del tag
   * Utilizza la **finestra di dialogo di selezione** per scegliere la posizione in AEM
   * Usa pagina corrente se lasciato vuoto
* **Tag** : a quali tag deve corrispondere?
   * Utilizza la finestra di dialogo **Sfoglia** per selezionare i tag
* **Corrispondenza** : consente di definire il tipo di corrispondenza da applicare a una pagina da includere nell’elenco.
   * **qualsiasi tag**
   * **tutti i tag**

#### Opzioni di ordinamento {#sort-options}

Indipendentemente dalla modalità di creazione dell’elenco, è sempre possibile definire alcune opzioni di ordinamento.

![](/help/assets/chlimage_1-43.png)

* **Ordina per**  - Come devono essere ordinati gli elementi
   * **Titolo**
   * **Data ultima modifica**
* **Ordina** : l&#39;ordine in cui gli articoli devono essere ordinati
   * **crescente**
   * **decrescente**
* **Numero massimo elementi** : numero massimo di elementi visualizzati nell&#39;elenco.
   * Lascia vuoto per restituire tutti gli elementi.

### Impostazioni elemento {#item-settings}

Utilizzando la scheda **Impostazioni elemento**, è possibile configurare la formattazione degli elementi dell’elenco.

![](/help/assets/chlimage_1-44.png)

* **Collega**
elementiCollega elementi alla pagina corrispondente
* **Mostra**
descrizioneMostra descrizioni dell&#39;elemento di collegamento
* **Mostra**
dataMostra data di modifica dell&#39;elemento di collegamento

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire i tipi di elenchi da consentire agli autori dei contenuti e le impostazioni degli elementi disponibili.

### Impostazioni elenco {#list-settings-1}

Nella scheda **Impostazioni elenco** , è possibile definire il formato della data e il tipo di elenchi da rendere disponibili nel componente agli autori dei contenuti.

![](/help/assets/chlimage_1-45.png)

* **Formato data**  - Formato da utilizzare per la visualizzazione dell&#39;ultima data di modifica
* **Disabilita elementi figlio**  - Disattiva il tipo di elenco figlio nel componente
* **Disattiva statico** : disattiva il tipo di elenco statico nel componente
* **Disattiva ricerca**  - Disattiva il tipo di elenco di ricerca nel componente
* **Disabilita tag** : disabilita il tipo di elenco dei tag nel componente

### Impostazioni elemento {#item-settings-1}

Nella scheda **Impostazioni elemento** è possibile definire le opzioni di formattazione per i singoli elementi dell’elenco che devono essere disponibili nel componente per gli autori di contenuti.

![](/help/assets/chlimage_1-46.png)

* **Collega elementi** : opzione Abilita elementi di collegamento nella finestra di dialogo di  [modifica](#edit-dialog)
* **Mostra descrizioni**  - Abilita Mostra descrizioni opzione nella finestra di dialogo di  [modifica](#edit-dialog)
* **Mostra data** : opzione Abilita data mostra nella finestra di dialogo di  [modifica](#edit-dialog)

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Elenco [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .
