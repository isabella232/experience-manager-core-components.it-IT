---
title: Componente titolo
description: Il componente core Titolo è un componente di intestazione di sezione che offre funzioni di modifica diretta.
role: Architect, Developer, Admin, User
exl-id: 393af72c-549f-4609-afb0-2712f827b549
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '569'
ht-degree: 100%

---

# Componente Titolo{#title-component}

Il componente core Titolo è un componente di intestazione di sezione che offre funzioni di modifica diretta.

## Utilizzo {#usage}

Il componente Titolo deve essere utilizzato come titolo o intestazione di una sezione di contenuto. I livelli di intestazione disponibili possono essere definiti dall’autore del modello nella [finestra di dialogo per progettazione](#design-dialog). L’editor di contenuto può selezionare tra i livelli di intestazione disponibili nella [finestra di dialogo per modifica](#edit-dialog). Per maggiore comodità, è disponibile anche una semplice modifica diretta del testo dell’intestazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Titolo è la v2, introdotta con la versione 2.0.0 dei Componenti core a gennaio 2018, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](v1/title-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Titolo e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_title_it).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Titolo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_title_v2_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per modifica {#edit-dialog}

La finestra di dialogo per modifica consente all’autore di contenuto di definire il testo del titolo e selezionare il livello dell’intestazione.

* **Titolo**: se questo campo viene lasciato vuoto, viene utilizzato il titolo della pagina
* **Tipo/Dimensione**: definisce il livello di intestazione del titolo
* **Collegamento**: definisce il contenuto a cui verrà collegato il titolo. Può essere un percorso che punta a una pagina di contenuto, un URL esterno o un ancoraggio di pagina.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

![Finestra di dialogo per modifica del componente Titolo](/help/assets/title-edit.png)

>[!NOTE]
>
>La possibilità di definire un collegamento per il titolo è stata introdotta con la versione 2.2.0 dei Componenti core.

L’editor locale può essere utilizzato anche per modificare il testo del componente Titolo.

![Modifica diretta del componente Titolo](/help/assets/title-edit-inline.png)

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire il livello di intestazione predefinito dei componenti Titolo che vengono creati dagli autori di contenuto.

### Scheda Dimensioni {#sizes-tab}

![Finestra di dialogo per progettazione del componente Titolo](/help/assets/title-design.png)

* **Tipi/dimensioni consentiti per autori**: abilita o disabilita i tipi di intestazione che saranno disponibili per gli autori di contenuto quando utilizzano il componente Titolo.
* **Tipo/dimensione predefinito**: definisce il tipo di intestazione che verrà assegnato automaticamente quando un autore di contenuti aggiunge il componente Titolo a una pagina.
* **Disabilita collegamento**: disabilita il supporto dei collegamenti nel componente Titolo per impedire agli autori di contenuto di collegare i titoli.

>[!NOTE]
>
>La possibilità di definire un collegamento per il titolo è stata introdotta con la versione 2.2.0 dei Componenti core.

### Scheda Stili {#styles-tab}

Il componente Titolo supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

## Adobe Client Data Layer {#data-layer}

Il componente Titolo supporta [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
