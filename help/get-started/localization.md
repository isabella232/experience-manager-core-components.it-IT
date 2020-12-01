---
title: Funzioni di localizzazione dei componenti core
description: Funzioni di localizzazione dei componenti core
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 0%

---


# Funzioni di localizzazione dei componenti core {#localization-features-of-the-core-components}

Molti siti Web richiedono la distribuzione di contenuti in un formato localizzato in più lingue e aree geografiche. I componenti core selezionati offrono una risoluzione intelligente dei riferimenti che semplifica la creazione di un modello unificato per tutti i contenuti localizzati che si adattano automaticamente in base alla struttura del sito localizzata.

## Esempio - Pagina localizzata con navigazione e piè di pagina {#example}

La maggior parte dei siti richiede che un piè di pagina sia presente in tutte le pagine. Questi piè di pagina sono generalmente coerenti per tutto il contenuto della pagina. Tuttavia, per una pagina di contenuto localizzata, è necessario visualizzare una versione localizzata di tale intestazione o piè di pagina.

Analogamente, un componente di navigazione in genere deve essere visualizzato su tutte le pagine. Tuttavia, dovrà riflettere anche il contenuto delle pagine localizzate.

Utilizzando le funzioni di localizzazione del [componente core di navigazione](/help/components/navigation.md) e del [componente principale frammento esperienza](/help/components/experience-fragment.md) insieme ai [modelli modificabili di AEM](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html), si tratta di un&#39;attività semplice. L&#39;esempio potrebbe essere ulteriormente esteso per utilizzare anche il [Componente di navigazione della lingua](/help/components/language-navigation.md).

## Struttura del contenuto {#content-structure}

Tutte le funzioni di localizzazione di AEM e dei relativi componenti core si basano su una struttura di contenuto chiara e logica per i contenuti localizzati.

Supponiamo che il tuo sito sia semplicemente chiamato `my-site` e si trovi qui:

```
/content/my-site
```

Diciamo anche che si crea il sito in inglese e lo si offre anche in francese. Se disponete di una semplice pagina denominata `my-page`, la potete trovare in due rami di localizzazione nella struttura dei contenuti del sito:

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

È sotto questi rami di localizzazione che si creano ulteriori pagine di siti.

I piè di pagina sono generalmente realizzati utilizzando i frammenti esperienza, per cui è necessaria una versione inglese e francese come le pagine. Tuttavia, i frammenti esperienza non sono pagine, ma parti di pagine che possono essere riutilizzate tra le pagine, pertanto non vivono direttamente sotto `/content` come le altre pagine. Vivono invece sotto la propria cartella, ma poiché devono essere localizzati, la loro struttura deve rispecchiare la struttura di localizzazione del sito.

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

È attraverso la struttura di localizzazione speculare che i componenti core possono trovare il contenuto localizzato necessario per una pagina corrispondente.

## Piè di pagina - Frammento esperienza {#xf-footer}

Il componente Frammento esperienza è molto flessibile ed è adatto per un&#39;intestazione o un piè di pagina di pagina.

Poiché il nostro sito ipotetico è disponibile in inglese e francese, sarà necessario creare due frammenti esperienza, entrambi denominati `footer` [nelle posizioni precedentemente descritte.](#content-structure)

![](/help/assets/screen-shot-2019-09-09-11.08.28.png)

## Modello pagina {#template}

Poiché il piè di pagina verrà visualizzato su ogni pagina, sarà necessario aggiungere il frammento esperienza al modello di pagina standard.

Il nostro modello si chiama semplicemente `my-template` e si trova con i nostri altri modelli:

```
/conf/my-site/settings/wcm/templates/my-template
```

A questo modello aggiungeremo i componenti di base sui quali vogliamo basare le nostre pagine.

* [Componente di navigazione](/help/components/navigation.md)
   * Il componente Navigazione viene visualizzato nella parte superiore di ogni pagina.
   * Nel componente di navigazione viene definito il livello principale di navigazione, indicando il componente da cui inizia la struttura di navigazione del sito.
   * In base al livello principale di navigazione, il componente può trovare automaticamente il contenuto localizzato corrispondente.
* [Componente contenitore](/help/components/container.md)
   * Ogni pagina conterrà un componente Contenitore modificabile in modo che gli autori possano inserire contenuto aggiuntivo nella pagina.
* [Frammento esperienza](/help/components/experience-fragment.md)
   * Il componente Frammento esperienza viene indirizzato al percorso del frammento nella lingua di authoring del frammento che rappresenta il piè di pagina.
   * In base al percorso del frammento e alla struttura dei frammenti esperienza che rispecchia la struttura di pagina localizzata, il componente può trovare automaticamente il contenuto localizzato corrispondente.

   ![](/help/assets/screen-shot-2019-09-09-11.20.10.png)

## Pagine {#pages}

Durante il lavoro di configurazione della struttura e del modello del sito, l’autore del contenuto deve semplicemente aggiungere alle pagine il contenuto necessario. Grazie ai modelli e alla logica di localizzazione dei componenti, la navigazione e i piè di pagina verranno automaticamente aggiunti alla pagina e localizzati.

Ad esempio, l’autore deve solo aggiungere contenuto, ad esempio un componente di testo, alle pagine inglese e francese (rappresentato in blu sotto).

Il componente Navigazione e il componente Frammento esperienza provengono dal modello di pagina e sono in grado di visualizzare automaticamente il contenuto corretto in base alla struttura di localizzazione e alla posizione della pagina stessa (rappresentata in bianco di seguito).

![](/help/assets/screen-shot-2019-09-09-11.22.14.png)

## Adatta tutto {#fitting-it-all-together}

Di seguito viene illustrato il funzionamento di questi elementi semplici e potenti per distribuire pagine localizzate agli autori dei contenuti.

![](/help/assets/screen-shot-2019-09-09-11.27.58.png)
