---
title: Componente Pulsante Modulo
description: Il componente Principale Modulo nascosto consente di includere un campo nascosto in un modulo.
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Componente Pulsante Modulo {#form-button-component}

Il componente di base Pulsante Modulo del componente permette di includere un pulsante per attivare un’azione su una pagina.

## Utilizzo {#usage}

Il componente Pulsante Modulo componente di base consente di creare un campo pulsante, spesso per attivare l’invio del modulo e deve essere utilizzato insieme al componente [Contenitore](form-container.md)modulo.

Le proprietà del pulsante possono essere definite dall&#39;editor del contenuto nella finestra di dialogo [di](#configure-dialog)configurazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pulsante Modulo è v2, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-button-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Pulsante Modulo e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visitare la Libreria [](https://adobe.com/go/aem_cmp_library_form_button)Componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pulsante Modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_button_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all&#39;autore del contenuto di definire i parametri del pulsante.

### Scheda Proprietà {#properties-tab}

![Finestra di dialogo di modifica del componente Pulsante Modulo](/help/assets/form-button-edit.png)

* **Tipo**

   * **Pulsante**
   * **Invia**

* **Titolo** - Testo visualizzato sul pulsante

   * Se non ne è stato fornito nessuno, per impostazione predefinita viene utilizzato il tipo di pulsante

* **Nome** - Il nome del pulsante, inviato con i dati del modulo
* **Valore** - Il valore del pulsante, inviato con i dati del modulo

* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Pulsante Modulo supporta AEM [Style System](/help/get-started/authoring.md#component-styling).
