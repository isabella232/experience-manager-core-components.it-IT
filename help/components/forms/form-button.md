---
title: Componente Pulsante Modulo
description: Il componente Principale Modulo nascosto consente di includere un campo nascosto in un modulo.
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 4%

---


# Componente pulsante modulo {#form-button-component}

Il componente di base Pulsante Modulo del componente permette di includere un pulsante per attivare un’azione su una pagina.

## Utilizzo {#usage}

Il componente Pulsante Modulo componente di base consente la creazione di un campo pulsante, spesso per attivare l’invio del modulo e deve essere utilizzato insieme al componente [Contenitore modulo](form-container.md).

Le proprietà del pulsante possono essere definite dall&#39;editor del contenuto nella finestra di dialogo di [configurazione](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pulsante Modulo è v2, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-button-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente Pulsante modulo e per vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library_form_button).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pulsante Modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_button_v2).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all&#39;autore del contenuto di definire i parametri del pulsante.

### Scheda Proprietà {#properties-tab}

![Finestra di dialogo di modifica del componente Pulsante Modulo](/help/assets/form-button-edit.png)

* **Tipo**

   * **Pulsante**
   * **Invia**

* **Titolo**  - Testo visualizzato sul pulsante

   * Se non ne è stato fornito nessuno, per impostazione predefinita viene utilizzato il tipo di pulsante

* **Nome** : il nome del pulsante che viene inviato insieme ai dati del modulo
* **Valore**  - Il valore del pulsante, inviato con i dati del modulo

* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Pulsante Modulo supporta il AEM [Sistema di stile](/help/get-started/authoring.md#component-styling).
