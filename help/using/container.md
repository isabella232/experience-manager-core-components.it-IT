---
title: Componente contenitore
seo-title: Componente contenitore
description: 'null'
seo-description: Il componente Contenitore componenti core consente la creazione di un contenitore per più componenti aggiuntivi su una pagina.
uuid: ec807de9-f76c-4850-9ece-c3e439a1d626
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: f093f58e-9755-4a4f-803a-ab93a50e6870
translation-type: tm+mt
source-git-commit: 3e2e7a297c6ee1d6c8d092c619df8febdc900e25

---


# Componente contenitore{#container-component}

Il componente Contenitore componenti core consente la creazione di un contenitore per più componenti aggiuntivi su una pagina.

## Utilizzo {#usage}

Il componente Contenitore componenti core consente di creare un contenitore per più componenti aggiuntivi su una pagina e può essere utilizzato per raggruppare altri componenti e applicare uno stile o un layout comune.

* Le proprietà del contenitore possono essere selezionate nella finestra di dialogo [di](#configure-dialog)configurazione.
* I valori predefiniti per il componente Contenitore quando viene aggiunto a una pagina possono essere definiti nella finestra di dialogo [](#design-dialog)della progettazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente contenitore è v1, introdotto con la release 2.5.0 dei componenti core nel giugno 2019, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Contenitore ed esempi delle relative opzioni di configurazione, nonché dell’output HTML e JSON, visita la Libreria [](http://opensource.adobe.com/aem-core-wcm-components/library/container.html)Componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente contenitore [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/container/v1/container).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all'autore del contenuto di definire l'elemento contenitore e il suo funzionamento e la sua visualizzazione sulla pagina da parte di un visitatore.

![](assets/screen-shot-2019-06-21-13.59.26.png)

* **Layout** - Questa opzione definisce il comportamento o il comportamento del layout del componente Contenitore.
   * **Semplice** - Definisce un contenitore come una semplice raccolta di componenti
   * **Griglia** reattiva - Definisce un contenitore come griglia reattiva [AEM](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/responsive-layout.html)
* **ID** - Utilizzate questa opzione per definire l'attributo ID HTML da applicare al componente.
* **Colore** di sfondo - Definibile come valori RGB a forma libera o utilizzando il selettore colore, [a seconda della configurazione](#background-tab)
* **Immagine** di sfondo - Definisce un colore di sfondo per il contenitore, [a seconda della configurazione](#background-tab)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all'autore del modello di definire le opzioni disponibili per l'autore del contenuto che utilizza il componente Contenitore.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda Componenti **** consentiti viene utilizzata per definire quali componenti possono essere aggiunti al componente Contenitore dall’autore del contenuto come elementi.

La scheda Componenti consentiti funziona nello stesso modo della scheda con lo stesso nome quando si [definisce il criterio e le proprietà di un Contenitore di layout nell'Editor modelli.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Scheda Componenti predefiniti {#default-components-tab}

La scheda Componenti predefiniti consente di definire quale componente viene aggiunto al componente quando un particolare tipo di risorsa viene rilasciato sul contenitore, in modo simile alla [definizione dei componenti predefiniti nel modello](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html#EditingTemplatesTemplateAuthors)di pagina.

### Scheda Impostazioni reattive {#responsive-settings-tab}

![](assets/screen-shot-2019-06-21-09.33.03.png)

* **Colonne** - Definisce il numero di colonne nella griglia del contenitore risultante.

### Scheda Sfondo {#background-tab}

![](assets/screen-shot-2019-06-21-09.42.42.png)

* **Immagine di sfondo**
   * **Abilita immagine** di sfondo - Selezionate questa opzione per consentire all'autore del contenuto di definire un'immagine di sfondo per il contenitore.
* **Colore di sfondo**
   * **Attiva colore** di sfondo - Selezionate questa opzione per consentire all'autore del contenuto di definire un colore di sfondo per il contenitore.
   * **Solo** campioni - Selezionate questa opzione per consentire all’autore del contenuto di selezionare solo i campioni colore predefiniti per il colore di sfondo del contenitore.
      * Disponibile solo se **Attiva colore** di sfondo è selezionato
* **Campioni consentiti** - Consente di definire i colori predefiniti da cui l'autore del contenuto può selezionare il colore di sfondo del contenitore
   * Usate il pulsante **Aggiungi** per aggiungere un campione colore predefinito. Una volta aggiunta, una voce viene aggiunta all'elenco, che contiene le seguenti colonne:
   * **Valore** - Definire manualmente il colore tramite i valori RGB
      * Toccate o fate clic sul selettore colore per selezionare più facilmente un colore regolando i singoli valori RGB o definendo un valore esadecimale.
   * **Elimina** - Toccate o fate clic per eliminare un campione.
   * **Ridisponi** - Toccate o fate clic e trascinate per riordinare i campioni.

### Scheda Stili {#styles-tab}

Il componente Contenitore supporta AEM [Style System](authoring.md#component-styling).
