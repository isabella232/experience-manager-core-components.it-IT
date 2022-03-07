---
title: Componente Navigazione
description: Il componente Navigazione consente agli utenti di navigare facilmente nella struttura globalizzata di un sito.
role: Architect, Developer, Admin, User
exl-id: 9154f2a3-3d1e-4865-a413-298748fa66d3
source-git-commit: 395a1669cf3e17f649c23852addc37316b923bfd
workflow-type: ht
source-wordcount: '1544'
ht-degree: 100%

---

# Componente Navigazione{#navigation-component}

Il componente Navigazione consente agli utenti di navigare facilmente nella struttura globalizzata di un sito.

## Utilizzo {#usage}

Il componente Navigazione visualizza una struttura di pagine che consente agli utenti di navigare facilmente nel sito.

Il componente Navigazione può rilevare automaticamente la struttura globalizzata del tuo sito e [adattarsi automaticamente a una pagina localizzata.](#localized-site-structure) Inoltre, può supportare qualsiasi struttura arbitraria del sito utilizzando le [pagine di reindirizzamento ombra](#shadow-structure) per rappresentare un’altra struttura diversa dalla struttura di contenuto principale.

La [finestra di dialogo per modifica](#edit-dialog) consente all’autore di contenuto di definire la pagina principale di navigazione e il livello di annidamento della navigazione. La [finestra di dialogo per progettazione](#design-dialog) consente all’autore del modello di definire i valori predefiniti per la directory principale di navigazione e il livello di annidamento della navigazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Navigazione è la v2, introdotta con la versione 2.18.0 dei Componenti core a febbraio 2022, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | - | Compatibile | Compatibile |
| [v1](v1/navigation.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Supporto della struttura localizzata del sito {#localized-site-structure}

I siti web sono spesso disponibili in più lingue per diverse aree geografiche. In genere, ogni pagina localizzata contiene un elemento di navigazione incluso nel modello della pagina. Il componente Navigazione consente di posizionarlo una sola volta in un modello per tutte le pagine del sito e quindi di adattarsi automaticamente alle singole pagine localizzate in base alla struttura globalizzata del sito.

* Per un esempio della funzione di localizzazione del componente Navigazione, vedi [la sezione che segue](#example-localization).
* Per un esempio dell’interazione delle funzioni di localizzazione dei Componenti core, visita la pagina [Funzioni di localizzazione dei Componenti core](/help/get-started/localization.md).

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

Per il WKND del sito, è probabile che tu voglia inserire il componente Navigazione nel modello di una pagina come parte dell’intestazione. Una volta inserito nel modello, è possibile impostare **Directory principale di navigazione** del componente su `/content/wknd/language-masters/en`, in quanto è da lì che inizia il contenuto principale di quel sito. Puoi anche impostare **Annidamento struttura di navigazione** su `2`, in quanto probabilmente non vuoi che il componente visualizzi l’intera struttura del contenuto, ma solo i primi due livelli, in modo che funga da panoramica.

Con il valore di **Directory principale di navigazione**, il componente Navigazione sa che dopo `/content/wknd/language-masters/en` la navigazione inizia e può generare opzioni di navigazione ripetendo la struttura del sito due livelli più in basso (come definito dal valore di **Annidamento struttura di navigazione**).

Indipendentemente dalla pagina che un utente sta visualizzando, il componente Navigazione è in grado di trovare la pagina localizzata corrispondente conoscendo la posizione della pagina corrente, risalendo all’indietro fino alla directory principale e quindi in avanti fino alla pagina corrispondente.

Pertanto, se un visitatore sta visualizzando `/content/ch/de/experience/arctic-surfing-in-lofoten`, il componente è in grado di generare la struttura di navigazione in base a `/content/wknd/language-masters/de`. Analogamente, se il visitatore sta visualizzando `/content/us/en/experience/arctic-surfing-in-lofoten`, il componente è in grado di generare la struttura di navigazione in base a `/content/wknd/language-masters/en`.

## Supporto della struttura del sito ombra {#shadow-structure}

A volte è necessario creare un menu di navigazione per il visitatore, che sia diverso dalla struttura effettiva del sito. Forse per una promozione, è necessario evidenziare un determinato contenuto nel menu riorganizzandone l’elenco. Utilizzando le pagine ombra che si reindirizzano semplicemente ad altre pagine di contenuto, il componente Navigazione può generare qualsiasi struttura di navigazione arbitraria necessaria.

A questo scopo, devi:

1. Creare pagine ombra come pagine vuote che rappresentano la struttura del sito desiderata. Questa viene spesso definita struttura del sito ombra.
1. Nelle proprietà della pagina, imposta i valori di **Reindirizza** su queste pagine per puntare alle pagine di contenuto effettivo.
1. Nelle proprietà della pagina, imposta l’opzione **Nascondi in navigazione** per le pagine ombra.
1. Imposta il valore di **Directory principale di navigazione** del componente Navigazione per puntare alla directory principale della nuova struttura del sito ombra.

Il componente Navigazione esegue quindi il rendering del menu in base alla struttura del sito ombra. I collegamenti di cui è stato eseguito il rendering dal componente puntano alle pagine di contenuto effettive a cui le pagine ombra vengono reindirizzate e non alle pagine ombra stesse. Inoltre, il componente visualizza i nomi delle pagine effettive ed evidenzia correttamente la pagina attiva, anche quando la navigazione è basata su pagine ombra. Il componente Navigazione rende le pagine ombra completamente trasparenti per il visitatore.

>[!NOTE]
>Le pagine ombra rendono le opzioni di navigazione molto più flessibili, ma tieni presente che la manutenzione di questa struttura è completamente manuale. Se ridisponi il contenuto effettivo del sito o aggiungi/rimuovi contenuto, dovrai aggiornare manualmente la struttura ombra secondo necessità.

>[!NOTE]
>Quando si esegue il rendering della struttura di un sito ombra, solo le pagine ombra vengono ripetute dalla logica di navigazione. La logica non ripete la struttura delle destinazioni del reindirizzamento.

## Reindirizzamenti nei componenti Navigazione {#redirects}

Quando una pagina presenta una destinazione di reindirizzamento (che sia verso un URL esterno o un’altra pagina AEM), un componente di navigazione che contiene i relativi link punta direttamente all’URL della destinazione di reindirizzamento.

### Esempio {#redirect-example}

* Crea una pagina A che reindirizza alla pagina B.
* Crea una pagina C che reindirizza a `https://aemcomponents.dev`
* In una pagina D, inserisci un componente di navigazione contenente le pagine A e C
* I rispettivi link generati puntano direttamente alle pagine B e `https://aemcomponents.dev`

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Navigazione e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_navigation_it).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Navigazione [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_navigation_v1_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

>[!NOTE]
>
>A partire dalla versione 2.1.0 dei Componenti core, il componente Navigazione supporta i [microdati schema.org](https://schema.org).

## Finestra di dialogo per modifica {#edit-dialog}

Nella finestra di dialogo per modifica, l’autore di contenuto può definire la pagina principale di navigazione e l’annidamento della struttura di navigazione.

### Scheda Proprietà {#properties-tab}

![Scheda Proprietà della finestra di dialogo per modifica del componente Navigazione](/help/assets/navigation-edit-properties.png)

* **Directory principale di navigazione**: la pagina principale che verrà utilizzata per generare la struttura di navigazione.
* **Escludi livelli di navigazione principali**: spesso la directory principale non deve essere inclusa nella navigazione. Questa opzione consente di specificare il numero dei livelli principali di navigazione da escludere. Esempio:
   * 0 = mostra il livello principale
   * 1 = esclude il livello principale
   * 2 = esclude il livello principale e 1 livello superiore
   * ecc.
* **Raccogli tutte le pagine figlie**: raccoglie tutte le pagine discendenti della directory principale di navigazione.
* **Annidamento struttura di navigazione**: definisce il numero di livelli sotto la struttura di navigazione che il componente deve visualizzare rispetto alla directory principale di navigazione (disponibile solo quando non è selezionata l’opzione **Raccogli tutte le pagine figlie**).
* **Disattiva ombreggiatura**: se la pagina nella gerarchia è reindirizzata, viene visualizzato il nome della pagina di reindirizzamento al posto della pagina di destinazione. Per ulteriori informazioni, vedi [Supporto per la struttura del sito ombra](#shadow-structure).
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità della finestra di dialogo per modifica del componente Navigazione](/help/assets/navigation-edit-accessibility.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette di [accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente.

* **Etichetta**: il valore di un attributo dell’etichetta ARIA del componente

### Scheda Stili {#styles-tab-edit}

Il componente Navigazione supporta il [sistema di stili di AEM](/help/get-started/authoring.md#component-styling).

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nella [finestra di dialogo di progettazione](#design-dialog) affinché il menu a discesa sia disponibile.

![Scheda Stili della finestra di dialogo per modifica del componente Navigazione](/help/assets/navigation-edit-styles.png)

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di impostare i valori predefiniti per la pagina principale di navigazione e l’annidamento della struttura di navigazione che vengono visualizzati agli autori di contenuto.

### Scheda Proprietà {#properties-tab-design}

![Finestra di dialogo per progettazione del componente Navigazione](/help/assets/navigation-design.png)

* **Directory principale di navigazione**: valore predefinito della pagina principale della struttura di navigazione, che verrà utilizzato per generare la struttura di navigazione e utilizzato automaticamente quando l’autore di contenuto aggiunge il componente alla pagina.
* **Escludi livelli di navigazione principali**: spesso la directory principale non deve essere inclusa nella navigazione. Questa opzione consente di specificare il numero predefinito di livelli di navigazione principali da escludere. Esempio:
   * 0 = mostra il livello principale
   * 1 = esclude il livello principale
   * 2 = esclude il livello principale e 1 livello superiore
   * ecc.
* **Raccogli tutte le pagine figlie**: il valore predefinito dell’opzione che raccoglie tutte le pagine discendenti della directory principale di navigazione.
* **Annidamento struttura di navigazione**: valore predefinito dell’annidamento della struttura di navigazione.
* **Disattiva ombreggiatura**: valore predefinito per l’attivazione/disattivazione dell’ombreggiatura quando si aggiunge un componente Navigazione

### Scheda Stili {#styles-tab}

Il componente Navigazione supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

## Adobe Client Data Layer {#data-layer}

Il componente Navigazione supporta [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
