---
title: Componente contenitore modulo (v1)
description: Il componente Contenitore di moduli per componenti core consente la creazione di moduli di invio semplici.
index: n
role: Architetto, Sviluppatore, Amministratore, Business Practices
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 3%

---


# Componente contenitore modulo (v1) {#form-container-component-v1}

Il componente Contenitore di moduli per componenti core consente la creazione di moduli di invio semplici.

## Utilizzo {#usage}

Il componente Contenitore modulo ha abilitato la creazione di moduli e funzioni per l’invio di informazioni semplici, supportando moduli WCM semplici e utilizzando una struttura nidificata per consentire l’aggiunta di componenti modulo.

Utilizzando la [finestra di dialogo di impostazione](#settings-dialog) l’editor dei contenuti può definire il tipo di azione che attiva l’invio del modulo, dove deve essere memorizzato il contenuto inviato e se deve essere attivato un flusso di lavoro. L’autore del modello può utilizzare la finestra di dialogo [progettazione](#design-dialog) per definire i componenti consentiti e le relative mappature in modo simile alla finestra di dialogo di progettazione per il contenitore di layout [standard nell’editor dei modelli](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la v1 del componente per contenitori di moduli, originariamente introdotto con la versione 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità della versione 1 del componente Contenitore modulo.

| Versione di AEM | Componente contenitore modulo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Contenitore modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Contenitore modulo, consultare il documento [Componente contenitore modulo](/help/components/forms/form-container.md) .

## Finestra di dialogo Impostazioni {#settings-dialog}

La finestra di dialogo delle impostazioni consente all’autore del contenuto di definire le azioni da eseguire quando il componente viene inviato.

![](/help/assets/chlimage_1.png)

A seconda del **Tipo azione** selezionato, le opzioni disponibili all’interno del contenitore cambieranno. I tipi di azione disponibili sono:

* [E-mail](#mail)
* [Contenuto store](#store-content)
* [Invia ordine](#submit-order)
* [Aggiorna ordine](#update-order)

Indipendentemente dal tipo, esistono [impostazioni generali](#general-settings) che si applicano a ogni azione.

### E-mail {#mail}

Quando il modulo viene inviato, il tipo di azione e-mail invierà un messaggio e-mail ai destinatari designati.

![](/help/assets/chlimage_1-1.png)

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

![](/help/assets/chlimage_1-2.png)

* **Percorso contenuto** : percorso dell’archivio dei contenuti in cui è memorizzato il contenuto inviato
* **Visualizza dati** : tocca o fai clic per visualizzare come JSON i dati archiviati inviati
* **Avvia flusso di lavoro** : configura l’avvio di un flusso di lavoro con il contenuto memorizzato come payload al momento dell’invio del modulo

### Invia ordine {#submit-order}

Al momento dell’invio del modulo, l’ordine viene inviato.

![](/help/assets/chlimage_1-3.png)

### Aggiorna ordine {#update-order}

Quando il modulo viene inviato, l’ordine viene aggiornato.

![](/help/assets/chlimage_1-4.png)

### Impostazioni generali {#general-settings}

Indipendentemente dal tipo di azione selezionato, è sempre possibile definire una pagina di ringraziamento.

![](/help/assets/chlimage_1-5.png)

L’utente verrà reindirizzato alla pagina specificata dopo il completamento dell’invio del modulo.

* Utilizza la finestra di dialogo Selezione per selezionare una risorsa all’interno di AEM.
* Se la pagina di ringraziamento non è in AEM, specifica l’URL assoluto. Gli URL non assoluti verranno interpretati in base a AEM.
* Lasciare vuoto per visualizzare nuovamente il modulo dopo l’invio.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire i componenti consentiti e le relative mappature per il contenitore, in modo analogo alla finestra di dialogo di progettazione per il contenitore di layout [standard nell’editor modelli](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente per contenitori moduli [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .
