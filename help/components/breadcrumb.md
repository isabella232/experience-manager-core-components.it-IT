---
title: Componente Breadcrumb
description: Il componente di base Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.
translation-type: tm+mt
source-git-commit: ff943aeca0333b13e2b9aaf11f316457f001d507
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Componente Breadcrumb{#breadcrumb-component}

Il componente di base Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.

## Utilizzo {#usage}

Il componente Breadcrumb visualizza la posizione della pagina corrente all’interno della gerarchia del sito, consentendo ai visitatori della pagina di spostarsi nella gerarchia di pagina dalla posizione corrente. Questa funzione è spesso integrata nelle intestazioni o nei piè di pagina della pagina.

Le opzioni disponibili, come il livello di navigazione predefinito e la possibilità di visualizzare la pagina corrente o le pagine nascoste, possono essere definite dall&#39;autore del modello nella finestra di dialogo [](#design-dialog)della progettazione. L’editor dei contenuti può quindi scegliere se visualizzare o meno le pagine nascoste e il livello di navigazione effettivo per il componente nella finestra di dialogo [di](#edit-dialog)modifica.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Breadcrumb è v2, introdotta con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- | --- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](v1/breadcrumb-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Breadcrumb e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la libreria [](https://adobe.com/go/aem_cmp_library_breadcrumb)dei componenti.

>[!NOTE]
>
>Nella release 2.1.0 dei componenti core, il componente Breadcrumb supporta i microdati [](https://schema.org/BreadcrumbList)schema.org.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Breadcrumb [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di eliminare le pagine nascoste e attive nelle breadcrumb e la profondità nella gerarchia che dovrebbe visualizzare.

![Finestra di dialogo di modifica del componente Breadcrumb](/help/assets/breadcrumb-edit.png)

* **Livello** iniziale navigazione - Punto della gerarchia in cui il componente breadcrumb deve iniziare a camminare verso il basso fino alla pagina corrente. Esempio:

   * 0 inizia da `/content`
   * 1 inizia a `/content/<yourSite>`
   * 2 inizia a `/content/<yourSite>/<country>`

* **Mostra elementi** di navigazione nascosti - Mostra pagine contrassegnate come nascoste nel breadcrumb (per impostazione predefinita non vengono visualizzate)
* **Nascondi pagina** corrente - Elimina la pagina corrente nel percorso di navigazione (per impostazione predefinita verrà visualizzata)
* **Disattiva ombreggiatura** : se la pagina nella gerarchia è un reindirizzamento, il nome della pagina di reindirizzamento verrà visualizzato al posto della destinazione. Per ulteriori informazioni, consulta Supporto [struttura del sito](navigation.md#shadow-structure) shadow del componente Navigazione.
* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire i valori predefiniti per le opzioni che consentono di eliminare le pagine nascoste e attive nelle breadcrumb, nonché la profondità nella gerarchia che dovrebbe visualizzare.

### Scheda Principale {#main-tab}

![](/help/assets/breadcrumb-design.png)

* **Livello** iniziale navigazione - Definisce il valore predefinito per la posizione nella gerarchia in cui il componente breadcrumb deve iniziare a camminare verso il basso fino alla pagina corrente quando il componente breadcrumb viene aggiunto a una pagina.
* **Mostra elementi** di navigazione nascosti - Definisce il valore predefinito dell&#39;opzione **Mostra elementi** di navigazione nascosti quando il componente breadcrumb viene aggiunto a una pagina.

   * Non attiva o disattiva l’opzione per l’autore. Imposta solo il valore predefinito.

* **Nascondi pagina** corrente - Definisce il valore predefinito dell’opzione **Nascondi pagina** corrente quando il componente breadcrumb viene aggiunto a una pagina.

   * Non attiva o disattiva l’opzione per l’autore. Imposta solo il valore predefinito.

* **Disattiva ombreggiatura** - Definisce il valore predefinito dell’opzione **Disattiva ombreggiatura** quando il componente breadcrumb viene aggiunto a una pagina.

### Scheda Stili {#styles-tab}

Il componente Breadcrumb supporta AEM [Style System](/help/get-started/authoring.md#component-styling).
