---
title: Componente contenitore
description: Il componente Contenitore componenti core consente la creazione di un contenitore per più componenti aggiuntivi su una pagina.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 2%

---


# Componente contenitore{#container-component}

Il componente Contenitore componenti core consente la creazione di un contenitore per più componenti aggiuntivi su una pagina.

## Utilizzo {#usage}

Il componente Contenitore componenti core consente di creare un contenitore per più componenti aggiuntivi su una pagina e può essere utilizzato per raggruppare altri componenti e applicare uno stile o un layout comune.

* Le proprietà del contenitore possono essere selezionate nella finestra di dialogo di [configurazione](#configure-dialog).
* Le impostazioni predefinite per il componente contenitore quando viene aggiunto a una pagina possono essere definite nella finestra di dialogo di progettazione [a1/>.](#design-dialog)

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente contenitore è v1, introdotto con la release 2.5.0 dei componenti core nel giugno 2019, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente Contenitore ed esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visita la [Libreria componenti](https://adobe.com/go/aem_cmp_library_container).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente contenitore [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_container_v1).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all&#39;autore del contenuto di definire l&#39;elemento contenitore e il suo funzionamento e la sua visualizzazione sulla pagina da parte di un visitatore.

![Finestra di dialogo di modifica del componente contenitore](/help/assets/container-edit.png)

* **Layout** : questa opzione definisce il comportamento o il comportamento del layout del componente Contenitore.
   * **Semplice**  - Definisce un contenitore come una semplice raccolta di componenti
   * **Griglia**  reattiva - Definisce un contenitore come  [AEM layout reattivo](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)
* **Colore**  di sfondo - Definibile come valori RGB a forma libera o utilizzando il selettore colore,  [a seconda della configurazione](#background-tab)
* **Immagine**  di sfondo - Definisce un colore di sfondo per il contenitore,   [a seconda della configurazione](#background-tab)
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire le opzioni disponibili per l&#39;autore del contenuto che utilizza il componente Contenitore.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** viene utilizzata per definire quali componenti possono essere aggiunti al componente contenitore dall&#39;autore del contenuto come elementi.

La scheda Componenti consentiti funziona nello stesso modo della scheda con lo stesso nome quando si definisce il criterio e le proprietà di un Contenitore di layout nell&#39;Editor modelli.[](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Scheda Componenti predefiniti {#default-components-tab}

La scheda Componenti predefiniti viene utilizzata per definire quale componente viene aggiunto al componente quando un particolare tipo di risorsa viene rilasciato sul contenitore, in modo simile a [come vengono definiti i componenti predefiniti nel modello di pagina](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

### Scheda Impostazioni reattive {#responsive-settings-tab}

![Scheda Impostazioni reattive della finestra di dialogo di progettazione del componente Contenitore](/help/assets/container-design-responsive.png)

* **Colonne**  - Definisce il numero di colonne nella griglia del contenitore risultante.

### Scheda Sfondo {#background-tab}

![Scheda Sfondo della finestra di dialogo di progettazione del componente Contenitore](/help/assets/container-design-background.png)

* **Immagine di sfondo**
   * **Abilita immagine**  di sfondo: selezionate questa opzione per consentire all&#39;autore del contenuto di definire un&#39;immagine di sfondo per il contenitore.
* **Colore di sfondo**
   * **Attiva colore**  di sfondo: selezionate questa opzione per consentire all&#39;autore del contenuto di definire un colore di sfondo per il contenitore.
   * **Solo**  campioni: selezionate questa opzione per consentire all’autore del contenuto di selezionare solo i campioni colore predefiniti per il colore di sfondo del contenitore.
      * Disponibile solo se è selezionata l&#39;opzione **Attiva colore di sfondo**
* **Campioni consentiti**  - Consente di definire i colori predefiniti da cui l’autore del contenuto può selezionare il colore di sfondo del contenitore
   * Utilizzare il pulsante **Aggiungi** per aggiungere un campione colore predefinito. Una volta aggiunta, una voce viene aggiunta all&#39;elenco, che contiene le seguenti colonne:
   * **Valore**  - Definite il colore manualmente tramite i valori RGB
      * Toccate o fate clic sul selettore colore per selezionare più facilmente un colore regolando i singoli valori RGB o definendo un valore esadecimale.
   * **Elimina**  - Toccate o fate clic per eliminare un campione.
   * **Ridisponi**  - Toccate o fate clic e trascinate per riordinare i campioni.

### Scheda Stili {#styles-tab}

Il componente contenitore supporta il AEM [Sistema di stile](/help/get-started/authoring.md#component-styling).
