---
title: Componente Elenco frammenti di contenuto (v1)
description: Il componente core Elenco frammenti di contenuto consente la visualizzazione di un elenco di frammenti di contenuto.
role: Architect, Developer, Admin, User
source-git-commit: e5251010ca41025eb2bb56b66164ecf4cc0145c8
workflow-type: ht
source-wordcount: '725'
ht-degree: 100%

---


# Componente Elenco frammenti di contenuto (v1) {#content-fragment-list-component}

Il componente core Elenco frammenti di contenuto consente la visualizzazione di un elenco di [frammenti di contenuto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=it).

## Utilizzo {#usage}

Il componente core Elenco frammenti di contenuto consente di includere un elenco di [frammenti di contenuto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=it) in una pagina basata su un Modello del Frammento di contenuto. Questa funzione può essere particolarmente utile per creare [contenuto senza intestazione](https://helpx.adobe.com/it/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) che può essere facilmente riutilizzato da altre applicazioni.

* L’elenco e le relative proprietà possono essere selezionati nella [finestra di dialogo per configurazione](#configure-dialog).
* Gli stili possono essere applicati al componente nella [finestra di dialogo per progettazione](#design-dialog).

## Versione e compatibilità {#version-and-compatibility}

Il documento descrive la versione 1 del componente Frammento di contenuto, introdotto con la versione 2.4.0 dei componenti core a maggio 2019.

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Elenco Frammento di contenuto.
>
>Per informazioni dettagliate sulla versione corrente del componente Elenco Frammento di contenuto, consulta il documento [Componente Elenco Frammento di contenuto](/help/components/content-fragment-list.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Elenco frammenti di contenuto e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_cflist_it).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Elenco frammenti di contenuto [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_cflist_v1_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuto di definire i Frammenti di contenuto inclusi nell’elenco e gli elementi di quei frammenti da includere.

### Scheda Proprietà

La scheda **Proprietà** definisce quali Frammenti di contenuto sono inclusi nell’elenco. Si basa principalmente su un Modello del Frammento di contenuto selezionato, ma sono disponibili altre opzioni di filtro.

![Scheda Proprietà della finestra di dialogo per modifica del componente Elenco frammenti di contenuto](/help/assets/content-fragment-list-properties.png)

* **Modello**: percorso del Modello del Frammento di contenuto su cui è basato l’elenco.
   * Per impostazione predefinita, tutti i Frammenti di contenuto del Modello definito nel **percorso del modello** sono inclusi nell’elenco.
* **Percorso principale**: il percorso principale da cui viene creato l’elenco.
   * I Frammenti di contenuto basati sul **percorso del modello** selezionato verranno filtrati su quelli del **Percorso principale** specificato.
      * Tocca o fai clic sul pulsante **Apri finestra di dialogo per selezione** a destra del campo per specificare il percorso.
* **Tag**: l’elenco includerà solo i Frammenti di contenuto con i tag specificati.
   * Tocca o fai clic sul pulsante **Apri finestra di dialogo per selezione** a destra del campo per specificare i tag.
   * Tocca o fai clic sulla X accanto ai tag selezionati per rimuoverli.
* **Ordina per**: campo del Modello del Frammento di contenuto in base al quale verrà ordinato l’elenco
   * Si possono selezionare solo i campi di testo (compresi i campi numerici, data e ora).
* **Ordinamento**: ordinamento dell’elenco in base al campo **Ordina per**
   * Crescente o Decrescente
* **Max. elementi**: numero massimo di elementi da visualizzare nell’elenco
   * Se non specificato, vengono visualizzati tutti gli elementi.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

>[!NOTE]
>Le opzioni **Ordina per**, **Ordinamento** e **Max. elementi** sono state introdotte con la versione 2.7.0 dei Componenti core.

### Scheda Elementi

Per impostazione predefinita, tutti gli elementi del Modello del Frammento di contenuto vengono inclusi nell’elenco (a meno che il numero non sia limitato dal valore del campo **Max. elementi**). La scheda **Elementi** consente di specificare solo determinati elementi da includere.

![Scheda Elementi della finestra di dialogo per modifica del componente Elenco frammenti di contenuto](/help/assets/content-fragment-list-elements.png)

* **Elementi**: vengono visualizzati solo gli elementi dei Frammenti di contenuto nell’elenco specificato.
   * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere un nuovo elemento.
   * Tocca o fai clic sul pulsante **Elimina** per rimuovere un elemento selezionato.
   * Trascina la maniglia **di ordinamento** per cambiare l’ordine degli elementi.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire gli stili applicati al componente Elenco frammenti di contenuto.
