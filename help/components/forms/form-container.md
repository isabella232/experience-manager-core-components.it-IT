---
title: Componente contenitore modulo
description: Il componente Contenitore di moduli per componenti core consente la creazione di moduli di invio semplici.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Componente contenitore modulo {#form-container-component}

Il componente Contenitore di moduli per componenti core consente la creazione di moduli di invio semplici.

## Utilizzo {#usage}

Il componente Contenitore modulo consente di creare moduli e funzioni semplici per l&#39;invio di informazioni, mediante il supporto di semplici moduli WCM e l&#39;uso di una struttura nidificata per consentire l&#39;aggiunta di altri componenti modulo.

Utilizzando la finestra di dialogo [di](#configure-dialog) configurazione, l&#39;Editor contenuto può definire l&#39;azione attivata dall&#39;invio del modulo, dove memorizzare il contenuto inviato e se avviare un flusso di lavoro. L’autore del modello può utilizzare la finestra di dialogo [di](#design-dialog) progettazione per definire i componenti consentiti e le relative mappature in modo simile alla finestra di dialogo di progettazione per il contenitore di layout [standard nell’editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)modelli.

>[!NOTE]
>
>I componenti core Modulo contenitore Component supportano solo l’uso di componenti core per i componenti modulo (pulsante, testo, nascosti, ecc.). L&#39;utilizzo di componenti [](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) di base per i moduli all&#39;interno del contenitore dei moduli dei componenti core (e viceversa) non è supportato.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Contenitore modulo è v2, introdotta con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM come servizio cloud |
|--- |--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-container-v1.md) | Compatibile | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Contenitore moduli [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_container_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire le azioni da eseguire quando il componente viene inviato.

![](/help/assets/screen_shot_2018-01-12at122046.png)

A seconda del tipo **di** azione selezionato, le opzioni disponibili all&#39;interno del contenitore cambiano. I tipi di azione disponibili sono:

* [E-mail](#mail)
* [Contenuto store](#store-content)
* [Invia ordine](#submit-order)
* [Aggiorna ordine](#update-order)

Indipendentemente dal tipo, esistono impostazioni [](#general-settings) generali applicabili a ogni azione.

### E-mail {#mail}

Quando il modulo viene inviato, il tipo di azione e-mail invierà un messaggio e-mail ai destinatari designati.

![](/help/assets/screen_shot_2018-01-12at122554.png)

* **Oggetto** L&#39;oggetto dell&#39;e-mail che verrà inviata all&#39;invio del modulo
* **Da** L&#39;indirizzo e-mail del messaggio e-mail che verrà inviato all&#39;invio del modulo
* **A** Gli indirizzi dei destinatari che riceveranno un&#39;e-mail all&#39;invio del modulo

   * Toccate o fate clic sul pulsante **Aggiungi** per aggiungere altri indirizzi
   * Toccate o fate clic sul pulsante **Elimina** per rimuovere un indirizzo e-mail
* **CC** Gli indirizzi dei destinatari che riceveranno una copia in carbonio dell&#39;e-mail inviata al momento dell&#39;invio del modulo
   * Toccate o fate clic sul pulsante **Aggiungi** per aggiungere altri indirizzi
   * Toccate o fate clic sul pulsante **Elimina** per rimuovere un indirizzo e-mail

### Contenuto store {#store-content}

Quando il modulo viene inviato, il contenuto del modulo viene memorizzato in una posizione archivio designata.

![](/help/assets/screen_shot_2018-01-12at122538.png)

* **Percorso** contenuto Percorso archivio Contenuto percorso in cui viene memorizzato il contenuto inviato
* **Visualizza dati** Tocca o fai clic per visualizzare i dati inviati memorizzati come JSON
* **Avvia flusso di lavoro** Configura per avviare un flusso di lavoro con il contenuto memorizzato come payload al momento dell’invio del modulo

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

* Utilizzate la finestra di dialogo di selezione per selezionare una risorsa in AEM.
* Se la pagina di ringraziamento non è in AEM, specificate l’URL assoluto. Gli URL non assoluti verranno interpretati in relazione ad AEM.
* Lasciare vuoto per visualizzare nuovamente il modulo dopo l&#39;invio.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire i componenti consentiti e le relative mappature per il contenitore, in modo simile alla finestra di dialogo di progettazione per il contenitore di layout [standard nell&#39;editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)modelli.
