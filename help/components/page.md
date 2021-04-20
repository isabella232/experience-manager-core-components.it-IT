---
title: Componente pagina
description: Il componente Pagina è un componente di pagina estensibile progettato per funzionare con l’editor modelli e consente l’assemblaggio di componenti di intestazione/piè di pagina e struttura con l’editor modelli.
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: fa8ead438093681071b6b6f8ccfbba523f6d3bee
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 3%

---


# Componente pagina{#page-component}

Il componente Pagina è un componente di pagina estensibile progettato per funzionare con l’ [editor modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) e consente di assemblare i componenti di intestazione/piè di pagina e struttura con l’editor modelli.

## Utilizzo {#usage}

Il componente Pagina costituisce la base di tutte le pagine progettate con i componenti core e i modelli modificabili. Utilizzando il componente Pagina, le intestazioni, i piè di pagina e la struttura della pagina possono essere definiti come un modello utilizzando gli altri componenti core.

Utilizzando la [finestra di dialogo di progettazione](#design-dialog), è possibile definire librerie personalizzate lato client per la pagina. A differenza di altri componenti che dispongono di una finestra di dialogo di modifica accessibile direttamente dal componente, poiché il componente Pagina è la pagina stessa, la [finestra di dialogo di modifica](#edit-dialog) del componente Pagina è la finestra delle proprietà della pagina.

## Supporto progressivo per app Web {#pwa-support}

La versione 2.15.0 dei componenti core ha introdotto il supporto per AEM come funzionalità integrate [Progressive Web Apps (PWA) del Cloud Service.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/enable-pwa.html) Con una semplice configurazione a livello di sito, trasforma la tua esperienza AEM in un PWA!

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pagina è v2, introdotta con la versione 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](v1/page-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pagina [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_page_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Modifica {#edit-dialog}

Poiché il componente rappresenta l’intera pagina, le impostazioni normalmente presenti in una finestra di dialogo di modifica si trovano nella finestra [Proprietà pagina](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html).

## Finestra di dialogo Progettazione {#design-dialog}

Poiché il componente rappresenta l’intera pagina, la finestra di dialogo di progettazione è accessibile tramite **Informazioni pagina -> Criterio pagina** durante la modifica del modello di pagina.

![Criterio pagina](/help/assets/page-policy.png)

>[!NOTE]
>
>Nelle versioni precedenti di AEM, **Criterio pagina** era denominato **Progettazione pagina**.

### Scheda Proprietà {#properties-tab}

La finestra Progettazione pagina consente di definire le librerie client da caricare e la libreria delle risorse web per la pagina.

* **Librerie client**  - Definisce le categorie della libreria client da caricare. JavaScript viene aggiunto alla fine del corpo e il CSS viene aggiunto all’intestazione della pagina.
* **Intestazione pagina JavaScript delle librerie client** : definisce le categorie della libreria client JavaScript da caricare nell’intestazione di pagina.
   * Le categorie definite in questo campo che sono presenti anche nel campo **Librerie client** avranno JavaScript caricato nell&#39;intestazione della pagina invece che all&#39;estremità del corpo.
   * Non verrà caricato alcun CSS a meno che la categoria non sia presente anche nel campo **Librerie client** .

* **Libreria client di risorse web** : la categoria della libreria client utilizzata per distribuire risorse Web come favicon.

* **Passa al selettore principale degli elementi di contenuto** : utilizzato come funzione di accessibilità per passare direttamente al contenuto principale della pagina

![Finestra di dialogo Progettazione componente pagina](/help/assets/page-design.png)

Le librerie possono essere configurate per i campi **Librerie client** e **Librerie client Intestazione pagina JavaScript** come segue:

* Per aggiungere un nuovo campo, tocca o fai clic sul pulsante **Aggiungi** sotto i campi.
* Per rimuovere un campo, tocca o fai clic sull’icona del cestino accanto al campo da rimuovere.
* Per ridisporre l’ordine di caricamento, tocca o fai clic su e trascina la maniglia accanto al campo da spostare.

Per ulteriori informazioni sull&#39;utilizzo delle librerie lato client, consulta [Utilizzo delle librerie lato client](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html).

>[!CAUTION]
>
>Con la versione 2.2.0 dei componenti core è stata introdotta la possibilità di definire separatamente le librerie client per l’intestazione di pagina.

### Scheda Stili {#styles-tab}

Il componente Pagina supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

## Livello dati client di Adobe {#data-layer}

Il componente Pagina supporta il [Livello dati client di Adobe.](/help/developing/data-layer/overview.md)
