---
title: Componente Sommario
description: Il componente Sommario crea un A-C basato sui titoli nel contenuto della pagina, consentendo ai lettori di navigare rapidamente nella pagina.
role: Architect, Developer, Admin, User
exl-id: 006adde2-ebff-4e74-8e79-325cccd43e8f
source-git-commit: 394a8b968d7bcde7e766ed719c5914ec5cb60744
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 22%

---

# Componente Sommario {#table-of-contents-component}

Il componente Sommario crea un A-C basato sui titoli nel contenuto della pagina, consentendo ai lettori di navigare rapidamente nella pagina.

## Utilizzo {#usage}

Il componente Sommario offre ai visitatori del sito la possibilità di navigare rapidamente nel contenuto della pagina attraverso un sommario generato in modo efficiente in base ai titoli del contenuto delle pagine.

* Il ToC viene generato lato server.
* È completamente memorizzato nella cache dal dispatcher per una consegna rapida.
* Funziona con tutti i componenti della pagina, non solo con i componenti core.

La [finestra di dialogo modifica](#edit-dialog) consente all’autore dei contenuti di definire la gamma di titoli da utilizzare nei AC. Utilizzo della [finestra di dialogo di progettazione](#design-dialog), l’autore del modello può impostare il valore predefinito per i titoli quando un autore di contenuti aggiunge un componente Sommario a una pagina e limita i titoli inclusi nel campo AC in base ai nomi delle classi.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Sommario è v1, introdotta con la versione 2.20.0 dei componenti core a maggio 2022, ed è descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente Sommario e dei relativi output HTML e JSON, visita il [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_tableofcontents).

### Dettagli tecnici {#technical-details}

Documentazione tecnica più recente sul componente Sommario [disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di definire gli intervalli dei livelli del titolo che il componente Sommario deve rappresentare come A-C.

![Finestra di dialogo di modifica del componente Sommario](/help/assets/tableofcontents-edit.png)

**Tipo di elenco** - Questa opzione definisce se l’elenco deve essere un elenco puntato o un elenco numerato.
* **Livello iniziale titolo** - Questa opzione definisce il livello più alto di titoli che il componente Sommario deve riprodurre.
* **Livello di interruzione titolo** - Questa opzione definisce il livello più basso di titoli che il componente Sommario deve riprodurre.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e nel [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

## Finestra di dialogo per progettazione {#design-dialog}

Utilizzando la finestra di dialogo di progettazione, l’autore del modello può impostare il valore predefinito per l’intervallo di titoli del componente Sommario e limitare i titoli inclusi nel componente AC in base ai nomi delle classi.

### Scheda Proprietà {#properties-tab}

![Finestra di dialogo per progettazione del componente Ricerca rapida](/help/assets/tableofcontents-design.png)

* **Limita tipo elenco** - Questa opzione definisce il tipo di elenco che verrà generato dal componente. Quando si seleziona questa opzione, l’autore del contenuto può scegliere un altro tipo di elenco.
* **Limitare il livello iniziale** - Questa opzione definisce il livello di titolo più alto che l’autore del contenuto può selezionare per definire il AC.
* **Limitare il livello di arresto** - Questa opzione definisce il livello del titolo più basso che l’autore del contenuto può selezionare per definire il AC.
* **Includi nomi delle classi** - Se questa opzione è impostata, solo i titoli con i nomi di classe specificati o contenuti all&#39;interno degli elementi dei nomi di classe specificati saranno considerati dal componente Sommario.
   * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere uno o più nomi di classe.
   * Tocca o fai clic sul pulsante **Elimina** accanto al nome di una classe per eliminarla.
* **Ignora nomi classe** - Se questa opzione è impostata, i titoli con i nomi di classe specificati o contenuti all&#39;interno degli elementi dei nomi di classe specificati verranno ignorati dal componente Sommario.
   * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere uno o più nomi di classe.
   * Tocca o fai clic sul pulsante **Elimina** accanto al nome di una classe per eliminarla.

### Scheda Stili {#styles-tab}

Il componente Sommario supporta la AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

Il componente Sommario supporta il [Livello dati client di Adobe.](/help/developing/data-layer/overview.md)
