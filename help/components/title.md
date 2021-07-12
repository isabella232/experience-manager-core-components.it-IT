---
title: Componente titolo
description: Il componente Titolo componente di base è un componente di intestazione di sezione che presenta funzioni di modifica diretta.
role: Architect, Developer, Admin, User
exl-id: 393af72c-549f-4609-afb0-2712f827b549
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 3%

---

# Componente titolo{#title-component}

Il componente Titolo componente di base è un componente di intestazione di sezione che presenta funzioni di modifica diretta.

## Utilizzo {#usage}

Il componente Titolo deve essere utilizzato come titolo o intestazione di una sezione di contenuto. I livelli di intestazione disponibili possono essere definiti dall&#39;autore del modello nella finestra di dialogo [progettazione](#design-dialog). L’editor dei contenuti può selezionare tra i livelli di intestazione disponibili nella finestra di dialogo [modifica](#edit-dialog). Per maggiore comodità, è disponibile anche una semplice modifica diretta del testo dell’intestazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Titolo è v2, introdotta con la versione 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](v1/title-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente Titolo e dell’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_title) .

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Titolo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_title_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di definire il testo del titolo e selezionare il livello del titolo.

* **Titolo** : se questo campo viene lasciato vuoto, viene utilizzato il titolo della pagina
* **Tipo/Dimensione**  - Definisce il livello del titolo
* **Collegamento**  - Definisce il contenuto a cui verrà collegato il titolo. Può essere un percorso a una pagina di contenuto, un URL esterno o un ancoraggio di pagina.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

![Finestra di dialogo di modifica del componente Titolo](/help/assets/title-edit.png)

>[!NOTE]
>
>La possibilità di definire un collegamento per il titolo è stata introdotta con la versione 2.2.0 dei componenti core.

L’editor locale può essere utilizzato anche per modificare il testo del componente titolo.

![Modifica diretta del componente Titolo](/help/assets/title-edit-inline.png)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire il livello di intestazione predefinito che i componenti titolo avranno quando creati dagli autori dei contenuti.

### Scheda Dimensioni {#sizes-tab}

![Finestra di dialogo di progettazione del componente Titolo](/help/assets/title-design.png)

* **Tipi/dimensioni consentiti per gli autori**  - Abilita o disabilita i tipi di intestazione che saranno disponibili per gli autori di contenuti quando utilizzano il componente Titolo.
* **Tipo/dimensione predefinito**: definisci il tipo di intestazione che verrà assegnato automaticamente quando un autore di contenuti aggiunge il componente Titolo a una pagina.
* **Disattiva collegamento**: disabilita il supporto dei collegamenti nel componente titolo per impedire agli autori di contenuti di effettuare collegamenti dai titoli.

>[!NOTE]
>
>La possibilità di definire un collegamento per il titolo è stata introdotta con la versione 2.2.0 dei componenti core.

### Scheda Stili {#styles-tab}

Il componente Titolo supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

## Livello dati client di Adobe {#data-layer}

Il componente Titolo supporta [Livello dati client di Adobe.](/help/developing/data-layer/overview.md)
