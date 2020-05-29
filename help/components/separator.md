---
title: Componente separatore
description: Il componente separatore crea un’interruzione tra i componenti di una pagina
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 5%

---


# Componente separatore {#separator-component}

Il componente Separatore componenti core visualizza una regola orizzontale per la separazione del contenuto.

## Utilizzo {#usage}

Il componente Separatore consente all&#39;autore del contenuto di creare facilmente una regola orizzontale come interruzione tra i contenuti per organizzare meglio le informazioni su una pagina.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Separatore è v1, introdotto con la release 2.3.0 dei componenti core nel febbraio 2019, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Compatibile | Compatibile | Compatibile |

## Output componente di esempio {#sample-component-output}

Per provare il componente Separatore e per visualizzare esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](https://adobe.com/go/aem_cmp_library_separator)Componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Separatore [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_separator_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Configura finestra di dialogo {#configure-dialog}

![Finestra di dialogo di modifica del componente Separatore](/help/assets/separator-edit.png)

* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire gli stili applicati al componente Separatore.

### Scheda Stili {#styles-tab}

Il componente Separatore supporta AEM [Style System](/help/get-started/authoring.md#component-styling).
