---
title: Componente pagina
description: Il componente Pagina è un componente di pagina estensibile progettato per funzionare con l’editor modelli e consente di assemblare con l’editor modelli i componenti di intestazione/piè di pagina e struttura della pagina.
translation-type: tm+mt
source-git-commit: f4a45b2af87e5a5f0396b335c65856ce821455c9
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 2%

---


# Componente pagina{#page-component}

Il componente Pagina è un componente di pagina estensibile progettato per funzionare con l&#39; [editor modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) e consente di assemblare con l&#39;editor modelli i componenti di intestazione/piè di pagina e struttura della pagina.

## Utilizzo {#usage}

Il componente Pagina costituisce la base di tutte le pagine progettate con i componenti core e modelli modificabili. Utilizzando il componente Pagina, le intestazioni, i piè di pagina e la struttura della pagina possono essere definiti come un modello utilizzando gli altri componenti core.

Utilizzando la finestra di dialogo [progettazione](#design-dialog), è possibile definire librerie personalizzate sul lato client per la pagina. A differenza di altri componenti che dispongono di una finestra di dialogo di modifica accessibile direttamente dal componente, poiché il componente Pagina è la pagina stessa, la [finestra di dialogo di modifica](#edit-dialog) del componente Pagina è la finestra delle proprietà della pagina.

## Supporto progressivo delle app Web {#pwa-support}

La release 2.15.0 dei componenti core ha introdotto il supporto per la AEM come  di funzioni integrate delle app Web progressive (PWA). Con una semplice configurazione a livello di sito, trasforma la tua esperienza AEM in un PWA!

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pagina è v2, introdotta con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](v1/page-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pagina [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_page_v2).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Finestra di dialogo Modifica {#edit-dialog}

Poiché il componente rappresenta l’intera pagina, le impostazioni che normalmente si trovano in una finestra di dialogo di modifica si trovano nella finestra [Proprietà pagina](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html).

## Finestra di dialogo Progettazione {#design-dialog}

Poiché il componente rappresenta l’intera pagina, la finestra di dialogo della progettazione è accessibile tramite **Informazioni pagina -> Criteri pagina** quando si modifica il modello di pagina.

![Criterio pagina](/help/assets/page-policy.png)

>[!NOTE]
>
>Nelle versioni precedenti di AEM, **Page Policy** era denominata **Page Design**.

### Scheda Proprietà {#properties-tab}

La finestra Progettazione pagina consente di definire le librerie client da caricare, nonché la libreria delle risorse Web per la pagina.

* **Librerie**  client - Definisce le categorie della libreria client da caricare. JavaScript viene aggiunto alla fine del corpo e il CSS viene aggiunto all&#39;intestazione della pagina.
* **Intestazione**  pagina JavaScript delle librerie client: definisce le categorie della libreria client JavaScript da caricare nell&#39;intestazione della pagina.
   * Le categorie qui definite che sono presenti anche nel campo **Client Libraries** avranno JavaScript caricato nell&#39;intestazione della pagina invece che all&#39;estremità del corpo.
   * Non verrà caricato alcun CSS a meno che la categoria non sia presente anche nel campo **Client Libraries**.

* **Libreria**  client risorse Web - La categoria della libreria client utilizzata per distribuire risorse Web come favicons.

* **Passa al selettore**  principale degli elementi di contenuto: utilizzato come funzione di accessibilità per passare direttamente al contenuto principale della pagina

![Finestra di dialogo Progettazione componenti pagina](/help/assets/page-design.png)

Le librerie possono essere configurate per i campi **Client Libraries** e **Client Libraries testina pagina JavaScript** come segue:

* Per aggiungere un nuovo campo, fare clic o toccare il pulsante **Aggiungi** sotto i campi.
* Per rimuovere un campo, fare clic o toccare l&#39;icona del cestino accanto al campo da rimuovere.
* Per riordinare l&#39;ordine di caricamento, fare clic o toccare e trascinare la maniglia accanto al campo da spostare.

Per ulteriori informazioni sull&#39;utilizzo delle librerie lato client, vedere [Utilizzo delle librerie lato client](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html).

>[!CAUTION]
>
>La possibilità di definire separatamente le librerie client per l&#39;intestazione di pagina è stata introdotta con la release 2.2.0 dei componenti core.

### Scheda Stili {#styles-tab}

Il componente Pagina supporta il AEM [Sistema di stile](/help/get-started/authoring.md#component-styling).

## Livello dati client  Adobe {#data-layer}

Il componente Pagina supporta il [ livello dati client Adobe.](/help/developing/data-layer/overview.md)
