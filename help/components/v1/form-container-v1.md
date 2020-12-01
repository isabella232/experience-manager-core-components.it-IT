---
title: Componente contenitore modulo (v1)
description: Il componente Contenitore di moduli per componenti core consente la creazione di moduli di invio semplici.
index: n
translation-type: tm+mt
source-git-commit: 68472ab548fb6ebb443a06c12e7b37797a0c1302
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 3%

---


# Componente contenitore modulo (v1) {#form-container-component-v1}

Il componente Contenitore di moduli per componenti core consente la creazione di moduli di invio semplici.

## Utilizzo {#usage}

Il componente Contenitore modulo ha attivato la creazione di moduli e funzioni semplici per l&#39;invio di informazioni, supportando semplici moduli WCM e utilizzando una struttura nidificata per consentire l&#39;aggiunta di altri componenti del modulo.

Utilizzando la [finestra di dialogo di impostazione](#settings-dialog) l&#39;editor di contenuti può definire il tipo di azioni che attivano l&#39;invio del modulo, dove memorizzare il contenuto inviato e se avviare un flusso di lavoro. L&#39;autore del modello può utilizzare la finestra di dialogo [progettazione](#design-dialog) per definire i componenti allow e le relative mappature in modo simile alla finestra di dialogo di progettazione per il contenitore di layout [standard nell&#39;editor modelli](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la v1 del componente Contenitore modulo, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è elencata la compatibilità di v1 del componente Contenitore modulo.

| Versione di AEM | Componente contenitore modulo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Contenitore modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Contenitore modulo, vedere il documento [Componente contenitore modulo](/help/components/forms/form-container.md).

## Finestra di dialogo Impostazioni {#settings-dialog}

La finestra di dialogo delle impostazioni consente all’autore del contenuto di definire le azioni da eseguire quando il componente viene inviato.

![](/help/assets/chlimage_1.png)

A seconda del **Tipo di azione** selezionato, le opzioni disponibili all&#39;interno del contenitore cambieranno. I tipi di azione disponibili sono:

* [E-mail](#mail)
* [Contenuto store](#store-content)
* [Invia ordine](#submit-order)
* [Aggiorna ordine](#update-order)

Indipendentemente dal tipo, esistono [impostazioni generali](#general-settings) che si applicano a ogni azione.

### E-mail {#mail}

Quando il modulo viene inviato, il tipo di azione e-mail invierà un messaggio e-mail ai destinatari designati.

![](/help/assets/chlimage_1-1.png)

* **Oggetto**  - Oggetto dell&#39;e-mail che verrà inviata all&#39;invio del modulo
* **Da**  - L&#39;indirizzo e-mail del messaggio e-mail che verrà inviato all&#39;invio del modulo
* **A**  - Gli indirizzi dei destinatari che riceveranno un&#39;e-mail al momento dell&#39;invio del modulo
   * Toccate o fate clic sul pulsante **Aggiungi** per aggiungere altri indirizzi
   * Toccate o fate clic sul pulsante **Elimina** per rimuovere un indirizzo e-mail
* **CC** - Gli indirizzi dei destinatari che riceveranno una copia in carbonio dell&#39;e-mail inviata al momento dell&#39;invio del modulo
   * Toccate o fate clic sul pulsante **Aggiungi** per aggiungere altri indirizzi
   * Toccate o fate clic sul pulsante **Elimina** per rimuovere un indirizzo e-mail

### Contenuto store {#store-content}

Quando il modulo viene inviato, il contenuto del modulo viene memorizzato in una posizione archivio designata.

![](/help/assets/chlimage_1-2.png)

* **Percorso**  contenuto - Percorso dell&#39;archivio dei contenuti in cui è memorizzato il contenuto inviato
* **Visualizza dati**  - Toccate o fate clic per visualizzare i dati inviati memorizzati come JSON
* **Avvia flusso di lavoro** : configura per avviare un flusso di lavoro con il contenuto memorizzato come payload al momento dell&#39;invio del modulo

### Invia ordine {#submit-order}

Quando il modulo viene inviato, l&#39;ordine viene inviato.

![](/help/assets/chlimage_1-3.png)

### Aggiorna ordine {#update-order}

Quando il modulo viene inviato, l&#39;ordine viene aggiornato.

![](/help/assets/chlimage_1-4.png)

### Impostazioni generali {#general-settings}

Indipendentemente dal tipo di azione selezionato, è sempre possibile definire una pagina di ringraziamento.

![](/help/assets/chlimage_1-5.png)

L&#39;utente verrà reindirizzato alla pagina specificata dopo il completamento dell&#39;invio del modulo.

* Utilizzare la finestra di dialogo di selezione per selezionare una risorsa all&#39;interno di AEM.
* Se la pagina di ringraziamento non è AEM, specificate l’URL assoluto. Gli URL non assoluti verranno interpretati in relazione ai AEM.
* Lasciare vuoto per visualizzare nuovamente il modulo dopo l&#39;invio.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire i componenti consentiti e le relative mappature per il contenitore, in modo simile alla finestra di dialogo di progettazione per il contenitore di layout [standard nell&#39;editor modelli](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Contenitore moduli [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).
