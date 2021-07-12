---
title: Componente visualizzatore PDF
description: Il componente Visualizzatore PDF consente la visualizzazione di un documento PDF.
role: Architect, Developer, Admin, User
exl-id: deb635f5-2b73-4e7a-9838-3a941e39e898
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 3%

---

# Componente visualizzatore PDF {#pdf-viewer-component}

Il componente Visualizzatore PDF per componenti core consente di includere un documento PDF in una pagina.

## Utilizzo {#usage}

Il componente Visualizzatore PDF dei componenti core incorpora un visualizzatore per visualizzare i file PDF archiviati come risorse sulla pagina.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente visualizzatore PDF è la v1, introdotta con la versione 2.10.0 dei componenti core a giugno 2020, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente visualizzatore PDF e dell’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_pdfviewer).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente visualizzatore PDF [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

>[!NOTE]
>
>Il componente visualizzatore PDF sfrutta [le API di Adobe Document Services](https://www.adobe.io/apis/documentcloud/dcsdk.html) e richiede all’amministratore di configurare una [configurazione in base al contesto](/help/developing/context-aware-configs.md) per utilizzare questi servizi. Per informazioni dettagliate su questa configurazione, consulta la documentazione tecnica del componente.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)[

## Finestra di dialogo Configura {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il visualizzatore e come si comporterà e apparirà per un visitatore alla pagina.

### Scheda Configurazione {#configuration-tab}

La scheda Configurazione consente all’autore di definire quale PDF visualizzare. Il percorso può essere definito come risorsa in AEM o come percorso assoluto di un’altra risorsa.

![Scheda Configurazione della finestra di dialogo di modifica del componente Visualizzatore PDF](/help/assets/pdf-viewer-edit-configuration.png)

### Scheda Personalizza {#customize-tab}

La scheda Personalizza consente all’autore di definire le opzioni disponibili nel visualizzatore per il lettore e come deve essere presentato il visualizzatore.

![Scheda Personalizza della finestra di dialogo di modifica del componente Visualizzatore PDF](/help/assets/pdf-viewer-edit-customize.png)

Il numero di opzioni disponibili dipende dal **Tipo** selezionato.

* [Finestra](#full-window)  completa - Viene eseguito il rendering dell&#39;area di visualizzazione nel browser completo. Questa soluzione è ideale per applicazioni di storage e produttività.
* [Contenitore dimensioni](#sized-container) : l’area di visualizzazione viene sottoposta a rendering nel browser completo. Questa soluzione è ideale per applicazioni di storage e produttività.
* [In-Line](#in-line) : tutte le pagine PDF sottoposte a rendering in linea all’interno di una pagina web. Questa funzione è particolarmente adatta per le applicazioni di lettura.

#### Finestra intera {#full-window}

Viene eseguito il rendering dell’area di visualizzazione nel browser completo. Questa soluzione è ideale per applicazioni di storage e produttività.

![Opzione Personalizza scheda finestra completa della finestra di dialogo di modifica del componente Visualizzatore PDF](/help/assets/pdf-viewer-edit-customize-full.png)

* **Modalità di visualizzazione predefinita** : adattamento del visualizzatore alla pagina in cui viene visualizzato
   * Adatta a pagina
   * Adatta a larghezza
* **Schermo intero** : se attivato, il visualizzatore occuperà l’altezza/larghezza completa del riquadro di visualizzazione.
* **Strumenti di annotazione** : se attivata, sono disponibili gli strumenti di annotazione.
* **Pannello a sinistra** : se attivato, viene visualizzato il pannello a sinistra.
* **Scarica PDF**  - Quando abilitato, viene visualizzato il pulsante di download.
* **Stampa PDF** : se attivato, viene visualizzato il pulsante Stampa.
* **Controlli pagina** : consente di attivare o disattivare il funzionamento dei controlli pagina.
   * Àncora
   * Disancora

#### Contenitore dimensionato {#sized-container}

Viene eseguito il rendering dell’area di visualizzazione nel browser completo. Questa soluzione è ideale per applicazioni di storage e produttività.

![Opzione Personalizza contenitore di dimensioni scheda della finestra di dialogo di modifica del componente visualizzatore PDF](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **Schermo intero** : se attivato, il visualizzatore occuperà l’altezza/larghezza completa del riquadro di visualizzazione.
* **Scarica PDF**  - Quando abilitato, viene visualizzato il pulsante di download.
* **Stampa PDF** : se attivato, viene visualizzato il pulsante Stampa.
* **Controlli pagina** : consente di attivare o disattivare il funzionamento dei controlli pagina.
   * Àncora
   * Disancora

#### In linea {#in-line}

Viene eseguito il rendering di tutte le pagine PDF allineate all’interno di una pagina web. Questa funzione è particolarmente adatta per le applicazioni di lettura.

![Opzione Personalizza contenitore di dimensioni scheda della finestra di dialogo di modifica del componente visualizzatore PDF](/help/assets/pdf-viewer-edit-customize-inline.png)

* **Scarica PDF**  - Quando abilitato, viene visualizzato il pulsante di download.
* **Stampa PDF** : se attivato, viene visualizzato il pulsante Stampa.

## Finestra di dialogo Progettazione {#design-dialog}

Non è disponibile una finestra di dialogo di progettazione per il componente visualizzatore PDF.
