---
title: Componente Ricerca rapida
description: Il componente Ricerca rapida fornisce funzionalità di ricerca a un sito Web e presenta i risultati di ricerca in modo che i visitatori possano effettuare ricerche nel sito e filtrare i risultati.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 2%

---


# Componente Ricerca rapida {#quick-search-component}

Il componente Ricerca rapida fornisce funzionalità di ricerca a un sito Web e presenta i risultati di ricerca in modo che i visitatori possano trovare facilmente contenuti corrispondenti e visualizzare i risultati.

## Utilizzo {#usage}

Il componente Ricerca rapida offre ai visitatori del sito la possibilità di cercare contenuti, visualizzare i risultati sul posto e passare facilmente alle pagine corrispondenti. I nuovi risultati vengono recuperati dinamicamente mentre l’utente scorre i risultati della ricerca.

La [finestra di dialogo di modifica](#edit-dialog) consente all&#39;autore del contenuto di definire dove deve iniziare la ricerca nella struttura del contenuto. Utilizzando la finestra di dialogo [progettazione](#design-dialog), l&#39;autore del modello può impostare il valore predefinito per dove deve iniziare la ricerca nella struttura del contenuto, nonché una dimensione massima del set di risultati e una lunghezza minima del termine di ricerca.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Ricerca rapida è v1, introdotto con la release 2.0.0 dei componenti core a gennaio 2018, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

### Dettagli tecnici {#technical-details}

>[!NOTE]
>
>La protezione del componente di ricerca o di qualsiasi applicazione basata su AEM contro attacchi DOS deve essere implementata a un livello superiore, ad esempio utilizzando `mod_security` sul dispatcher.

La documentazione tecnica più recente sul componente di ricerca rapida [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_search_v1).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di definire la posizione di inizio della ricerca nella struttura del contenuto.

![Finestra di dialogo di modifica del componente Ricerca rapida](/help/assets/quick-search-edit.png)

**Radice**  ricerca - La pagina principale da cui avviare la ricerca. La directory principale di ricerca può essere una pagina master blueprint, una lingua o una pagina normale.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Finestra di dialogo Progettazione {#design-dialog}

Utilizzando la finestra di dialogo Progettazione, l&#39;autore del modello può impostare il valore predefinito per l&#39;inizio della ricerca nella struttura del contenuto, nonché una dimensione massima del set di risultati e una lunghezza minima del termine di ricerca. La finestra di dialogo Progettazione consente all&#39;autore del modello di definire quali opzioni di formattazione del testo sono disponibili per gli autori del contenuto.

### Scheda Proprietà {#properties-tab}

![Finestra di dialogo di progettazione del componente Ricerca rapida](/help/assets/quick-search-design.png)

* **Ricerca**
radiceIl valore predefinito della ricerca radice quando un autore di contenuto inserisce il componente Ricerca rapida in una pagina di contenuto
* **Dimensioni**
risultati: il numero massimo di risultati recuperati da una richiesta di ricerca
* **Termine di ricerca**
Lunghezza minimaLunghezza minima del termine di ricerca per avviare la ricerca

>[!NOTE]
>
>**Dimensioni** dei risultati e  **Durata minima** ricerca possono essere impostati solo in modalità di progettazione e quindi solo a livello di modello, il che significa che gli autori dei contenuti non sono in grado di modificare questi valori.

>[!CAUTION]
>
>**Dimensioni** dei risultati e  **Termine di ricerca** Lunghezze minime possono avere un impatto sulle prestazioni se sono impostati rispettivamente troppo alti o troppo bassi.

### Scheda Stili {#styles-tab}

Il componente Ricerca rapida supporta il AEM [Sistema di stile](/help/get-started/authoring.md#component-styling).
