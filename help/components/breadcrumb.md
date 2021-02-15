---
title: Componente Breadcrumb
description: Il componente di base Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.
translation-type: tm+mt
source-git-commit: d3ebcea5fa1523c1a986841cd3d1a64e16e85f6d
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 2%

---


# Breadcrumb Component{#breadcrumb-component}

Il componente di base Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.

## Utilizzo {#usage}

Il componente Breadcrumb visualizza la posizione della pagina corrente all’interno della gerarchia del sito, consentendo ai visitatori della pagina di spostarsi nella gerarchia di pagina dalla posizione corrente. Questa funzione è spesso integrata nelle intestazioni o nei piè di pagina della pagina.

Le opzioni disponibili, come il livello di navigazione predefinito e la possibilità di visualizzare la pagina corrente o le pagine nascoste, possono essere definite dall&#39;autore del modello nella finestra di dialogo di [progettazione](#design-dialog). L&#39;editor dei contenuti può quindi scegliere se visualizzare o meno le pagine nascoste e il livello di navigazione effettivo per il componente nella finestra di dialogo di [modifica](#edit-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Breadcrumb è v2, introdotta con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- | --- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](v1/breadcrumb-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente Breadcrumb e per vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library_breadcrumb).

>[!NOTE]
>
>A partire dalla release 2.1.0 dei componenti core, il componente Breadcrumb supporta [schema.org microdata](https://schema.org/BreadcrumbList).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Breadcrumb [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di eliminare le pagine nascoste e attive nelle breadcrumb e la profondità nella gerarchia che dovrebbe visualizzare.

![Finestra di dialogo di modifica del componente Breadcrumb](/help/assets/breadcrumb-edit.png)

* **Livello**  iniziale navigazione - Punto della gerarchia in cui il componente breadcrumb deve iniziare a spostarsi verso il basso fino alla pagina corrente. Esempio:

   * 0 inizia da `/content`
   * 1 inizia a `/content/<yourSite>`
   * 2 inizia da `/content/<yourSite>/<country>`

* **Mostra elementi**  di navigazione nascosti - Mostra pagine contrassegnate come nascoste nel breadcrumb (per impostazione predefinita non vengono visualizzate)
* **Nascondi pagina**  corrente - Elimina la pagina corrente nel percorso di navigazione (per impostazione predefinita verrà visualizzata)
* **Disattiva ombreggiatura** : se la pagina nella gerarchia è un reindirizzamento, il nome della pagina di reindirizzamento verrà visualizzato al posto della destinazione. Per ulteriori informazioni, vedere [Supporto della struttura del sito ombra](navigation.md#shadow-structure) del componente di navigazione.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire i valori predefiniti per le opzioni che consentono di eliminare le pagine nascoste e attive nelle breadcrumb, nonché la profondità nella gerarchia che dovrebbe visualizzare.

### Scheda principale {#main-tab}

![](/help/assets/breadcrumb-design.png)

* **Livello**  iniziale navigazione - Definisce il valore predefinito per la posizione nella gerarchia in cui il componente breadcrumb deve iniziare a camminare verso il basso fino alla pagina corrente quando il componente breadcrumb viene aggiunto a una pagina.
* **Mostra elementi**  di navigazione nascosti - Definisce il valore predefinito dell’ **opzione Mostra** elemento di navigazione nascosto quando il componente breadcrumb viene aggiunto a una pagina.

   * Non attiva o disattiva l’opzione per l’autore. Imposta solo il valore predefinito.

* **Nascondi pagina** corrente - Definisce il valore predefinito dell’opzione  **Nascondi** pagina corrente quando il componente breadcrumb viene aggiunto a una pagina.

   * Non attiva o disattiva l’opzione per l’autore. Imposta solo il valore predefinito.

* **Disattiva ombreggiatura** : definisce il valore predefinito dell’opzione  **Disattiva** ombreggiatura quando il componente breadcrumb viene aggiunto a una pagina.

### Scheda Stili {#styles-tab}

Il componente Breadcrumb supporta il AEM [Style System](/help/get-started/authoring.md#component-styling).

## Livello dati client  Adobe {#data-layer}

Il componente Breadcrumb supporta il [ livello dati client Adobe.](/help/developing/data-layer/overview.md)
