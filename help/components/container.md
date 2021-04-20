---
title: Componente contenitore
description: Il componente Contenitore di componenti core consente la creazione di un contenitore per più componenti aggiuntivi su una pagina.
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 2%

---


# Componente contenitore{#container-component}

Il componente Contenitore di componenti core consente la creazione di un contenitore per più componenti aggiuntivi su una pagina.

## Utilizzo {#usage}

Il componente Contenitore di componenti core consente la creazione di un contenitore per più componenti aggiuntivi su una pagina e può essere utilizzato per raggruppare altri componenti e applicare uno stile o un layout comune.

* Le proprietà del contenitore possono essere selezionate nella finestra di dialogo [configura](#configure-dialog).
* Le impostazioni predefinite per il componente Contenitore quando lo si aggiunge a una pagina possono essere definite nella finestra di dialogo di progettazione [a1/>.](#design-dialog)

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Contenitore è la v1, introdotta con la versione 2.5.0 dei componenti core a giugno 2019, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente Contenitore e dell’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_container) .

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente contenitore [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_container_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire l’elemento contenitore e il suo comportamento e la sua visualizzazione sulla pagina da parte di un visitatore.

![Finestra di dialogo Modifica del componente contenitore](/help/assets/container-edit.png)

* **Layout** : questa opzione definisce il comportamento o il comportamento del layout del componente Contenitore.
   * **Semplice**  - Definisce un contenitore come una semplice raccolta di componenti
   * **Griglia reattiva** : definisce un contenitore come un layout reattivo  [AEM](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)
* **Colore di sfondo**  - Definibile come valori RGB a forma libera o utilizzando il selettore colore,  [a seconda della configurazione](#background-tab)
* **Immagine di sfondo**  - Definisce un colore di sfondo per il contenitore,   [a seconda della configurazione](#background-tab)
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore del contenuto che utilizza il componente Contenitore .

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** viene utilizzata per definire quali componenti possono essere aggiunti dall’autore del contenuto come elementi al componente contenitore.

La scheda Componenti consentiti funziona allo stesso modo della scheda dello stesso nome quando [definisci i criteri e le proprietà di un contenitore di layout nell’Editor modelli.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Scheda Componenti predefiniti {#default-components-tab}

La scheda Componenti predefiniti consente di definire quale componente viene aggiunto al componente quando un particolare tipo di risorsa viene rilasciato sul contenitore, in modo analogo a [come vengono definiti i componenti predefiniti nel modello di pagina](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

### Scheda Impostazioni reattive {#responsive-settings-tab}

![Scheda delle impostazioni reattive della finestra di dialogo di progettazione del componente Contenitore](/help/assets/container-design-responsive.png)

* **Colonne**  - Definisce il numero di colonne nella griglia del contenitore risultante.

### Scheda Sfondo {#background-tab}

![Scheda Sfondo della finestra di dialogo di progettazione del componente Contenitore](/help/assets/container-design-background.png)

* **Immagine di sfondo**
   * **Abilita immagine di sfondo** : seleziona questa opzione per consentire all’autore del contenuto di definire un’immagine di sfondo per il contenitore.
* **Colore di sfondo**
   * **Attiva colore**  di sfondo: seleziona questa opzione per consentire all’autore del contenuto di definire un colore di sfondo per il contenitore.
   * **Solo campioni** : seleziona questa opzione per consentire solo all’autore del contenuto di selezionare da campioni di colore predefiniti per il colore di sfondo del contenitore.
      * Disponibile solo se è selezionato **Abilita colore di sfondo**
* **Campioni consentiti** : consente di definire colori predefiniti da cui l’autore del contenuto può selezionare il colore di sfondo del contenitore
   * Utilizza il pulsante **Aggiungi** per aggiungere un campione di colore predefinito. Una volta aggiunta, una voce viene aggiunta all’elenco, che contiene le colonne seguenti:
   * **Valore**  - Definisci il colore manualmente tramite i valori RGB
      * Tocca o fai clic sul selettore colore per selezionare più facilmente un colore regolando i singoli valori RGB o definendo un valore esadecimale.
   * **Elimina** : tocca o fai clic per eliminare un campione.
   * **Ridisponi**  - Tocca o fai clic e trascina per ridisporre l’ordine dei campioni.

### Scheda Stili {#styles-tab}

Il componente Contenitore supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).
