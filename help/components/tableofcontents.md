---
title: Componente Sommario
description: Il componente Sommario crea un sommario basato sui titoli nel contenuto della pagina, consentendo ai lettori di navigare rapidamente all'interno della pagina.
role: Architect, Developer, Admin, User
exl-id: 006adde2-ebff-4e74-8e79-325cccd43e8f
source-git-commit: 394a8b968d7bcde7e766ed719c5914ec5cb60744
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 92%

---

# Componente Sommario {#table-of-contents-component}

Il componente Sommario crea un sommario basato sui titoli nel contenuto della pagina, consentendo ai lettori di navigare rapidamente all&#39;interno della pagina.

## Utilizzo {#usage}

Il componente Sommario offre ai visitatori del sito la possibilità di navigare rapidamente nel contenuto della pagina attraverso un sommario generato in modo efficiente in base ai titoli del contenuto delle pagine.

* Il ToC viene generato lato server.
* È completamente memorizzato nella cache dal dispatcher per una consegna rapida.
* Funziona con tutti i componenti della pagina, non solo con i componenti core.

La [finestra di dialogo di modifica](#edit-dialog) consente all’autore dei contenuti di definire la serie di titoli da inserire nel sommario. Utilizzando la [finestra di dialogo di progettazione](#design-dialog), l’autore del modello può impostare il valore predefinito per i titoli quando un autore di contenuti aggiunge un componente Sommario a una pagina, nonché limitare i titoli da includere nel sommario in base a nomi di classi.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Sommario è la v1, introdotta con la versione 2.20.0 dei componenti core a maggio 2022, ed è descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per conoscere il componente Sommario e vedere esempi delle sue opzioni di configurazione e dell’output HTML e JSON, visita la [Libreria di componenti](https://adobe.com/go/aem_cmp_library_tableofcontents).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Sommario [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di definire la serie di livelli di titolo che il componente Sommario deve riprodurre come voci del sommario.

![Finestra di dialogo di modifica del componente Sommario](/help/assets/tableofcontents-edit.png)

**Tipo di elenco**: questa opzione definisce se l’elenco deve essere puntato o numerato.
* **Livello titolo iniziale**: questa opzione definisce il livello di titolo più alto che il componente Sommario deve riprodurre.
* **Livello titolo finale**: questa opzione definisce il livello di titolo più basso che il componente Sommario deve riprodurre.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e nel [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

## Finestra di dialogo per progettazione {#design-dialog}

Utilizzando la finestra di dialogo di progettazione, l’autore del modello può impostare il valore predefinito per la serie di titoli del componente Sommario e limitare i titoli da includere nel sommario in base a nomi di classi.

### Scheda Proprietà {#properties-tab}

![Finestra di dialogo per progettazione del componente Ricerca rapida](/help/assets/tableofcontents-design.png)

* **Limita tipo di elenco**: questa opzione definisce il tipo di elenco che verrà generato dal componente. Selezionando questa opzione, viene limitata la possibilità dell’autore del contenuto di scegliere un altro tipo di elenco.
* **Limita il livello iniziale**: questa opzione definisce il livello di titolo più alto che l’autore del contenuto può selezionare per definire il sommario.
* **Limita il livello finale**: questa opzione definisce il livello di titolo più basso che l’autore del contenuto può selezionare per definire il sommario.
* **Includi nomi di classe**: se questa opzione è impostata, solo i titoli con i nomi di classi specificati o contenuti all&#39;interno di elementi con i nomi di classi specificati verranno considerati dal componente Sommario.
   * Tocca o fai clic sull’icona **Aggiungi** per aggiungere uno o più nomi di classi.
   * Tocca o fai clic sull&#39;icona **Elimina** accanto al nome di una classe per eliminarla.
* **Ignora nomi di classe**: se questa opzione è impostata, i titoli con i nomi di classe specificati o contenuti all&#39;interno di elementi con i nomi di classe specificati verranno ignorati dal componente Sommario.
   * Tocca o fai clic sull’icona **Aggiungi** per aggiungere uno o più nomi di classi.
   * Tocca o fai clic sull’icona **Elimina** accanto al nome di una classe per eliminarla.

### Scheda Stili {#styles-tab}

Il componente Sommario supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

## Adobe Client Data Layer {#data-layer}

Il componente Sommario supporta [Adobe Client Data Layer](/help/developing/data-layer/overview.md).
