---
title: Componente Campo nascosto modulo
description: Il componente core Campo nascosto modulo consente la visualizzazione di un campo nascosto di un modulo.
role: Architect, Developer, Admin, User
exl-id: 0364cd3b-3c09-46db-9392-a67e3f9ea7a5
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: ht
source-wordcount: '432'
ht-degree: 100%

---

# Componente Campo nascosto modulo {#form-hidden-component}

Il componente core Campo nascosto modulo consente la visualizzazione di un campo nascosto di un modulo.

## Utilizzo {#usage}

Il componente core Campo nascosto modulo consente la creazione di campi nascosti per restituire informazioni sulla pagina corrente ad AEM e deve essere utilizzato insieme al [componente Contenitore modulo](form-container.md).

Le proprietà del campo possono essere definite tramite l’editor di contenuto nella [finestra di dialogo per configurazione](form-hidden.md).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Campo nascosto modulo è la v2, introdotta con la versione 2.0.0 dei Componenti core a gennaio 2018, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile con<br>[versione 2.17.4](/help/versions.md) e precedenti | Compatibile | Compatibile |
| [v1](/help/components/v1/form-hidden-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Campo nascosto modulo e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_form_hidden_it).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Campo nascosto modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_hidden_v2_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuto di definire i parametri del campo nascosto.

![Finestra di dialogo per modifica del componente Campo nascosto modulo](/help/assets/form-hidden-edit.png)

* **Nome**: il nome del campo, che viene inviato con i dati del modulo
* **Valore**: il valore del campo, che viene inviato con i dati del modulo
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

Poiché il componente Campo nascosto modulo di solito non dispone di attributi visibili, il segnaposto del componente nell’editor visualizza i valori dei campi **Nome** e **Valore**, se assegnati per aiutare l’autore a identificare il componente Campo nascosto modulo appropriato.

![Esempio di componente Campo nascosto modulo](/help/assets/form-hidden-example.png)

## Finestra di dialogo per progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Campo nascosto modulo supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
