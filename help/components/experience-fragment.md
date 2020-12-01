---
title: Componente frammento esperienza
description: Il componente Frammento esperienza consente all’autore del contenuto di aggiungere a una pagina una variante di frammento esperienza.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 1%

---


# Componente frammento esperienza{#experience-fragment-component}

Il componente di base Frammento esperienza del componente consente all’autore del contenuto di inserire una variante del frammento esperienza in una pagina, mentre supporta una struttura del sito localizzata.

## Utilizzo {#usage}

Il componente di base Frammento esperienza del componente permette all’autore del contenuto di selezionare tra le varianti di frammento esperienza esistenti e di inserirne una nella pagina del contenuto. Il componente Frammento esperienza supporta anche una struttura del sito localizzata.

* Le proprietà del componente possono essere definite nella finestra di dialogo di [configurazione](#configure-dialog).
* I valori predefiniti per il componente quando viene aggiunto a una pagina possono essere definiti nella finestra di dialogo di progettazione [a1/>.](#design-dialog)

## Supporto struttura sito localizzata {#localized-site-structure}

Il componente Frammento esperienza si adatta alle strutture del sito localizzate ed esegue il rendering del frammento esperienza appropriato in base alla localizzazione della pagina. A tal fine, il frammento di esperienza deve soddisfare le seguenti condizioni.

* Il componente Frammento esperienza viene aggiunto a un modello.
* Tale modello viene utilizzato per creare una nuova pagina di contenuto che fa parte di una struttura localizzata sotto `/content/<site>`.
* Il frammento esperienza a cui si fa riferimento in una pagina di contenuto fa parte di una struttura di frammento esperienza localizzata sotto `/content/experience-fragments` che segue gli stessi pattern del sito sotto `/content/<site>`, incluso l&#39;utilizzo degli stessi nomi di componente.

In questo caso, il frammento con la stessa localizzazione (lingua, blueprint o Live Copy) della pagina corrente verrà rappresentato come parte del modello.

Questo comportamento è limitato ai componenti frammento esperienza aggiunti ai modelli. Frammenti esperienza I componenti aggiunti alle singole pagine di contenuto renderanno effettive le rappresentazioni dei frammenti esperienza configurate all’interno del componente.

* Per un esempio del funzionamento delle funzioni di localizzazione del componente Frammento esperienza, consultate la sezione [sotto](#example).
* Per un esempio di come le funzioni di localizzazione dei componenti core funzionano insieme, consultate la pagina [Localization Features (Caratteristiche di localizzazione) dei componenti core](/help/get-started/localization.md).

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

Tenere presente che la struttura seguente `/content/experience-fragments/wknd` rispecchia la struttura di `/content/wknd`.

In questo caso, se il componente Frammento esperienza `/content/experience-fragments/wknd/us/en/footerTextXf` viene inserito in un modello, le pagine localizzate create in base a tale modello eseguiranno automaticamente il rendering del frammento esperienza localizzato che corrisponde alla pagina del contenuto localizzato.

Pertanto, se andate a una pagina di contenuto in `/content/wknd/ch/de` che utilizza lo stesso modello, verrà eseguito il rendering di `/content/experience-fragments/wknd/ch/de/footerTextXf` invece di `/content/experience-fragments/wknd/us/en/footerTextXf`.

### Fallback {#fallback}

Il componente Frammento esperienza tenta di trovare un componente localizzato corrispondente nell’ordine seguente.

1. Per prima cosa cerca di trovare una radice della lingua.
1. Se non viene trovato, tenta di trovare un modello.
1. Se non viene trovata, cerca di trovare una Live Copy.
1. Se non viene trovata, per impostazione predefinita viene utilizzato il frammento esperienza configurato nel componente.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento esperienza è v1, introdotto con la release 2.6.0 dei componenti core a settembre 2019, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente Frammento esperienza e vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visita la [Libreria componenti](https://adobe.com/go/aem_cmp_library_xf).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Frammento esperienza [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_xf_v1).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all&#39;autore del contenuto di selezionare la variante del frammento esperienza da visualizzare sulla pagina.

![Finestra di dialogo di modifica del componente Frammento esperienza](/help/assets/experience-fragment-edit.png)

Utilizzare il pulsante **Apri finestra di dialogo di selezione** per aprire il selettore di componenti e scegliere quale variante di componente di frammento esperienza aggiungere alla pagina del contenuto.

Se aggiungete il componente Frammento esperienza a un modello, tenete presente che verrà localizzato automaticamente a condizione che i frammenti esperienza siano localizzati, pertanto il rendering sulla pagina potrebbe variare a seconda del componente selezionato in modo esplicito. [Per ulteriori informazioni, consulta l’esempio ](#example) precedente.

È inoltre possibile definire un **ID**. Questa opzione consente di controllare l&#39;identificatore univoco del componente nell&#39;HTML e nel [Livello dati](/help/developing/data-layer/overview.md).

* Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
* Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
* La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore del contenuto che utilizza il componente Frammento esperienza e le impostazioni predefinite al momento dell’inserimento del componente Frammento esperienza.

### Scheda Stili {#styles-tab}

Il componente Frammento esperienza supporta il AEM [Sistema di stile](/help/get-started/authoring.md#component-styling).
