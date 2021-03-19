---
title: Funzioni di localizzazione dei componenti core
description: Funzioni di localizzazione dei componenti core
role: Architetto, Sviluppatore, Amministratore, Business Practices
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 0%

---


# Funzioni di localizzazione dei componenti core {#localization-features-of-the-core-components}

Molti siti web richiedono la distribuzione di contenuti in un formato localizzato in più lingue e aree geografiche. I componenti core selezionati dispongono di una risoluzione intelligente dei riferimenti che consente di creare facilmente un modello unificato per tutti i contenuti localizzati che si adattano automaticamente in base alla struttura del sito localizzata.

## Esempio: pagina localizzata con navigazione e piè di pagina {#example}

La maggior parte dei siti richiede che un piè di pagina sia presente in tutte le pagine. Questi piè di pagina sono generalmente coerenti per tutto il contenuto della pagina. Tuttavia, per una pagina di contenuto localizzata, è necessario visualizzare una versione localizzata di tale intestazione o piè di pagina.

Analogamente, un componente di navigazione in genere deve essere visualizzato su tutte le pagine. Tuttavia, dovrà riflettere anche il contenuto delle pagine localizzate.

Utilizzando le funzioni di localizzazione dei [componenti core di navigazione](/help/components/navigation.md) e [componenti core frammento esperienza](/help/components/experience-fragment.md) insieme ai [modelli modificabili di AEM](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html), questo diventa un compito semplice. L&#39;esempio potrebbe essere ulteriormente esteso per utilizzare anche il [componente di navigazione della lingua](/help/components/language-navigation.md).

## Struttura dei contenuti {#content-structure}

Tutte le funzioni di localizzazione di AEM e dei relativi componenti core si basano su una struttura dei contenuti chiara e logica per i contenuti localizzati.

Supponiamo che il tuo sito sia semplicemente chiamato `my-site` e si trovi qui:

```
/content/my-site
```

Diciamo anche che si autore il tuo sito in inglese e lo si offre anche in francese. Pertanto, se disponi di una pagina semplice denominata `my-page` , questa si trova in due rami di localizzazione nella struttura dei contenuti del sito:

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

È sotto questi rami di localizzazione che creerai pagine di siti aggiuntive.

I piè di pagina vengono generalmente creati utilizzando Frammenti esperienza per richiedere una versione inglese e francese come le tue pagine. Tuttavia, i frammenti esperienza non sono pagine, ma sono parti di pagine che possono essere riutilizzate tra le pagine, in modo che non vivano direttamente sotto `/content` come le altre pagine. Vivono invece sotto la propria cartella, ma poiché devono anche essere localizzati, la loro struttura deve rispecchiare la struttura di localizzazione del sito.

```
/content
+-- experience-fragments
   +-- en
      \-- footer
   \-- fr
      \-- footer
\-- my-site
   +-- en
      \-- my-page
   \-- fr
      \-- my-page
```

È attraverso la struttura di localizzazione con mirroring che i componenti core possono trovare il contenuto localizzato necessario per una pagina corrispondente.

## Piè di pagina - Frammento esperienza {#xf-footer}

Il componente Frammento esperienza è molto flessibile ed è adatto per un’intestazione di pagina o un piè di pagina.

Poiché il nostro sito web ipotetico è disponibile in inglese e francese, dovremo creare due frammenti esperienza, entrambi denominati `footer` [nelle posizioni precedentemente descritte.](#content-structure)

![](/help/assets/screen-shot-2019-09-09-11.08.28.png)

## Modello pagina {#template}

Poiché il piè di pagina verrà visualizzato in ogni pagina, sarà necessario aggiungere il frammento esperienza al modello di pagina standard.

Il nostro modello si chiama semplicemente `my-template` e si trova con gli altri modelli:

```
/conf/my-site/settings/wcm/templates/my-template
```

A questo modello verranno aggiunti i componenti di base sui quali si desidera basare le pagine.

* [Componente di navigazione](/help/components/navigation.md)
   * Il componente di navigazione viene visualizzato nella parte superiore di ogni pagina.
   * Nel componente di navigazione viene definita la directory principale di navigazione, in cui viene indicato al componente in cui inizia la struttura di navigazione del sito.
   * In base alla radice di navigazione, il componente può trovare automaticamente il contenuto localizzato corrispondente.
* [Componente contenitore](/help/components/container.md)
   * Ogni pagina contiene un componente Contenitore modificabile che consente agli autori di inserire contenuto aggiuntivo nella pagina.
* [Frammento esperienza](/help/components/experience-fragment.md)
   * Il componente Frammento esperienza viene indirizzato al percorso del frammento nel linguaggio di authoring del frammento che rappresenta il piè di pagina.
   * In base al percorso del frammento e alla struttura dei frammenti di esperienza che rispecchia la struttura della pagina localizzata, il componente può trovare automaticamente il contenuto localizzato corrispondente.

   ![](/help/assets/screen-shot-2019-09-09-11.20.10.png)

## Pagine {#pages}

Con il duro lavoro svolto nella configurazione della struttura del sito e del modello, l’autore del contenuto deve semplicemente aggiungere alle pagine il contenuto necessario. Grazie ai modelli e alla logica di localizzazione dei componenti, la navigazione e i piè di pagina verranno aggiunti automaticamente alla pagina e localizzati.

Ad esempio, l’autore dovrebbe aggiungere solo contenuti, come un componente testo alle pagine inglese e francese (rappresentati in blu di seguito).

Il componente di navigazione e il componente Frammento esperienza provengono dal modello di pagina e sono in grado di visualizzare automaticamente il contenuto corretto in base alla struttura di localizzazione e alla posizione della pagina stessa (rappresentata in bianco di seguito).

![](/help/assets/screen-shot-2019-09-09-11.22.14.png)

## Adatta tutto {#fitting-it-all-together}

Ecco l’immagine completa di come questi elementi semplici ma potenti lavorano insieme per distribuire pagine localizzate agli autori dei contenuti.

![](/help/assets/screen-shot-2019-09-09-11.27.58.png)
