---
title: Componente Navigazione lingua
description: Il componente Navigazione lingua fornisce una navigazione per lingua/paese in un sito, consentendo ai visitatori di visualizzare la stessa pagina in una lingua diversa.
role: Architect, Developer, Admin, User
exl-id: 10b218b4-c439-4a0f-a46f-0b15d78b0360
source-git-commit: 28409185f2e46a30fa588b3f92b83b2fa05de96d
workflow-type: ht
source-wordcount: '957'
ht-degree: 100%

---

# Componente Navigazione lingua{#language-navigation-component}

Il componente Navigazione lingua fornisce una navigazione per lingua/paese in un sito, consentendo ai visitatori di visualizzare la stessa pagina in una lingua diversa.

## Utilizzo {#usage}

I siti web sono spesso disponibili in più lingue per diverse aree geografiche. Il componente Navigazione lingua consente a un visitatore di visualizzare la stessa pagina in diverse lingue. Pertanto, un lettore che si trovi nella versione in tedesco svizzero del sito, può passare facilmente passare alla versione italiana della stessa pagina. Il componente Navigazione lingua gestisce la comprensione della struttura delle lingue del sito e trova automaticamente la pagina corrispondente.

* Per un esempio della funzione di localizzazione del componente Navigazione lingua, vedi [la sezione che segue](#example).
* Per un esempio dell’interazione delle funzioni di localizzazione dei Componenti core, visita la pagina [Funzioni di localizzazione dei Componenti core](/help/get-started/localization.md).

La [finestra di dialogo per modifica](#edit-dialog) consente di definire la directory principale di navigazione globale del sito e specificare fino a che profondità nella struttura può arrivare la navigazione. Utilizzando la [finestra di dialogo per progettazione](#design-dialog), l’autore del modello può impostare i valori predefiniti per le stesse opzioni.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Navigazione lingua è la versione 2, introdotta con la versione 2.18.0 dei Componenti core a febbraio 2022, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | - | Compatibile | Compatibile |
| [v1](v1/language-navigation.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Navigazione lingua e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_langnav_it).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Navigazione lingua [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_langnav_v1_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente di definire la directory principale di navigazione globale del sito e specificare fino a che profondità nella struttura può arrivare la navigazione.

In genere, queste configurazioni devono essere eseguite solo a livello di modello della pagina. Tuttavia, possono essere modificate anche livello di pagina tramite la [finestra di dialogo per modifica](#edit-dialog).

### Scheda Proprietà {#properties-tab}

![Finestra di dialogo per progettazione del componente Navigazione lingua](/help/assets/language-navigation-design.png)

* **Directory principale di navigazione**
   * La navigazione nelle lingue del sito inizia da qui.
   * La struttura delle lingue del sito inizia al livello immediatamente successivo sotto la directory principale di navigazione.
* **Annidamento struttura lingua**
   * È il numero di livelli della struttura del contenuto sotto la **Directory di navigazione principale** che rappresentano la struttura delle lingue del sito. Esempi:
      * `1` in genere significa che hai solo la scelta della lingua.
      * `2` in genere significa che hai la scelta di lingua e paese.
      * `3` in genere significa che hai la scelta di lingua, paese e area geografica.

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

Per il WKND del sito, è probabile che tu voglia inserire il componente Navigazione lingua nel modello di una pagina come parte dell’intestazione. Una volta inserito nel modello, è possibile impostare **Directory principale di navigazione** del componente su `/content/wknd`, in quanto è da lì che inizia il contenuto localizzato di quel sito. Puoi anche impostare **Annidamento struttura lingua** su `2`, poiché la struttura è di due livelli (paese e lingua).

Con il valore di **Directory principale di navigazione**, il componente Navigazione lingua sa che dopo `/content/wknd` inizia la navigazione e può generare opzioni di navigazione nelle lingue riconoscendo i due livelli successivi nella struttura del contenuto come struttura di navigazione nelle lingue del sito (come definito dal valore di **Annidamento struttura lingua**).

Indipendentemente dalla pagina che un utente sta visualizzando, il componente Navigazione lingua è in grado di trovare la pagina localizzata corrispondente conoscendo la posizione della pagina corrente, risalendo all’indietro fino alla directory principale e quindi in avanti fino alla pagina corrispondente.

### Scheda Stili {#styles-tab}

Il componente Navigazione lingua supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

## Finestra di dialogo per modifica {#edit-dialog}

### Scheda Proprietà {#properties-tab-edit}

In genere il componente Navigazione lingua deve essere aggiunto e configurato solo nei modelli di pagina di un sito. Tuttavia, se è necessario aggiungere il componente Navigazione lingua a una singola pagina di contenuto, la finestra di dialogo per modifica consente all’autore di contenuto di configurare gli stessi valori come descritto nella [finestra di dialogo per progettazione](#design-dialog)

Inoltre, si può anche impostare un **ID**. Questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e nel [Data Layer](/help/developing/data-layer/overview.md).

* Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
* Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
* La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

![Finestra di dialogo per modifica del componente Navigazione lingua](/help/assets/language-navigation-edit.png)

### Scheda Accessibilità {#accessibility-tab}

* **Etichetta** - Questa opzione deve essere definita se sulla pagina è presente più di una navigazione lingua per impostare l’attributo dell’etichetta aria del componente.

![Scheda Accesso facilitato alla navigazione lingua](/help/assets/language-navigation-edit-accessibility.png)

### Scheda Stili {#styles-tab-edit}

Il componente Navigazione lingua supporta il [sistema di stili di AEM](/help/get-started/authoring.md#component-styling).

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nella [finestra di dialogo di progettazione](#design-dialog) affinché il menu a discesa sia disponibile.

![Scheda Stili della finestra di dialogo di modifica del componente Navigazione lingua](/help/assets/language-navigation-edit-styles.png)

## Adobe Client Data Layer {#data-layer}

Il componente Navigazione lingua supporta [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
