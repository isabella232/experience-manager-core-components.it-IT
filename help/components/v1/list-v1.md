---
title: Componente Elenco (v1)
description: Il componente core Elenco consente di creare facilmente elenchi dinamici e statici.
index: n
role: Architect, Developer, Admin, User
exl-id: 510d059c-e60a-40aa-9032-66a901109f6e
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 100%

---

# Componente Elenco (v1) {#list-component-v}

Il componente core Elenco consente di creare facilmente elenchi dinamici e statici.

## Utilizzo {#usage}

Il componente Elenco può essere utilizzato per creare, ad esempio, un elenco dinamico di pagine figlie o un elenco statico di elementi definiti arbitrariamente.

Il tipo di elenchi disponibili e le opzioni di formattazione possono essere definiti dall’autore del modello nella [finestra di dialogo per progettazione](#design-dialog). L’editor di contenuto può scegliere tra i tipi di elenchi disponibili e come formattare gli elementi dell’elenco nella [finestra di dialogo per modifica](#edit-dialog).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Elenco, originariamente introdotto con la versione 1.0.0 dei Componenti core in AEM 6.3.

La tabella che segue riporta la compatibilità della versione 1 del componente Elenco.

| Versione di AEM | Componente Elenco v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Elenco.
>
>Per informazioni dettagliate sulla versione corrente del componente Elenco, vedi il documento [Componente Elenco](/help/components/list.md).

## Esempio di output del componente {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://experienceleague.adobe.com/docs/experience-manager-64/developing/bestpractices/we-retail/we-retail.html?lang=it).

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
>L’esportazione JSON dai Componenti core richiede la versione 1.1.0 dei Componenti core. Per ulteriori informazioni, vedi le [informazioni sulla compatibilità dei Componenti core v1](/help/versions.md).

## Finestra di dialogo per modifica {#edit-dialog}

La finestra di dialogo per modifica consente all’autore di contenuto di configurare l’elenco e i relativi elementi.

### Impostazioni elenco {#list-settings}

L’elenco può essere creato in diversi modi.

* [Pagine figlie](#child-pages)
* [Elenco fisso](#fixed-list)
* [Ricerca](#search-list)
* [Tag](#tags)

Indipendentemente dalla modalità di creazione dell’elenco, è sempre possibile configurare le [Opzioni di ordinamento](#sort-options).

![](/help/assets/chlimage_1-38.png)

A seconda di come l’autore del contenuto sceglie di creare l’elenco, le opzioni di configurazione aggiuntive cambiano.

#### Pagine figlie {#child-pages}

L’elenco può essere costituito dalle pagine figlie della pagina corrente o di un’altra pagina.

![](/help/assets/chlimage_1-39.png)

* **Pagina padre**
   * Pagina da cui creare l’elenco di pagine figlie
   * Lascia il campo vuoto per usare la pagina corrente
* **Profondità elementi figlio**: quanti livelli di profondità gerarchica devono essere utilizzati

#### Elenco fisso {#fixed-list}

L’elenco può essere creato utilizzando elementi fissi.

![](/help/assets/chlimage_1-40.png)

Tocca il o fai clic sul pulsante **Aggiungi** per inserire un nuovo elemento nell’elenco.

* Inserisci il testo per l’elemento inserito nell’elenco oppure utilizza la **finestra di dialogo per selezione** per scegliere un elemento da AEM.
* Utilizza la maniglia di trascinamento per modificare la disposizione degli elementi nell’elenco.
* Utilizza l’icona cestino per eliminare elementi dall’elenco.

#### Ricerca {#search-list}

L’elenco può essere creato utilizzando i risultati di una ricerca di contenuto AEM.

![](/help/assets/chlimage_1-41.png)

* **Query di ricerca**: stringa per la quale verrà eseguita una ricerca di testo completa per generare gli elementi dell’elenco
* **Cerca in**: posizione in cui eseguire la ricerca
   * Utilizza la **finestra di dialogo per selezione** per scegliere la posizione in AEM
   * Se non specificata, viene utilizzata la pagina corrente

#### Tag {#tags}

L’elenco può essere creato utilizzando pagine che corrispondono a determinati tag presenti in una posizione specifica.

![](/help/assets/chlimage_1-42.png)

* **Pagina padre**: la pagina da cui inizia la ricerca delle corrispondenze con i tag
   * Utilizza la **finestra di dialogo per selezione** per scegliere la posizione in AEM
   * Se non specificata, viene utilizzata la pagina corrente
* **Tag**: i tag per i quali deve esistere una corrispondenza
   * Utilizza la finestra di dialogo **Sfoglia** per selezionare i tag
* **Corrispondenza**: consente di definire il tipo di corrispondenza da applicare a una pagina da includere nell’elenco
   * **qualsiasi tag**
   * **tutti i tag**

#### Opzioni di ordinamento {#sort-options}

Indipendentemente dalla modalità di creazione dell’elenco, è sempre possibile definire alcune opzioni di ordinamento.

![](/help/assets/chlimage_1-43.png)

* **Ordina per**: il criterio con cui devono essere ordinati gli elementi
   * **Titolo**
   * **Data ultima modifica**
* **Ordinamento**: l’ordine in cui devono essere disposti gli elementi
   * **crescente**
   * **decrescente**
* **Max. elementi**: il numero massimo di elementi da visualizzare nell’elenco.
   * Lascia vuoto il campo per restituire tutti gli elementi.

### Impostazioni elemento {#item-settings}

Utilizzando la scheda **Impostazioni elemento**, è possibile configurare la formattazione degli elementi dell’elenco.

![](/help/assets/chlimage_1-44.png)

* **Collega elementi**
Collega gli elementi alla pagina corrispondente
* **Mostra descrizione**
Mostra la descrizione dell’elemento da collegare
* **Mostra data**
Mostra la data di modifica dell’elemento da collegare

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire i tipi di elenchi da consentire agli autori di contenuto e le impostazioni disponibili per gli elementi.

### Impostazioni elenco {#list-settings-1}

Nella scheda **Impostazioni elenco**, è possibile definire il formato della data e i tipi di elenchi da rendere disponibili nel componente per gli autori di contenuto.

![](/help/assets/chlimage_1-45.png)

* **Formato data**: il formato da utilizzare per visualizzare la data dell’ultima modifica
* **Disabilita elementi figlio**: disabilita il tipo di elenco elementi figlio nel componente
* **Disabilita statico**: disabilita il tipo di elenco statico nel componente
* **Disabilita ricerca**: disabilita il tipo di elenco ricerca nel componente
* **Disabilita tag**: disabilita il tipo di elenco tag nel componente

### Impostazioni elemento {#item-settings-1}

Nella scheda **Impostazioni elemento**, è possibile definire le opzioni di formattazione per i singoli elementi dell’elenco che devono essere disponibili nel componente per gli autori di contenuto.

![](/help/assets/chlimage_1-46.png)

* **Collega elementi**: abilita l’opzione Collega elementi nella [finestra di dialogo per modifica](#edit-dialog)
* **Mostra descrizione**: abilita l’opzione Mostra descrizione nella [finestra di dialogo per modifica](#edit-dialog)
* **Mostra data**: Abilita l’opzione Mostra data nella [finestra di dialogo per modifica](#edit-dialog)

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Elenco [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list).

L’intero progetto dei Componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).
