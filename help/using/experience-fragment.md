---
title: Experience Fragment Component
seo-title: Experience Fragment Component
description: The Experience Fragment Component allows the content author to add an experience fragment variation to a page.
seo-description: The Experience Fragment Component allows the content author to add an experience fragment variation to a page.
content-type: riferimento
topic-tags: core-components
translation-type: tm+mt
source-git-commit: c4e86960ec271464661193f6409cd93d1b9ec51b

---


# Experience Fragment Component{#experience-fragment-component}

The Core Component Experience Fragment Component allows the content author to place an experience fragment variation on a page while supporting a localized site structure.

## Utilizzo {#usage}

The Core Component Experience Fragment Component allows the content author to select from existing experience fragment varations and place one on the content page. The Experience Fragment component also supports a localized site structure.

* Le proprietà dei componenti possono essere definite nella finestra di dialogo [di](#configure-dialog)configurazione.
* Defaults for the component when adding it to a page can be defined in the design dialog.[](#design-dialog)

## Supporto struttura sito localizzata {#localized-site-structure}

Il componente Frammento esperienza si adatta alle strutture del sito localizzate ed esegue il rendering del frammento esperienza appropriato in base alla localizzazione della pagina. A tal fine, il frammento di esperienza deve soddisfare le seguenti condizioni.

* Il componente Frammento esperienza viene aggiunto a un modello.
* Tale modello viene utilizzato per creare una nuova pagina di contenuto che fa parte di una struttura localizzata di seguito `/content/<site>`.
* Il frammento esperienza a cui si fa riferimento in una pagina di contenuto fa parte di una struttura di frammento esperienza localizzata sotto `/content/experience-fragments` che segue gli stessi pattern del sito sottostante, `/content/<site>` compreso l'utilizzo degli stessi nomi di componente.

In questo caso, il frammento con la stessa localizzazione (lingua, blueprint o Live Copy) della pagina corrente verrà rappresentato come parte del modello.

Questo comportamento è limitato ai componenti frammento esperienza aggiunti ai modelli. Frammenti esperienza I componenti aggiunti alle singole pagine di contenuto renderanno effettive le rappresentazioni dei frammenti esperienza configurate all’interno del componente.

* Per un esempio del funzionamento delle funzioni di localizzazione del componente Frammento esperienza, consultate [la sezione seguente](#example).
* Per un esempio di come le funzioni di localizzazione dei componenti core funzionano insieme, consultate le funzioni di [localizzazione della pagina](localization.md)Componenti principali.

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

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Frammento esperienza e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](http://opensource.adobe.com/aem-core-wcm-components/library/experience-fragment.html)componenti.

## Technical Details {#technical-details}

The latest technical documentation about the Experience Fragment Component can be found on GitHub.[](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/experience-fragment/v1/experience-fragment)

Further details about developing Core Components can be found in the Core Components developer documentation.[](developing.md)

## Configure Dialog {#configure-dialog}

The configure dialog allows the content author to select the experience fragment variation that should be rendered on the page.

![](assets/screen-shot-2019-08-23-10.49.21.png)

Use the Open Selection Dialog button to open the component selector to choose which experience fragment component variation to add to the content page.****

If you add the Experience Fragment Component to a template, note that it will be automatically localized provided that the Experience Fragments are localized, so what is rendered on the page may vary from the component you explicitly select. [See the example above for more information.](#example)

## Design Dialog {#design-dialog}

The design dialog allows the template author to define the options available to the content author who uses the Experience Fragment Component and the defaults set when placing the Experience Fragment Component.

![](assets/screen-shot-2019-08-23-10.48.36.png)

The Experience Fragment Component supports the AEM Style System.[](authoring.md#component-styling)
