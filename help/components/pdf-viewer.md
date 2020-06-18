---
title: Componente visualizzatore PDF
description: Il componente Visualizzatore PDF consente la visualizzazione di un documento PDF.
translation-type: tm+mt
source-git-commit: 0df759a020020c21d776eb8f45d40cb7aff45cea
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 2%

---


# Componente visualizzatore PDF {#pdf-viewer-component}


Il componente Visualizzatore PDF per componenti core consente di includere un documento PDF in una pagina.

## Utilizzo {#usage}

Il componente Visualizzatore PDF per componenti core incorpora un visualizzatore per visualizzare i file PDF memorizzati come risorse sulla pagina.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente visualizzatore PDF è v1, introdotto con la release 2.10.0 dei componenti core nel giugno 2020, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente visualizzatore PDF e per vedere alcuni esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visitare la Libreria [](https://adobe.com/go/aem_cmp_library_pdf_viewer)componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente visualizzatore PDF [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_pdf-viewer_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il visualizzatore e il suo funzionamento e la sua visualizzazione sulla pagina da parte di un visitatore.

### Configuration Tab {#configuration-tab}

La scheda Configurazione consente all’autore di definire il PDF da visualizzare. Il percorso può essere definito come una risorsa in AEM o come percorso assoluto di un’altra risorsa.

![Scheda Configurazione della finestra di dialogo di modifica del componente Visualizzatore PDF](/help/assets/pdf-viewer-edit-configuration.png)

### Personalizza, scheda {#customize-tab}

La scheda Personalizza consente all’autore di definire le opzioni disponibili nel visualizzatore per il lettore e la modalità di presentazione del visualizzatore.

![Scheda Personalizza della finestra di dialogo di modifica del componente Visualizzatore PDF](/help/assets/pdf-viewer-edit-customize.png)

Il numero di opzioni disponibili dipende dal **tipo** selezionato.

* [Finestra](#full-window) completa - L&#39;area di visualizzazione viene riprodotta nel browser completo. Questa funzione è ideale per applicazioni di storage e produttività.
* [Contenitore](#sized-container) dimensioni - L&#39;area di visualizzazione viene riprodotta nel browser completo. Questa funzione è ideale per applicazioni di storage e produttività.
* [In-Line](#in-line) - Viene eseguito il rendering di tutte le pagine PDF allineate all’interno di una pagina Web. Questa funzione è ideale per le applicazioni di lettura.

#### Finestra completa {#full-window}

L’area di visualizzazione viene riprodotta nel browser completo. Questa funzione è ideale per applicazioni di storage e produttività.

![Personalizza scheda finestra completa opzione della finestra di dialogo di modifica del componente Visualizzatore PDF](/help/assets/pdf-viewer-edit-customize-full.png)

* **Modalità** di visualizzazione predefinita: l&#39;adattamento del visualizzatore alla pagina in cui è visualizzato
   * Adatta a pagina
   * Adatta a larghezza
* **Schermo** intero: se attivato, il visualizzatore occupa l&#39;intera altezza/larghezza della finestra.
* **Strumenti** di annotazione - Quando abilitata, sono disponibili gli strumenti di annotazione.
* **Pannello** mano sinistra - Se attivato, viene visualizzato il pannello a sinistra.
* **Scarica PDF** - Quando attivato, viene visualizzato il pulsante di download.
* **Stampa PDF** - Se abilitata, viene visualizzato il pulsante Stampa.
* **Controlli** pagina - Attiva/disattiva il comportamento dei controlli di pagina.
   * Aggancia
   * Sgancia

#### Contenitore dimensione {#sized-container}

L’area di visualizzazione viene riprodotta nel browser completo. Questa funzione è ideale per applicazioni di storage e produttività.

![Personalizzare l’opzione di un contenitore di dimensioni tabulazione della finestra di dialogo di modifica del componente visualizzatore PDF](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **Schermo** intero: se attivato, il visualizzatore occupa l&#39;intera altezza/larghezza della finestra.
* **Scarica PDF** - Quando attivato, viene visualizzato il pulsante di download.
* **Stampa PDF** - Se abilitata, viene visualizzato il pulsante Stampa.
* **Controlli** pagina - Attiva/disattiva il comportamento dei controlli di pagina.
   * Aggancia
   * Sgancia

#### In linea {#in-line}

Viene eseguito il rendering di tutte le pagine PDF allineate all’interno di una pagina Web. Questa funzione è ideale per le applicazioni di lettura.

![Personalizzare l’opzione di un contenitore di dimensioni tabulazione della finestra di dialogo di modifica del componente visualizzatore PDF](/help/assets/pdf-viewer-edit-customize-inline.png)

* **Scarica PDF** - Quando attivato, viene visualizzato il pulsante di download.
* **Stampa PDF** - Se abilitata, viene visualizzato il pulsante Stampa.

## Finestra di dialogo Progettazione {#design-dialog}

Nessuna finestra di dialogo Progettazione per il componente Visualizzatore PDF.
