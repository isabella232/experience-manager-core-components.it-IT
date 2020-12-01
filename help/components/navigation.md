---
title: Componente di navigazione
description: Il componente Navigazione consente agli utenti di navigare facilmente in una struttura del sito globalizzata.
translation-type: tm+mt
source-git-commit: ff943aeca0333b13e2b9aaf11f316457f001d507
workflow-type: tm+mt
source-wordcount: '1369'
ht-degree: 1%

---


# Componente di navigazione{#navigation-component}

Il componente Navigazione consente agli utenti di navigare facilmente in una struttura del sito globalizzata.

## Utilizzo {#usage}

Il componente di navigazione elenca una struttura di pagine che consente agli utenti di un sito di navigare facilmente nella struttura del sito.

Il componente di navigazione è in grado di rilevare automaticamente la struttura del sito globalizzata e [adattarsi automaticamente a una pagina localizzata.](#localized-site-structure) Inoltre, può supportare qualsiasi struttura arbitraria del sito utilizzando  [pagine di reindirizzamento ](#shadow-structure) ombreggiate per rappresentare un&#39;altra struttura diversa dalla struttura di contenuto principale.

La [finestra di dialogo di modifica](#edit-dialog) consente all&#39;autore del contenuto di definire la pagina principale di navigazione insieme alla profondità della navigazione. La finestra di dialogo [progettazione](#design-dialog) consente all&#39;autore del modello di definire i valori predefiniti per la radice e la profondità di navigazione.

## Supporto struttura sito localizzata {#localized-site-structure}

I siti Web sono spesso disponibili in più lingue per diverse aree geografiche. In genere, ogni pagina localizzata contiene un elemento di navigazione incluso nel modello di pagina. Il componente Navigazione consente di inserirlo una volta in un modello per tutte le pagine del sito e quindi si adatta automaticamente per le singole pagine localizzate in base alla struttura globalizzata del sito.

* Per un esempio del funzionamento della funzione di localizzazione del componente di navigazione, vedere [la sezione seguente](#example-localization).
* Per un esempio di come le funzioni di localizzazione dei componenti core funzionano insieme, consultate la pagina [Localization Features (Caratteristiche di localizzazione) dei componenti core](/help/get-started/localization.md).

### Esempio {#example-localization}

Supponiamo che il contenuto sia simile al seguente:

```
/content
+-- wknd
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

Per il WKND del sito, è consigliabile inserire il componente di navigazione in un modello di pagina come parte dell&#39;intestazione. Una volta fatto parte del modello, è possibile impostare la **radice di navigazione** del componente su `/content/wknd/language-masters/en`, in quanto è da lì che inizia il contenuto principale per tale sito. È inoltre possibile impostare **Profondità struttura di navigazione** su `2`, poiché probabilmente non si desidera che l&#39;intera struttura del contenuto venga visualizzata dal componente, ma piuttosto dai primi due livelli, in modo che funga da panoramica.

Con il valore **Radice di navigazione**, il componente di navigazione sa che dopo `/content/wknd/language-masters/en` la navigazione ha inizio e può generare opzioni di navigazione ripetendo la struttura del sito due livelli verso il basso (come definito dal valore **Profondità struttura di navigazione**).

Indipendentemente dalla pagina localizzata visualizzata dall’utente, il componente Navigazione è in grado di individuare la pagina localizzata corrispondente, conoscendo la posizione della pagina corrente, eseguendo operazioni all’indietro fino al livello principale e quindi inoltrando la pagina corrispondente.

Quindi, se un visitatore sta visualizzando `/content/ch/de/experience/arctic-surfing-in-lofoten`, il componente sa generare la struttura di navigazione in base a `/content/wknd/language-masters/de`. Analogamente, se il visitatore sta visualizzando `/content/us/en/experience/arctic-surfing-in-lofoten`, il componente è in grado di generare la struttura di navigazione in base a `/content/wknd/language-masters/en`.

## Supporto struttura del sito shadow {#shadow-structure}

A volte è necessario creare un menu di navigazione per il visitatore diverso dalla struttura del sito effettiva. È possibile che una promozione evidenzi alcuni contenuti nel menu riorganizzando l&#39;elenco dei contenuti. Utilizzando le pagine shadow, che si reindirizzano semplicemente ad altre pagine di contenuto, il componente di navigazione può generare qualsiasi struttura di navigazione arbitraria necessaria.

A tal fine, è necessario:

1. Create pagine ombreggiate come pagine vuote che rappresentino la struttura del sito desiderata. Questo viene spesso definito come struttura del sito ombra.
1. Impostate i valori **Redirect** nelle proprietà della pagina su queste pagine per puntare alle pagine di contenuto effettive.
1. Impostare l&#39;opzione **Nascondi in navigazione** nelle proprietà della pagina delle pagine shadow.
1. Impostare il valore **Radice di navigazione** del componente di navigazione in modo che punti alla radice della nuova struttura del sito ombreggiato.

Il componente di navigazione eseguirà quindi il rendering del menu in base alla struttura del sito ombra. I collegamenti di cui viene eseguito il rendering dal componente sono alle pagine di contenuto effettive a cui le pagine ombra reindirizzano e non alle pagine ombra stesse. Inoltre, il componente visualizza i nomi delle pagine effettive e evidenzia correttamente la pagina attiva, anche quando la navigazione è basata su pagine ombra. Il componente Navigazione rende le pagine shadow completamente trasparenti per il visitatore.

>[!NOTE]
>Le pagine ombreggiate rendono le opzioni di navigazione molto più flessibili, ma tenete presente che la manutenzione di questa struttura è quindi completamente manuale. Se ridisponete il contenuto effettivo del sito o aggiungete/rimuovete contenuto, dovrete aggiornare manualmente la struttura ombreggiata secondo le necessità.

>[!NOTE]
>Durante il rendering di una struttura del sito ombreggiata, solo le pagine ombra vengono ricorse dalla logica di navigazione. La logica non ricorre alla struttura delle destinazioni di reindirizzamento.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente di navigazione è v1, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente di navigazione e per visualizzare esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library_navigation).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente di navigazione [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_navigation_v1).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

>[!NOTE]
>
>A partire dalla release 2.1.0 dei componenti core, il componente di navigazione supporta i microdati [schema.org](https://schema.org).

## Finestra di dialogo Modifica {#edit-dialog}

Nella finestra di dialogo di modifica, l’autore del contenuto può definire la pagina principale per la navigazione e la profondità della struttura di navigazione.

### Scheda Proprietà {#properties-tab}

![Scheda delle proprietà della finestra di dialogo di modifica del componente di navigazione](/help/assets/navigation-edit-properties.png)

* **Radice**  di navigazione - La pagina principale, che verrà utilizzata per generare la struttura ad albero.
* **Escludi livelli**  di radice - Spesso la radice non deve essere inclusa nella navigazione. Questa opzione consente di specificare il numero di livelli rispetto al livello principale da escludere. Esempio:
   * 0 = mostra il livello principale
   * 1 = escludere il livello principale
   * 2 = escludere la radice e 1 altro livello verso l&#39;alto
   * etc.
* **Raccogli tutte le pagine**  figlie - Raccogliere tutte le pagine discendenti della radice di navigazione.
* **Profondità**  struttura di navigazione - Definisce il numero di livelli sotto la struttura di navigazione che il componente deve visualizzare rispetto alla radice di navigazione (disponibile solo quando  **Raccoglie tutte le** pagine figlie non è selezionata).
* **Disattiva ombreggiatura** : se la pagina nella gerarchia è un reindirizzamento, il nome della pagina di reindirizzamento verrà visualizzato al posto della destinazione. Per ulteriori informazioni, vedere [Supporto per la struttura del sito ombra](#shadow-structure).
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

### Scheda Accessibilità {#accessibility-tab}

![Scheda di accesso facilitato della finestra di dialogo di modifica del componente di navigazione](/help/assets/navigation-edit-accessibility.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette [Accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente.

* **Etichetta**  - Valore di un attributo etichetta ARIA per il componente

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di impostare i valori predefiniti per la pagina principale di navigazione e la profondità di navigazione che vengono presentati agli autori del contenuto.

### Scheda Proprietà {#properties-tab-design}

![Finestra di dialogo Progettazione del componente di navigazione](/help/assets/navigation-design.png)

* **Radice**  di navigazione - Il valore predefinito della pagina principale della struttura di navigazione, che verrà utilizzato per generare la struttura di navigazione e predefinito quando l&#39;autore del contenuto aggiunge il componente alla pagina.
* **Escludi livelli**  di radice - Spesso la radice non deve essere inclusa nella navigazione. Questa opzione consente di specificare il numero predefinito di livelli rispetto al livello principale da escludere. Esempio:
   * 0 = mostra il livello principale
   * 1 = escludere il livello principale
   * 2 = escludere la radice e 1 altro livello verso l&#39;alto
   * ecc.
* **Raccogli tutte le pagine**  figlie - Il valore predefinito dell&#39;opzione per raccogliere tutte le pagine discendenti della radice di navigazione.
* **Profondità**  struttura di navigazione - Il valore predefinito della profondità della struttura di navigazione.
* **Disabilita ombreggiatura** : il valore predefinito di se la condivisione deve essere disabilitata quando si aggiunge un componente di navigazione

### Scheda Stili {#styles-tab}

Il componente di navigazione supporta il AEM [Sistema di stile](/help/get-started/authoring.md#component-styling).
