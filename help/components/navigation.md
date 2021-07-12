---
title: Componente di navigazione
description: Il componente Navigazione consente agli utenti di navigare facilmente in una struttura del sito globalizzata.
role: Architect, Developer, Admin, User
exl-id: 9154f2a3-3d1e-4865-a413-298748fa66d3
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '1382'
ht-degree: 1%

---

# Componente di navigazione{#navigation-component}

Il componente Navigazione consente agli utenti di navigare facilmente in una struttura del sito globalizzata.

## Utilizzo {#usage}

Il componente di navigazione elenca una struttura ad albero delle pagine che consente agli utenti di un sito di navigare facilmente nella struttura del sito.

Il componente di navigazione è in grado di rilevare automaticamente la struttura del sito globalizzata e [adattarsi automaticamente a una pagina localizzata.](#localized-site-structure) Inoltre, può supportare qualsiasi struttura di sito arbitraria utilizzando le pagine di reindirizzamento  [ ](#shadow-structure) shadow per rappresentare un’altra struttura diversa dalla struttura di contenuto principale.

La [finestra di dialogo di modifica](#edit-dialog) consente all’autore del contenuto di definire la pagina principale di navigazione e il livello di profondità di navigazione. La [finestra di dialogo di progettazione](#design-dialog) consente all’autore del modello di definire i valori predefiniti per la radice e la profondità di navigazione.

## Supporto per la struttura del sito localizzata {#localized-site-structure}

I siti web sono spesso disponibili in più lingue per diverse aree geografiche. In genere, ogni pagina localizzata conterrà un elemento di navigazione incluso come parte del modello di pagina. Il componente Navigazione consente di posizionarlo una volta su un modello per tutte le pagine del sito e quindi si adatta automaticamente alle singole pagine localizzate in base alla struttura globalizzata del sito.

* Per un esempio del funzionamento della funzione di localizzazione del componente di navigazione, vedere [la sezione seguente](#example-localization).
* Per un esempio del funzionamento congiunto delle funzioni di localizzazione dei componenti core, consulta la pagina [Funzioni di localizzazione dei componenti core](/help/get-started/localization.md) .

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

Per il WKND del sito, è probabile che si desideri inserire il componente di navigazione in un modello di pagina come parte dell’intestazione. Una volta parte del modello, è possibile impostare la **Radice di navigazione** del componente su `/content/wknd/language-masters/en`, in quanto è da lì che inizia il contenuto principale per quel sito. Puoi anche impostare **Profondità struttura di navigazione** su `2` in quanto probabilmente non desideri che l’intera struttura del contenuto venga visualizzata dal componente, ma piuttosto dai primi due livelli, in modo che funga da panoramica.

Con il valore **Radice di navigazione**, il componente di navigazione sa che dopo `/content/wknd/language-masters/en` la navigazione inizia e può generare opzioni di navigazione ripetendo la struttura del sito di due livelli verso il basso (come definito dal valore **Profondità struttura di navigazione**).

Indipendentemente dalla pagina localizzata che un utente sta visualizzando, il componente Navigazione è in grado di trovare la pagina localizzata corrispondente conoscendo la posizione della pagina corrente, lavorando all’indietro fino alla pagina principale e quindi inoltrando alla pagina corrispondente.

Quindi, se un visitatore sta visualizzando `/content/ch/de/experience/arctic-surfing-in-lofoten`, il componente è in grado di generare la struttura di navigazione in base a `/content/wknd/language-masters/de`. Analogamente, se il visitatore visualizza `/content/us/en/experience/arctic-surfing-in-lofoten`, il componente è in grado di generare la struttura di navigazione in base a `/content/wknd/language-masters/en`.

## Supporto per la struttura del sito ombreggiato {#shadow-structure}

A volte è necessario creare un menu di navigazione per il visitatore che sia diverso dalla struttura effettiva del sito. Forse una promozione dovrebbe evidenziare determinati contenuti nel menu riorganizzando l&#39;elenco dei contenuti. Utilizzando le pagine shadow, che si reindirizzano semplicemente ad altre pagine di contenuto, il componente di navigazione può generare qualsiasi struttura di navigazione arbitraria necessaria.

A questo scopo, dovrai:

1. Crea pagine ombreggiate come pagine vuote che rappresentano la struttura del sito desiderata. Questo viene spesso definito struttura del sito ombra.
1. Imposta i valori **Reindirizza** nelle proprietà della pagina in queste pagine in modo che puntino alle pagine di contenuto effettive.
1. Imposta l&#39;opzione **Nascondi in navigazione** nelle proprietà della pagina delle pagine shadow.
1. Impostare il valore **Radice di navigazione** del componente di navigazione in modo che punti alla directory principale della nuova struttura del sito shadow.

Il componente di navigazione esegue quindi il rendering del menu in base alla struttura del sito ombreggiata. I collegamenti di cui è stato eseguito il rendering dal componente sono destinati alle pagine di contenuto effettive a cui le pagine shadow vengono reindirizzate e non alle pagine shadow stesse. Inoltre, il componente visualizza i nomi delle pagine effettive ed evidenzia correttamente la pagina attiva, anche quando la navigazione è basata su pagine ombreggiate. Il componente di navigazione rende le pagine ombreggiate completamente trasparenti per il visitatore.

>[!NOTE]
>Le pagine shadow rendono le opzioni di navigazione molto più flessibili, ma ricorda che la manutenzione di questa struttura è quindi completamente manuale. Se ridisponi il contenuto effettivo del sito o aggiungi/rimuovi contenuto, dovrai aggiornare manualmente la struttura shadow in base alle necessità.

>[!NOTE]
>Quando si esegue il rendering di una struttura del sito ombreggiata, solo le pagine shadow vengono ricorse dalla logica di navigazione. La logica non ricorre alla struttura delle destinazioni di reindirizzamento.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente di navigazione è la v1, introdotta con la versione 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente di navigazione e dell’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_navigation) .

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente di navigazione [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_navigation_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

>[!NOTE]
>
>A partire dalla versione 2.1.0 dei componenti core, il componente di navigazione supporta [schema.org microdata](https://schema.org).

## Finestra di dialogo Modifica {#edit-dialog}

Nella finestra di dialogo di modifica, l’autore del contenuto può definire la pagina principale per la navigazione e la profondità della struttura di navigazione.

### Scheda Proprietà {#properties-tab}

![Scheda delle proprietà della finestra di dialogo di modifica del componente di navigazione](/help/assets/navigation-edit-properties.png)

* **Radice di navigazione** : la pagina principale, che verrà utilizzata per generare la struttura di navigazione.
* **Escludi livelli radice** : spesso la radice non deve essere inclusa nella navigazione. Questa opzione consente di specificare il numero di livelli dalla radice da escludere. Esempio:
   * 0 = mostra il livello principale
   * 1 = escludere il livello principale
   * 2 = escludere la radice e 1 livello superiore
   * etc.
* **Raccogli tutte le pagine figlie**  - Raccogli tutte le pagine discendenti della radice di navigazione.
* **Profondità struttura di navigazione** : definisce il numero di livelli sotto la struttura di navigazione che il componente deve visualizzare rispetto alla radice di navigazione (disponibile solo quando non è selezionata l’opzione  **Raccogli tutte le** pagine figlie).
* **Disabilita ombreggiatura** : se la pagina nella gerarchia è un reindirizzamento, viene visualizzato il nome della pagina di reindirizzamento al posto del target. Per ulteriori informazioni, consulta il [Supporto per la struttura del sito shadow](#shadow-structure) .
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

### Scheda Accessibilità {#accessibility-tab}

![Scheda della finestra di dialogo di accesso facilitato del componente di navigazione](/help/assets/navigation-edit-accessibility.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette [Accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente.

* **Etichetta**  - Valore di un attributo dell’etichetta ARIA per il componente

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di impostare i valori predefiniti per la navigazione nella pagina principale e la profondità di navigazione che vengono presentati agli autori dei contenuti.

### Scheda Proprietà {#properties-tab-design}

![Finestra di dialogo di progettazione del componente di navigazione](/help/assets/navigation-design.png)

* **Radice di navigazione** : valore predefinito della pagina principale della struttura di navigazione, che verrà utilizzato per generare la struttura di navigazione e predefinito quando l’autore del contenuto aggiunge il componente alla pagina.
* **Escludi livelli radice** : spesso la radice non deve essere inclusa nella navigazione. Questa opzione consente di specificare il numero predefinito di livelli dalla radice da escludere. Esempio:
   * 0 = mostra il livello principale
   * 1 = escludere il livello principale
   * 2 = escludere la radice e 1 livello superiore
   * ecc.
* **Raccogli tutte le pagine figlie**  - Il valore predefinito dell’opzione per raccogliere tutte le pagine discendenti della radice di navigazione.
* **Profondità struttura di navigazione** : valore predefinito della profondità della struttura di navigazione.
* **Disabilita ombreggiatura** : il valore predefinito di se l’ombreggiatura deve essere disabilitata quando si aggiunge un componente di navigazione

### Scheda Stili {#styles-tab}

Il componente Navigazione supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

## Livello dati client di Adobe {#data-layer}

Il componente di navigazione supporta il [livello dati client di Adobe.](/help/developing/data-layer/overview.md)
