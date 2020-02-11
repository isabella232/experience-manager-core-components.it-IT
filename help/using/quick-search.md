---
title: Componente Ricerca rapida
description: Il componente Ricerca rapida fornisce funzionalità di ricerca a un sito Web e presenta i risultati di ricerca in modo che i visitatori possano effettuare ricerche nel sito e filtrare i risultati.
translation-type: tm+mt
source-git-commit: 65f900ad6759206a13f2bda6169900f62d968d8d

---


# Componente Ricerca rapida {#quick-search-component}

Il componente Ricerca rapida fornisce funzionalità di ricerca a un sito Web e presenta i risultati di ricerca in modo che i visitatori possano trovare facilmente contenuti corrispondenti e visualizzare i risultati.

## Utilizzo {#usage}

Il componente Ricerca rapida offre ai visitatori del sito la possibilità di cercare contenuti, visualizzare i risultati sul posto e passare facilmente alle pagine corrispondenti. I nuovi risultati vengono recuperati dinamicamente mentre l’utente scorre i risultati della ricerca.

La finestra di dialogo [di](#edit-dialog) modifica consente all’autore del contenuto di definire la posizione di inizio della ricerca nella struttura del contenuto. Utilizzando la finestra di dialogo [di](#design-dialog)progettazione, l&#39;autore del modello può impostare il valore predefinito per l&#39;inizio della ricerca nella struttura del contenuto, nonché la dimensione massima del set di risultati e la lunghezza minima del termine di ricerca.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Ricerca rapida è v1, introdotto con la release 2.0.0 dei componenti core a gennaio 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM come servizio cloud |
|--- |--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Esempio tratto da [We.Retail](https://docs.adobe.com/content/help/en/experience-manager-65/developing/bestpractices/we-retail/we-retail.html).

### Schermata {#screenshot}

![](assets/screen_shot_2018-01-19at094248.png)

### HTML {#html}

```
<section class="cmp-search" role="search" data-cmp-is="search" data-cmp-min-length="3" data-cmp-results-size="10">
    <form class="cmp-search__form" data-cmp-hook-search="form" method="get" action="/content/we-retail/us/en/equipment.searchresults.json/_jcr_content/root/responsivegrid/search" autocomplete="off">
        <div class="cmp-search__field">
            <i class="cmp-search__icon" data-cmp-hook-search="icon"></i>
            <span class="cmp-search__loading-indicator" data-cmp-hook-search="loadingIndicator"></span>
            <input class="cmp-search__input" data-cmp-hook-search="input" type="text" name="fulltext" placeholder="Search" role="combobox" aria-autocomplete="list" aria-haspopup="true" aria-invalid="false">
            <button class="cmp-search__clear" data-cmp-hook-search="clear">
                <i class="cmp-search__clear-icon"></i>
            </button>
        </div>
    </form>
    <div class="cmp-search__results" data-cmp-hook-search="results" role="listbox" aria-multiselectable="false"></div>
    
<script data-cmp-hook-search="itemTemplate" type="x-template">
    <a class="cmp-search__item" data-cmp-hook-search="item">
        <span class="cmp-search__item-title" data-cmp-hook-search="itemTitle"></span>
    </a>
</script>
</section>
```

### JSON {#json}

```
"search":{  
                     "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                     "relativePath":"/jcr:content/root/responsivegrid/search",
                     "resultsSize":10,
                     "searchTermMinimumLength":3,
                     ":type":"core/wcm/components/search/v1/search"
                  }
```

### Dettagli tecnici {#technical-details}

>[!NOTE]
>
>La protezione del componente di ricerca o di qualsiasi applicazione basata su AEM contro attacchi DOS dovrebbe essere implementata a un livello superiore, ad esempio utilizzando `mod_security` il dispatcher.

La documentazione tecnica più recente sul componente Ricerca rapida [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_search_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di definire la posizione di inizio della ricerca nella struttura del contenuto.

![](assets/screen_shot_2018-04-03at120132.png)

**Radice** ricerca - La pagina principale da cui avviare la ricerca. La directory principale di ricerca può essere una pagina master blueprint, una lingua o una pagina normale.

## Finestra di dialogo Progettazione {#design-dialog}

Utilizzando la finestra di dialogo Progettazione, l&#39;autore del modello può impostare il valore predefinito per l&#39;inizio della ricerca nella struttura del contenuto, nonché una dimensione massima del set di risultati e una lunghezza minima del termine di ricerca. La finestra di dialogo Progettazione consente all&#39;autore del modello di definire le opzioni di formattazione del testo disponibili per gli autori del contenuto.

### Scheda Proprietà {#properties-tab}

![](assets/screen_shot_2018-04-03at120028.png)

* **Radice** di ricerca Il valore predefinito della radice di ricerca quando un autore di contenuto inserisce il componente Ricerca rapida in una pagina di contenuto
* **Dimensioni** risultati Il numero massimo di risultati recuperati da una richiesta di ricerca
* **Termine di ricerca Lunghezza** minima Lunghezza minima del termine di ricerca per avviare la ricerca

>[!NOTE]
>
>**Dimensioni** dei risultati e **Termine di ricerca Lunghezza** minima può essere impostata solo in modalità di progettazione e quindi solo a livello di modello, il che significa che gli autori dei contenuti non sono in grado di modificare questi valori.

>[!CAUTION]
>
>**Dimensioni** dei risultati e Lunghezza **minima del termine di** ricerca possono avere un impatto sulle prestazioni se sono impostati rispettivamente troppo alti o troppo bassi.

### Scheda Stili {#styles-tab}

Il componente Ricerca rapida supporta AEM [Style System](authoring.md#component-styling).
