---
title: Componente di navigazione
seo-title: Componente di navigazione
description: 'null'
seo-description: Il componente Navigazione consente agli utenti di spostarsi facilmente in una struttura del sito globalizzata.
uuid: 616c03fb-39b3-402a-b990-f56c87bc6df4
content-type: riferimento
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: da8d67d7-b65e-4041-bc0e-e998f24a68f9
disttype: dist5
gnavtheme: chiaro
groupsectionnavitems: 'no'
hidemerchandisingbar: eredita
hidepromocomponent: eredita
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c4e86960ec271464661193f6409cd93d1b9ec51b

---


# Componente di navigazione{#navigation-component}

Il componente Navigazione consente agli utenti di spostarsi facilmente in una struttura del sito globalizzata.

## Utilizzo {#usage}

Il componente di navigazione elenca una struttura di pagine che consente agli utenti di un sito di navigare facilmente nella struttura del sito.

Il componente Navigazione è in grado di rilevare automaticamente la struttura del sito globalizzata e di [adattarsi automaticamente a una pagina localizzata.](#localized-site-strucutre) Inoltre, può supportare qualsiasi struttura arbitraria del sito utilizzando pagine [di reindirizzamento](#shadow-structure) shadow per rappresentare un'altra struttura diversa dalla struttura di contenuto principale.

La finestra di dialogo [di](#edit-dialog) modifica consente all’autore del contenuto di definire la pagina principale di navigazione insieme alla profondità della navigazione. La finestra di dialogo [di](#design-dialog) progettazione consente all'autore del modello di definire i valori predefiniti per la radice e la profondità di navigazione.

## Supporto struttura sito localizzata {#localized-site-structure}

I siti Web sono spesso disponibili in più lingue per diverse aree geografiche. In genere, ogni pagina localizzata contiene un elemento di navigazione incluso nel modello di pagina. Il componente Navigazione consente di inserirlo una volta in un modello per tutte le pagine del sito e quindi si adatta automaticamente alle singole pagine localizzate in base alla struttura globalizzata del sito.

* Per un esempio del funzionamento della funzione di localizzazione del componente di navigazione, vedere [la sezione seguente](#example-localiatzion).
* Per un esempio di come le funzioni di localizzazione dei componenti core funzionano insieme, consultate le funzioni di [localizzazione della pagina](localization.md)Componenti principali.

### Esempio {#example-localization}

Supponiamo che il contenuto sia simile al seguente:

```
/content
+-- we-retail
   +-- language-masters
      +-- de
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- en
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- es
      +-- fr
      \-- it
   +-- us
      +-- en
         \-- experience
            \-- arctic-surfing-in-lofoten
      \-- es
   \-- ch
      +-- de
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

Per il sito We.Retail, è probabile che si desideri inserire il componente di navigazione in un modello di pagina come parte dell'intestazione. Una volta fatto parte del modello, è possibile impostare la directory principale **di** navigazione del componente su `/content/we-retail/language-masters/en` tale posizione, dal momento che il contenuto principale per tale sito ha inizio. È possibile impostare anche Profondità **struttura di** navigazione in modo che `2` non venga visualizzata l’intera struttura del contenuto dal componente, ma piuttosto i primi due livelli in modo che funga da panoramica.

Con il valore Radice **di** navigazione, il componente di navigazione sa che dopo `/content/we-retail/language-masters/en` che la navigazione ha inizio e può generare opzioni di navigazione ripetendo la struttura del sito due livelli verso il basso (come definito dal valore Profondità **della struttura di** navigazione).

Indipendentemente dalla pagina localizzata visualizzata dall’utente, il componente Navigazione è in grado di individuare la pagina localizzata corrispondente, conoscendo la posizione della pagina corrente, eseguendo operazioni all’indietro fino al livello principale e quindi inoltrando la pagina corrispondente.

Quindi, se un visitatore sta visualizzando `/content/ch/de/experience/arctic-surfing-in-lofoten`il componente sa generare la struttura di navigazione in base a `/content/we-retail/language-masters/de`. Analogamente, se il visitatore sta visualizzando `/content/us/en/experience/arctic-surfing-in-lofoten`il componente sa generare la struttura di navigazione in base a `/content/we-retail/language-masters/en`.

## Supporto per la struttura del sito ombreggiato {#shadow-structure}

A volte è necessario creare un menu di navigazione per il visitatore diverso dalla struttura del sito effettiva. È possibile che una promozione evidenzi alcuni contenuti nel menu riorganizzando l'elenco dei contenuti. Utilizzando le pagine shadow, che si reindirizzano semplicemente ad altre pagine di contenuto, il componente di navigazione può generare qualsiasi struttura di navigazione arbitraria necessaria.

A tal fine, è necessario:

1. Create pagine ombreggiate come pagine vuote che rappresentano la struttura del sito desiderata. Questo viene spesso definito come struttura del sito ombra.
1. Impostate i valori **Redirect** nelle proprietà della pagina su queste pagine in modo che puntino alle pagine di contenuto effettive.
1. Impostare l'opzione **Nascondi in navigazione** nelle proprietà della pagina delle pagine shadow.
1. Impostare il valore **Navigation Root** del componente di navigazione in modo che punti alla radice della nuova struttura del sito shadow.

Il componente di navigazione eseguirà quindi il rendering del menu in base alla struttura del sito ombra. I collegamenti di cui viene eseguito il rendering dal componente sono alle pagine di contenuto effettive a cui le pagine ombra reindirizzano e non alle pagine ombra stesse. Inoltre, il componente visualizza i nomi delle pagine effettive e evidenzia correttamente la pagina attiva, anche quando la navigazione è basata su pagine ombra. Il componente Navigazione rende le pagine shadow completamente trasparenti per il visitatore.

>[!NOTE]
>Le pagine ombreggiate rendono le opzioni di navigazione molto più flessibili, ma tenete presente che la manutenzione di questa struttura è quindi completamente manuale. Se ridisponete il contenuto effettivo del sito o aggiungete/rimuovete contenuto, dovrete aggiornare manualmente la struttura ombreggiata secondo le necessità.

>[!NOTE]
>Durante il rendering di una struttura del sito ombreggiata, solo le pagine ombra vengono ricorse dalla logica di navigazione. La logica non ricorre alla struttura delle destinazioni di reindirizzamento.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente di navigazione è v1, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente di navigazione e per vedere esempi delle relative opzioni di configurazione, nonché l'output HTML e JSON, visitare la Libreria [](http://opensource.adobe.com/aem-core-wcm-components/library/navigation.html)componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente di navigazione [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/navigation/v1/navigation).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

>[!NOTE]
>
>Nella release 2.1.0 dei componenti core, il componente di navigazione supporta i microdati [](https://schema.org)schema.org.

## Edit Dialog {#edit-dialog}

Nella finestra di dialogo di modifica, l’autore del contenuto può definire la pagina principale per la navigazione e la profondità della struttura di navigazione.

### Scheda Proprietà {#properties-tab}

![](assets/screen-shot-2019-08-29-12.23.45.png)

* **Radice** di navigazione La pagina principale, che verrà utilizzata per generare la struttura ad albero.
* **Escludi radice** di navigazione Escludi la radice di navigazione nella struttura risultante, includi solo i relativi discendenti.
* **Raccogli tutte le pagine** figlie Raccogliere tutte le pagine discendenti della radice di navigazione.
* **Profondità** struttura di navigazione Definisce il numero di livelli sotto la struttura di navigazione che il componente deve visualizzare rispetto al livello principale di navigazione (disponibile solo se **Raccolta di tutte le pagine** figlie non è selezionata).

### Scheda Accessibilità {#accessibility-tab}

![](assets/screen-shot-2019-08-29-12.23.53.png)

Nella scheda **Accessibilità** , è possibile impostare i valori per le etichette di accessibilità [](https://www.w3.org/WAI/standards-guidelines/aria/) ARIA per il componente.

* **Etichetta** - Valore di un attributo etichetta ARIA per il componente

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all'autore del modello di impostare i valori predefiniti per la pagina principale di navigazione e la profondità di navigazione che vengono presentati agli autori del contenuto.

### Scheda Proprietà {#properties-tab-design}

![](assets/screen_shot_2018-04-03at112357.png)

* **Radice** di navigazione Il valore predefinito della pagina principale della struttura di navigazione, che verrà utilizzato per generare la struttura di navigazione e predefinito quando l'autore del contenuto aggiunge il componente alla pagina.
* **Escludi radice** di navigazione Il valore predefinito dell'opzione per escludere la radice di navigazione nella struttura ad albero risultante.
* **Raccogli tutte le pagine** figlie Il valore predefinito dell'opzione per raccogliere tutte le pagine discendenti della radice di navigazione.
* **Profondità** struttura di navigazione Il valore predefinito della profondità della struttura di navigazione.

### Scheda Stili {#styles-tab}

Il componente di navigazione supporta AEM [Style System](authoring.md#component-styling).
