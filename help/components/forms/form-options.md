---
title: Componente Opzioni modulo
description: Il componente core Opzioni modulo consente la selezione di opzioni predefinite in vari formati.
role: Architect, Developer, Admin, User
exl-id: 8a74bd37-9b12-4fa6-bff2-53e337b16251
source-git-commit: 16930ccaa281f9d9c4ddbb890d4222e128557580
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 100%

---

# Componente Opzioni modulo {#form-options-component}

Il componente core Opzioni modulo consente la selezione di opzioni predefinite in vari formati.

## Utilizzo {#usage}

Il componente core Opzioni modulo consente di inviare diversi tipi di opzioni visualizzate in molti modi differenti ed è concepito per essere utilizzato insieme al [componente Contenitore modulo](form-container.md).

La visualizzazione delle opzioni, delle etichette e delle singole opzioni può essere definita dall’editor di contenuto nella [finestra di dialogo per configurazione](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Opzioni modulo è la v2, introdotta con la versione 2.0.0 dei Componenti core a gennaio 2018, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile  con<br>[versione 2.17.4](/help/versions.md) e precedenti | Compatibile | Compatibile |
| [v1](/help/components/v1/form-options-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Opzioni modulo e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_form_options_it).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Opzioni modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_options_v2_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuto di definire il tipo di opzioni da visualizzare, le etichette e le opzioni disponibili.

![Finestra di dialogo per modifica del componente Opzioni modulo](/help/assets/form-options-edit.png)

* **Tipi**: il modo in cui le opzioni vengono visualizzate
   * **Caselle di controllo**
   * **Pulsanti di scelta**
   * **Elenchi a discesa**
   * **Elenchi a discesa a selezione multipla**
* **Titolo**: il titolo che verrà visualizzato come etichetta per le opzioni
* **Nome**: il nome del campo che viene inviato con i dati del modulo
* **Origine**: dove sono definite le opzioni
   * **Locale**: definito all’interno del componente
      * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere un valore o sul pulsante **Elimina** per rimuovere un valore
         * **Valore**: valore salvato quando l’opzione viene selezionata al momento dell’invio del modulo
         * **Testo**: l’etichetta dell’opzione visualizzata sul modulo
         * **Attiva**: l’opzione viene contrassegnata come selezionata al caricamento del modulo
         * **Disattivato**: l’opzione non è selezionabile ma è ancora visualizzata
   * **Elenco**: per le opzioni viene utilizzato un elenco statico definito altrove in AEM
      * **Elenco**: il percorso dell’elenco statico in AEM
         * Utilizza il pulsante Sfoglia per individuare la risorsa elenco
   * **Origine dati**: un’origine dati utilizzata per le opzioni
      * **Origine dati**: tipo di risorsa dell’origine dati
* **Messaggio di aiuto**: suggerimento per l’utente per la compilazione del campo
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

## Finestra di dialogo per progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Opzioni modulo supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
