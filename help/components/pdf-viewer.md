---
title: Componente visualizzatore PDF
description: Il componente Visualizzatore PDF consente la visualizzazione di un documento PDF.
translation-type: tm+mt
source-git-commit: 24a810ff634f8846881dfa0095e879476d0f16f0
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 3%

---


# Componente visualizzatore PDF {#pdf-viewer-component}

Il componente Visualizzatore PDF per componenti core consente di includere un documento PDF in una pagina.

## Utilizzo {#usage}

Il componente Visualizzatore PDF per componenti core incorpora un visualizzatore per visualizzare i file PDF memorizzati come risorse sulla pagina.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente visualizzatore PDF è v1, introdotto con la release 2.10.0 dei componenti core nel giugno 2020, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente visualizzatore PDF e per vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library_pdfviewer).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente visualizzatore PDF [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

>[!NOTE]
>
>Il componente visualizzatore PDF utilizza [ API di Document Services](https://www.adobe.io/apis/documentcloud/dcsdk.html) e richiede all&#39;amministratore di configurare una [configurazione sensibile al contesto](/help/developing/context-aware-configs.md) per l&#39;utilizzo di tali servizi. Per informazioni dettagliate su questa configurazione, consultare la documentazione tecnica del componente.[](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il visualizzatore e il suo funzionamento e la sua visualizzazione sulla pagina da parte di un visitatore.

### Scheda Configurazione {#configuration-tab}

La scheda Configurazione consente all’autore di definire il PDF da visualizzare. Il percorso può essere definito come una risorsa in AEM o come percorso assoluto verso un’altra risorsa.

![Scheda Configurazione della finestra di dialogo di modifica del componente Visualizzatore PDF](/help/assets/pdf-viewer-edit-configuration.png)

### Personalizza scheda {#customize-tab}

La scheda Personalizza consente all’autore di definire le opzioni disponibili nel visualizzatore per il lettore e la modalità di presentazione del visualizzatore.

![Scheda Personalizza della finestra di dialogo di modifica del componente Visualizzatore PDF](/help/assets/pdf-viewer-edit-customize.png)

Il numero di opzioni disponibili dipende dal **Tipo** selezionato.

* [Finestra](#full-window)  completa - L&#39;area di visualizzazione viene riprodotta nel browser completo. Questa funzione è ideale per applicazioni di storage e produttività.
* [Contenitore](#sized-container)  dimensioni: l&#39;area di visualizzazione viene riprodotta nel browser completo. Questa funzione è ideale per applicazioni di storage e produttività.
* [In-Line](#in-line)  - Viene eseguito il rendering di tutte le pagine PDF allineate all’interno di una pagina Web. Questa funzione è ideale per le applicazioni di lettura.

#### Finestra intera {#full-window}

L’area di visualizzazione viene riprodotta nel browser completo. Questa funzione è ideale per applicazioni di storage e produttività.

![Personalizza scheda finestra completa opzione della finestra di dialogo di modifica del componente Visualizzatore PDF](/help/assets/pdf-viewer-edit-customize-full.png)

* **Modalità**  di visualizzazione predefinita: adattamento del visualizzatore alla pagina in cui è visualizzato
   * Adatta a pagina
   * Adatta a larghezza
* **Schermo**  intero: se attivato, il visualizzatore occupa l&#39;intera altezza/larghezza della finestra.
* **Strumenti**  di annotazione: se abilitata, sono disponibili gli strumenti di annotazione.
* **Pannello**  mano sinistra - Se attivato, viene visualizzato il pannello a sinistra.
* **Scarica PDF**  - Quando attivato, viene visualizzato il pulsante di download.
* **Stampa PDF**  - Se abilitata, viene visualizzato il pulsante Stampa.
* **Controlli**  pagina - Attiva o disattiva il funzionamento dei controlli di pagina.
   * Àncora
   * Disancora

#### Contenitore dimensionato {#sized-container}

L’area di visualizzazione viene riprodotta nel browser completo. Questa funzione è ideale per applicazioni di storage e produttività.

![Personalizzare l’opzione di un contenitore di dimensioni tabulazione della finestra di dialogo di modifica del componente visualizzatore PDF](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **Schermo**  intero: se attivato, il visualizzatore occupa l&#39;intera altezza/larghezza della finestra.
* **Scarica PDF**  - Quando attivato, viene visualizzato il pulsante di download.
* **Stampa PDF**  - Se abilitata, viene visualizzato il pulsante Stampa.
* **Controlli**  pagina - Attiva o disattiva il funzionamento dei controlli di pagina.
   * Àncora
   * Disancora

#### In linea {#in-line}

Viene eseguito il rendering di tutte le pagine PDF allineate all’interno di una pagina Web. Questa funzione è ideale per le applicazioni di lettura.

![Personalizzare l’opzione di un contenitore di dimensioni tabulazione della finestra di dialogo di modifica del componente visualizzatore PDF](/help/assets/pdf-viewer-edit-customize-inline.png)

* **Scarica PDF**  - Quando attivato, viene visualizzato il pulsante di download.
* **Stampa PDF**  - Se abilitata, viene visualizzato il pulsante Stampa.

## Finestra di dialogo Progettazione {#design-dialog}

Nessuna finestra di dialogo Progettazione per il componente Visualizzatore PDF.
