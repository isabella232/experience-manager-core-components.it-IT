---
title: Componente core dei moduli adattivi - Contenitore di moduli
description: Aggiungere un modulo adattivo a una pagina web.
role: Architect, Developer, Admin, User
hide: true
hidefromtoc: true
exl-id: 1e413ef3-7a6f-41fc-825d-dbe09ebaffe9
source-git-commit: 37ac7d3a9ae8c88d4c9be8129cfbd1eb4a7cccd1
workflow-type: ht
source-wordcount: '1048'
ht-degree: 100%

---

# reCPATCHA di Google {#google-recaptcha}

Il CAPTCHA (Completely Automated Public Turing test to tell Computers and Humans Apart) è un programma comunemente utilizzato nelle transazioni online per distinguere tra esseri umani e programmi o bot automatizzati. Rappresenta una sfida e valuta la risposta dell’utente per determinare se si tratta di un essere umano o di un bot che interagisce con il sito. Impedisce all’utente di procedere se il test non riesce e contribuisce a rendere sicure le transazioni online impedendo ai bot di pubblicare spam o avere scopi dannosi.

AEM Forms as a Cloud Service supporta il reCAPTCHA di Google v2 nei Moduli adattivi. Puoi utilizzarlo per presentare una sfida CAPTCHA all’invio del modulo

## Utilizzo {#reasons-to-use-google-recaptcha}


- **Prevenzione di spam e bot**: uno dei motivi principali per cui utilizzare un reCAPTCHA è quello di evitare che gli invii di spam e i bot dannosi invadano il modulo. Gli algoritmi avanzati di reCAPTCHA possono rilevare i tentativi automatizzati di inviare il modulo, garantendo in tal modo che solo gli utenti legittimi possano interagire con esso.

- **Sicurezza avanzata**: implementando un reCAPTCHA, aggiungi un ulteriore livello di sicurezza al modulo adattivo. In questo modo è possibile proteggere le informazioni riservate e impedire a utenti malintenzionati di sfruttare le vulnerabilità.

- **Esperienza utente**: mentre a volte i CAPTCHA possono essere considerati come un inconveniente, l’approccio adattivo di reCAPTCHA implica che alla maggior parte degli utenti viene presentata un’esperienza semplificata e intuitiva che richiede un’interazione minima. Questo può contribuire a mantenere un’esperienza utente positiva scoraggiando al contempo i bot.

- **Adattabilità**: il meccanismo adattivo di reCAPTCHA analizza il comportamento degli utenti e le interazioni per determinare se si tratta di esseri umani o meno. Ciò significa che il livello di sfida presentato all’utente può variare in base alla probabilità che si tratti di un bot. Questa adattabilità riduce gli attriti per gli utenti autentici mantenendo al contempo una sicurezza elevata.

- **Moderazione manuale ridotta**: riducendo in modo significativo il numero di invii di spam e di contenuti generati da bot, il reCAPTCHA può risparmiare tempo e risorse che altrimenti verrebbero spese per la moderazione manuale e la pulizia.

## Versione e compatibilità {#version-and-compatibility}

Il componente core reCAPTCHA di Google per moduli adattivi è stato rilasciato nell’agosto 2023 come parte della “versione” dei componenti core. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile con<br>[versione 2.0.4](/help/versions.md) e successive | Compatibile | Compatibile |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md).

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente core reCAPTCHA di Google per moduli adattivi, consulta la documentazione tecnica disponibile su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/recaptcha/v1/recaptcha). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza reCAPTCHA di Google per i visitatori tramite la finestra di dialogo Configura. Puoi anche definire le opzioni reCAPTCHA di Google facilmente per un’esperienza utente semplice.

### Scheda Base {#basic-tab}

- **Nome**: è possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

- **Titolo**: con il relativo titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungi un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

- **Nascondi titolo**: seleziona l’opzione per nascondere il titolo del componente.

- **Configurazione** -

- **Tipo** -

- **Nascondi componente**: seleziona questa opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.

- **Disattiva componente**: seleziona questa opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. I dati del componente disabilitato non vengono inviati. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

- **Sola lettura**: seleziona questa opzione per rendere il componente non modificabile. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.

### Scheda Convalida {#validation-tab}

- **Messaggio di errore**: questa opzione consente di inserire un messaggio visualizzato se la casella di controllo **Obbligatorio** è selezionata e il campo modulo viene lasciato vuoto.

## Consulta anche {#see-also}

- [Creare un modulo adattivo di AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=it)
- [Aggiungere un modulo adattivo di AEM a una pagina AEM Sites](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=it)
- [Applicare i temi a un modulo adattivo di AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=it)
- [Aggiungere componenti a un modulo adattivo di AEM](/help/adaptive-forms/introduction.md#adaptive-forms-core-components-components)
- [Utilizzare reCAPTCHA in un modulo adattivo di AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/captcha-adaptive-forms.html?lang=it)
- [Generare la versione PDF (DoR) di un modulo adattivo di AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/generate-document-of-record-core-components.html?lang=it)
- [Tradurre un modulo adattivo di AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-aem-translation-workflow-to-localize-adaptive-forms-core-components.html?lang=it)
- [Abilitare Adobe Analytics per un modulo adattivo per tenere traccia dell’utilizzo dei moduli](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/services/enable-adobe-analytics-adaptive-form-using-experience-cloud-setup-automation.html?lang=it)
- [Collegare un modulo adattivo a Microsoft SharePoint](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#create-sharepoint-configuration.html?lang=it)
- [Collegare un modulo adattivo a Microsoft Power Automate](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#microsoft-power-automate.html?lang=it)
- [Collegare un modulo adattivo a Microsoft OneDrive](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-onedrive.html?lang=it)
- [Collegare un modulo adattivo all’archiviazione BLOB di Microsoft Azure](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-azure-blob-storage.html?lang=it)
- [Collegare un modulo adattivo a Salesforce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/oauth2-client-credentials-flow-for-server-to-server-integration.html?lang=it)
- [Utilizzare Adobe Sign in un modulo adattivo di AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/use-adobe-sign/working-with-adobe-sign.html?lang=it)
- [Aggiungere una nuova lingua per un modulo adattivo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/supporting-new-language-localization-core-components.html?lang=it)
- [Inviare dati del modulo adattivo a un database](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/data-integration.html?lang=it)
- [Inviare dati del modulo adattivo a un endpoint REST](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-rest-endpoint.html?lang=it)
- [Inviare dati del modulo adattivo al flusso di lavoro di AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#invoke-an-aem-workflow.html?lang=it)
- [Utilizzare il portale dei moduli per elencare moduli adattivi di AEM su un sito web di AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-forms-portal.html?lang=it)

