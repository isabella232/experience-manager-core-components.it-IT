---
title: Componente contenitore modulo
description: Il componente Contenitore di moduli per componenti core consente la creazione di moduli di invio semplici.
role: Architect, Developer, Admin, User
exl-id: 552f9dd5-6a3a-42d9-9969-e62a1f36e811
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 2%

---

# Componente contenitore modulo {#form-container-component}

Il componente Contenitore di moduli per componenti core consente la creazione di moduli di invio semplici.

## Utilizzo {#usage}

Il componente Contenitore modulo consente di creare semplici moduli e funzioni per l’invio di informazioni, mediante il supporto di semplici moduli WCM e l’utilizzo di una struttura nidificata per consentire l’aggiunta di componenti modulo.

Utilizzando la [finestra di dialogo di configurazione](#configure-dialog) l’editor di contenuti può definire l’azione attivata dall’invio del modulo, l’URL che deve gestire l’invio e se deve essere attivato un flusso di lavoro. L’autore del modello può utilizzare la finestra di dialogo [progettazione](#design-dialog) per definire i componenti consentiti e le relative mappature in modo simile alla finestra di dialogo di progettazione per il contenitore di layout [standard nell’editor dei modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>Il componente Contenitore modulo dei componenti core supporta solo l’utilizzo di componenti di base per i moduli (pulsanti, testo, nascosti, ecc.). Non è supportato l’utilizzo di componenti modulo [foundation](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) all’interno del contenitore modulo dei componenti core (e viceversa).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Contenitore modulo è v2, introdotta con la versione 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-container-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione e dell’output HTML e JSON del componente contenitore modulo, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_form_container) .

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente per contenitori moduli [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_container_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Configura {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire le azioni da eseguire quando il componente viene inviato.

A seconda del **Tipo azione** selezionato, le opzioni disponibili all’interno del contenitore cambieranno. I tipi di azione disponibili sono:

* [Dati modulo post](#post-data)
* [Mail](#mail)
* [Contenuto store](#store-content)

Indipendentemente dal tipo, esistono [impostazioni generali](#general-settings) che si applicano a ogni azione.

### Dati modulo post {#post-data}

Quando il modulo viene inviato, il tipo di azione per i dati del modulo di pubblicazione trasmette i dati inviati a un terzo come JSON per l’elaborazione.

![Opzioni per i dati del modulo nella finestra di dialogo di modifica del componente del contenitore del modulo](/help/assets/form-container-edit-post.png)

* **Endpoint**  - Il servizio HTTPS completo che elaborerà i dati
* **Messaggio di errore** : messaggio da visualizzare se l’invio non ha esito positivo

>[!TIP]
>Sono disponibili opzioni di timeout aggiuntive che un amministratore di sistema può modificare per gestire l’elaborazione dei dati del modulo inoltrati. [Per ulteriori informazioni, consulta la documentazione tecnica su GitHub .](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/actions/rpc)

### Posta {#mail}

Quando il modulo viene inviato, il tipo di azione e-mail invierà un messaggio e-mail ai destinatari designati.

![Opzioni e-mail nella finestra di dialogo di modifica del componente del contenitore del modulo](/help/assets/form-container-edit-mail.png)

* **Oggetto** : Oggetto dell’e-mail che verrà inviata all’invio del modulo
* **Da** : l’indirizzo e-mail del mittente dell’e-mail che verrà inviato all’invio del modulo
* **A** : gli indirizzi dei destinatari che riceveranno un’e-mail al momento dell’invio del modulo
   * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere altri indirizzi
   * Tocca o fai clic sul pulsante **Elimina** per rimuovere un indirizzo e-mail
* **CC** : gli indirizzi dei destinatari che riceveranno una copia carbone dell’e-mail inviata al momento dell’invio del modulo
   * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere altri indirizzi
   * Tocca o fai clic sul pulsante **Elimina** per rimuovere un indirizzo e-mail

### Contenuto store {#store-content}

Quando il modulo viene inviato, il contenuto del modulo verrà memorizzato in una posizione archivio specifica.

![Opzioni di archiviazione del contenuto nella finestra di dialogo di modifica del contenitore del modulo](/help/assets/form-container-edit-store.png)

* **Percorso contenuto** : percorso dell’archivio dei contenuti in cui è memorizzato il contenuto inviato
* **Visualizza dati** : tocca o fai clic per visualizzare come JSON i dati archiviati inviati
* **Avvia flusso di lavoro** : configura l’avvio di un flusso di lavoro con il contenuto memorizzato come payload al momento dell’invio del modulo

>[!NOTE]
>
>Al fine di semplificare la gestione dei dati utente e di applicare la separazione dei problemi, si sconsiglia generalmente di archiviare i contenuti generati dagli utenti all’interno dell’archivio.
>
>Utilizza invece il tipo di azione [Pubblica dati modulo](#post-data) per trasmettere i contenuti utente a un provider di servizi dedicato.

### Impostazioni generali {#general-settings}

Indipendentemente dal tipo di azione selezionato, è sempre possibile definire una pagina di ringraziamento.

![Opzioni generali nella finestra di dialogo di modifica del componente Contenitore modulo](/help/assets/form-container-edit-general.png)

* **Pagina di ringraziamento** : l’utente verrà reindirizzato alla pagina specificata dopo il completamento dell’invio del modulo.
   * Utilizza la finestra di dialogo Selezione per selezionare una risorsa all’interno di AEM.
   * Se la pagina di ringraziamento non è in AEM, specifica l’URL assoluto. Gli URL non assoluti verranno interpretati in base a AEM.
   * Lasciare vuoto per visualizzare nuovamente il modulo dopo l’invio.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire i componenti consentiti e le relative mappature per il contenitore, in modo analogo alla finestra di dialogo di progettazione per il contenitore di layout [standard nell’editor modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

### Scheda Stili {#styles-tab}

Il componente Contenitore modulo supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).
