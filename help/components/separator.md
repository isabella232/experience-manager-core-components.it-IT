---
title: Componente separatore
description: Il componente Separatore crea un’interruzione tra i componenti di una pagina
role: Architect, Developer, Admin, User
exl-id: 79f19368-67fa-4864-93f7-2aa801d13fdb
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: ht
source-wordcount: '308'
ht-degree: 100%

---

# Componente Separatore {#separator-component}

Il componente core Separatore visualizza un righello orizzontale per la separazione del contenuto.

## Utilizzo {#usage}

Il componente Separatore consente all’autore di contenuto di creare facilmente un righello orizzontale e utilizzarlo come interruzione di contenuto per organizzare meglio le informazioni su una pagina.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Separatore è la v1, introdotta con la versione 2.3.0 dei Componenti core a febbraio 2019, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Compatibile con<br>[versione 2.17.4](/help/versions.md) e precedenti | Compatibile | Compatibile |

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Separatore e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_separator_it).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Separatore [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_separator_v1_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per configurazione {#configure-dialog}

![Finestra di dialogo per modifica del componente Separatore](/help/assets/separator-edit.png)

* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire gli stili applicati al componente Separatore.

### Scheda Stili {#styles-tab}

Il componente Separatore supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
