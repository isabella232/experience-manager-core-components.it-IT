---
title: Componente barra di avanzamento
description: Il componente Barra di avanzamento rappresenta visivamente il progresso verso un obiettivo
role: Architetto, Sviluppatore, Amministratore, Business Practices
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 3%

---


# Componente barra di avanzamento {#progress-bar-component}

Il componente Barra di avanzamento del componente di base rappresenta visivamente l’avanzamento verso un obiettivo.

## Utilizzo {#usage}

Il componente Barra di avanzamento consente all’autore del contenuto di creare facilmente una barra di avanzamento definendo una percentuale di completamento, consentendo una visualizzazione visiva intuitiva dell’avanzamento verso un obiettivo.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Barra di avanzamento è la v1, introdotta con la versione 2.9.0 dei componenti core a maggio 2020, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Compatibile | Compatibile | Compatibile |

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente Barra di avanzamento e dei relativi output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_progressbar).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Barra di avanzamento [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_progress_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Configura finestra di dialogo {#configure-dialog}

![Finestra di dialogo di modifica del componente Barra di avanzamento](/help/assets/progress-bar-edit.png)

* **Completamento**  - Avanzamento rappresentato da una percentuale
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire gli stili applicati al componente Barra di avanzamento.

### Scheda Stili {#styles-tab}

Il componente Barra di avanzamento supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

## Livello dati client di Adobe {#data-layer}

Il componente Barra di avanzamento supporta [Livello dati client di Adobe.](/help/developing/data-layer/overview.md)
