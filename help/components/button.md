---
title: Componente pulsante
description: Il componente Pulsante del componente core consente di creare e visualizzare un pulsante.
role: Architect, Developer, Admin, User
exl-id: e17efd1d-90d4-497a-9e7d-45934d81bc28
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 3%

---

# Componente pulsante{#button-component}

Il componente Pulsante del componente core consente di configurare e visualizzare un pulsante su una pagina.

## Utilizzo {#usage}

Il componente Pulsante del componente core consente di includere un pulsante in una pagina.

* Le proprietà del pulsante possono essere selezionate nella finestra di dialogo [configura](#configure-dialog).
* Gli stili per il componente pulsante possono essere definiti nella finestra di dialogo di progettazione [a1/>.](#design-dialog)

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente pulsante è la v1, introdotta con la versione 2.5.0 dei componenti core a giugno 2019, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione e dell’output HTML e JSON del componente Pulsante, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_button) .

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pulsante [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_button_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Configura {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il pulsante e il suo comportamento e la sua visualizzazione sulla pagina da parte del visitatore.

### Scheda Proprietà {#properties-tab}

![Scheda Proprietà della finestra di dialogo di modifica del componente Pulsante](/help/assets/button-edit-properties.png)

* **Testo** : testo da visualizzare sul pulsante
* **Collegamento** : collegamento a una pagina di contenuto in AEM, una risorsa esterna o un ancoraggio
   * Utilizza la finestra di dialogo **Selezione** per scegliere un percorso all&#39;interno di AEM.
* **Icona** : identificatore per la visualizzazione di un’icona nel pulsante
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità della finestra di dialogo di modifica del componente Pulsante](/help/assets/button-edit-accessibility.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette [Accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente.

* **Etichetta**  - Valore di un attributo dell’etichetta ARIA per il componente

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Pulsante supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

## Livello dati client di Adobe {#data-layer}

Il componente Pulsante supporta il [Livello dati client Adobe.](/help/developing/data-layer/overview.md)
