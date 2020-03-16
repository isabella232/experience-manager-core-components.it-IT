---
title: Componente Pulsante Modulo
description: Il componente Principale Modulo nascosto consente di includere un campo nascosto in un modulo.
translation-type: tm+mt
source-git-commit: 95c0621f5423bfa515fe5e8b693e127ea56b4ae0

---


# Componente Pulsante Modulo {#form-button-component}

Il componente di base Pulsante Modulo del componente permette di includere un pulsante per attivare un’azione su una pagina.

## Utilizzo {#usage}

Il componente Pulsante Modulo componente di base consente di creare un campo pulsante, spesso per attivare l’invio del modulo e deve essere utilizzato insieme al componente [Contenitore](form-container.md)modulo.

Le proprietà del pulsante possono essere definite dall&#39;editor del contenuto nella finestra di dialogo [di](#configure-dialog)configurazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pulsante Modulo è v2, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-button-v1.md) | Compatibile | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Pulsante Modulo e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visitare la Libreria [](https://adobe.com/go/aem_cmp_library_form_button)Componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pulsante Modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_button_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all&#39;autore del contenuto di definire i parametri del pulsante.

### Scheda Proprietà {#properties-tab}

![](/help/assets/screen_shot_2018-01-12at120433.png)

* **Tipo**

   * **Pulsante**
   * **Invia**

* **Titolo** - Testo visualizzato sul pulsante

   * Se non ne è stato fornito nessuno, per impostazione predefinita viene utilizzato il tipo di pulsante

* **Nome** - Il nome del pulsante, inviato con i dati del modulo
* **Valore** - Il valore del pulsante, inviato con i dati del modulo

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Pulsante Modulo supporta AEM [Style System](/help/get-started/authoring.md#component-styling).
