---
title: Componente Contenitore modulo
seo-title: Componente Contenitore modulo
description: 'null'
seo-description: Il componente Contenitore di componenti di componente core consente di creare moduli di invio semplici.
uuid: 9 d 556 daf -3 fe 7-4 b 2 a-b 5 ae -6926 acb 267 a 9
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: 3 d 33 fe 60-a 0 ac -4 ff 2-a 865-d 600 b 5448 aeb
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
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# Componente Contenitore modulo{#form-container-component}

Il componente Contenitore di componenti di componente core consente di creare moduli di invio semplici.

## Utilizzo {#usage}

Il componente Contenitore di contenitori consente di creare moduli di invio delle informazioni semplici e funzioni mediante il supporto di moduli WCM semplici e l&#39;utilizzo di una struttura nidificata per consentire altri componenti modulo.

Utilizzando la [finestra di dialogo](#configure-dialog) di configurazione, l&#39;editor di contenuto può definire l&#39;azione attivata dall&#39;invio del modulo, dove memorizzare il contenuto inviato e se deve essere attivato un flusso di lavoro. L&#39;autore del modello può utilizzare la [finestra di dialogo](#design-dialog) di progettazione per definire i componenti consentiti e le relative mappature simili alla finestra di dialogo di progettazione per il contenitore di layout [standard nell&#39;editor modelli](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html).

>[!NOTE]
>
>I componenti core Modulo modulo supportano solo l&#39;uso dei componenti dei componenti core (pulsante, testo, nascosto, ecc.). L&#39;utilizzo [dei componenti](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) modulo di base nel contenitore dei componenti core (e viceversa) non è supportato.

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Contenitore contenitore è v 2, introdotta con la release 2.0.0 dei componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](form-container-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente relativa al componente [Contenitore modulo è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v2/container).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo Configura consente all&#39;autore del contenuto di definire le azioni intraprese durante l&#39;invio del componente.

![](assets/screen_shot_2018-01-12at122046.png)

A seconda del tipo **di azione selezionato**, le opzioni disponibili all&#39;interno del contenitore cambiano. I tipi di azioni disponibili sono:

* [E-mail](#mail)
* [Contenuto store](#store-content)
* [Invia ordine](#submit-order)
* [Aggiorna ordine](#update-order)

A prescindere dal tipo, sono [disponibili impostazioni](#general-settings) generali per ogni azione.

### E-mail {#mail}

Quando il modulo viene inviato, il tipo di azione invia un messaggio e-mail a destinatari designati.

![](assets/screen_shot_2018-01-12at122554.png)

* **Oggetto**
dell&#39;e-mail che verrà inviata all&#39;invio del modulo
* **Dall**&#39;indirizzo
e-mail dell&#39;e-mail che verrà inviata all&#39;invio del modulo
* **Agli**
indirizzi dei destinatari che riceveranno un messaggio e-mail all&#39;invio del modulo

   * Tocca o fai clic sul **pulsante Aggiungi** per aggiungere altri indirizzi
   * Toccate o fate clic sul **pulsante Elimina** per rimuovere un indirizzo e-mail
* **CC**
Gli indirizzi dei destinatari che riceveranno un carbon copy riceveranno l&#39;e-mail inviata all&#39;invio del modulo
   * Tocca o fai clic sul **pulsante Aggiungi** per aggiungere altri indirizzi
   * Toccate o fate clic sul **pulsante Elimina** per rimuovere un indirizzo e-mail

### Contenuto store {#store-content}

Quando il modulo viene inviato, il contenuto del modulo verrà memorizzato in una posizione archivio designata.

![](assets/screen_shot_2018-01-12at122538.png)

* **Percorso archivio** contenuto contenuto in cui è memorizzato il contenuto inviato
* **View Data**
Toccare o fare clic per visualizzare i dati inviati come JSON
* **Avvia**Configurazione flusso di lavoro
per avviare un flusso di lavoro con il contenuto memorizzato come payload all&#39;invio del modulo

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

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire i componenti consentiti e le relative mappature per il contenitore, simile alla finestra di dialogo di progettazione per il [contenitore di layout standard nell&#39;editor modelli](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html).