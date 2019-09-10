---
title: Componente Frammento esperienza
seo-title: Componente Frammento esperienza
description: Il componente Frammenti esperienza consente all'autore del contenuto di aggiungere una variante di frammento esperienza a una pagina.
seo-description: Il componente Frammenti esperienza consente all'autore del contenuto di aggiungere una variante di frammento esperienza a una pagina.
content-type: riferimento
topic-tags: componenti core
translation-type: tm+mt
source-git-commit: c4e86960ec271464661193f6409cd93d1b9ec51b

---


# Componente Frammento esperienza{#experience-fragment-component}

Il componente Frammenti esperienza di componente core consente all'autore del contenuto di inserire una variante di frammento esperienza su una pagina, al momento di supportare una struttura localizzata del sito.

## Utilizzo {#usage}

Il componente Frammenti esperienza di componente core consente all'autore del contenuto di selezionare tra le diverse versioni di frammenti esperienza e posizionarne uno nella pagina del contenuto. Il componente Frammento esperienza supporta anche una struttura localizzata del sito.

* Le proprietà dei componenti possono essere definite nella finestra di dialogo [Configura](#configure-dialog).
* I valori predefiniti per il componente durante l'aggiunta a una pagina possono essere definiti nella finestra di dialogo [di progettazione](#design-dialog).

## Supporto struttura sito localizzato {#localized-site-structure}

Il componente Frammento esperienza è adattabile alle strutture localizzate del sito e riproduce il frammento esperienza corretto in base alla localizzazione della pagina. A tal fine, il frammento esperienza deve soddisfare le condizioni seguenti.

* Il componente Frammento esperienza viene aggiunto a un modello.
* Tale modello viene utilizzato per creare una nuova pagina di contenuto che fa parte di una struttura localizzata di seguito `/content/<site>`.
* Il frammento esperienza a cui si fa riferimento in una pagina di contenuto fa parte di una struttura di frammenti esperienza localizzata di seguito `/content/experience-fragments` con gli stessi pattern del sito sottostante `/content/<site>` , utilizzando gli stessi nomi di componente.

In questo caso, il frammento con la stessa localizzazione (lingua, blueprint o Live Copy) sarà rappresentato come parte del modello.

Questo comportamento è limitato ai componenti Frammento esperienza aggiunti ai modelli. Componenti frammento esperienza Aggiunti a singole pagine di contenuto renderanno disponibili le rappresentazioni esatte dei frammenti di esperienza configurate all'interno del componente.

* Per un esempio di funzionamento delle funzioni di localizzazione del componente Frammento esperienza, consulta [la sezione di seguito](#example).
* Per un esempio di funzionamento delle funzioni di localizzazione dei Componenti core, consultate le funzioni [di localizzazione della pagina Componenti principali](localization.md).

### Esempio {#example}

Supponiamo che il tuo contenuto abbia un aspetto simile al seguente:

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

La struttura di seguito `/content/experience-fragments/we-retail` riflette la struttura di `/content/we-retail`.

In questo caso, se il componente Frammento esperienza `/content/experience-fragments/we-retail/us/en/footerTextXf` è collocato in un modello, le pagine localizzate create in base a tale modello eseguiranno automaticamente il rendering del frammento esperienza localizzato corrispondente alla pagina del contenuto localizzata.

Pertanto, se passate a una pagina di contenuto che `/content/we-retail/ch/de` utilizza lo stesso modello, `/content/experience-fragments/we-retail/ch/de/footerTextXf` verrà eseguito il rendering invece `/content/experience-fragments/we-retail/us/en/footerTextXf`di.

### Riserva {#fallback}

Il componente Frammento esperienza tenterà di trovare un componente localizzato corrispondente nel seguente ordine.

1. Ffirst cerca di trovare una radice della lingua.
1. Se non viene trovato, tenta di trovare un blueprint.
1. Se non viene trovata, cerca di trovare una Live Copy.
1. Se non viene trovato, utilizza il frammento esperienza configurato nel componente.

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento esperienza è v 1, introdotta con la release 2.6.0 dei componenti core a settembre 2019, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Per provare il componente Frammento esperienza e vedere alcuni esempi delle opzioni di configurazione e l'output HTML e JSON, visita la [Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library/experience-fragment.html).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente [Frammento esperienza è disponibile su github](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/experience-fragment/v1/experience-fragment).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo Configura consente all'autore del contenuto di selezionare la variante del frammento esperienza che deve essere sottoposta a rendering sulla pagina.

![](assets/screen-shot-2019-08-23-10.49.21.png)

Per aprire il selettore dei componenti, usate il **pulsante Apri finestra di dialogo** di selezione per scegliere la variante del componente frammento esperienza da aggiungere alla pagina del contenuto.

Se aggiungi il componente Frammento esperienza a un modello, nota che verrà localizzato automaticamente, a condizione che i frammenti esperienza siano localizzati, quindi il rendering sulla pagina può variare a seconda del componente selezionato in modo esplicito. [Per ulteriori informazioni, consultate l'esempio precedente](#example) .

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all'autore del modello di definire le opzioni disponibili per l'autore di contenuto che utilizza il componente Frammento esperienza e le impostazioni predefinite quando si inserisce il componente Frammento esperienza.

![](assets/screen-shot-2019-08-23-10.48.36.png)

Il componente Frammento esperienza supporta il sistema [di stile AEM](authoring.md#component-styling).
