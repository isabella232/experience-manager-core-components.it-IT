---
title: Componente Pulsante
description: Il componente core Pulsante consente di creare e visualizzare un pulsante.
role: Architect, Developer, Admin, User
exl-id: e17efd1d-90d4-497a-9e7d-45934d81bc28
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '451'
ht-degree: 100%

---

# Componente Pulsante{#button-component}

Il componente core Pulsante consente di configurare e visualizzare un pulsante su una pagina.

## Utilizzo {#usage}

Il componente core Pulsante consente di includere un pulsante in una pagina.

* Le proprietà del Pulsante possono essere selezionate nella [finestra di dialogo per configurazione](#configure-dialog).
* Gli stili del componente Pulsante possono essere definiti nella [finestra di dialogo per progettazione](#design-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pulsante è la v1, introdotta con la versione 2.5.0 dei Componenti core a giugno 2019, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Pulsante e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_button).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pulsante [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_button_v1).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuto di definire l’elemento Pulsante e il suo comportamento e aspetto nei confronti di chi visita la pagina.

### Scheda Proprietà {#properties-tab}

![Scheda Proprietà della finestra di dialogo per modifica del componente Pulsante](/help/assets/button-edit-properties.png)

* **Testo**: il testo da visualizzare sul pulsante
* **Collegamento**: il collegamento a una pagina di contenuto in AEM, una risorsa esterna o un ancoraggio
   * Utilizza la **finestra di dialogo per selezione** per scegliere un percorso all’interno di AEM.
* **Icona**: identificatore per la visualizzazione di un’icona nel pulsante
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità della finestra di dialogo per modifica del componente Pulsante](/help/assets/button-edit-accessibility.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette di [accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente.

* **Etichetta**: il valore di un attributo dell’etichetta ARIA del componente

## Finestra di dialogo per progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Pulsante supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

## Adobe Client Data Layer {#data-layer}

Il componente Pulsante supporta [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
