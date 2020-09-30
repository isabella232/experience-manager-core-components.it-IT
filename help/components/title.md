---
title: Componente titolo
description: Il componente Titolo componente di base è un componente di intestazione di sezione che include la modifica locale.
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Componente titolo{#title-component}

Il componente Titolo componente di base è un componente di intestazione di sezione che include la modifica locale.

## Utilizzo {#usage}

Il componente Titolo è destinato a essere utilizzato come titolo o intestazione di una sezione di contenuto. I livelli di intestazione disponibili possono essere definiti dall’autore del modello nella finestra di dialogo [di](#design-dialog)progettazione. L’editor del contenuto può selezionare tra i livelli di intestazione disponibili nella finestra di dialogo [di](#edit-dialog)modifica. Per maggiore comodità, è disponibile anche la semplice modifica locale del testo dell’intestazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Titolo è v2, introdotta con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](v1/title-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Titolo e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](https://adobe.com/go/aem_cmp_library_title)Componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Titolo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_title_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di definire il testo del titolo e selezionare il livello del titolo.

* **Titolo** - Se vuoto, verrà utilizzato il titolo della pagina
* **Tipo/Dimensione** - Definisce il livello di intestazione del titolo
* **Collegamento** - Definisce il contenuto a cui verrà collegato il titolo. Può essere un percorso a una pagina di contenuto, un URL esterno o un ancoraggio di pagina.
* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

![Finestra di dialogo di modifica del componente Titolo](/help/assets/title-edit.png)

>[!NOTE]
>
>La possibilità di definire un collegamento per il titolo è stata introdotta con la release 2.2.0 dei componenti core.

L’editor locale può essere utilizzato anche per modificare il testo del componente titolo.

![Modifica diretta del componente Titolo](/help/assets/title-edit-inline.png)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire il livello di intestazione predefinito che i componenti titolo avranno al momento della creazione da parte degli autori dei contenuti.

### Scheda Dimensioni {#sizes-tab}

![Finestra di dialogo Progettazione del componente Titolo](/help/assets/title-design.png)

* **Tipi/dimensioni consentiti per gli autori** - Abilitare o disabilitare i tipi di intestazione che saranno disponibili per gli autori di contenuti quando utilizzano il componente Titolo.
* **Tipo/Dimensione** predefinita: consente di definire il tipo di intestazione che verrà assegnato automaticamente quando un autore di contenuto aggiunge il componente Titolo a una pagina.
* **Disattiva collegamento**- Disattiva il supporto per i collegamenti nel componente titolo per impedire agli autori di contenuti di collegare i titoli.

>[!NOTE]
>
>La possibilità di definire un collegamento per il titolo è stata introdotta con la release 2.2.0 dei componenti core.

### Scheda Stili {#styles-tab}

Il componente Titolo supporta AEM [Style System](/help/get-started/authoring.md#component-styling).
