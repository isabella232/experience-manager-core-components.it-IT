---
title: Componente Contenitore modulo
description: Il componente core Contenitore modulo consente la creazione di semplici moduli per l’invio.
role: Architect, Developer, Admin, User
exl-id: 552f9dd5-6a3a-42d9-9969-e62a1f36e811
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '956'
ht-degree: 100%

---

# Componente Contenitore modulo {#form-container-component}

Il componente core Contenitore modulo consente la creazione di semplici moduli per l’invio.

## Utilizzo {#usage}

Il componente Contenitore modulo consente di creare semplici moduli e funzioni per l’invio di informazioni, mediante il supporto di semplici moduli WCM e l’utilizzo di una struttura nidificata per consentire l’aggiunta di altri componenti Modulo.

Utilizzando la [finestra di dialogo per configurazione](#configure-dialog) l’editor di contenuto può definire l’azione attivata dall’invio del modulo, l’URL che deve gestire l’invio e se deve essere attivato un flusso di lavoro. L’autore del modello può utilizzare la [finestra di dialogo per progettazione](#design-dialog) per definire i componenti consentiti e i relativi mapping in modo simile alla finestra di dialogo per progettazione del [contenitore di layout standard nell’editor di modelli](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>Il componente core Contenitore modulo supporta solo l’utilizzo di altri componenti core Modulo (pulsante, testo, nascosto, ecc.). Non è supportato l’utilizzo di [componenti Modulo di base](https://docs.adobe.com/content/help/it-IT/experience-manager-65/authoring/siteandpage/default-components-foundation.html) all’interno del componente core Contenitore modulo (e viceversa).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Contenitore modulo è la v2, introdotta con la versione 2.0.0 dei Componenti core a gennaio 2018, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-container-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Contenitore modulo e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_form_container_it).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Contenitore modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_container_v2_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuto di definire le azioni da eseguire quando il componente viene inviato.

A seconda del **Tipo di azione** selezionato, le opzioni disponibili all’interno del contenitore cambiano. I tipi di azione disponibili sono:

* [Pubblica dati modulo](#post-data)
* [Mail](#mail)
* [Contenuto store](#store-content)

Indipendentemente dal tipo, ci sono [impostazioni generali](#general-settings) che si applicano a ogni azione.

### Pubblica dati modulo {#post-data}

Quando il modulo viene inviato, il tipo di azione Pubblica dati modulo trasmette i dati inviati a una terza parte come output JSON per l’elaborazione.

![Opzione Pubblica dati modulo nella finestra di dialogo per modifica del componente Contenitore modulo](/help/assets/form-container-edit-post.png)

* **Endpoint**: il servizio HTTPS idoneo che elaborerà i dati
* **Messaggio di errore**: il messaggio da visualizzare se l’invio non ha esito positivo

>[!TIP]
>Sono disponibili opzioni di timeout aggiuntive che un amministratore di sistema può modificare per gestire l’elaborazione dei dati del modulo inviati. [Per ulteriori informazioni, vedi la documentazione tecnica su GitHub.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/actions/rpc)

### Mail {#mail}

Quando il modulo viene inviato, il tipo di azione Mail invierà un messaggio e-mail ai destinatari designati.

![Opzione Mail nella finestra di dialogo per modifica del componente Contenitore modulo](/help/assets/form-container-edit-mail.png)

* **Oggetto**: l’oggetto dell’e-mail che verrà inviata in seguito all’invio del modulo
* **Da**: l’indirizzo del mittente dell’e-mail che verrà inviata in seguito all’invio del modulo
* **A**: gli indirizzi dei destinatari che riceveranno un’e-mail al momento dell’invio del modulo
   * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere altri indirizzi
   * Tocca o fai clic sul pulsante **Elimina** per rimuovere un indirizzo e-mail
* **CC**: gli indirizzi dei destinatari che riceveranno una copia carbone dell’e-mail inviata al momento dell’invio del modulo
   * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere altri indirizzi
   * Tocca o fai clic sul pulsante **Elimina** per rimuovere un indirizzo e-mail

### Contenuto store {#store-content}

Quando il modulo viene inviato, il contenuto del modulo verrà memorizzato in una posizione specifica dell’archivio.

![Opzione Contenuto store nella finestra di dialogo per modifica del Contenitore modulo](/help/assets/form-container-edit-store.png)

* **Percorso contenuto**: il percorso dell’archivio in cui viene memorizzato il contenuto inviato
* **Visualizza dati**: tocca o fai clic su questo pulsante per visualizzare i dati inviati come output JSON
* **Avvia flusso di lavoro**: configura l’avvio di un flusso di lavoro con il contenuto memorizzato come carico utile al momento dell’invio del modulo

>[!NOTE]
>
>Al fine di semplificare la gestione dei dati utente e di applicare la separazione tra logica e markup, in genere si sconsiglia di memorizzare contenuto generato dall’utente all’interno dell’archivio.
>
>Puoi invece utilizzare il tipo di azione [Pubblica dati modulo](#post-data) per trasmettere contenuto dell’utente a un fornitore di servizi dedicato.

### Impostazioni generali {#general-settings}

Indipendentemente dal tipo di azione selezionato, è sempre possibile definire una pagina di ringraziamento.

![Opzioni generali nella finestra di dialogo per modifica del componente Contenitore modulo](/help/assets/form-container-edit-general.png)

* **Pagina di ringraziamento**: l’utente verrà reindirizzato alla pagina specificata dopo il completamento dell’invio del modulo.
   * Utilizza la finestra di dialogo di selezione per selezionare una risorsa all’interno di AEM.
   * Se la pagina di ringraziamento non è in AEM, specifica l’URL assoluto. Gli URL non assoluti verranno interpretati come relativi ad AEM.
   * Lascia vuoto questo campo per visualizzare di nuovo il modulo dopo l’invio.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

## Finestra di dialogo per progettazione {#design-dialog}

L’autore del modello può utilizzare la finestra di dialogo per progettazione per definire i componenti consentiti e i relativi mapping in modo simile alla finestra di dialogo per progettazione del [contenitore di layout standard nell’editor di modelli](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/sites/authoring/features/templates.html).

### Scheda Stili {#styles-tab}

Il componente Contenitore modulo supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
