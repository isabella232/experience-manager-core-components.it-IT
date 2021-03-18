---
title: Componente Frammento esperienza
description: Il componente Frammento esperienza consente all’autore del contenuto di aggiungere a una pagina una variante del frammento esperienza.
role: Architetto, Sviluppatore, Amministratore, Business Practices
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 1%

---


# Componente Frammento esperienza{#experience-fragment-component}

Il componente Frammento esperienza del componente di base consente all’autore del contenuto di inserire una variante del frammento di esperienza in una pagina e al contempo di supportare una struttura del sito localizzata.

## Utilizzo {#usage}

Il componente Frammento esperienza del componente di base consente all’autore del contenuto di selezionare tra le varianti di frammento di esperienza esistenti e inserirne una nella pagina del contenuto. Il componente Frammento esperienza supporta anche una struttura del sito localizzata.

* Le proprietà del componente possono essere definite nella finestra di dialogo [configura](#configure-dialog).
* I valori predefiniti per il componente quando lo si aggiunge a una pagina possono essere definiti nella finestra di dialogo [progettazione](#design-dialog).

## Supporto per la struttura del sito localizzata {#localized-site-structure}

Il componente Frammento esperienza si adatta alle strutture del sito localizzate ed esegue il rendering del frammento esperienza appropriato in base alla localizzazione della pagina. A questo scopo, il frammento di esperienza deve soddisfare le seguenti condizioni.

* Il componente Frammento esperienza viene aggiunto a un modello.
* Tale modello viene utilizzato per creare una nuova pagina di contenuto che fa parte di una struttura localizzata sotto `/content/<site>`.
* Il frammento di esperienza a cui si fa riferimento in una pagina di contenuto fa parte di una struttura di frammento di esperienza localizzata sotto `/content/experience-fragments` che segue gli stessi pattern del sito sotto `/content/<site>`, incluso l’utilizzo degli stessi nomi di componente.

In questo caso, come parte del modello, verrà eseguito il rendering del frammento con la stessa localizzazione (lingua, blueprint o Live Copy) della pagina corrente.

Questo comportamento è limitato ai componenti Frammento esperienza aggiunti ai modelli. I componenti Frammento esperienza aggiunti alle singole pagine di contenuto renderanno le rappresentazioni esatte dei frammenti di esperienza configurate all’interno del componente.

* Per un esempio del funzionamento delle funzioni di localizzazione del componente Frammento esperienza, consulta [la sezione seguente](#example).
* Per un esempio del funzionamento congiunto delle funzioni di localizzazione dei componenti core, consulta la pagina [Funzioni di localizzazione dei componenti core](/help/get-started/localization.md) .

### Esempio {#example}

Supponiamo che il contenuto sia simile al seguente:

```
/content
+-- experience-fragments
   \-- wknd
      +-- language-masters
      +-- us
         +-- en
            +-- footerTextXf
            \-- headerTextXf
         \-- es
            +-- footerTextXf
            \-- headerTextXf
      \-- ch
         +-- de
            +-- footerTextXf
            \-- headerTextXf
         +-- fr
            +-- footerTextXf
            \-- headerTextXf
         \-- it
            +-- footerTextXf
            \-- headerTextXf
+-- wknd
   +-- language-masters
   +-- us
      +-- en
      \-- es
   +-- ch
      +-- de
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

La struttura seguente `/content/experience-fragments/wknd` rispecchia la struttura di `/content/wknd`.

In questo caso, se il componente Frammento esperienza `/content/experience-fragments/wknd/us/en/footerTextXf` è posizionato su un modello, le pagine localizzate create in base a tale modello renderanno automaticamente il frammento di esperienza localizzato corrispondente alla pagina del contenuto localizzato.

Quindi, se passi a una pagina di contenuto sotto `/content/wknd/ch/de` che utilizza lo stesso modello, viene eseguito il rendering di `/content/experience-fragments/wknd/ch/de/footerTextXf` invece di `/content/experience-fragments/wknd/us/en/footerTextXf`.

### Fallback {#fallback}

Il componente Frammento esperienza tenta di trovare un componente localizzato corrispondente nell’ordine seguente.

1. Prima cerca di trovare una radice linguistica.
1. Se non viene trovato, cerca di trovare un modello.
1. Se non viene trovato, cerca di trovare una Live Copy.
1. Se non viene trovato, per impostazione predefinita viene visualizzato il frammento di esperienza configurato nel componente.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento esperienza è la v1, introdotta con la versione 2.6.0 dei componenti core a settembre 2019, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per provare il componente Frammento esperienza e visualizzare esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la [Libreria di componenti](https://adobe.com/go/aem_cmp_library_xf) .

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Frammento esperienza [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_xf_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di selezionare la variante del frammento di esperienza da eseguire sulla pagina.

![Finestra di dialogo di modifica del componente Frammento esperienza](/help/assets/experience-fragment-edit.png)

Utilizza il pulsante **Apri finestra di dialogo di selezione** per aprire il selettore dei componenti e scegliere la variante del componente del frammento di esperienza da aggiungere alla pagina del contenuto.

Se aggiungi il componente Frammento esperienza a un modello, noterai che sarà localizzato automaticamente a condizione che i Frammenti esperienza siano localizzati, in modo che il rendering sulla pagina possa variare dal componente selezionato in modo esplicito. [Per ulteriori informazioni, consulta l’esempio ](#example) precedente.

Puoi anche definire un **ID**. Questa opzione consente di controllare l&#39;identificatore univoco del componente nell&#39;HTML e nel [Livello dati](/help/developing/data-layer/overview.md).

* Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
* Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
* La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore del contenuto che utilizza il componente Frammento esperienza e le impostazioni predefinite al momento del posizionamento del componente Frammento esperienza.

### Scheda Stili {#styles-tab}

Il componente Frammento esperienza supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).
