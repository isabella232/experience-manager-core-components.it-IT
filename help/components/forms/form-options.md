---
title: Componente Opzioni modulo
description: Il componente Opzioni modulo per componenti core consente la selezione da opzioni predefinite in vari formati.
translation-type: tm+mt
source-git-commit: 95c0621f5423bfa515fe5e8b693e127ea56b4ae0

---


# Componente Opzioni modulo {#form-options-component}

Il componente Opzioni modulo per componenti core consente la selezione da opzioni predefinite in vari formati.

## Utilizzo {#usage}

Il componente Opzioni modulo per componenti core consente di inviare diversi tipi di opzioni presentate in diversi modi e deve essere utilizzato insieme al componente [Contenitore](form-container.md)modulo.

La presentazione delle opzioni, delle etichette e delle singole opzioni può essere definita dall&#39;editor di contenuti nella finestra di dialogo [di](#configure-dialog)configurazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Opzioni modulo è v2, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-options-v1.md) | Compatibile | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Opzioni modulo e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visitare la Libreria [](https://adobe.com/go/aem_cmp_library_form_options)componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Opzioni modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_options_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il tipo di opzioni da presentare, le etichette e le opzioni disponibili.

![](/help/assets/screen_shot_2018-01-12at113153.png)

* **Tipi** - Modalità di presentazione delle opzioni
   * **Caselle di controllo**
   * **Pulsanti di scelta**
   * **A discesa**
   * **Menu a discesa a selezione multipla**
* **Titolo** Titolo che verrà visualizzato come etichetta per le opzioni
* **Nome** Il nome del campo inviato con i dati del modulo
* **Origine** Dove sono definite le opzioni
   * **Locale** definito nel componente
      * Toccate o fate clic sul pulsante **Aggiungi** per aggiungere un valore, **Elimina** per rimuovere un valore
      * **Valore** Il valore salvato quando l&#39;opzione viene selezionata all&#39;invio del modulo
      * **Testo** Etichetta per l&#39;opzione visualizzata sul modulo
      * **Attivo** L&#39;opzione è contrassegnata come selezionata al caricamento del modulo
      * **Disattivato** L&#39;opzione non è selezionabile ma continua a essere visualizzata
      * **Elenco** Per le opzioni viene utilizzato un elenco statico definito altrove in AEM
         * **Elenco** Percorso dell’elenco statico in AEM
            * Utilizzare il pulsante Sfoglia per individuare la risorsa dell&#39;elenco
      * **Origine** dati Un&#39;origine dati viene utilizzata per le opzioni
         * **Origine** dati Tipo di risorsa dell&#39;origine dati
* **Messaggio** della Guida Un suggerimento per l&#39;utente di ciò che può essere immesso nel campo

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Opzioni modulo supporta AEM [Style System](/help/get-started/authoring.md#component-styling).
