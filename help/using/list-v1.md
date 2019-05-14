---
title: Componente elenco (v 1)
seo-title: Componente elenco (v 1)
description: 'null'
seo-description: Il componente Elenco componenti core consente di creare con facilità elenchi statici e statici.
uuid: 06658 c 9 d-cbf 2-4 bfe-b 425-d 980 d 1181908
content-type: riferimento
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: 7 c 130 ccc -83 ff -464 d-b 58 f-d 581 f 4365 dbd
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


# Componente elenco (v 1){#list-component-v}

Il componente Elenco componenti core consente di creare con facilità elenchi statici e statici.

## Utilizzo {#usage}

Il componente Elenco può essere utilizzato per creare, ad esempio, un elenco dinamico di pagine figlie o un elenco statico di elementi definiti arbitrariamente.

Il tipo di elenchi disponibili e le opzioni di formattazione possono essere definite dall&#39;autore del modello nella finestra di dialogo [di progettazione](list-v1.md#main-pars_title_1995166862). L&#39;Editor contenuto può selezionare i tipi di elenchi disponibili e formattare gli elementi dell&#39;elenco nella finestra di dialogo [di modifica](list-v1.md#main-pars_title).

## Versione e Compatibilità {#version-and-compatibility}

Questo documento descrive v 1 del componente Elenco, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità della release v 1 del componente Elenco.

| Versione di AEM | Componente elenco v 1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la v 1 del componente Elenco.
>
>Per informazioni dettagliate sulla versione corrente del componente Elenco, consultate [il documento Componente](list.md) Elenco.

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>L&#39;esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consultate le informazioni [di compatibilità per i componenti core v 1](versions.md#main-pars_title_236368006) .

## Finestra di dialogo di modifica {#edit-dialog}

La finestra di dialogo di modifica consente all&#39;autore del contenuto di configurare l&#39;elenco e gli elementi dell&#39;elenco.

### Impostazioni elenco {#list-settings}

L&#39;elenco può essere creato in diversi modi.

* [Pagine figlie](list-v1.md#main-pars_title_1861279796)
* [Elenco fisso](list-v1.md#main-pars_title_1227896889)
* [Ricerca](list-v1.md#main-pars_title_1224003560)
* [Tag](list-v1.md#main-pars_title_700759533)

A prescindere dalla modalità di creazione dell&#39;elenco, [sono disponibili Opzioni](list-v1.md#main-pars_title_1568376452) di ordinamento.

![](assets/chlimage_1-38.png)

A seconda del modo in cui l&#39;autore del contenuto sceglie di creare l&#39;elenco, vengono modificate anche le opzioni di configurazione aggiuntive.

#### Pagine figlie {#child-pages}

L&#39;elenco può essere creato dalle pagine figlie della pagina corrente o di un&#39;altra pagina.

![](assets/chlimage_1-39.png)

* **Pagina padre**
   * Pagina le cui pagine figlie devono essere elencate
   * Lasciate vuoto per usare la pagina corrente
* **Profondità secondari** - Il numero di livelli in basso nella gerarchia

#### Elenco fisso {#fixed-list}

L&#39;elenco può essere creato utilizzando un elenco fisso di elementi.

![](assets/chlimage_1-40.png)

Toccate o fate clic sul **pulsante Aggiungi** per inserire un nuovo elemento nell&#39;elenco.

* Immettete il testo per l&#39;elemento nell&#39;elenco o utilizzate la **finestra di dialogo di selezione** per scegliere un elemento da AEM.
* Utilizzare la maniglia di trascinamento per ridisporre gli elementi nell&#39;elenco.
* Usate l&#39;icona del cestino per eliminare gli elementi nell&#39;elenco.

#### Ricerca {#search}

L&#39;elenco può essere creato utilizzando i risultati di una ricerca di contenuto AEM.

![](assets/chlimage_1-41.png)

* **Query di ricerca** - Stringa per la quale verrà eseguita una ricerca full-text per generare gli elementi dell&#39;elenco
* **Cerca in** - Dove eseguire la ricerca
   * Utilizzare la **finestra di dialogo** di selezione per scegliere la posizione in AEM
   * Usa pagina corrente se lasciata vuota

#### Tag {#tags}

L&#39;elenco può essere creato utilizzando pagine che corrispondono a determinati tag in una posizione specifica.

![](assets/chlimage_1-42.png)

* **Pagina** padre: dove deve iniziare la corrispondenza dei tag
   * Utilizzare la **finestra di dialogo** di selezione per scegliere la posizione in AEM
   * Usa pagina corrente se lasciata vuota
* **Tag** : corrispondenti ai tag
   * Utilizzare la **finestra di** dialogo Sfoglia per selezionare i tag
* **Corrispondenza** : definite quale tipo di corrispondenza deve qualificare una pagina da includere nell&#39;elenco
   * **qualsiasi tag**
   * **tutti i tag**

#### Opzioni ordinamento {#sort-options}

A prescindere dalla modalità di creazione dell&#39;elenco, alcune opzioni di ordinamento possono essere sempre definite.

![](assets/chlimage_1-43.png)

* **Ordina per** - Come devono essere ordinati gli elementi
   * **Titolo**
   * **Data ultima modifica**
* **Ordinamento:** ordine in cui gli elementi devono essere ordinati
   * **crescente**
   * **decrescente**
* **Massimo elementi** - Numero massimo di elementi visualizzati nell&#39;elenco.
   * Lasciate vuoto per restituire tutti gli elementi.

### Impostazioni elemento {#item-settings}

La scheda **Impostazioni** elemento consente di configurare la formattazione degli elementi dell&#39;elenco.

![](assets/chlimage_1-44.png)

* **Collegare elementi**
collegamento alla pagina corrispondente
* **Mostra descrizione**
Mostra le descrizioni della voce di collegamento
* **Mostra data di modifica** mostra data di modifica dell&#39;elemento di collegamento

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire quali tipi di elenchi consentire agli autori di contenuto e alle impostazioni degli elementi disponibili.

### Impostazioni elenco {#list-settings-1}

Nella **scheda Impostazioni** elenco, è possibile definire il formato della data e il tipo di elenchi disponibili nel componente agli autori di contenuto.

![](assets/chlimage_1-45.png)

* **Formato data** - Formato da utilizzare per la visualizzazione dell&#39;ultima data di modifica
* **Disattiva elementi figlio** - Disabilita il tipo di elenco Elementi figlio nel componente
* **Disable Static** - Disable the static list type in the component
* **Disattiva ricerca** : disabilita il tipo di elenco di ricerca nel componente
* **Disattiva tag** - Disabilita il tipo di elenco tag nel componente

### Impostazioni elemento {#item-settings-1}

Nella **scheda Impostazioni** elemento, le opzioni di formattazione per i singoli elementi dell&#39;elenco che dovrebbero essere disponibili nel componente per gli autori di contenuto possono essere definite.

![](assets/chlimage_1-46.png)

* **Collega elementi** - Opzione Abilita elementi collegamento nella finestra [di dialogo di modifica](list-v1.md#main-pars_title_550499279)
* **Mostra descrizioni** - Abilita le descrizioni Mostra nella finestra di [dialogo di modifica](list-v1.md#main-pars_title_550499279)
* **Mostra data** - Abilita data mostra data nella finestra [di dialogo di modifica](list-v1.md#main-pars_title_550499279)

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente [Elenco è disponibile su github](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list).

L&#39;intero progetto componenti core può essere scaricato da github.

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).
