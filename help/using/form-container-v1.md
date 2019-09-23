---
title: Componente contenitore modulo (v1)
seo-title: Componente contenitore modulo (v1)
description: Il componente Contenitore di moduli per componenti core consente la creazione di moduli di invio semplici.
seo-description: Il componente Contenitore di moduli per componenti core consente la creazione di moduli di invio semplici.
uuid: 075d83ed-de40-414e-a18f-46b3a857acba
content-type: riferimento
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 800c064e-2ad5-41f3-9cef-b025a555efd9
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# Form Container Component (v1){#form-container-component-v}

Il componente Contenitore di moduli per componenti core consente la creazione di moduli di invio semplici.

## Utilizzo {#usage}

Il componente Contenitore modulo ha attivato la creazione di moduli e funzioni semplici per l'invio di informazioni, supportando semplici moduli WCM e utilizzando una struttura nidificata per consentire l'aggiunta di altri componenti modulo.

Utilizzando la finestra di dialogo [di](form-container-v1.md#main-pars_title) impostazione, l'Editor contenuto può definire il tipo di attivazione dell'invio del modulo, dove memorizzare il contenuto inviato e se avviare un flusso di lavoro. L’autore del modello può utilizzare la finestra di dialogo [di](form-container-v1.md#main-pars_title_1995166862) progettazione per definire i componenti allow e le relative mappature in modo simile alla finestra di dialogo di progettazione per il contenitore di layout [standard nell’editor](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843)modelli.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la v1 del componente Contenitore di moduli, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è elencata la compatibilità di v1 del componente Contenitore modulo.

| Versione di AEM | Componente contenitore modulo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Contenitore modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Contenitore modulo, vedere il documento del componente [Contenitore](form-container.md) modulo.

## Finestra di dialogo Impostazioni {#settings-dialog}

La finestra di dialogo delle impostazioni consente all’autore del contenuto di definire le azioni da eseguire quando il componente viene inviato.

![](assets/chlimage_1.png)

A seconda del tipo **di** azione selezionato, le opzioni disponibili all'interno del contenitore cambiano. I tipi di azione disponibili sono:

* [E-mail](form-container-v1.md#main-pars_title_966511656)
* [Contenuto store](form-container-v1.md#main-pars_title_2065985840)
* [Invia ordine](form-container-v1.md#main-pars_title_686874527)
* [Aggiorna ordine](form-container-v1.md#main-pars_title_410109286)

Indipendentemente dal tipo, esistono impostazioni [](form-container-v1.md#main-pars_title_375403046) generali applicabili a ogni azione.

### E-mail {#mail}

Quando il modulo viene inviato, il tipo di azione e-mail invierà un messaggio e-mail ai destinatari designati.

![](assets/chlimage_1-1.png)

* **Oggetto** - Oggetto dell'e-mail che verrà inviata all'invio del modulo
* **Da** - L'indirizzo e-mail del messaggio e-mail che verrà inviato all'invio del modulo
* **A** - Gli indirizzi dei destinatari che riceveranno un'e-mail all'invio del modulo
   * Toccate o fate clic sul pulsante **Aggiungi** per aggiungere altri indirizzi
   * Toccate o fate clic sul pulsante **Elimina** per rimuovere un indirizzo e-mail
* **CC** - Gli indirizzi dei destinatari che riceveranno una copia del messaggio e-mail inviato al momento dell'invio del modulo
   * Toccate o fate clic sul pulsante **Aggiungi** per aggiungere altri indirizzi
   * Toccate o fate clic sul pulsante **Elimina** per rimuovere un indirizzo e-mail

### Contenuto store {#store-content}

Quando il modulo viene inviato, il contenuto del modulo viene memorizzato in una posizione archivio designata.

![](assets/chlimage_1-2.png)

* **Percorso** contenuto - Percorso dell'archivio dei contenuti in cui è memorizzato il contenuto inviato
* **Visualizza dati** - Toccate o fate clic per visualizzare i dati inviati memorizzati come JSON
* **Avvia flusso di lavoro** - Configura l'avvio di un flusso di lavoro con il contenuto memorizzato come payload al momento dell'invio del modulo

### Invia ordine {#submit-order}

Quando il modulo viene inviato, l'ordine viene inviato.

![](assets/chlimage_1-3.png)

### Aggiorna ordine {#update-order}

Quando il modulo viene inviato, l'ordine viene aggiornato.

![](assets/chlimage_1-4.png)

### Impostazioni generali {#general-settings}

Indipendentemente dal tipo di azione selezionato, è sempre possibile definire una pagina di ringraziamento.

![](assets/chlimage_1-5.png)

L'utente verrà reindirizzato alla pagina specificata dopo il completamento dell'invio del modulo.

* Utilizzate la finestra di dialogo di selezione per selezionare una risorsa in AEM.
* Se la pagina di ringraziamento non è in AEM, specificate l’URL assoluto. Gli URL non assoluti verranno interpretati in relazione ad AEM.
* Lasciare vuoto per visualizzare nuovamente il modulo dopo l'invio.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all'autore del modello di definire i componenti consentiti e le relative mappature per il contenitore, in modo simile alla finestra di dialogo di progettazione per il contenitore di layout [standard nell'editor](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843)modelli.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Contenitore moduli [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.
