---
title: Componente Opzioni modulo
description: Il componente per le opzioni del modulo dei componenti core consente la selezione da opzioni predefinite in vari formati.
role: Architect, Developer, Admin, User
exl-id: 8a74bd37-9b12-4fa6-bff2-53e337b16251
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 3%

---

# Componente Opzioni modulo {#form-options-component}

Il componente per le opzioni del modulo dei componenti core consente la selezione da opzioni predefinite in vari formati.

## Utilizzo {#usage}

Il componente Opzioni modulo per componente core consente di inviare diversi tipi di opzioni presentate in diversi modi e deve essere utilizzato insieme al componente [Contenitore modulo](form-container.md).

La presentazione delle opzioni, delle etichette e delle singole opzioni può essere definita dall&#39;editor dei contenuti nella finestra di dialogo [configura](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Opzioni modulo è v2, introdotta con la versione 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-options-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente Opzioni modulo e dei relativi output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_form_options).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Opzioni modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_options_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Configura {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il tipo di opzioni da presentare, le etichette e le opzioni disponibili.

![Finestra di dialogo di modifica del componente Opzioni modulo](/help/assets/form-options-edit.png)

* **Tipi**  - Modalità di presentazione delle opzioni
   * **Caselle di controllo**
   * **Pulsanti di scelta**
   * **A discesa**
   * **Menu a discesa a selezione multipla**
* **Titolo** : il titolo che verrà visualizzato come etichetta per le opzioni
* **Nome** : nome del campo inviato con i dati del modulo
* **Origine**  - Dove sono definite le opzioni
   * **Locale**  - Definito all’interno del componente
      * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere un valore, **Elimina** per rimuovere un valore
         * **Valore** : valore salvato quando tale opzione viene selezionata al momento dell’invio del modulo
         * **Testo** : l’etichetta dell’opzione visualizzata sul modulo
         * **Attivo** : l’opzione viene contrassegnata come selezionata al caricamento del modulo
         * **Disabilitato** : l’opzione non è selezionabile ma è ancora visualizzata
   * **Elenco** : per le opzioni viene utilizzato un elenco statico definito altrove in AEM
      * **Elenco** : percorso dell’elenco statico in AEM
         * Utilizzare il pulsante Sfoglia per individuare la risorsa dell’elenco
   * **Origine**  dati: un’origine dati utilizzata per le opzioni
      * **Origine**  dati: tipo di risorsa dell’origine dati
* **Messaggio della Guida** : un suggerimento per l’utente di ciò che può essere immesso nel campo
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Opzioni modulo supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).
