---
title: Componente barra di avanzamento
description: Il componente della barra di avanzamento rappresenta visivamente il progresso verso un obiettivo
translation-type: tm+mt
source-git-commit: d3ebcea5fa1523c1a986841cd3d1a64e16e85f6d
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 3%

---


# Componente barra di avanzamento {#progress-bar-component}

Il componente Core Component Progress Bar Component rappresenta visivamente il progresso verso un obiettivo.

## Utilizzo {#usage}

Il componente Barra di avanzamento consente all’autore del contenuto di creare facilmente una barra di avanzamento definendo una percentuale di completamento, consentendo una visualizzazione intuitiva dell’avanzamento verso un obiettivo.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Barra di avanzamento è v1, introdotto con la release 2.9.0 dei componenti core a maggio 2020, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Compatibile | Compatibile | Compatibile |

## Esempio di output del componente {#sample-component-output}

Per provare il componente Barra di avanzamento e per vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library_progressbar).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente della barra di avanzamento [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_progress_v1).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Configura finestra di dialogo {#configure-dialog}

![Finestra di dialogo di modifica del componente della barra di avanzamento](/help/assets/progress-bar-edit.png)

* **Completamento**  - L&#39;avanzamento come rappresentato da una percentuale
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire gli stili applicati al componente Barra di avanzamento.

### Scheda Stili {#styles-tab}

Il componente Barra di avanzamento supporta il AEM [Sistema di stile](/help/get-started/authoring.md#component-styling).

## Livello dati client  Adobe {#data-layer}

Il componente Barra di avanzamento supporta il [ livello dati client Adobe.](/help/developing/data-layer/overview.md)
