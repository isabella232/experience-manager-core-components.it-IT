---
title: Componente Breadcrumb
description: Il componente di base Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.
role: Architect, Developer, Admin, User
exl-id: 19d65b9d-a407-4f50-9c55-8de0f12222ed
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 2%

---

# Componente Breadcrumb{#breadcrumb-component}

Il componente di base Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.

## Utilizzo {#usage}

Il componente Breadcrumb visualizza la posizione della pagina corrente all’interno della gerarchia del sito, consentendo ai visitatori della pagina di spostarsi nella gerarchia della pagina dalla posizione corrente. Questo è spesso integrato nelle intestazioni o nei piè di pagina.

Le opzioni disponibili, ad esempio il livello di navigazione predefinito e la possibilità di visualizzare la pagina corrente o le pagine nascoste, possono essere definite dall’autore del modello nella finestra di dialogo [progettazione](#design-dialog). L’editor dei contenuti può quindi scegliere se visualizzare o meno le pagine nascoste e il livello di navigazione effettivo per il componente nella finestra di dialogo [modifica](#edit-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Breadcrumb è v2, introdotta con la versione 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- | --- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](v1/breadcrumb-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per provare il componente Breadcrumb e per visualizzare esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_breadcrumb).

>[!NOTE]
>
>A partire dalla versione 2.1.0 dei componenti core, il componente Breadcrumb supporta [schema.org microdata](https://schema.org/BreadcrumbList).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Breadcrumb [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di eliminare le pagine nascoste e attive nelle breadcrumb e la profondità nella gerarchia che deve visualizzare.

![Finestra di dialogo di modifica del componente Breadcrumb](/help/assets/breadcrumb-edit.png)

* **Livello iniziale di navigazione** : il punto della gerarchia in cui il componente breadcrumb deve iniziare a spostarsi verso il basso fino alla pagina corrente. Esempio:

   * 0 inizia a `/content`
   * 1 inizia a `/content/<yourSite>`
   * 2 inizia a `/content/<yourSite>/<country>`

* **Mostra elementi di navigazione nascosti** : mostra le pagine contrassegnate come nascoste nel breadcrumb (per impostazione predefinita non verranno visualizzate)
* **Nascondi pagina**  corrente: consente di eliminare la pagina corrente nel breadcrumb (per impostazione predefinita verrà visualizzata).
* **Disabilita ombreggiatura** : se la pagina nella gerarchia è un reindirizzamento, viene visualizzato il nome della pagina di reindirizzamento al posto del target. Per ulteriori informazioni, consulta [Supporto struttura sito ombreggiata](navigation.md#shadow-structure) del componente di navigazione .
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire i valori predefiniti per le opzioni di eliminazione delle pagine nascoste e attive nelle breadcrumb, nonché la profondità nella gerarchia da visualizzare.

### Scheda principale {#main-tab}

![](/help/assets/breadcrumb-design.png)

* **Livello iniziale di navigazione** : definisce il valore predefinito per la posizione nella gerarchia in cui il componente breadcrumb deve iniziare a spostarsi verso il basso fino alla pagina corrente quando il componente breadcrumb viene aggiunto a una pagina.
* **Mostra elementi di navigazione nascosti**  - Definisce il valore predefinito dell’ **opzione Mostra** elemento di navigazione nascosto quando il componente breadcrumb viene aggiunto a una pagina.

   * Non attiva o disattiva l’opzione per l’autore. Imposta solo il valore predefinito.

* **Nascondi pagina corrente**: definisce il valore predefinito dell’opzione  **Nascondi** pagina corrente quando il componente breadcrumb viene aggiunto a una pagina.

   * Non attiva o disattiva l’opzione per l’autore. Imposta solo il valore predefinito.

* **Disabilita ombreggiatura** : definisce il valore predefinito dell’opzione  **Disattiva** ombreggiatura quando il componente breadcrumb viene aggiunto a una pagina.

### Scheda Stili {#styles-tab}

Il componente Breadcrumb supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

## Livello dati client di Adobe {#data-layer}

Il componente Breadcrumb supporta [Livello dati client di Adobe.](/help/developing/data-layer/overview.md)
