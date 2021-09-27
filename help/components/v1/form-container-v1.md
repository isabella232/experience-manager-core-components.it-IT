---
title: Componente Contenitore modulo (v1)
description: Il componente core Contenitore modulo consente la creazione di semplici moduli per l’invio.
index: n
role: Architect, Developer, Admin, User
exl-id: 1e34219f-fa82-494e-82e2-1b4d63d37fea
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '638'
ht-degree: 100%

---

# Componente Contenitore modulo (v1) {#form-container-component-v1}

Il componente core Contenitore modulo consente la creazione di semplici moduli per l’invio.

## Utilizzo {#usage}

Il componente Contenitore modulo consente di creare semplici moduli e funzioni per l’invio di informazioni, mediante il supporto di semplici moduli WCM e l’utilizzo di una struttura nidificata per consentire l’aggiunta di altri componenti Modulo.

Utilizzando la [finestra di dialogo per impostazione](#settings-dialog) l’editor di contenuto può definire il tipo di azione che attiva l’invio del modulo, dove deve essere memorizzato il contenuto inviato e se deve essere attivato un flusso di lavoro. L’autore del modello può utilizzare la [finestra di dialogo per progettazione](#design-dialog) per definire i componenti consentiti e i relativi mapping in modo simile alla finestra di dialogo per progettazione del [contenitore di layout standard nell’editor di modelli](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/siteandpage/templates.html?lang=it).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Contenitore modulo, originariamente introdotto con la versione 1.0.0 dei Componenti core in AEM 6.3.

La tabella che segue riporta la compatibilità della versione 1 del componente Contenitore modulo.

| Versione di AEM | Componente Contenitore modulo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Contenitore modulo.
>
>Per informazioni dettagliate sulla versione corrente del componente Contenitore modulo, vedi il documento [Componente Contenitore modulo](/help/components/forms/form-container.md).

## Finestra di dialogo per impostazione {#settings-dialog}

La finestra di dialogo per impostazione consente all’autore di contenuto di definire le azioni da eseguire quando il componente viene inviato.

![](/help/assets/chlimage_1.png)

A seconda del **Tipo di azione** selezionato, le opzioni disponibili all’interno del contenitore cambiano. I tipi di azione disponibili sono:

* [Mail](#mail)
* [Contenuto store](#store-content)
* [Invia ordine](#submit-order)
* [Aggiorna ordine](#update-order)

Indipendentemente dal tipo, ci sono [impostazioni generali](#general-settings) che si applicano a ogni azione.

### Mail {#mail}

Quando il modulo viene inviato, il tipo di azione Mail invierà un messaggio e-mail ai destinatari designati.

![](/help/assets/chlimage_1-1.png)

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

![](/help/assets/chlimage_1-2.png)

* **Percorso contenuto**: il percorso dell’archivio in cui viene memorizzato il contenuto inviato
* **Visualizza dati**: tocca o fai clic su questo pulsante per visualizzare i dati inviati come output JSON
* **Avvia flusso di lavoro**: configura l’avvio di un flusso di lavoro con il contenuto memorizzato come carico utile al momento dell’invio del modulo

### Invia ordine {#submit-order}

Al momento dell’invio del modulo, viene inviato anche l’ordine.

![](/help/assets/chlimage_1-3.png)

### Aggiorna ordine {#update-order}

Al momento dell’invio del modulo, l’ordine viene aggiornato.

![](/help/assets/chlimage_1-4.png)

### Impostazioni generali {#general-settings}

Indipendentemente dal tipo di azione selezionato, è sempre possibile definire una pagina di ringraziamento.

![](/help/assets/chlimage_1-5.png)

L’utente verrà reindirizzato alla pagina specificata dopo il completamento dell’invio del modulo.

* Utilizza la finestra di dialogo di selezione per selezionare una risorsa all’interno di AEM.
* Se la pagina di ringraziamento non è in AEM, specifica l’URL assoluto. Gli URL non assoluti verranno interpretati come relativi ad AEM.
* Lascia vuoto questo campo per visualizzare di nuovo il modulo dopo l’invio.

## Finestra di dialogo per progettazione {#design-dialog}

L’autore del modello può utilizzare la finestra di dialogo per progettazione per definire i componenti consentiti e i relativi mapping in modo simile alla finestra di dialogo per progettazione del [contenitore di layout standard nell’editor di modelli](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/siteandpage/templates.html?lang=it).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Contenitore modulo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container).

L’intero progetto dei Componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).
