---
title: Componente di navigazione
seo-title: Componente di navigazione
description: 'null'
seo-description: Il componente Navigazione consente agli utenti di navigare facilmente in una struttura del sito globalizzata.
uuid: 616 c 03 fb -39 b 3-402 a-b 990-f 56 c 87 bc 6 df 4
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: da 8 d 67 d 7-b 65 e -4041-bc 0 e-e 998 f 24 a 68 f 9
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

Il componente Navigazione consente agli utenti di navigare facilmente in una struttura del sito globalizzata.

## Utilizzo {#usage}

Gli elenchi dei componenti di navigazione elencano una struttura di pagine in modo che gli utenti di un sito possano navigare facilmente nella struttura del sito.

Il componente di navigazione può rilevare automaticamente la struttura del sito globalizzata del sito e [si adatta automaticamente a una pagina localizzata.](#localized-site-strucutre) Inoltre, supporta qualsiasi struttura arbitraria del sito utilizzando [le pagine di reindirizzamento ombra](#shadow-structure) per rappresentare un'altra struttura diversa dalla struttura del contenuto principale.

La [finestra di dialogo](#edit-dialog) di modifica consente all'autore del contenuto di definire la pagina principale di navigazione e la profondità di navigazione. La [finestra di dialogo](#design-dialog) Progettazione consente all'autore del modello di definire valori predefiniti per la profondità di navigazione e la profondità.

## Supporto struttura sito localizzato {#localized-site-structure}

I siti Web vengono spesso forniti in più lingue per diverse regioni. In genere ciascuna pagina localizzata conterrà un elemento di navagation incluso nel modello della pagina. Il componente di navigazione consente di posizionarlo una volta su un modello per tutte le pagine del sito e si adatterà automaticamente per le singole pagine localizzate basate sulla struttura del sito globalizzata.

* Per un esempio di funzionamento della funzione di localizzazione del componente di navigazione, consultate la [sezione di seguito](#example-localiatzion).
* Per un esempio di funzionamento delle funzioni di localizzazione dei Componenti core, consultate le funzioni [di localizzazione della pagina Componenti principali](localization.md).

### Esempio {#example-localization}

Supponiamo che il tuo contenuto abbia un aspetto simile al seguente:

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

Per il sito We. Retail, probabilmente desiderate posizionare il componente di navigazione su un modello di pagina come parte dell'intestazione. Una volta parte del modello, potete impostare la **radice** di navigazione del componente su `/content/we-retail/language-masters/en` , da dove inizia il contenuto principale del sito. Desiderate anche impostare la Profondità struttura **di navigazione** su di `2` essa, perché probabilmente non desiderate che l'intera struttura del contenuto venga visualizzata dal componente, ma i primi due livelli in modo che fungano da panoramica.

Con il **valore Radice** di navigazione, il componente di navigazione sa che dopo `/content/we-retail/language-masters/en` l'inizio della navigazione e può generare opzioni di navigazione, ricorricorendo alla struttura del sito in due livelli (come definito dal valore **Profondità** struttura di navigazione).

A prescindere dalla pagina localizzata che l'utente sta visualizzando, il componente di navigazione può trovare la pagina localizzata corrispondente conoscendo la posizione della pagina corrente, lavorando all'interno della radice e quindi andando alla pagina corrispondente.

Quindi, se un visitatore sta visualizzando `/content/ch/de/experience/arctic-surfing-in-lofoten`, il componente sa di generare la struttura di navigazione basata su `/content/we-retail/language-masters/de`. Analogamente, se il visitatore sta visualizzando `/content/us/en/experience/arctic-surfing-in-lofoten`, il componente sa di generare la struttura di navigazione basata su `/content/we-retail/language-masters/en`.

## Supporto struttura sito ombra {#shadow-structure}

A volte è necessario creare un menu di navigazione per il visitatore diverso dalla struttura effettiva del sito. Potrebbe essere utile evidenziare alcuni contenuti nel menu ridisponendo l'elenco dei contenuti. Utilizzando le pagine di ombra, che si limitano a reindirizzare ad altre pagine di contenuto, il componente di navigazione può generare qualsiasi struttura di navigazione arbitraria.

A tal fine dovrai:

1. Create pagine di ombra come pagine oblicole che rappresentano la struttura desiderata del sito. Questa operazione viene spesso definita struttura del sito ombra.
1. Impostate i **valori di reindirizzamento** nella proporzione della pagina su queste pagine per indirizzare le pagine di contenuto effettive.
1. Impostare **l'opzione Nascondi in navigazione** nelle proprietà della pagina delle pagine dell'ombra.
1. Impostate il **valore Radice** di navigazione del componente di navigazione affinché punti al livello principale della nuova struttura del sito ombra.

Il componente di navigazione eseguirà quindi il rendering del menu in base alla struttura del sito ombra. I collegamenti sottoposti a rendering dal componente sono indirizzati alle pagine di contenuto effettive a cui le pagine dell'ombra vengono reindirizzate e non alle pagine dell'ombra. Inoltre, il componente visualizza i nomi delle pagine effettive e evidenzia correttamente la pagina attiva, anche quando la navigazione è basata sulle pagine di ombra. Il componente di navigazione rende le pagine dell'ombra completamente trasparenti per il visitatore.

>[!NOTE]
>Le pagine di ombra rendono le opzioni di navigazione molto più flessibili, ma ricordatevi che la manutenzione di questa struttura è quindi completamente manuale. Se ridisponete il contenuto effettivo del sito o aggiungete/rimuovete il contenuto, dovrete aggiornare manualmente la struttura dell'ombra, a seconda delle necessità.

>[!NOTE]
>Quando si esegue il rendering di una struttura del sito ombreggiatura, solo le pagine di ombra vengono riformate dalla logica di navigazione. La logica non comporta la refresh della struttura delle destinazioni di reindirizzamento.

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente di navigazione è v 1, introdotta con la release 2.0.0 dei componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Per provare il componente di navigazione e vedere alcuni esempi delle opzioni di configurazione e l'output HTML e JSON, visita la [Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library/navigation.html).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente [di navigazione è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/navigation/v1/navigation).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

>[!NOTE]
>
>Nella release 2.1.0 dei componenti core, il componente di navigazione supporta [schema.org microdati](https://schema.org).

## Edit Dialog {#edit-dialog}

Nella finestra di dialogo di modifica, l'autore del contenuto può definire la pagina principale per la navigazione e la profondità della struttura di navigazione.

### Scheda Proprietà {#properties-tab}

![](assets/screen-shot-2019-08-29-12.23.45.png)

* **Radice
di navigazione** La pagina principale, che verrà utilizzata per generare la struttura di navigazione.
* **Escludi principale
di navigazione** Escludi la radice di navigazione nella struttura ad albero risultante, includi solo i relativi discendenti.
* **Raccolta di tutte le pagine**
figlie Raccoglie tutte le pagine che sono discendenti della radice di navigazione.
* **Profondità
struttura di navigazione** Definisce quanti livelli ridurre la struttura di navigazione, il componente dovrebbe essere visualizzato rispetto alla radice di navigazione (disponibile solo quando **l'opzione Raccoglie tutte le pagine** figlie non è selezionata).

### Scheda Accessibilità {#accessibility-tab}

![](assets/screen-shot-2019-08-29-12.23.53.png)

Nella scheda **Accessibilità** , è possibile impostare i valori per [le etichette di accessibilità](https://www.w3.org/WAI/standards-guidelines/aria/) AIR per il componente.

* **Etichetta** : valore di un attributo label AIR per il componente

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all'autore del modello di impostare i valori predefiniti per la pagina di navigazione e la profondità di navigazione presentati agli autori di contenuto.

### Scheda Proprietà {#properties-tab-design}

![](assets/screen_shot_2018-04-03at112357.png)

* **Radice**
di navigazione Il valore predefinito della pagina principale della struttura di navigazione, che verrà utilizzata per generare la struttura di navigazione e per impostazione predefinita quando l'autore del contenuto aggiunge il componente alla pagina.
* **Escludi radice
di navigazione** Il valore predefinito dell'opzione per escludere la radice di navigazione nella struttura ad albero risultante.
* **Raccolta di pagine
figlie** Il valore predefinito dell'opzione per raccogliere tutte le pagine discendenti della radice di navigazione.
* **Profondità**
struttura di navigazione Il valore predefinito della profondità della struttura di navigazione.

### Scheda Stili {#styles-tab}

Il componente di navigazione supporta il sistema [di stile AEM](authoring.md#component-styling).
