---
title: Componente contenitore modulo
seo-title: Componente contenitore modulo
description: 'null'
seo-description: Il componente Contenitore di moduli per componenti core consente la creazione di moduli di invio semplici.
uuid: 9d556daf-3fe7-4b2a-b5ae-6926acb267a9
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 3d33fe60-a0ac-4ff2-a865-d600b5448aeb
disttype: dist5
gnavtheme: chiaro
groupsectionnavitems: 'no'
hidemerchandisingbar: eredita
hidepromocomponent: eredita
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 62643e5bd49ab006230f65004bb9374822dcc017

---


# Componente contenitore modulo{#form-container-component}

Il componente Contenitore di moduli per componenti core consente la creazione di moduli di invio semplici.

## Utilizzo {#usage}

Il componente Contenitore modulo consente di creare moduli e funzioni semplici per l'invio di informazioni, mediante il supporto di semplici moduli WCM e l'uso di una struttura nidificata per consentire l'aggiunta di altri componenti modulo.

Utilizzando la finestra di dialogo [di](#configure-dialog) configurazione, l'Editor contenuto può definire l'azione attivata dall'invio del modulo, dove memorizzare il contenuto inviato e se avviare un flusso di lavoro. L’autore del modello può utilizzare la finestra di dialogo [di](#design-dialog) progettazione per definire i componenti consentiti e le relative mappature in modo simile alla finestra di dialogo di progettazione per il contenitore di layout [standard nell’editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)modelli.

>[!NOTE]
>
>I componenti core Modulo contenitore Component supportano solo l’uso di componenti core per i componenti modulo (pulsante, testo, nascosti, ecc.). L'utilizzo di componenti [](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) di base per i moduli all'interno del contenitore dei moduli dei componenti core (e viceversa) non è supportato.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Contenitore modulo è v2, introdotta con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](form-container-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Contenitore moduli [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v2/container).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire le azioni da eseguire quando il componente viene inviato.

![](assets/screen_shot_2018-01-12at122046.png)

A seconda del tipo **di** azione selezionato, le opzioni disponibili all'interno del contenitore cambiano. I tipi di azione disponibili sono:

* [E-mail](#mail)
* [Contenuto store](#store-content)
* [Invia ordine](#submit-order)
* [Aggiorna ordine](#update-order)

Indipendentemente dal tipo, esistono impostazioni [](#general-settings) generali applicabili a ogni azione.

### E-mail {#mail}

Quando il modulo viene inviato, il tipo di azione e-mail invierà un messaggio e-mail ai destinatari designati.

![](assets/screen_shot_2018-01-12at122554.png)

* **Oggetto** L'oggetto dell'e-mail che verrà inviata all'invio del modulo
* **Da** L'indirizzo e-mail del messaggio e-mail che verrà inviato all'invio del modulo
* **A** Gli indirizzi dei destinatari che riceveranno un'e-mail all'invio del modulo

   * Toccate o fate clic sul pulsante **Aggiungi** per aggiungere altri indirizzi
   * Toccate o fate clic sul pulsante **Elimina** per rimuovere un indirizzo e-mail
* **CC** Gli indirizzi dei destinatari che riceveranno una copia in carbonio dell'e-mail inviata al momento dell'invio del modulo
   * Toccate o fate clic sul pulsante **Aggiungi** per aggiungere altri indirizzi
   * Toccate o fate clic sul pulsante **Elimina** per rimuovere un indirizzo e-mail

### Contenuto store {#store-content}

Quando il modulo viene inviato, il contenuto del modulo viene memorizzato in una posizione archivio designata.

![](assets/screen_shot_2018-01-12at122538.png)

* **Percorso** contenuto Percorso archivio Contenuto percorso in cui viene memorizzato il contenuto inviato
* **Visualizza dati** Tocca o fai clic per visualizzare i dati inviati memorizzati come JSON
* **Avvia flusso di lavoro** Configura per avviare un flusso di lavoro con il contenuto memorizzato come payload al momento dell’invio del modulo

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

La finestra di dialogo di progettazione consente all'autore del modello di definire i componenti consentiti e le relative mappature per il contenitore, in modo simile alla finestra di dialogo di progettazione per il contenitore di layout [standard nell'editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)modelli.