---
title: Componente core Forms adattivo - Contenitore modulo
description: Aggiungere un modulo adattivo a una pagina web.
role: Architect, Developer, Admin, User
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 2%

---


# Contenitore modulo {#form-container-adaptive-forms-core-component}

Forms consente ai visitatori del sito web di interagire con il sito web fornendo informazioni preziose, che possono aumentare il coinvolgimento e la soddisfazione degli utenti. Un contenitore di moduli adattivi in Adobe Experience Manager (AEM) Sites consente ai proprietari di siti web di aggiungere facilmente i moduli alle proprie pagine. Questo aiuta a facilitare la comunicazione tra i visitatori del sito web e il proprietario o l&#39;organizzazione del sito web, fornendo ai visitatori un modo semplificato per fornire feedback, fare indagini e completare altre azioni

## Utilizzo {#reasons-to-use-forms-container}

Ci sono diversi motivi per cui un modulo può essere aggiunto a un sito web:

* **Raccolta dati**: Forms può essere utilizzato per raccogliere dati dai visitatori del sito web per vari scopi, come ricerche di mercato, analisi del comportamento degli utenti e altro ancora.

* **Generazione di lead**: Un modulo può essere utilizzato per raccogliere informazioni dai potenziali clienti, ad esempio nome e indirizzo e-mail, per generare lead per attività di vendita e marketing.

* **E-commerce**: Forms può essere utilizzato per lo shopping online, consentendo ai clienti di effettuare ordini e pagamenti attraverso il sito web.

* **Contatto**: Un modulo di contatto consente ai visitatori del sito web di raggiungere facilmente il proprietario o l’organizzazione del sito web.

* **Indagini e sondaggi**: Forms può essere utilizzato per raccogliere feedback e opinioni dai visitatori del sito attraverso sondaggi e sondaggi.

* **Registrazione degli eventi**: Forms può essere utilizzato per la registrazione degli eventi, consentendo ai visitatori del sito web di iscriversi a eventi o webinar.

* **Abbonamenti**: Forms può essere utilizzato per gli abbonamenti a siti web, consentendo ai visitatori di iscriversi a una newsletter o ad altre comunicazioni regolari.

* **Autenticazione utente**: Forms può essere utilizzato per l’autenticazione degli utenti, consentendo ai visitatori del sito web di creare account e di accedere a contenuti o funzionalità esclusive.

* **Aumento del tasso di conversione**: Un modulo ben progettato può aumentare il tasso di conversione rendendo più semplice per gli utenti completare l&#39;azione desiderata, ad esempio acquistare un prodotto o iscriversi a un servizio.


## Versione e compatibilità {#version-and-compatibility}

Il componente core per pannello a soffietto adattivo di Forms è stato rilasciato a febbraio 2023 come parte dei componenti core 2.0.4 per Cloud Service e i componenti core 1.1.12 per Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM 6.5.16.0 Forms o versione successiva |
|---|---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successivi | Compatibile con<br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive ma inferiori a 2.0.0. |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/adaptive-forms/version.md) documento.
<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Scarica le informazioni più recenti sul componente core del contenitore di Forms adattivo nella documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

È possibile personalizzare facilmente l’esperienza del contenitore di moduli per i visitatori tramite la finestra di dialogo Configura . È inoltre possibile definire le opzioni del contenitore di moduli con facilità per un’esperienza utente senza soluzione di continuità.

### Scheda di base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/formcontainer_basictab.png)

* **Servizi di precompilazione** - Questa opzione consente all’utente di selezionare un servizio di precompilazione per il recupero dei dati durante il rendering del modulo adattivo. Ulteriori informazioni [come creare e configurare un servizio di precompilazione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=en#aem-forms-custom-prefill-service).

* **Categoria Libreria client** - L’utente può configurare una libreria JavaScript personalizzata per modulo adattivo. Si consiglia di mantenere solo le funzioni riutilizzabili nella libreria, che dipendono dalle librerie di terze parti jquery e underscore.js.

### Scheda Invio {#submission-tab}

![Scheda Invio](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

Gli utenti possono configurare azioni diverse per gli invii di moduli adattivi.

* **URL/percorso di reindirizzamento** - Questa opzione consente agli utenti di configurare una pagina per ciascun modulo, a cui verranno reindirizzati gli utenti dopo l’invio di un modulo adattivo. Fai clic qui per ulteriori informazioni su [come configurare le pagine di reindirizzamento](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html).

![Mostra scheda Messaggio](/help/adaptive-forms/assets/formconatiner_showmessage.png)

* **Mostra messaggio** - Questa opzione consente agli utenti di aggiungere un messaggio da visualizzare quando il modulo adattivo viene inviato correttamente. Il testo predefinito viene incluso nella finestra di dialogo e può essere modificato dall’utente. La finestra di dialogo Mostra messaggio supporta gli strumenti di formattazione RTF che consentono agli utenti di formattare il testo aggiunto.

* **Invia azione** - Un’azione di invio viene attivata quando l’utente fa clic sul pulsante Invia in un modulo adattivo. Gli utenti possono selezionare Invia azioni dall’elenco a discesa supportato come predefinito. Scopri come [configurare un’azione di invio nella scheda Invio](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#supporting-custom-functions-in-validation-expressions-br).
