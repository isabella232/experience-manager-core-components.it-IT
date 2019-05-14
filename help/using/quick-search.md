---
title: Componente Ricerca rapida
seo-title: Componente Ricerca rapida
description: 'null'
seo-description: Il componente Ricerca rapida fornisce funzionalità di ricerca a un sito Web e presenta i risultati di ricerca per consentire ai visitatori di eseguire ricerche nel sito e filtrare i risultati.
uuid: 1 ba 69 be 3-537 e -4 f 20-9 f 17-b 4 b 7174 a 8 e 88
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: 906 a 684 d -5663-4497-bef 3-37 f 13 d 5 b 46 c 7
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


# Componente Ricerca rapida{#quick-search-component}

Il componente Ricerca rapida fornisce funzionalità di ricerca a un sito Web e presenta i risultati della ricerca in modo che i visitatori possano trovare facilmente contenuti corrispondenti e visualizzare i risultati.

## Utilizzo {#usage}

Il componente Ricerca rapida offre ai visitatori del sito la possibilità di cercare contenuti, visualizzare i risultati in loco e passare facilmente alle pagine corrispondenti. I nuovi risultati vengono recuperati in modo dinamico quando l&#39;utente scorre i risultati della ricerca.

La [finestra di dialogo](#edit-dialog) di modifica consente all&#39;autore del contenuto di definire dove deve iniziare la ricerca nella struttura del contenuto. Mediante la finestra di dialogo [di progettazione](#design-dialog), l&#39;autore del modello può impostare il valore predefinito per la posizione di inizio della ricerca, nonché per le dimensioni massime del set di risultati e per la lunghezza minima del termine di ricerca.

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Ricerca rapida è v 1, introdotta con la release 2.0.0 dei Componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

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
>La protezione del componente Ricerca o di qualsiasi applicazione basata su AEM contro gli attacchi DOS deve essere implementata a livello più elevato, ad esempio utilizzando `mod_security` il dispatcher.

La documentazione tecnica più recente sul componente [Ricerca rapida è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/search/v1/search).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Finestra di dialogo di modifica {#edit-dialog}

La finestra di dialogo di modifica consente all&#39;autore del contenuto di definire dove deve iniziare la ricerca nella struttura del contenuto.

![](assets/screen_shot_2018-04-03at120132.png)

**Root Root** - La pagina principale da cui avviare la ricerca. La funzione di ricerca può essere una pagina master blueprint, master o regolare.

## Finestra di dialogo Progettazione {#design-dialog}

Mediante la finestra di dialogo di progettazione, l&#39;autore del modello può impostare il valore predefinito per la posizione in cui la ricerca deve iniziare, oltre a una dimensione massima impostata per i risultati e per la lunghezza minima del termine di ricerca. La finestra di dialogo di progettazione consente all&#39;autore del modello di definire le opzioni di formattazione del testo disponibili per gli autori di contenuto.

### Scheda Proprietà {#properties-tab}

![](assets/screen_shot_2018-04-03at120028.png)

* **Cartella
di ricerca** Il valore predefinito della radice di ricerca quando un autore inserisce il componente Ricerca rapida in una pagina di contenuto
* **Dimensioni
risultati** Il numero massimo di risultati recuperati da una richiesta di ricerca
* **Lunghezza minima lunghezza minima Lunghezza**
minima Lunghezza del termine di ricerca per avviare la ricerca

>[!NOTE]
>
>**Le dimensioni** dei risultati e **il termine di ricerca minima possono** essere impostati solo in modalità Progettazione e quindi solo a livello di modello, e non sono quindi in grado di modificare tali valori.

>[!CAUTION]
>
>**Le dimensioni** dei risultati e **il termine Lunghezza minima possono** avere impatto sulle prestazioni se sono impostate su un valore troppo elevato o troppo basso.

### Scheda Stili {#styles-tab}

Il componente Ricerca rapida supporta il sistema [di stile AEM](authoring.md#component-styling).