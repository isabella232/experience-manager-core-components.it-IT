---
title: Componente pulsante modulo
description: Il componente di base Nascosto per modulo consente di includere un campo nascosto in un modulo.
role: Architetto, Sviluppatore, Amministratore, Business Practices
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 4%

---


# Componente pulsante modulo {#form-button-component}

Il componente per pulsante modulo del componente core consente di includere un pulsante per attivare un’azione su una pagina.

## Utilizzo {#usage}

Il componente Pulsante modulo del componente core consente la creazione di un campo pulsante, spesso per attivare l’invio del modulo e deve essere utilizzato insieme al componente [Contenitore modulo](form-container.md).

Le proprietà del pulsante possono essere definite dall&#39;editor dei contenuti nella finestra di dialogo [configura](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pulsante modulo è v2, introdotta con la versione 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-button-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione e dell’output HTML e JSON del componente Pulsante modulo, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_form_button).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pulsante modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_button_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire i parametri del pulsante.

### Scheda Proprietà {#properties-tab}

![Finestra di dialogo di modifica del componente Pulsante modulo](/help/assets/form-button-edit.png)

* **Tipo**

   * **Pulsante**
   * **Invia**

* **Titolo** : il testo visualizzato sul pulsante

   * Se non ne è stato fornito nessuno, viene impostato automaticamente sul tipo di pulsante

* **Nome** : il nome del pulsante che viene inviato insieme ai dati del modulo
* **Valore**  - Il valore del pulsante, che viene inviato insieme ai dati del modulo

* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Pulsante modulo supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).
