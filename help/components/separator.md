---
title: Componente separatore
description: Il componente separatore crea un’interruzione tra i componenti di una pagina
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 5%

---


# Componente separatore {#separator-component}

Il componente Separatore componenti core visualizza una regola orizzontale per la separazione del contenuto.

## Utilizzo {#usage}

Il Componente separatore consente all’autore del contenuto di creare facilmente una regola orizzontale come interruzione di contenuto per organizzare meglio le informazioni su una pagina.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del Componente separatore è la v1, introdotta con la versione 2.3.0 dei Componenti core a febbraio 2019, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Compatibile | Compatibile | Compatibile |

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del Componente separatore e dell’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_separator).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul Componente separatore [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_separator_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Configura finestra di dialogo {#configure-dialog}

![Finestra di dialogo di modifica del componente separatore](/help/assets/separator-edit.png)

* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire gli stili applicati al Componente separatore.

### Scheda Stili {#styles-tab}

Il componente Separatore supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).
