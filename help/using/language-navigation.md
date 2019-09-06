---
title: Componente di navigazione lingua
seo-title: Componente di navigazione lingua
description: 'null'
seo-description: Il componente di navigazione lingua fornisce una navigazione lingua/paese per un sito, in modo che i visitatori possano passare alla stessa pagina con un'altra lingua.
uuid: ce 736458-9 cdf -4 bc 2-b 90 f -9 c 5 a 62 fe 1 ca 0
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: 8 f 232 eb 0-65 d 5-4075-8668-75 f 1366882 c 8
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
source-git-commit: ee6976f39894b4e67b42503503a51589224583f5

---


# Language Navigation Component{#language-navigation-component}

Il componente Navigazione lingua fornisce una navigazione lingua/paese per un sito, in modo che i visitatori possano passare alla stessa pagina con un'altra lingua.

## Utilizzo {#usage}

I siti Web vengono spesso forniti in più lingue per diverse regioni. Il componente di navigazione lingua consente a un visitatore di visualizzare la stessa pagina in lingue/lingue diverse. Quindi, se siete un lettore della versione tedesca del sito Web, potete passare facilmente alla versione inglese statunitense della stessa pagina. Il componente Navigazione lingua gestisce l'aspetto della lingua del sito e trova automaticamente la pagina corrispondente.

La [finestra di dialogo](#edit-dialog) di modifica consente di definire la directory principale di navigazione globale del sito e di analizzare la struttura della navigazione. Mediante la finestra di dialogo [di progettazione](#design-dialog), l'autore del modello può impostare i valori predefiniti per le stesse opzioni.

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente di navigazione lingua è v 1, introdotta con la release 2.0.0 dei componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Per provare il componente di navigazione lingua e vedere alcuni esempi delle opzioni di configurazione e l'output HTML e JSON, visitare la [Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library/language-navigation/language-structure/us/en/language-navigation.html).

## Dettagli tecnici {#technical-details}

In github è disponibile la documentazione tecnica più recente relativa al componente [di navigazione lingua](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di modifica consente di definire la directory principale di navigazione globale del sito e di analizzare la struttura della navigazione.

In genere queste configurazioni devono essere eseguite solo nel modello di pagina. Tuttavia, possono essere modificati a livello di pagina tramite la finestra di dialogo [di modifica](#edit-dialog).

### Scheda Proprietà {#properties-tab}

![](assets/screen_shot_2018-01-12at133642.png)

* **Directory principale di navigazione**
   * Da dove deve iniziare la navigazione langauge del sito.
   * La struttura della lingua del sito inizia al livello successivo sotto questa radice.
* **Annidamento struttura lingua**
   * Questo è il numero di livelli della struttura ad albero del contenuto sotto la radice **di navigazione** , che rappresentano la struttura della lingua del sito. Esempi:
      * `1` in genere è possibile scegliere solo la lingua desiderata.
      * `2` consente di scegliere una lingua e un paese.
      * `3` in genere è possibile scegliere tra lanci, Paese e regione.

#### Esempio {#example}

Supponiamo che il tuo contenuto abbia un aspetto simile al seguente:

```
/content
+-- we-retail
   +-- language-masters
   +-- us
      +-- en
      \-- es
   \-- ch
      +-- de
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

Per il sito We. Retail, probabilmente desiderate inserire il componente Navigazione lingua in un modello di pagina come parte dell'intestazione. Una volta parte del modello, potete impostare la **radice** di navigazione del componente su `/content/we-retail` , da dove inizia il contenuto localizzato per quel sito. Occorre anche impostare Profondità struttura **lingua** in `2` quanto la struttura è di due livelli (Paese e quindi laguage).

Con il **valore Radice** di navigazione, il componente Lingua sa che dopo `/content/we-retail` l'inizio della navigazione è possibile generare le opzioni di navigazione della lingua riconoscendo i due livelli successivi nella struttura del contenuto come struttura di navigazione lingua del sito (come definito dal **valore Profondità** della struttura lingua).

A prescindere dalla pagina visualizzata dall'utente, il componente Navigazione lingua è in grado di trovare la pagina corrispondente in un'altra lingua, conoscendo la posizione della pagina corrente e lavorando all'interno della pagina principale, e quindi in futuro.

### Scheda Stili {#styles-tab}

Il componente di navigazione lingua supporta il sistema [di stile AEM](authoring.md#component-styling).

## Edit Dialog {#edit-dialog}

In genere è necessario aggiungere e configurare il componente Navigazione Langauge nei modelli delle pagine di un sito. Tuttavia, se il componente Navigazione lingua deve essere aggiunto a una singola pagina di contenuto, la finestra di dialogo di modifica consente a un autore di contenuto di configurare gli stessi valori come descritto nella finestra di dialogo [Progettazione](#design-dialog).

![](assets/screen_shot_2018-01-12at133353.png)
