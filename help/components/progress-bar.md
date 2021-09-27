---
title: Componente Barra di avanzamento
description: Il componente Barra di avanzamento rappresenta visivamente lo stato di avanzamento verso un obiettivo
role: Architect, Developer, Admin, User
exl-id: 47afc5a6-ac57-4b6c-92c4-015ca956a20b
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '338'
ht-degree: 100%

---

# Componente Barra di avanzamento {#progress-bar-component}

Il componente core Barra di avanzamento rappresenta visivamente lo stato di avanzamento verso un obiettivo.

## Utilizzo {#usage}

Il componente Barra di avanzamento consente all’autore di contenuto di creare facilmente una barra di avanzamento definendo una percentuale di completamento, consentendo una visualizzazione intuitiva dell’avanzamento verso un obiettivo.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Barra di avanzamento è la v1, introdotta con la versione 2.9.0 dei Componenti core a maggio 2020, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Compatibile | Compatibile | Compatibile |

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Barra di avanzamento e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_progressbar_it).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Barra di avanzamento [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_progress_v1).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per configurazione {#configure-dialog}

![Finestra di dialogo per modifica del componente Barra di avanzamento](/help/assets/progress-bar-edit.png)

* **Completamento**: lo stato di avanzamento espresso in percentuale
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire gli stili applicati al componente Barra di avanzamento.

### Scheda Stili {#styles-tab}

Il componente Barra di avanzamento supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

## Adobe Client Data Layer {#data-layer}

Il componente Barra di avanzamento supporta [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
