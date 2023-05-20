---
title: Componente Visualizzatore PDF
description: Il componente Visualizzatore PDF consente la visualizzazione di un documento PDF.
role: Architect, Developer, Admin, User
exl-id: deb635f5-2b73-4e7a-9838-3a941e39e898
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 100%

---

# Componente Visualizzatore PDF {#pdf-viewer-component}

Il componente core Visualizzatore PDF consente di includere un documento PDF in una pagina.

## Utilizzo {#usage}

Il componente core Visualizzatore PDF incorpora un visualizzatore per visualizzare i file PDF memorizzati come risorse sulla pagina.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Visualizzatore PDF è la v1, introdotta con la versione 2.10.0 dei Componenti core a giugno 2020, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile  con<br>[versione 2.17.4](/help/versions.md) e precedenti | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Visualizzatore PDF e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_pdfviewer_it).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Visualizzatore PDF [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

>[!NOTE]
>
>Il componente Visualizzatore PDF utilizza [le API di Adobe Document Services](https://www.adobe.io/apis/documentcloud/dcsdk.html) e richiede all’amministratore di impostare una [configurazione in base al contesto](/help/developing/context-aware-configs.md) per utilizzare questi servizi. Per [informazioni dettagliate su questa configurazione](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config), vedi la documentazione tecnica del componente.

## Finestra di dialogo per configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuto di definire il visualizzatore e il suo comportamento e aspetto nei confronti di chi visita la pagina.

### Scheda Configurazione {#configuration-tab}

La scheda Configurazione consente all’autore di definire quale PDF visualizzare. Il percorso può essere definito come risorsa in AEM o come percorso assoluto di un’altra risorsa.

![Scheda Configurazione della finestra di dialogo per modifica del componente Visualizzatore PDF](/help/assets/pdf-viewer-edit-configuration.png)

### Scheda Personalizza {#customize-tab}

La scheda Personalizza consente all’autore di definire le opzioni disponibili per il lettore nel visualizzatore e come si deve presentare il visualizzatore.

![Scheda Personalizza della finestra di dialogo per modifica del componente Visualizzatore PDF](/help/assets/pdf-viewer-edit-customize.png)

Il numero di opzioni disponibili dipende dal **Tipo** selezionato.

* [Finestra intera](#full-window): l’area di visualizzazione occupa l’intera finestra del browser. Questa soluzione è ideale per applicazioni di storage e produttività.
* [Contenitore dimensionato](#sized-container): l’area di visualizzazione occupa l’intera finestra del browser. Questa soluzione è ideale per applicazioni di storage e produttività.
* [In linea](#in-line): tutte le pagine del PDF compaiono in linea in una pagina web. Questa funzione è particolarmente adatta per la lettura.

#### Finestra intera {#full-window}

L’area di visualizzazione occupa l’intera finestra del browser. Questa soluzione è ideale per applicazioni di storage e produttività.

![Scheda Personalizza con l’opzione Finestra intera nella finestra di dialogo per modifica del componente Visualizzatore PDF](/help/assets/pdf-viewer-edit-customize-full.png)

* **Modalità di visualizzazione predefinita**: il visualizzatore si adatta alla pagina in cui viene visualizzato
   * Adatta pagina
   * Adatta larghezza
* **Schermo intero**: se selezionata, il visualizzatore occuperà l’intera altezza/larghezza del riquadro di visualizzazione.
* **Strumenti di annotazione**: se selezionata, sono disponibili gli strumenti di annotazione.
* **Pannello a sinistra**: se selezionata, viene visualizzato il pannello a sinistra.
* **Scarica PDF**: se selezionata, viene visualizzato il pulsante Scarica.
* **Stampa PDF**: se selezionata, viene visualizzato il pulsante Stampa.
* **Controlli pagina**: consente di attivare o disattivare i controlli della pagina.
   * Àncora
   * Disancora

#### Contenitore dimensionato {#sized-container}

L’area di visualizzazione occupa l’intera finestra del browser. Questa soluzione è ideale per applicazioni di storage e produttività.

![Scheda Personalizza con l’opzione Contenitore selezionato nella finestra di dialogo per modifica del componente Visualizzatore PDF](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **Schermo intero**: se selezionata, il visualizzatore occuperà l’intera altezza/larghezza del riquadro di visualizzazione.
* **Scarica PDF**: se selezionata, viene visualizzato il pulsante Scarica.
* **Stampa PDF**: se selezionata, viene visualizzato il pulsante Stampa.
* **Controlli pagina**: consente di attivare o disattivare i controlli della pagina.
   * Àncora
   * Disancora

#### In linea {#in-line}

Tutte le pagine del PDF compaiono in linea in una pagina web. Questa funzione è particolarmente adatta per la lettura.

![Scheda Personalizza con l’opzione Contenitore selezionato nella finestra di dialogo per modifica del componente Visualizzatore PDF](/help/assets/pdf-viewer-edit-customize-inline.png)

* **Scarica PDF**: se selezionata, viene visualizzato il pulsante Scarica.
* **Stampa PDF**: se selezionata, viene visualizzato il pulsante Stampa.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione non è disponibile per il componente Visualizzatore PDF.
