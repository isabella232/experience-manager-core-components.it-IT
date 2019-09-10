---
title: Funzioni di localizzazione dei componenti core
seo-title: Funzioni di localizzazione dei componenti core
description: Funzioni di localizzazione dei componenti core
seo-description: Funzioni di localizzazione dei componenti core
content-type: riferimento
topic-tags: componenti core
index: y
internal: n
translation-type: tm+mt
source-git-commit: c4e86960ec271464661193f6409cd93d1b9ec51b

---


# Funzioni di localizzazione dei componenti core {#localization-features-of-the-core-components}

Molti siti Web richiedono la distribuzione del contenuto in un formato localizzato in più lingue e aree geografiche. Resoultion di riferimento avanzato delle funzionalità Componenti core selezionati, per semplificare la creazione di un modello unificato per tutto il contenuto localizzato che si adatta automaticamente in base alla struttura localizzata del sito.

## Esempio - Pagina localizzata con Navigazione e piè di pagina {#example}

La maggior parte dei siti richiede un piè di pagina da presentare a tutte le pagine. Questi piè di pagina sono generalmente coerenti in tutto il contenuto della pagina. Tuttavia, per una pagina di contenuto localizzata è necessario visualizzare una versione localizzata dell'intestazione o del piè di pagina.

In genere, è necessario visualizzare in tutte le pagine un componente di navigazione. Tuttavia, sarà necessario riflettere anche il contenuto delle pagine localizzate.

Utilizzando le funzioni di localizzazione del componente [di navigazione di navigazione e](navigation.md) del [componente core Esperienza](experience-fragment.md) insieme ai [modelli modificabili di AEM](https://docs.adobe.com/content/help/en/experience-manager-64/authoring/siteandpage/templates.html), diventa un'attività smiple.

## Struttura contenuto {#content-structure}

Tutte le funzioni di localizzazione di AEM e dei suoi componenti core si basano su una struttura di contenuto chiara e logica per il contenuto localizzato.

Supponiamo che il tuo sito sia semplicemente chiamato `my-site` e che si trovi qui:

```
/content/my-site
```

Supponiamo anche di creare il sito in lingua inglese e di offrirlo in francese. Quindi, se disponete di una semplice pagina chiamata, `my-page` si troverebbe in due rami di localizzazione nella struttura del contenuto del sito:

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

In questi rami di localizzazione verranno creati ulteriori pagine di siti.

I piè di pagina delle pagine vengono in genere effettuati utilizzando frammenti esperienza, in modo da disporre di una versione inglese e francese come le pagine. Tuttavia, i frammenti esperienza non sono pagine, ma sono parti di pagine che possono essere riutilizzate su più pagine, in modo da non essere live direttamente `/content` nelle altre pagine. Al contrario, sono in diretta nella propria cartella, ma perché devono anche essere localizzati, la struttura deve rispecchiare la struttura di localizzazione del sito.

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

È attraverso la struttura di localizzazione riflettente che i componenti core possono trovare il contenuto localizzato necessario per una pagina corrispondente.

## Piè pagina pagina - Frammento esperienza {#xf-footer}

Il componente Frammento esperienza è molto flessibile ed è molto adatto per l'intestazione o il piè di pagina di una pagina.

Poiché il nostro sito Web ipotetico è offerto in inglese e francese, sarà necessario creare due frammenti esperienza, entrambi chiamati `footer`[nelle posizioni precedentemente descritte.](#content-structure)

![](assets/screen-shot-2019-09-09-11.08.28.png)

## Modello pagina {#template}

Poiché il piè di pagina verrà visualizzato in ogni pagina, sarà necessario aggiungere il frammento esperienza al modello di pagina standard.

Il nostro modello viene semplicemente chiamato `my-template` e si trova con gli altri modelli:

```
/conf/my-site/settings/wcm/templates/my-template
```

A questo modello verranno aggiunti i componenti di base su cui si desidera basare le pagine.

* [Componente di navigazione](navigation.md)
   * Il componente di navigazione viene visualizzato nella parte superiore di ogni pagina.
   * Nel componente di navigazione definiamo la radice di navigazione, indicando al componente dove inizia la struttura di navigazione del sito.
   * In base alla radice di navigazione, il componente può trovare automaticamente il contenuto localizzato corrispondente.
* [Componente Contenitore](container.md)
   * Ogni pagina conterrà un componente contenitore modificabile in modo che gli autori possano inserire altri contenuti nella pagina.
* [Frammento esperienza](experience-fragment.md)
   * Il componente Frammento di esperienza è indicato nel percorso di frammento del frammento che rappresenta il piè di pagina.
   * In base al percorso del frammento e alla struttura dei frammenti esperienza che rispecchiano la struttura della pagina localizzata, il componente può trovare automaticamente il corrispondente contenuto localizzato.
   ![](assets/screen-shot-2019-09-09-11.20.10.png)

## Pagine {#pages}

Eseguendo l'operazione di configurazione della struttura del sito e del modello, l'autore del contenuto deve semplicemente aggiungere il contenuto necessario alle pagine. Grazie ai modelli e alla logica di localizzazione dei componenti, la navigazione e i piè di pagina verranno aggiunti automaticamente alla pagina e localizzati.

Ad esempio, l'autore deve solo aggiungere contenuto come un componente di testo alle pagine inglese e francese (rappresentato in blu sotto).

Il componente di navigazione e il componente Frammenti esperienza provengono dal modello di pagina e sanno di visualizzare automaticamente il contenuto corretto in base alla struttura di localizzazione e alla posizione della pagina stessa (rappresentata in bianco sotto).

![](assets/screen-shot-2019-09-09-11.22.14.png)

## Adattamento completo {#fitting-it-all-together}

Ecco l'illustrazione completa su come questi elementi semplici ma potenti lavorano per distribuire pagine localizzate per gli autori di contenuto.

![](assets/screen-shot-2019-09-09-11.27.58.png)
