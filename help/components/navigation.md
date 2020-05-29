---
title: Componente di navigazione
description: Il componente Navigazione consente agli utenti di navigare facilmente in una struttura del sito globalizzata.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '1369'
ht-degree: 1%

---


# Componente di navigazione{#navigation-component}

Il componente Navigazione consente agli utenti di navigare facilmente in una struttura del sito globalizzata.

## Utilizzo {#usage}

Il componente di navigazione elenca una struttura di pagine che consente agli utenti di un sito di navigare facilmente nella struttura del sito.

Il componente Navigazione è in grado di rilevare automaticamente la struttura del sito globalizzata e di [adattarsi automaticamente a una pagina localizzata.](#localized-site-structure) Inoltre, può supportare qualsiasi struttura arbitraria del sito utilizzando pagine [di reindirizzamento](#shadow-structure) shadow per rappresentare un&#39;altra struttura diversa dalla struttura di contenuto principale.

La finestra di dialogo [di](#edit-dialog) modifica consente all’autore del contenuto di definire la pagina principale di navigazione insieme alla profondità della navigazione. La finestra di dialogo [di](#design-dialog) progettazione consente all&#39;autore del modello di definire i valori predefiniti per la radice e la profondità di navigazione.

## Supporto struttura sito localizzata {#localized-site-structure}

I siti Web sono spesso disponibili in più lingue per diverse aree geografiche. In genere, ogni pagina localizzata contiene un elemento di navigazione incluso nel modello di pagina. Il componente Navigazione consente di inserirlo una volta in un modello per tutte le pagine del sito e quindi si adatta automaticamente per le singole pagine localizzate in base alla struttura globalizzata del sito.

* Per un esempio del funzionamento della funzione di localizzazione del componente di navigazione, vedere [la sezione seguente](#example-localization).
* Per un esempio di come le funzioni di localizzazione dei componenti core funzionano insieme, consultate le funzioni di [localizzazione della pagina](/help/get-started/localization.md)Componenti principali.

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

Per il sito We.Retail, è probabile che si desideri inserire il componente di navigazione in un modello di pagina come parte dell&#39;intestazione. Una volta fatto parte del modello, è possibile impostare la directory principale **di** navigazione del componente su `/content/wknd/language-masters/en` tale posizione, dal momento che il contenuto principale per tale sito ha inizio. È possibile impostare anche Profondità **struttura di** navigazione in modo che `2` non venga visualizzata l’intera struttura del contenuto dal componente, ma piuttosto i primi due livelli in modo che funga da panoramica.

Con il valore Radice **di** navigazione, il componente di navigazione sa che dopo `/content/wknd/language-masters/en` che la navigazione ha inizio e può generare opzioni di navigazione eseguendo la ricorsione verso il basso della struttura del sito di due livelli (come definito dal valore Profondità **della struttura di** navigazione).

Indipendentemente dalla pagina localizzata visualizzata dall’utente, il componente Navigazione è in grado di individuare la pagina localizzata corrispondente, conoscendo la posizione della pagina corrente, eseguendo operazioni all’indietro fino al livello principale e quindi inoltrando la pagina corrispondente.

Quindi, se un visitatore sta visualizzando `/content/ch/de/experience/arctic-surfing-in-lofoten`il componente sa generare la struttura di navigazione in base a `/content/wknd/language-masters/de`. Analogamente, se il visitatore sta visualizzando `/content/us/en/experience/arctic-surfing-in-lofoten`il componente sa generare la struttura di navigazione in base a `/content/wknd/language-masters/en`.

## Supporto per la struttura del sito ombreggiato {#shadow-structure}

A volte è necessario creare un menu di navigazione per il visitatore diverso dalla struttura del sito effettiva. È possibile che una promozione evidenzi alcuni contenuti nel menu riorganizzando l&#39;elenco dei contenuti. Utilizzando le pagine shadow, che si reindirizzano semplicemente ad altre pagine di contenuto, il componente di navigazione può generare qualsiasi struttura di navigazione arbitraria necessaria.

A tal fine, è necessario:

1. Create pagine ombreggiate come pagine vuote che rappresentino la struttura del sito desiderata. Questo viene spesso definito come struttura del sito ombra.
1. Impostate i valori di **reindirizzamento** nelle proprietà della pagina su queste pagine in modo che puntino alle pagine di contenuto effettive.
1. Impostare l&#39;opzione **Nascondi in navigazione** nelle proprietà della pagina delle pagine shadow.
1. Impostare il valore **Navigation Root** del componente di navigazione in modo che punti alla radice della nuova struttura del sito shadow.

Il componente di navigazione eseguirà quindi il rendering del menu in base alla struttura del sito ombra. I collegamenti di cui viene eseguito il rendering dal componente sono alle pagine di contenuto effettive a cui le pagine ombra reindirizzano e non alle pagine ombra stesse. Inoltre, il componente visualizza i nomi delle pagine effettive e evidenzia correttamente la pagina attiva, anche quando la navigazione è basata su pagine ombra. Il componente Navigazione rende le pagine shadow completamente trasparenti per il visitatore.

>[!NOTE]
>Le pagine ombreggiate rendono le opzioni di navigazione molto più flessibili, ma tenete presente che la manutenzione di questa struttura è quindi completamente manuale. Se ridisponete il contenuto effettivo del sito o aggiungete/rimuovete contenuto, dovrete aggiornare manualmente la struttura ombreggiata secondo le necessità.

>[!NOTE]
>Durante il rendering di una struttura del sito ombreggiata, solo le pagine ombra vengono ricorse dalla logica di navigazione. La logica non ricorre alla struttura delle destinazioni di reindirizzamento.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente di navigazione è v1, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente di navigazione e per vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la Libreria [](https://adobe.com/go/aem_cmp_library_navigation)componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente di navigazione [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_navigation_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

>[!NOTE]
>
>Nella release 2.1.0 dei componenti core, il componente di navigazione supporta i microdati [](https://schema.org)schema.org.

## Edit Dialog {#edit-dialog}

Nella finestra di dialogo di modifica, l’autore del contenuto può definire la pagina principale per la navigazione e la profondità della struttura di navigazione.

### Scheda Proprietà {#properties-tab}

![Scheda delle proprietà della finestra di dialogo di modifica del componente di navigazione](/help/assets/navigation-edit-properties.png)

* **Radice** di navigazione - La pagina principale, che verrà utilizzata per generare la struttura ad albero.
* **Escludi livelli** di radice: spesso la radice non deve essere inclusa nella navigazione. Questa opzione consente di specificare il numero di livelli rispetto al livello principale da escludere. Ad esempio:
   * 0 = mostra il livello principale
   * 1 = escludere il livello principale
   * 2 = escludere la radice e 1 altro livello verso l&#39;alto
   * etc.
* **Raccolta di tutte le pagine** figlie - Raccolta di tutte le pagine discendenti della radice di navigazione.
* **Profondità** struttura di navigazione - Definisce il numero di livelli sotto la struttura di navigazione che il componente deve visualizzare rispetto al livello principale di navigazione (disponibile solo se **Raccolta di tutte le pagine** figlie non è selezionata).
* **Disattiva ombreggiatura** : se la pagina nella gerarchia è un reindirizzamento, il nome della pagina di reindirizzamento verrà visualizzato al posto della destinazione. Per ulteriori informazioni, consulta [Supporto](#shadow-structure) struttura del sito ombreggiata.
* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

### Scheda Accessibilità {#accessibility-tab}

![Scheda di accesso facilitato della finestra di dialogo di modifica del componente di navigazione](/help/assets/navigation-edit-accessibility.png)

Nella scheda **Accessibilità** , è possibile impostare i valori per le etichette di accessibilità [](https://www.w3.org/WAI/standards-guidelines/aria/) ARIA per il componente.

* **Etichetta** - Valore di un attributo etichetta ARIA per il componente

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di impostare i valori predefiniti per la pagina principale di navigazione e la profondità di navigazione che vengono presentati agli autori del contenuto.

### Scheda Proprietà {#properties-tab-design}

![Finestra di dialogo Progettazione del componente di navigazione](/help/assets/navigation-design.png)

* **Radice** di navigazione - Il valore predefinito della pagina principale della struttura di navigazione, che verrà utilizzato per generare la struttura di navigazione e predefinito quando l&#39;autore del contenuto aggiunge il componente alla pagina.
* **Escludi livelli** di radice: spesso la radice non deve essere inclusa nella navigazione. Questa opzione consente di specificare il numero predefinito di livelli rispetto al livello principale da escludere. Ad esempio:
   * 0 = mostra il livello principale
   * 1 = escludere il livello principale
   * 2 = escludere la radice e 1 altro livello verso l&#39;alto
   * etc.
* **Raccogli tutte le pagine** figlie - Il valore predefinito dell&#39;opzione per raccogliere tutte le pagine discendenti della radice di navigazione.
* **Profondità** struttura di navigazione - Il valore predefinito della profondità della struttura di navigazione.
* **Disabilita ombreggiatura** - Il valore predefinito di se la condivisione deve essere disabilitata quando si aggiunge un componente di navigazione

### Scheda Stili {#styles-tab}

Il componente di navigazione supporta AEM [Style System](/help/get-started/authoring.md#component-styling).
