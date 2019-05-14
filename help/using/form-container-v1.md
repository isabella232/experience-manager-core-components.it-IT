---
title: Componente Contenitore modulo (v 1)
seo-title: Componente Contenitore modulo (v 1)
description: Il componente Contenitore di componenti di componente core consente di creare moduli di invio semplici.
seo-description: Il componente Contenitore di componenti di componente core consente di creare moduli di invio semplici.
uuid: 075 d 83 ed-de 40-414 e-a 18 f -46 b 3 a 857 acba
content-type: riferimento
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: 800 c 064 e -2 ad 5-41 f 3-9 cef-b 025 a 555 efd 9
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# Componente Contenitore modulo (v 1){#form-container-component-v}

Il componente Contenitore di componenti di componente core consente di creare moduli di invio semplici.

## Utilizzo {#usage}

Il componente Contenitore di modulo ha abilitato la creazione di moduli e funzionalità semplici di invio delle informazioni supportando i moduli WCM semplici e utilizzando una struttura nidificata per consentire altri componenti modulo.

Utilizzando la [finestra di dialogo](form-container-v1.md#main-pars_title) di impostazione, l&#39;editor di contenuto può definire il tipo di trigger di invio del modulo action, dove deve essere memorizzato il contenuto inviato e se dovrebbe essere attivato un flusso di lavoro. L&#39;autore del modello può utilizzare la [finestra di dialogo](form-container-v1.md#main-pars_title_1995166862) di progettazione per definire i componenti e le relative mappature simili alla finestra di dialogo di progettazione per il contenitore di layout [standard nell&#39;editor modelli](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843).

## Versione e Compatibilità {#version-and-compatibility}

Questo documento descrive v 1 del componente Contenitore modulo, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità della release v 1 del componente Contenitore di modulo.

| Versione di AEM | Componente Contenitore modulo v 1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la v 1 del componente Contenitore modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Contenitore contenitore, vedere [il documento Componente](form-container.md) Contenitore contenitore.

## Finestra di dialogo Impostazioni {#settings-dialog}

La finestra di dialogo Impostazioni consente all&#39;autore del contenuto di definire le azioni da eseguire durante l&#39;invio del componente.

![](assets/chlimage_1.png)

A seconda del tipo **di azione selezionato**, le opzioni disponibili all&#39;interno del contenitore cambiano. I tipi di azioni disponibili sono:

* [E-mail](form-container-v1.md#main-pars_title_966511656)
* [Contenuto store](form-container-v1.md#main-pars_title_2065985840)
* [Invia ordine](form-container-v1.md#main-pars_title_686874527)
* [Aggiorna ordine](form-container-v1.md#main-pars_title_410109286)

A prescindere dal tipo, sono [disponibili impostazioni](form-container-v1.md#main-pars_title_375403046) generali per ogni azione.

### E-mail {#mail}

Quando il modulo viene inviato, il tipo di azione invia un messaggio e-mail a destinatari designati.

![](assets/chlimage_1-1.png)

* **Oggetto** : oggetto dell&#39;e-mail che verrà inviato all&#39;invio del modulo
* **From** - The from email address of the email that will be send on form submit
* **A** - Gli indirizzi dei destinatari che riceveranno un messaggio e-mail all&#39;invio del modulo
   * Tocca o fai clic sul **pulsante Aggiungi** per aggiungere altri indirizzi
   * Toccate o fate clic sul **pulsante Elimina** per rimuovere un indirizzo e-mail
* **CC** - Gli indirizzi dei destinatari che riceveranno un carbon copy riceveranno l&#39;e-mail inviata all&#39;invio del modulo
   * Tocca o fai clic sul **pulsante Aggiungi** per aggiungere altri indirizzi
   * Toccate o fate clic sul **pulsante Elimina** per rimuovere un indirizzo e-mail

### Contenuto store {#store-content}

Quando il modulo viene inviato, il contenuto del modulo verrà memorizzato in una posizione archivio designata.

![](assets/chlimage_1-2.png)

* **Percorso contenuto** - Percorso archivio contenuto in cui è memorizzato il contenuto inviato
* **Visualizza dati** : tocca o fai clic per visualizzare i dati inviati come JSON
* **Avvia flusso di lavoro** - Configura per avviare un flusso di lavoro con il contenuto memorizzato come payload all&#39;invio del modulo

### Invia ordine {#submit-order}

Quando il modulo viene inviato, l&#39;ordine viene inviato.

![](assets/chlimage_1-3.png)

### Aggiorna ordine {#update-order}

Quando il modulo viene inviato, l&#39;ordine viene aggiornato.

![](assets/chlimage_1-4.png)

### Impostazioni generali {#general-settings}

Indipendentemente dal tipo di azione selezionato, è sempre possibile definire una pagina di ringraziamento.

![](assets/chlimage_1-5.png)

L&#39;utente verrà reindirizzato alla pagina specificata dopo il completamento dell&#39;invio del modulo.

* Utilizzate la finestra di dialogo di selezione per selezionare una risorsa in AEM.
* Se la pagina di ringraziamento non è in AEM, specificate l&#39;URL assoluto. Gli URL non assoluti verranno interpretati in base ad AEM.
* Lasciate vuoto per visualizzare nuovamente il modulo dopo l&#39;invio.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire i componenti consentiti e le relative mappature per il contenitore, simile alla finestra di dialogo di progettazione per il [contenitore di layout standard nell&#39;editor modelli](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente relativa al componente [Contenitore modulo è disponibile su github](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container).

L&#39;intero progetto componenti core può essere scaricato da github.

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).
