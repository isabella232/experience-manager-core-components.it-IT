---
title: Funzioni di localizzazione dei Componenti core
description: Funzioni di localizzazione dei Componenti core
role: Architect, Developer, Admin, User
exl-id: 9140b65a-6dd7-4ec9-9095-6e8243ec8424
source-git-commit: 888719359f9a1d1c9dccff97fb639b332f2be54c
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 100%

---

# Funzioni di localizzazione dei Componenti core {#localization-features-of-the-core-components}

Molti siti web richiedono la distribuzione di contenuto in più lingue per diverse aree geografiche. Alcuni dei Componenti core dispongono di una risoluzione intelligente dei riferimenti che consente di creare facilmente un modello unificato per tutto il contenuto localizzato che si adatta automaticamente in base alla struttura localizzata del sito.

## Esempio: pagina localizzata con navigazione e piè di pagina {#example}

La maggior parte dei siti richiede che un piè di pagina sia presente in tutte le pagine. Questi piè di pagina sono generalmente coerenti per tutto il contenuto della pagina. Tuttavia, per una pagina di contenuto localizzato, è necessario che anche l’intestazione o il piè di pagina compaiano nella versione localizzata.

Analogamente, un componente di navigazione in genere deve essere visualizzato su tutte le pagine. Tuttavia, dovrà riflettere anche il contenuto delle pagine localizzate.

Questo compito diventa semplice utilizzando le funzioni di localizzazione del [componente core Navigazione](/help/components/navigation.md) e del [componente core Frammento esperienza](/help/components/experience-fragment.md), insieme ai [modelli modificabili di AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it). L’esempio potrebbe essere ulteriormente esteso per utilizzare anche il [componente Navigazione lingua](/help/components/language-navigation.md).

## Struttura del contenuto {#content-structure}

Tutte le funzioni di localizzazione di AEM e dei relativi Componenti core si basano su una struttura di contenuto chiara e logica predisposta per la localizzazione.

Supponiamo che il tuo sito si chiami semplicemente `my-site` e si trovi qui:

```
/content/my-site
```

Supponiamo anche che il sito nasca in inglese, ma venga offerto anche in francese. Pertanto, se hai una pagina semplice denominata `my-page`, essa si trova in due settori di localizzazione nella struttura del contenuto del tuo sito:

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

È in questi settori di localizzazione che verranno create le pagine aggiuntive del sito.

I piè di pagina vengono generalmente creati utilizzando i Frammenti esperienza, pertanto dovrai avere una versione inglese e francese proprio come le pagine. Tuttavia, i Frammenti esperienza non sono in realtà pagine, ma parti di pagine che possono essere riutilizzate in più pagine, e per questo motivo non risiedono direttamente in `/content` come le altre pagine. Risiedono invece in una propria cartella, ma poiché devono anche essere localizzati, la loro struttura deve rispecchiare la struttura di localizzazione del sito.

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

È attraverso il mirroring della struttura di localizzazione che i Componenti core possono trovare il contenuto localizzato necessario per una pagina corrispondente.

## Piè di pagina: Frammento esperienza {#xf-footer}

Il componente Frammento esperienza è molto flessibile ed è adatto per un’intestazione o un piè di pagina.

Poiché il nostro ipotetico sito web è disponibile in inglese e francese, dovremo creare due Frammenti esperienza, entrambi denominati `footer` [nelle posizioni già precedentemente descritte.](#content-structure)

![](/help/assets/screen-shot-2019-09-09-11.08.28.png)

## Modello della pagina {#template}

Poiché il piè di pagina comparirà in ogni pagina, sarà necessario aggiungere il Frammento esperienza al modello di pagina standard.

Il nostro modello si chiama semplicemente `my-template` e si trova con gli altri nostri modelli:

```
/conf/my-site/settings/wcm/templates/my-template
```

A questo modello aggiungeremo i componenti di base sui quali vogliamo basare le nostre pagine.

* [Componente Navigazione](/help/components/navigation.md)
   * Il componente Navigazione viene visualizzato nella parte superiore di ogni pagina.
   * Nel componente Navigazione viene definita la directory principale di navigazione che indica al componente dove inizia la struttura di navigazione del sito.
   * In base alla directory principale di navigazione, il componente può trovare automaticamente il contenuto localizzato corrispondente.
* [Componente Contenitore](/help/components/container.md)
   * Ogni pagina contiene un componente Contenitore modificabile che consente agli autori di inserire contenuto aggiuntivo nella pagina.
* [Frammento esperienza](/help/components/experience-fragment.md)
   * Il componente Frammento esperienza punta al percorso del frammento nella lingua di authoring del frammento che rappresenta il piè di pagina.
   * In base al percorso del frammento e alla struttura dei Frammenti esperienza che rispecchia la struttura della pagina localizzata, il componente può trovare automaticamente il contenuto localizzato corrispondente.

   ![](/help/assets/screen-shot-2019-09-09-11.20.10.png)

## Pagine {#pages}

Dopo il duro lavoro svolto per configurare la struttura e il modello del sito, l’autore di contenuto deve ora semplicemente aggiungere il necessario contenuto alle pagine. Grazie ai modelli e alla logica di localizzazione dei componenti, la navigazione e i piè di pagina verranno aggiunti automaticamente alla pagina e localizzati.

Ad esempio, l’autore deve aggiungere solo contenuto, come un componente Testo, alle pagine in inglese e francese (di seguito rappresentate in blu).

Il componente Navigazione e il componente Frammento esperienza provengono dal modello della pagina e possono visualizzare automaticamente il contenuto corretto in base alla struttura di localizzazione e alla posizione della pagina stessa (di seguito rappresentata in bianco).

![](/help/assets/screen-shot-2019-09-09-11.22.14.png)

## Tutti gli elementi insieme {#fitting-it-all-together}

Ecco l’immagine completa di come questi semplici ma efficaci elementi agiscono insieme per distribuire pagine localizzate agli autori di contenuto.

![](/help/assets/screen-shot-2019-09-09-11.27.58.png)
