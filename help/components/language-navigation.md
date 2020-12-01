---
title: Componente navigazione lingua
description: Il componente di navigazione della lingua fornisce una navigazione tra la lingua e il paese per un sito, in modo che i visitatori possano passare alla stessa pagina in un'impostazione internazionale diversa.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 2%

---


# Componente navigazione lingua{#language-navigation-component}

Il componente Navigazione lingua fornisce una navigazione in lingua/paese per un sito, in modo che i visitatori possano passare alla stessa pagina in un&#39;altra lingua.

## Utilizzo {#usage}

I siti Web sono spesso disponibili in più lingue per diverse aree geografiche. Il componente di navigazione della lingua consente a un visitatore di visualizzare la stessa pagina in diverse lingue/lingue. Se si è lettori della versione svizzera tedesca del sito, è possibile passare facilmente alla versione inglese USA della stessa pagina. Il componente Navigazione lingua gestisce la comprensione della struttura della lingua del sito e trova automaticamente la pagina corrispondente.

* Per un esempio del funzionamento della funzione di localizzazione del componente Navigazione lingua, vedere [la sezione seguente](#example).
* Per un esempio di come le funzioni di localizzazione degli altri componenti core funzionano insieme, consultate la pagina [Localization Features (Caratteristiche di localizzazione) dei componenti core](/help/get-started/localization.md).

La [finestra di dialogo di modifica](#edit-dialog) consente di definire la radice di navigazione del sito globale e di definire la profondità della struttura di navigazione. Utilizzando la finestra di dialogo [progettazione](#design-dialog), l&#39;autore del modello può impostare i valori predefiniti per le stesse opzioni.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Navigazione lingua è v1, introdotto con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente Navigazione lingua e per vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library_langnav).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Navigazione lingua [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_langnav_v1).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di modifica consente di definire la radice di navigazione del sito globale e di definire la profondità della struttura di navigazione.

In genere queste configurazioni devono essere eseguite solo a livello di modello di pagina. Tuttavia, possono essere modificati a livello di pagina tramite la finestra di dialogo di modifica [a1/>.](#edit-dialog)

### Scheda Proprietà {#properties-tab}

![Finestra di dialogo Progettazione del componente Navigazione lingua](/help/assets/language-navigation-design.png)

* **Directory principale di navigazione**
   * Qui è dove dovrebbe iniziare la navigazione della lingua del sito.
   * La struttura della lingua del sito inizia al livello successivo sotto questa radice.
* **Annidamento struttura lingua**
   * Questo è il numero di livelli della struttura del contenuto sotto la **Radice di navigazione** che rappresentano la struttura della lingua del sito. Esempi:
      * `1` in genere significa che hai solo la scelta della lingua.
      * `2` in genere significa che hai una scelta di lingua e paese.
      * `3` in genere indica che si dispone di una scelta di lingua, paese e regione.

#### Esempio {#example}

Supponiamo che il contenuto sia simile al seguente:

```
/content
+-- wknd
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

Per il WKND del sito, è consigliabile inserire il componente Navigazione lingua in un modello di pagina come parte dell’intestazione. Una volta fatto parte del modello, è possibile impostare **Radice di navigazione** del componente su `/content/wknd`, dal momento che è da qui che inizia il contenuto localizzato per tale sito. È inoltre necessario impostare **Profondità struttura lingua** su `2`, poiché la struttura è di due livelli (paese e lingua).

Con il valore **Radice di navigazione**, il componente Lingua sa che dopo `/content/wknd` inizia la navigazione e può generare opzioni di navigazione nella lingua riconoscendo i due livelli successivi nella struttura del contenuto come struttura di navigazione della lingua del sito (come definito dal valore **Profondità struttura della lingua**).

Indipendentemente dalla pagina visualizzata dall’utente, il componente Navigazione lingua è in grado di trovare la pagina corrispondente in un’altra lingua, conoscendo la posizione della pagina corrente e lavorando all’indietro fino al livello principale, quindi inoltrando la pagina corrispondente.

### Scheda Stili {#styles-tab}

Il componente Navigazione lingua supporta il AEM [Sistema di stile](/help/get-started/authoring.md#component-styling).

## Finestra di dialogo Modifica {#edit-dialog}

In genere il componente Navigazione lingua deve essere aggiunto e configurato solo nei modelli di pagina di un sito. Tuttavia, se il componente Navigazione lingua deve essere aggiunto a una singola pagina di contenuto, la finestra di dialogo di modifica consente a un autore di contenuto di configurare gli stessi valori come descritto nella finestra di dialogo [progettazione](#design-dialog).

È inoltre possibile impostare un **ID**. Questa opzione consente di controllare l&#39;identificatore univoco del componente nell&#39;HTML e nel [Livello dati](/help/developing/data-layer/overview.md).

* Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
* Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
* La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

![Finestra di dialogo di modifica del componente Navigazione lingua](/help/assets/language-navigation-edit.png)
