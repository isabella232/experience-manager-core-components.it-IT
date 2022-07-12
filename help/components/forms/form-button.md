---
title: Componente Pulsante modulo
description: Il componente core Campo nascosto modulo consente di includere un campo nascosto in un modulo.
role: Architect, Developer, Admin, User
exl-id: 1e5cff43-57db-4bfc-b2d2-23307eaf5eb3
source-git-commit: 16930ccaa281f9d9c4ddbb890d4222e128557580
workflow-type: ht
source-wordcount: '417'
ht-degree: 100%

---

# Componente Pulsante modulo {#form-button-component}

Il componente core Pulsante modulo consente di includere un pulsante per attivare un’azione su una pagina.

## Utilizzo {#usage}

Il componente core Pulsante modulo consente la creazione di un campo pulsante, spesso per attivare l’invio del modulo, che deve essere utilizzato insieme al componente [Contenitore modulo](form-container.md).

Le proprietà del pulsante possono essere definite tramite l’editor di contenuto nella [finestra di dialogo per configurazione](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pulsante modulo la v2, introdotta con la versione 2.0.0 dei Componenti core a gennaio 2018, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile  con<br>[versione 2.17.4](/help/versions.md) e precedenti | Compatibile | Compatibile |
| [v1](/help/components/v1/form-button-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Pulsante modulo e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_form_button_it).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pulsante modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_button_v2_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuto di definire i parametri del pulsante.

### Scheda Proprietà {#properties-tab}

![Finestra di dialogo per modifica del componente Pulsante modulo](/help/assets/form-button-edit.png)

* **Tipo**

   * **Pulsante**
   * **Invia**

* **Titolo**: il testo visualizzato sul pulsante

   * Se non viene specificato alcun testo, viene utilizzato automaticamente il tipo di pulsante

* **Nome**: il nome del pulsante, che viene inviato con i dati del modulo
* **Valore**: il valore del pulsante, che viene inviato con i dati del modulo

* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

## Finestra di dialogo per progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Pulsante modulo supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
