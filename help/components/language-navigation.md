---
title: Componente di navigazione lingua
description: Il componente Navigazione lingua fornisce una navigazione in lingua/paese per un sito, in modo che i visitatori possano passare alla stessa pagina in un’altra impostazione internazionale.
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 2%

---


# Componente di navigazione della lingua{#language-navigation-component}

Il componente Navigazione lingua fornisce una navigazione in lingua/paese per un sito, in modo che i visitatori possano passare alla stessa pagina in impostazioni internazionali diverse.

## Utilizzo {#usage}

I siti web sono spesso disponibili in più lingue per diverse aree geografiche. Il componente di navigazione della lingua consente a un visitatore di visualizzare la stessa pagina in lingue/impostazioni internazionali diverse. Quindi, se siete lettori nella versione tedesca svizzera del sito web, è possibile facilmente passare alla versione inglese USA della stessa pagina. Il componente Navigazione lingua gestisce la comprensione della struttura della lingua del sito e trova automaticamente la pagina corrispondente.

* Per un esempio del funzionamento della funzione di localizzazione del componente di navigazione in lingua, consulta [la sezione seguente](#example).
* Per un esempio del funzionamento congiunto delle funzioni di localizzazione degli altri componenti core, consulta la pagina [Funzioni di localizzazione dei componenti core](/help/get-started/localization.md) .

La [finestra di dialogo di modifica](#edit-dialog) consente di definire la directory principale globale di navigazione del sito e di specificare la profondità della struttura in cui deve essere effettuata la navigazione. Utilizzando la finestra di dialogo [progettazione](#design-dialog), l&#39;autore del modello può impostare i valori predefiniti per le stesse opzioni.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente di navigazione in lingua è la v1, introdotta con la versione 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente Navigazione lingua e dei relativi output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_langnav).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente di navigazione in lingua [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_langnav_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di modifica consente di definire la directory principale di navigazione del sito globale e di specificare la profondità della struttura in cui deve essere effettuata la navigazione.

In genere queste configurazioni devono essere eseguite solo a livello di modello di pagina. Tuttavia, possono essere modificati a livello di pagina tramite la finestra di dialogo [modifica](#edit-dialog).

### Scheda Proprietà {#properties-tab}

![Finestra di dialogo di progettazione del componente Navigazione lingua](/help/assets/language-navigation-design.png)

* **Directory principale di navigazione**
   * È qui che dovrebbe iniziare la navigazione in lingua del sito.
   * La struttura della lingua del sito inizia al livello successivo sotto questa radice.
* **Annidamento struttura lingua**
   * Questo è il numero di livelli della struttura del contenuto sotto la **Radice di navigazione** che rappresentano la struttura della lingua del sito. Esempi:
      * `1` in genere significa che hai solo la scelta della lingua.
      * `2` in genere significa che hai una scelta di lingua e paese.
      * `3` in genere significa che si dispone di una scelta di lingua, paese e regione.

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

Per il WKND del sito, è probabile che si desideri inserire il componente Navigazione lingua in un modello di pagina come parte dell’intestazione. Una volta parte del modello, è possibile impostare la **Radice di navigazione** del componente su `/content/wknd`, in quanto è da lì che inizia il contenuto localizzato per quel sito. Imposta anche **Profondità struttura lingua** su `2` poiché la struttura è di due livelli (paese e lingua).

Con il valore **Radice di navigazione**, il componente Lingua sa che dopo `/content/wknd` la navigazione inizia e può generare opzioni di navigazione nella lingua riconoscendo i due livelli successivi nella struttura del contenuto come struttura di navigazione della lingua del sito (come definito dal valore **Profondità della struttura della lingua** ).

Indipendentemente dalla pagina visualizzata dall’utente, il componente Navigazione lingua è in grado di trovare la pagina corrispondente in un’altra lingua, conoscendo la posizione della pagina corrente e lavorando all’indietro fino alla pagina principale, quindi inoltrandola alla pagina corrispondente.

### Scheda Stili {#styles-tab}

Il componente Navigazione lingua supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

## Finestra di dialogo Modifica {#edit-dialog}

In genere il componente Navigazione lingua deve essere aggiunto e configurato solo nei modelli di pagina di un sito. Tuttavia, se è necessario aggiungere il componente Navigazione lingua a una singola pagina di contenuto, la finestra di dialogo di modifica consente all’autore di contenuti di configurare gli stessi valori come descritto nella [finestra di dialogo di progettazione](#design-dialog).

Inoltre puoi impostare un **ID**. Questa opzione consente di controllare l&#39;identificatore univoco del componente nell&#39;HTML e nel [Livello dati](/help/developing/data-layer/overview.md).

* Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
* Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
* La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

![Finestra di dialogo di modifica del componente Navigazione lingua](/help/assets/language-navigation-edit.png)

## Livello dati client di Adobe {#data-layer}

Il componente Navigazione lingua supporta il [Livello dati client di Adobe.](/help/developing/data-layer/overview.md)
