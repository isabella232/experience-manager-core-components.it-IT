---
title: Componente navigazione lingua
description: Il componente di navigazione della lingua fornisce una navigazione tra la lingua e il paese per un sito, in modo che i visitatori possano passare alla stessa pagina in un'impostazione internazionale diversa.
translation-type: tm+mt
source-git-commit: 65f900ad6759206a13f2bda6169900f62d968d8d

---


# Language Navigation Component{#language-navigation-component}

Il componente Navigazione lingua fornisce una navigazione in lingua/paese per un sito, in modo che i visitatori possano passare alla stessa pagina in un&#39;altra lingua.

## Utilizzo {#usage}

I siti Web sono spesso disponibili in più lingue per diverse aree geografiche. Il componente di navigazione della lingua consente a un visitatore di visualizzare la stessa pagina in diverse lingue/lingue. Se si è lettori della versione svizzera tedesca del sito, è possibile passare facilmente alla versione inglese USA della stessa pagina. Il componente Navigazione lingua gestisce la comprensione della struttura della lingua del sito e trova automaticamente la pagina corrispondente.

* Per un esempio del funzionamento della funzione di localizzazione del componente Navigazione lingua, vedere [la sezione seguente](#example).
* Per un esempio di come le funzioni di localizzazione degli altri componenti core funzionano insieme, consultate la pagina [Caratteristiche di](localization.md)localizzazione dei componenti core.

La finestra di dialogo [di](#edit-dialog) modifica consente di definire la radice di navigazione del sito globale e di definire la profondità della struttura di navigazione. Utilizzando la finestra di dialogo [di](#design-dialog)progettazione, l&#39;autore del modello può impostare i valori predefiniti per le stesse opzioni.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Navigazione lingua è v1, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM come servizio cloud |
|--- |--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Navigazione lingua e per vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la Libreria [](https://adobe.com/go/aem_cmp_library_langnav)componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Navigazione lingua [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_langnav_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di modifica consente di definire la radice di navigazione del sito globale e di definire la profondità della struttura di navigazione.

In genere queste configurazioni devono essere eseguite solo a livello di modello di pagina. Tuttavia, possono essere modificati a livello di pagina tramite la finestra di dialogo [di](#edit-dialog)modifica.

### Scheda Proprietà {#properties-tab}

![](assets/screen_shot_2018-01-12at133642.png)

* **Directory principale di navigazione**
   * Qui è dove dovrebbe iniziare la navigazione della lingua del sito.
   * La struttura della lingua del sito inizia al livello successivo sotto questa radice.
* **Annidamento struttura lingua**
   * È il numero di livelli della struttura del contenuto sotto la directory principale di **navigazione** che rappresenta la struttura della lingua del sito. Esempi:
      * `1` in genere significa che hai solo la scelta della lingua.
      * `2` in genere significa che hai una scelta di lingua e paese.
      * `3` in genere indica che si dispone di una scelta di lingua, paese e regione.

#### Esempio {#example}

Supponiamo che il contenuto sia simile al seguente:

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

Per il sito We.Retail, è probabile che si desideri inserire il componente Navigazione lingua in un modello di pagina come parte dell’intestazione. Una volta fatto parte del modello, è possibile impostare la directory principale **di** navigazione del componente su `/content/we-retail` tale posizione, in quanto il contenuto localizzato per tale sito ha inizio. Si desidera anche impostare la Profondità **della struttura della** lingua `2` perché la struttura è di due livelli (paese e quindi lingua).

Con il valore Radice **di** navigazione, il componente Lingua sa che dopo `/content/we-retail` che la navigazione ha inizio e può generare opzioni di navigazione nella lingua riconoscendo i due livelli successivi nella struttura del contenuto come struttura di navigazione della lingua del sito (come definito dal valore Profondità **struttura della** lingua).

Indipendentemente dalla pagina visualizzata dall’utente, il componente Navigazione lingua è in grado di trovare la pagina corrispondente in un’altra lingua, conoscendo la posizione della pagina corrente e lavorando all’indietro fino al livello principale, quindi inoltrando la pagina corrispondente.

### Scheda Stili {#styles-tab}

Il componente Navigazione lingua supporta AEM [Style System](authoring.md#component-styling).

## Edit Dialog {#edit-dialog}

In genere il componente Navigazione lingua deve essere aggiunto e configurato solo nei modelli di pagina di un sito. Tuttavia, se il componente Navigazione lingua deve essere aggiunto a una singola pagina di contenuto, la finestra di dialogo di modifica consente a un autore di contenuto di configurare gli stessi valori come descritto nella finestra di dialogo [](#design-dialog)della progettazione.

![](assets/screen_shot_2018-01-12at133353.png)
