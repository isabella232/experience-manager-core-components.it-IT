---
title: Componente nascosto per modulo
description: Il componente di base Nascosto per modulo consente la visualizzazione di un campo nascosto.
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 3%

---


# Componente nascosto per modulo{#form-hidden-component}

Il componente di base Nascosto per modulo consente la visualizzazione di un campo nascosto.

## Utilizzo {#usage}

Il componente di base Nascosto per modulo consente la creazione di campi nascosti per riportare in AEM le informazioni sulla pagina corrente e deve essere utilizzato insieme al [componente contenitore modulo](form-container.md).

Le proprietà del campo possono essere definite dall&#39;editor dei contenuti nella finestra di dialogo [configura](form-hidden.md).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Nascosto per modulo è v2, introdotta con la versione 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-hidden-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione e dell’output HTML e JSON del componente nascosto per modulo, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_form_hidden).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Nascosto per modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_hidden_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire i parametri del campo nascosto.

![Finestra di dialogo per la modifica nascosta del modulo](/help/assets/form-hidden-edit.png)

* **Nome** : il nome del campo che viene inviato insieme ai dati del modulo
* **Valore** : valore del campo, inviato insieme ai dati del modulo
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

Poiché il componente Nascosto per modulo di solito non dispone di attributi visibili, il segnaposto del componente nell’editor visualizza i valori dei campi **Nome** e **Valore** se assegnati per aiutare l’autore a identificare il componente Nascosto per modulo appropriato.

![Esempio di componente nascosto per modulo](/help/assets/form-hidden-example.png)

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Nascosto per modulo supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).
