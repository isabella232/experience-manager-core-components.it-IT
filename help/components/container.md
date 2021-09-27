---
title: Componente Contenitore
description: Il componente core Contenitore consente la creazione di un contenitore per più componenti aggiuntivi su una pagina.
role: Architect, Developer, Admin, User
exl-id: 53c7190d-44cb-42ff-bc1a-483c7875bcf8
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '792'
ht-degree: 100%

---

# Componente Contenitore{#container-component}

Il componente core Contenitore consente la creazione di un contenitore per più componenti aggiuntivi su una pagina.

## Utilizzo {#usage}

Il componente core Contenitore consente la creazione di un contenitore per più componenti aggiuntivi su una pagina e può essere utilizzato per raggruppare altri componenti e applicare uno stile o un layout comune.

* Le proprietà del Contenitore possono essere selezionate nella [finestra di dialogo per configurazione](#configure-dialog).
* Le impostazioni predefinite del componente Contenitore, quando lo si aggiunge a una pagina, possono essere definite nella [finestra di dialogo per progettazione](#design-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Contenitore è la v1, introdotta con la versione 2.5.0 dei Componenti core a giugno 2019, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Contenitore e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_container_it).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Contenitore [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_container_v1_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuto di definire l’elemento Contenitore e il suo comportamento e aspetto nei confronti di chi visita la pagina.

![Finestra di dialogo per modifica del componente Contenitore](/help/assets/container-edit.png)

* **Layout**: questa opzione definisce il comportamento o il comportamento del layout del componente Contenitore.
   * **Semplice**: definisce un contenitore come una semplice raccolta di componenti
   * **Griglia reattiva**: definisce un contenitore come un [layout reattivo AEM](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)
* **Colore sfondo**: definibile utilizzando i valori RGB in forma libera o utilizzando il selettore colore, [a seconda della configurazione](#background-tab)
* **Immagine di sfondo**: definisce il colore di sfondo del Contenitore, [a seconda della configurazione](#background-tab)
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore di contenuto quando utilizza questo componente.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** viene utilizzata per definire quali componenti possono essere aggiunti dall’autore di contenuto come elementi del componente Contenitore.

La scheda Componenti consentiti funziona come la scheda con lo stesso nome utilizzata per [definire i criteri e le proprietà di un Contenitore layout nell’editor di modelli.](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Scheda Componenti standard {#default-components-tab}

La scheda Componenti standard consente di definire quale componente viene aggiunto al componente Contenitore quando un particolare tipo di risorsa viene rilasciato sul Contenitore stesso, in modo analogo a [come vengono definiti i componenti predefiniti nel modello di pagina](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/sites/authoring/features/templates.html).

### Scheda Impostazioni reattive {#responsive-settings-tab}

![Scheda Impostazioni reattive della finestra di dialogo per progettazione del componente Contenitore](/help/assets/container-design-responsive.png)

* **Colonne**: definisce il numero di colonne nella griglia del Contenitore risultante.

### Scheda Sfondo {#background-tab}

![Scheda Sfondo della finestra di dialogo per progettazione del componente Contenitore](/help/assets/container-design-background.png)

* **Immagine di sfondo**
   * **Abilita immagine di sfondo**: seleziona questa opzione per consentire all’autore di contenuto di definire un’immagine di sfondo per il Contenitore.
* **Colore sfondo**
   * **Abilita colore di sfondo**: seleziona questa opzione per consentire all’autore di contenuto di definire un colore di sfondo per il Contenitore.
   * **Solo campioni**: seleziona questa opzione per consentire all’autore di contenuto di selezionare il colore di sfondo del Contenitore solo da campioni di colore predefiniti.
      * Disponibile solo se è selezionata l’opzione **Abilita colore di sfondo**
* **Campioni consentiti**: consente di definire colori predefiniti da cui l’autore di contenuto può selezionare il colore di sfondo del Contenitore
   * Utilizza il pulsante **Aggiungi** per aggiungere un campione di colore predefinito. Una volta aggiunto, all’elenco viene aggiunta una voce che contiene le seguenti colonne:
   * **Valore**: consente di definire manualmente il colore utilizzando i valori RGB
      * Tocca o fai clic sul selettore colore per selezionare più facilmente un colore regolando i singoli valori RGB o definendo un valore esadecimale.
   * **Elimina**: tocca o fai clic su un campione per eliminarlo.
   * **Ridisponi**: tocca o fai clic e trascina per modificare l’ordine dei campioni.

### Scheda Stili {#styles-tab}

Il componente Contenitore supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
