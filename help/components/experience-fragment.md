---
title: Componente frammento esperienza
description: Il componente Frammento esperienza consente all’autore del contenuto di aggiungere a una pagina una variante di frammento esperienza.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Componente frammento esperienza{#experience-fragment-component}

Il componente di base Frammento esperienza del componente consente all’autore del contenuto di inserire una variante del frammento esperienza in una pagina, mentre supporta una struttura del sito localizzata.

## Utilizzo {#usage}

Il componente di base Frammento esperienza del componente permette all’autore del contenuto di selezionare le varianti di frammento esperienza esistenti e di inserirne una nella pagina del contenuto. Il componente Frammento esperienza supporta anche una struttura del sito localizzata.

* Le proprietà del componente possono essere definite nella finestra di dialogo [di](#configure-dialog)configurazione.
* I valori predefiniti per il componente quando lo si aggiunge a una pagina possono essere definiti nella finestra di dialogo [](#design-dialog)della progettazione.

## Supporto struttura sito localizzata {#localized-site-structure}

Il componente Frammento esperienza si adatta alle strutture del sito localizzate ed esegue il rendering del frammento esperienza appropriato in base alla localizzazione della pagina. A tal fine, il frammento di esperienza deve soddisfare le seguenti condizioni.

* Il componente Frammento esperienza viene aggiunto a un modello.
* Tale modello viene utilizzato per creare una nuova pagina di contenuto che fa parte di una struttura localizzata di seguito `/content/<site>`.
* Il frammento esperienza a cui si fa riferimento in una pagina di contenuto fa parte di una struttura di frammento esperienza localizzata sotto `/content/experience-fragments` che segue gli stessi pattern del sito sottostante, `/content/<site>` compreso l&#39;utilizzo degli stessi nomi di componente.

In questo caso, il frammento con la stessa localizzazione (lingua, blueprint o Live Copy) della pagina corrente verrà rappresentato come parte del modello.

Questo comportamento è limitato ai componenti frammento esperienza aggiunti ai modelli. Frammenti esperienza I componenti aggiunti alle singole pagine di contenuto renderanno effettive le rappresentazioni dei frammenti esperienza configurate all’interno del componente.

* Per un esempio del funzionamento delle funzioni di localizzazione del componente Frammento esperienza, consultate [la sezione seguente](#example).
* Per un esempio di come le funzioni di localizzazione dei componenti core funzionano insieme, consultate le funzioni di [localizzazione della pagina](/help/get-started/localization.md)Componenti principali.

### Esempio {#example}

Supponiamo che il contenuto sia simile al seguente:

```
/content
+-- experience-fragments
   \-- we-retail
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
+-- we-retail
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

Notate che la struttura sottostante `/content/experience-fragments/we-retail` rispecchia la struttura di `/content/we-retail`.

In questo caso, se il componente Frammento esperienza `/content/experience-fragments/we-retail/us/en/footerTextXf` viene inserito in un modello, le pagine localizzate create in base a tale modello eseguiranno automaticamente il rendering del frammento esperienza localizzato che corrisponde alla pagina di contenuto localizzata.

Pertanto, se andate a una pagina di contenuto sotto `/content/we-retail/ch/de` che utilizza lo stesso modello, `/content/experience-fragments/we-retail/ch/de/footerTextXf` verrà eseguito il rendering invece di `/content/experience-fragments/we-retail/us/en/footerTextXf`.

### Fallback {#fallback}

Il componente Frammento esperienza tenta di trovare un componente localizzato corrispondente nell’ordine seguente.

1. Per prima cosa cerca di trovare una radice della lingua.
1. Se non viene trovato, tenta di trovare un modello.
1. Se non viene trovata, cerca di trovare una Live Copy.
1. Se non viene trovata, per impostazione predefinita viene utilizzato il frammento esperienza configurato nel componente.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento esperienza è v1, introdotto con la release 2.6.0 dei componenti core a settembre 2019, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM come servizio cloud |
|--- |--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Frammento esperienza e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](https://adobe.com/go/aem_cmp_library_xf)componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Frammento esperienza [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_xf_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all&#39;autore del contenuto di selezionare la variante del frammento esperienza da visualizzare sulla pagina.

![](/help/assets/screen-shot-2019-08-23-10.49.21.png)

Utilizzate il pulsante **Apri finestra di dialogo** di selezione per aprire il selettore dei componenti e scegliere quale variante del componente del frammento esperienza aggiungere alla pagina del contenuto.

Se aggiungete il componente Frammento esperienza a un modello, tenete presente che verrà localizzato automaticamente a condizione che i frammenti esperienza siano localizzati, pertanto il rendering sulla pagina potrebbe variare a seconda del componente selezionato in modo esplicito. [Per ulteriori informazioni, consulta l’esempio precedente](#example) .

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore del contenuto che utilizza il componente Frammento esperienza e le impostazioni predefinite al momento dell’inserimento del componente Frammento esperienza.

![](/help/assets/screen-shot-2019-08-23-10.48.36.png)

Il componente Frammento esperienza supporta AEM [Style System](/help/get-started/authoring.md#component-styling).
