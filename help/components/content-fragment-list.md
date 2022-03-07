---
title: Componente Elenco frammenti di contenuto
description: Il componente core Elenco frammenti di contenuto consente la visualizzazione di un elenco di frammenti di contenuto.
role: Architect, Developer, Admin, User
exl-id: 0f2295b1-d287-4f72-8ee4-fa98c4850e53
source-git-commit: 395a1669cf3e17f649c23852addc37316b923bfd
workflow-type: ht
source-wordcount: '831'
ht-degree: 100%

---

# Componente Elenco frammenti di contenuto{#content-fragment-list-component}

Il componente core Elenco frammenti di contenuto consente la visualizzazione di un elenco di [frammenti di contenuto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=it).

## Utilizzo {#usage}

Il componente core Elenco frammenti di contenuto consente di includere un elenco di [frammenti di contenuto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=it) in una pagina basata su un Modello del Frammento di contenuto. Questa funzione può essere particolarmente utile per creare [contenuto senza intestazione](https://helpx.adobe.com/it/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) che può essere facilmente riutilizzato da altre applicazioni.

* L’elenco e le relative proprietà possono essere selezionati nella [finestra di dialogo per configurazione](#configure-dialog).
* Gli stili possono essere applicati al componente nella [finestra di dialogo per progettazione](#design-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento di contenuto è la v2, introdotta con la versione 2.18.0 dei Componenti core a febbraio 2022, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|----|---|---|
| v2 | - | Compatibile | Compatibile |
| [v1](v1/content-fragment-list.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

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

### Scheda Stili {#styles-tab-edit}

![Scheda Stili della finestra di dialogo per modifica del componente Elenco frammenti di contenuto](/help/assets/content-fragment-list-styles.png)

Il componente Frammento esperienza supporta il [sistema di stili di AEM](/help/get-started/authoring.md#component-styling).

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nella [finestra di dialogo di progettazione](#design-dialog) affinché il menu a discesa sia disponibile.

## Finestra di dialogo per progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Frammento esperienza supporta il [sistema di stili di AEM.](/help/get-started/authoring.md#component-styling)
