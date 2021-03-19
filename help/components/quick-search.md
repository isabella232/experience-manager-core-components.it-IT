---
title: Componente Ricerca rapida
description: Il componente Ricerca rapida fornisce funzionalità di ricerca per un sito web e presenta i risultati di ricerca in modo che i visitatori possano cercare il sito e filtrare i risultati.
role: Architetto, Sviluppatore, Amministratore, Business Practices
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 2%

---


# Componente Ricerca rapida {#quick-search-component}

Il componente Ricerca rapida fornisce funzionalità di ricerca per un sito web e presenta i risultati di ricerca in modo che i visitatori possano trovare facilmente contenuti corrispondenti e visualizzare i risultati.

## Utilizzo {#usage}

Il componente Ricerca rapida offre ai visitatori del sito la possibilità di cercare contenuti, visualizzare i risultati sul posto e navigare facilmente nelle pagine corrispondenti. I nuovi risultati vengono recuperati dinamicamente mentre l’utente scorre i risultati della ricerca.

La [finestra di dialogo di modifica](#edit-dialog) consente all’autore del contenuto di definire da dove deve iniziare la ricerca nella struttura del contenuto. Utilizzando la [finestra di dialogo di progettazione](#design-dialog), l’autore del modello può impostare il valore predefinito per la posizione nella struttura del contenuto in cui deve iniziare la ricerca, nonché una dimensione massima del set di risultati e una lunghezza minima del termine di ricerca.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Ricerca rapida è la v1, introdotta con la versione 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

### Dettagli tecnici {#technical-details}

>[!NOTE]
>
>La protezione del componente di ricerca o di qualsiasi applicazione basata su AEM contro attacchi DOS deve essere implementata a un livello più alto, ad esempio utilizzando `mod_security` sul dispatcher.

La documentazione tecnica più recente sul componente Ricerca rapida [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_search_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di definire da dove deve iniziare la ricerca nella struttura del contenuto.

![Finestra di dialogo di modifica del componente Ricerca rapida](/help/assets/quick-search-edit.png)

**Cerca radice** : la pagina principale da cui avviare la ricerca. La directory principale di ricerca può essere una pagina master blueprint, una lingua master o una pagina normale.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

## Finestra di dialogo Progettazione {#design-dialog}

Tramite la finestra di dialogo Progettazione, l’autore del modello può impostare il valore predefinito per l’inizio della ricerca nella struttura del contenuto, nonché una dimensione massima del set di risultati e una lunghezza minima del termine di ricerca.La finestra di dialogo Progettazione consente all’autore del modello di definire quali opzioni di formattazione del testo sono disponibili per gli autori del contenuto.

### Scheda Proprietà {#properties-tab}

![Finestra di dialogo di progettazione del componente Ricerca rapida](/help/assets/quick-search-design.png)

* **Ricerca**
radiceIl valore predefinito della directory principale di ricerca quando un autore di contenuti inserisce il componente Ricerca rapida in una pagina di contenuto
* **Dimensione**
dei risultatiIl numero massimo di risultati recuperati da una richiesta di ricerca
* **Termine di ricerca**
Lunghezza minimaLunghezza minima del termine di ricerca per avviare la ricerca

>[!NOTE]
>
>**La dimensione** dei risultati e la  **** lunghezza minima del termine di ricerca possono essere impostate solo in modalità di progettazione e quindi solo a livello di modello, il che significa che gli autori dei contenuti non sono in grado di modificare questi valori.

>[!CAUTION]
>
>**Dimensione** dei risultati e  **durata minima del termine di ricerca** possono avere un impatto sulle prestazioni se sono impostati rispettivamente troppo alti o troppo bassi.

### Scheda Stili {#styles-tab}

Il componente Ricerca rapida supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).
