---
title: Componente contenitore modulo
description: Il componente Contenitore di moduli per componenti core consente la creazione di moduli di invio semplici.
translation-type: tm+mt
source-git-commit: 499047a8c15a6423a56b370f41fd020740481f80
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 2%

---


# Componente contenitore modulo {#form-container-component}

Il componente Contenitore di moduli per componenti core consente la creazione di moduli di invio semplici.

## Utilizzo {#usage}

Il componente Contenitore modulo consente di creare moduli e funzioni semplici per l&#39;invio di informazioni, mediante il supporto di semplici moduli WCM e l&#39;uso di una struttura nidificata per consentire l&#39;aggiunta di altri componenti modulo.

Utilizzando la finestra di dialogo [di](#configure-dialog) configurazione, l&#39;Editor contenuto può definire l&#39;azione attivata dall&#39;invio del modulo, l&#39;URL che deve gestire l&#39;invio e se è necessario avviare un flusso di lavoro. L’autore del modello può utilizzare la finestra di dialogo [di](#design-dialog) progettazione per definire i componenti consentiti e le relative mappature in modo simile alla finestra di dialogo di progettazione per il contenitore di layout [standard nell’editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)modelli.

>[!NOTE]
>
>I componenti core Modulo contenitore Component supportano solo l’uso di componenti core per i componenti modulo (pulsante, testo, nascosti, ecc.). L&#39;utilizzo di componenti [](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) di base per i moduli all&#39;interno del contenitore dei moduli dei componenti core (e viceversa) non è supportato.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Contenitore modulo è v2, introdotta con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-container-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Contenitore di moduli e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](https://adobe.com/go/aem_cmp_library_form_container)componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Contenitore moduli [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_container_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire le azioni da eseguire quando il componente viene inviato.

A seconda del tipo **di** azione selezionato, le opzioni disponibili all&#39;interno del contenitore cambiano. I tipi di azione disponibili sono:

* [Pubblica dati modulo](#post-data)
* [E-mail](#mail)
* [Contenuto store](#store-content)

Indipendentemente dal tipo, esistono impostazioni [](#general-settings) generali applicabili a ogni azione.

### Pubblica dati modulo {#post-data}

Quando il modulo viene inviato, il tipo di azione dei dati del modulo di posta passa i dati inviati a terzi come JSON per l&#39;elaborazione.

![Opzioni di inserimento dati modulo nella finestra di dialogo di modifica del componente Contenitore modulo](/help/assets/form-container-edit-post.png)

* **Endpoint** - Il servizio HTTPS completo che elaborerà i dati
* **Messaggio** di errore - Messaggio da visualizzare se l&#39;invio non ha esito positivo

>[!TIP]
>Sono disponibili opzioni di timeout aggiuntive che un amministratore di sistema può modificare per gestire l&#39;elaborazione dei dati del modulo inoltrato. [Per ulteriori informazioni, consulta la documentazione tecnica su GitHub.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/actions/rpc)

### E-mail {#mail}

Quando il modulo viene inviato, il tipo di azione e-mail invierà un messaggio e-mail ai destinatari designati.

![Opzioni e-mail nella finestra di dialogo di modifica del componente Contenitore modulo](/help/assets/form-container-edit-mail.png)

* **Oggetto** - Oggetto dell&#39;e-mail che verrà inviata all&#39;invio del modulo
* **Da** - L&#39;indirizzo e-mail del messaggio e-mail che verrà inviato all&#39;invio del modulo
* **A** - Gli indirizzi dei destinatari che riceveranno un&#39;e-mail all&#39;invio del modulo
   * Toccate o fate clic sul pulsante **Aggiungi** per aggiungere altri indirizzi
   * Toccate o fate clic sul pulsante **Elimina** per rimuovere un indirizzo e-mail
* **CC** - Gli indirizzi dei destinatari che riceveranno una copia in carbonio dell&#39;e-mail inviata al momento dell&#39;invio del modulo
   * Toccate o fate clic sul pulsante **Aggiungi** per aggiungere altri indirizzi
   * Toccate o fate clic sul pulsante **Elimina** per rimuovere un indirizzo e-mail

### Contenuto store {#store-content}

Quando il modulo viene inviato, il contenuto del modulo viene memorizzato in una posizione archivio designata.

![Opzioni di memorizzazione del contenuto nella finestra di dialogo di modifica del contenitore del modulo](/help/assets/form-container-edit-store.png)

* **Percorso** contenuto - Percorso dell&#39;archivio dei contenuti in cui è memorizzato il contenuto inviato
* **Visualizza dati** - Toccate o fate clic per visualizzare i dati inviati memorizzati come JSON
* **Avvia flusso di lavoro** - Configura l&#39;avvio di un flusso di lavoro con il contenuto memorizzato come payload al momento dell&#39;invio del modulo

>[!NOTE]
>
>Al fine di semplificare la gestione dei dati utente e di garantire la separazione delle preoccupazioni, si sconsiglia in genere di archiviare contenuti generati dagli utenti all’interno del repository.
>
>Utilizzate invece il tipo di azione [Pubblica dati](#post-data) modulo per trasmettere il contenuto dell&#39;utente a un provider di servizi dedicato.

### Impostazioni generali {#general-settings}

Indipendentemente dal tipo di azione selezionato, è sempre possibile definire una pagina di ringraziamento.

![Opzioni generali nella finestra di dialogo di modifica del componente Contenitore modulo](/help/assets/form-container-edit-general.png)

* **Pagina** di ringraziamento: l’utente verrà reindirizzato alla pagina specificata dopo il completamento dell’invio del modulo.
   * Utilizzare la finestra di dialogo di selezione per selezionare una risorsa all&#39;interno di AEM.
   * Se la pagina di ringraziamento non è AEM, specificate l’URL assoluto. Gli URL non assoluti verranno interpretati in relazione ai AEM.
   * Lasciare vuoto per visualizzare nuovamente il modulo dopo l&#39;invio.
* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire i componenti consentiti e le relative mappature per il contenitore, in modo simile alla finestra di dialogo di progettazione per il contenitore di layout [standard nell&#39;editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)modelli.

### Scheda Stili {#styles-tab}

Il componente Contenitore modulo supporta AEM [Style System](/help/get-started/authoring.md#component-styling).
