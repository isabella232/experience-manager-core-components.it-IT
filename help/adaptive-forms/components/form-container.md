---
title: Componente core dei moduli adattivi - Contenitore di moduli
description: Aggiungere un modulo adattivo a una pagina web.
role: Architect, Developer, Admin, User
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: ht
source-wordcount: '719'
ht-degree: 100%

---


# Contenitore modulo {#form-container-adaptive-forms-core-component}

I moduli consentono ai visitatori di un sito web di interagire con il sito web fornendo informazioni preziose, che possono aumentare il coinvolgimento e la soddisfazione degli utenti. Un contenitore di moduli adattivi in Adobe Experience Manager (AEM) Sites consente ai proprietari di siti web di aggiungere facilmente i moduli alle proprie pagine. Questo rende più facile la comunicazione tra i visitatori di un sito web e il proprietario o l’organizzazione del sito web, offrendo ai visitatori un modo semplificato per fornire feedback, rispondere ai sondaggi e completare altre azioni

## Utilizzo {#reasons-to-use-forms-container}

Ci sono diversi motivi per i quali viene aggiunto un modulo a un sito web:

* **Raccolta dati**: i moduli possono essere utilizzati per raccogliere dati dai visitatori di un sito web per vari scopi, come ricerche di mercato, analisi del comportamento degli utenti e altro ancora.

* **Generare lead**: un modulo può essere utilizzato per raccogliere informazioni dai potenziali clienti, ad esempio nome e indirizzo e-mail, per generare lead per attività di vendita e marketing.

* **E-commerce**: i moduli possono essere utilizzati per lo shopping online, poiché consentono ai clienti di effettuare ordini e pagamenti su un sito web.

* **Contatto**: un modulo di contatto consente ai visitatori di un sito web di raggiungere facilmente il proprietario o l’organizzazione del sito web.

* **Indagini e sondaggi**: i moduli possono essere utilizzati per raccogliere feedback e opinioni dai visitatori di un sito attraverso indagini di marketing e sondaggi.

* **Iscriversi ad eventi**: i moduli possono essere utilizzati per partecipare ad eventi, poiché consentono ai visitatori di un sito web di iscriversi ad eventi o webinar.

* **Abbonamenti**: i moduli possono essere utilizzati per sottoscrivere un abbonamento a un sito web, poiché consentono ai visitatori di iscriversi a una newsletter o ad altre comunicazioni regolari.

* **Autenticazione utente**: i moduli possono essere utilizzati per l’autenticazione degli utenti, poiché consentono ai visitatori di un sito web di creare account e di accedere a contenuti o funzionalità esclusive.

* **Aumentare il tasso di conversione**: un modulo ben progettato può aumentare il tasso di conversione rendendo più semplice per gli utenti completare un’azione desiderata, ad esempio acquistare un prodotto o iscriversi a un servizio.


## Versione e compatibilità {#version-and-compatibility}

Il componente core Pannello a soffietto moduli adattativi è stato rilasciato a febbraio 2023 come parte dei Componenti core 2.0.4 per Cloud Service e i Componenti core 1.1.12 per AEM Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM Forms 6.5.16.0 o versioni successive |
|---|---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successive | Compatibile con la <br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive, ma precedenti alla 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).
<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente core contenitore di moduli adattivi, consulta la documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [Documentazione per gli sviluppatori di componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

È possibile personalizzare facilmente l’esperienza del contenitore di moduli per i visitatori tramite la finestra di dialogo Configura. È, inoltre, possibile definire le opzioni del contenitore di moduli con facilità per un’esperienza utente perfetta.

### Scheda Base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/formcontainer_basictab.png)

* **Servizi di precompilazione**: questa opzione consente all’utente di selezionare un servizio di precompilazione per il recupero dei dati durante il rendering del modulo adattivo. Ulteriori informazioni su [come creare e configurare un servizio di precompilazione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=it#aem-forms-custom-prefill-service).

* **Categoria Libreria client**: l’utente può configurare una libreria JavaScript personalizzata per un modulo adattivo. Si consiglia di mantenere solo le funzioni riutilizzabili nella libreria, che dipendono dalle librerie di terze parti jquery e underscore.js.

### Scheda Invio {#submission-tab}

![Scheda Invio](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

Gli utenti possono configurare azioni diverse per gli invii di moduli adattivi.

* **URL/percorso di reindirizzamento**: questa opzione consente agli utenti di configurare una pagina per ciascun modulo, a cui verranno reindirizzati gli utenti dei moduli dopo l’invio di un modulo adattivo. Fai clic qui per ulteriori informazioni su [come configurare le pagine di reindirizzamento](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html?lang=it).

![Scheda Mostra Messaggio](/help/adaptive-forms/assets/formconatiner_showmessage.png)

* **Mostra Messaggio**: questa opzione consente agli utenti di aggiungere un messaggio da visualizzare quando il modulo adattivo viene inviato correttamente. Il testo predefinito viene incluso nella finestra di dialogo e può essere modificato dall’utente. La finestra di dialogo Mostra messaggio supporta gli strumenti di formattazione RTF che consentono agli utenti di formattare il testo aggiunto.

* **Azione di invio**: un’azione di invio viene attivata quando l’utente fa clic sul pulsante Invia in un modulo adattivo. Gli utenti possono selezionare azioni di Invio dall’elenco a discesa supportato come predefinito. Scopri come [configurare un’azione di invio nella scheda Invio](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html?lang=it#supporting-custom-functions-in-validation-expressions-br).
