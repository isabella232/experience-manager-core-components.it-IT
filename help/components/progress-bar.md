---
title: Componente barra di avanzamento
description: Il componente della barra di avanzamento rappresenta visivamente il progresso verso un obiettivo
translation-type: tm+mt
source-git-commit: cba1d898d7789af7f4045ef9aa052b4da6a6b33a
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 3%

---


# Componente barra di avanzamento {#progress-bar-component}

Il componente Core Component Progress Bar Component rappresenta visivamente il progresso verso un obiettivo.

## Utilizzo {#usage}

Il componente Barra di avanzamento consente all’autore del contenuto di creare facilmente una barra di avanzamento definendo una percentuale di completamento, consentendo una visualizzazione intuitiva dell’avanzamento verso un obiettivo.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Barra di avanzamento è v1, introdotto con la release 2.9.0 dei componenti core a maggio 2020, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Compatibile | Compatibile | Compatibile |

## Output componente di esempio {#sample-component-output}

Per provare il componente Barra di avanzamento e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visitare la Libreria [](https://adobe.com/go/aem_cmp_library_progressbar)componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Barra di avanzamento [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_progress_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Configura finestra di dialogo {#configure-dialog}

![Finestra di dialogo di modifica del componente della barra di avanzamento](/help/assets/progress-bar-edit.png)

* **Completamento** - L&#39;avanzamento come rappresentato da una percentuale
* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire gli stili applicati al componente Barra di avanzamento.

### Scheda Stili {#styles-tab}

Il componente Barra di avanzamento supporta AEM [Style System](/help/get-started/authoring.md#component-styling).
