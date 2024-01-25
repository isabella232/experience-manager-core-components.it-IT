---
title: Componente core dei moduli adattivi - Contenitore di moduli
description: Aggiungere un modulo adattivo a una pagina web.
role: Architect, Developer, Admin, User
exl-id: 03c4cf7c-51d6-4850-a566-1c0514d52dab
source-git-commit: 4d01c75fadb0220f0093a6647c27c4002cc979c9
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 90%

---

# Contenitore modulo {#form-container-adaptive-forms-core-component}

I moduli consentono ai visitatori di un sito web di interagire con il sito web fornendo informazioni preziose, che possono aumentare il coinvolgimento e la soddisfazione degli utenti. Un contenitore di moduli adattivi in Adobe Experience Manager (AEM) Sites consente ai proprietari di siti web di aggiungere facilmente i moduli alle proprie pagine. Questo rende più facile la comunicazione tra i visitatori di un sito web e il proprietario o l’organizzazione del sito web, offrendo ai visitatori un modo semplificato per fornire feedback, rispondere ai sondaggi e completare altre azioni

## Utilizzo {#reasons-to-use-forms-container}

Ci sono diversi motivi per i quali viene aggiunto un modulo a un sito web:

- **Raccolta dati**: i moduli possono essere utilizzati per raccogliere dati dai visitatori di un sito web per vari scopi, come ricerche di mercato, analisi del comportamento degli utenti e altro ancora.

- **Generare lead**: un modulo può essere utilizzato per raccogliere informazioni dai potenziali clienti, ad esempio nome e indirizzo e-mail, per generare lead per attività di vendita e marketing.

- **E-commerce**: i moduli possono essere utilizzati per lo shopping online, poiché consentono ai clienti di effettuare ordini e pagamenti su un sito web.

- **Contatto**: un modulo di contatto consente ai visitatori di un sito web di raggiungere facilmente il proprietario o l’organizzazione del sito web.

- **Indagini e sondaggi**: i moduli possono essere utilizzati per raccogliere feedback e opinioni dai visitatori di un sito attraverso indagini di marketing e sondaggi.

- **Iscriversi ad eventi**: i moduli possono essere utilizzati per partecipare ad eventi, poiché consentono ai visitatori di un sito web di iscriversi ad eventi o webinar.

- **Abbonamenti**: i moduli possono essere utilizzati per sottoscrivere un abbonamento a un sito web, poiché consentono ai visitatori di iscriversi a una newsletter o ad altre comunicazioni regolari.

- **Autenticazione utente**: i moduli possono essere utilizzati per l’autenticazione degli utenti, poiché consentono ai visitatori di un sito web di creare account e di accedere a contenuti o funzionalità esclusive.

- **Aumentare il tasso di conversione**: un modulo ben progettato può aumentare il tasso di conversione rendendo più semplice per gli utenti completare un’azione desiderata, ad esempio acquistare un prodotto o iscriversi a un servizio.


## Versione e compatibilità {#version-and-compatibility}

Il componente core Pannello a soffietto moduli adattativi è stato rilasciato a febbraio 2023 come parte dei Componenti core 2.0.4 per Cloud Service e i Componenti core 1.1.12 per AEM Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM Forms 6.5.16.0 o versioni successive |
|---|---|---|
| v1 | Compatibile con <br>[versione 2.0.4](/help/adaptive-forms/version.md) e successive | Compatibile con <br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive, ma precedenti a 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).
<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente core contenitore di moduli adattivi, consulta la documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [Documentazione per gli sviluppatori di componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

È possibile personalizzare facilmente l’esperienza del contenitore di moduli per i visitatori tramite la finestra di dialogo Configura. È, inoltre, possibile definire le opzioni del contenitore di moduli con facilità per un’esperienza utente perfetta.

### Scheda Base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/formcontainer_basictab.png)

- **Servizi di precompilazione**: questa opzione consente all’utente di selezionare un servizio di precompilazione per il recupero dei dati durante il rendering del modulo adattivo. Ulteriori informazioni su [come creare e configurare un servizio di precompilazione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=it#aem-forms-custom-prefill-service).

- **Categoria Libreria client**: l’utente può configurare una libreria JavaScript personalizzata per un modulo adattivo. Si consiglia di mantenere solo le funzioni riutilizzabili nella libreria, che hanno dipendenza da librerie di terze parti jquery e underscore.js.
A volte, se ci sono **regole di convalida complesse**, lo script di convalida esatto risiede nelle funzioni personalizzate e gli utenti chiamano tali funzioni personalizzate dall’espressione di convalida del campo. Per rendere nota e disponibile questa libreria di funzioni personalizzata durante l’esecuzione delle convalide lato server, l’utente del modulo può configurare il nome della libreria client AEM in **[!UICONTROL Base]** delle proprietà del Contenitore modulo adattivo, come illustrato di seguito.

L’utente può configurare una libreria JavaScript personalizzata per modulo adattivo. Nella libreria, mantieni solo le funzioni riutilizzabili, che hanno dipendenza da librerie di terze parti jquery e underscore.js.

### Scheda Modello dati {#data-model-tab}

![Scheda Invio](/help/adaptive-forms/assets/formcontainer_fdmtab.png)

È possibile utilizzare il modello dati modulo per collegare un modulo a un’origine dati per inviare e ricevere dati in base alle azioni degli utenti. È possibile anche collegare un modulo a uno schema JSON per ricevere i dati inviati in un formato predefinito. In base al requisito, connetti il modulo a uno schema JSON o a un modello di dati del modulo:
- Crea uno schema JSON e caricalo nell’ambiente
- Creare un modello dati modulo

### Scheda Invio {#submission-tab}

![Scheda Invio](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

Gli utenti possono configurare azioni diverse per gli invii di moduli adattivi.

- **URL/percorso di reindirizzamento**: questa opzione consente agli utenti di configurare una pagina per ciascun modulo, a cui verranno reindirizzati gli utenti dei moduli dopo l’invio di un modulo adattivo. Fai clic qui per ulteriori informazioni su [come configurare le pagine di reindirizzamento](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html?lang=it).

![Scheda Mostra Messaggio](/help/adaptive-forms/assets/formconatiner_showmessage.png)

- **Mostra Messaggio**: questa opzione consente agli utenti di aggiungere un messaggio da visualizzare quando il modulo adattivo viene inviato correttamente. Il testo predefinito viene incluso nella finestra di dialogo e può essere modificato dall’utente. La finestra di dialogo Mostra messaggio supporta gli strumenti di formattazione RTF che consentono agli utenti di formattare il testo aggiunto.

- **Azione di invio**: un’azione di invio viene attivata quando l’utente fa clic sul pulsante Invia in un modulo adattivo. Gli utenti possono selezionare azioni di Invio dall’elenco a discesa supportato come predefinito. Scopri come [configurare un’azione di invio nella scheda Invio](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html?lang=it#supporting-custom-functions-in-validation-expressions-br).

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente di definire e gestire gli stili CSS per il componente Contenitore modulo.

### Scheda Componenti Consentiti {#allowed-components-tab}

![Scheda Componente consentito della finestra di dialogo per la progettazione](/help/adaptive-forms/assets/formcontainer-allowedcomponents.png)

La scheda **Componenti consentiti** permette all’editor dei modelli di impostare i componenti che possono essere aggiunti come elementi ai pannelli nel componente dell’editor di moduli adattivi.

### Scheda Componenti predefiniti {#default-components-tab}

![Scheda Componente predefinito della finestra di dialogo per la progettazione](/help/adaptive-forms/assets/formcontainer-defaultcomponents.png)

La scheda **Componenti predefiniti** consente all’editor di modelli di specificare i componenti visibili per impostazione predefinita come elementi nel componente Contenitore modulo nell’editor moduli adattivi.

### Scheda Impostazioni reattive {#responsive-tab}

![Scheda Impostazioni reattive della finestra di dialogo per la progettazione](/help/adaptive-forms/assets/formcontainer-responsivestyle.png)

La scheda **Impostazioni reattive** consente all’editor di modelli di specificare il numero di colonne nella griglia all’interno del componente Contenitore modulo nell’editor di moduli adattivi.

### Scheda Stili {#styles-tab}

Il componente core Allegato file dei moduli adattivi supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

![Finestra di dialogo per la progettazione](/help/adaptive-forms/assets/formcontainer-styletab.png)

- **Classi CSS predefinite**: puoi fornire una classe CSS predefinita per il componente core Contenitore adattivo Forms Form.

- **Stili consentiti**: è possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di moduli adattivi. Per applicare uno stile, nell’editor dei moduli adattivi, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

### Scheda Proprietà personalizzate

![Finestra di dialogo Proprietà personalizzate](/help/adaptive-forms/assets/formcontainer-custompropertiestab.png)

Le proprietà personalizzate consentono di associare attributi personalizzati (coppie chiave-valore) a un componente core del modulo adattivo utilizzando il modello di modulo. Le proprietà personalizzate vengono riflesse nella sezione delle proprietà della rappresentazione headless del componente. Consentono di creare un comportamento di modulo dinamico che si adatta in base ai valori degli attributi personalizzati. Ad esempio, gli sviluppatori possono progettare diverse rappresentazioni di un componente moduli headless su piattaforme mobili, desktop o web, migliorando in modo significativo l’esperienza utente su un’ampia gamma di dispositivi.

- **Nome gruppo**: puoi fornire un nome per identificare il gruppo di proprietà personalizzate. È possibile aggiungere, eliminare o ridisporre più gruppi di proprietà personalizzate. Dopo aver aggiunto il gruppo di proprietà personalizzate, puoi visualizzare le seguenti opzioni:

   - **Coppie chiave-valore**: puoi aggiungere più nomi e valori della proprietà personalizzata facendo clic sul pulsante **Aggiungi** per ogni gruppo di proprietà personalizzate.

   - **Elimina**: tocca o fai clic per eliminare il nome e il valore della proprietà personalizzata.

   - **Ridisponi**: tocca o fai clic e trascina per ridisporre l’ordine del nome e del valore della proprietà personalizzata.

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## Articoli correlati {#related-articles}

{{more-like-this}}

## Consulta anche {#see-also}

{{see-also}}