---
title: Utilizzo dei componenti core e-mail
description: Scopri l’installazione, la configurazione e l’utilizzo di base dei componenti core di e-mail.
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 6%

---


# Utilizzo dei componenti core e-mail {#using}

Scopri l’installazione, la configurazione e l’utilizzo di base dei componenti core di e-mail.

## Installazione dei componenti core e-mail {#installation}

I componenti core e-mail possono essere utilizzati con AEM 6.5. Consulta [Sezione Requisiti del documento di introduzione dei componenti core e-mail](introduction.md#requirements) per ulteriori informazioni.

### Installare i componenti core {#core-components}

I componenti core e-mail sono basati sui componenti core AEM. Poiché i componenti core non sono forniti con AEM, devi prima installare i componenti core AEM prima di installare i componenti core e-mail.

Vedi la sezione [Scarica e installa](/help/get-started/using.md#download-and-install) sezione del documento Utilizzo dei componenti core per informazioni dettagliate su come installare i componenti core.

### Installazione dei componenti core e-mail {#email-core-components}

Una volta installati i componenti core nell’istanza, è necessario installare anche i componenti core e-mail. I componenti core e-mail non fanno ancora parte del AEM Project Archetype, quindi dovrai aggiungerli manualmente al progetto. Segui la documentazione in [il wiki GitHub per i componenti core di e-mail da installare.](https://github.com/adobe/aem-core-email-components/wiki/Adding-to-Existing-Project)

Puoi seguire queste stesse istruzioni se desideri adattare un progetto esistente per l’utilizzo dei componenti core e-mail .

## Configurazione {#configuration}

Dopo aver installato i componenti core, devi completare due importanti passaggi di configurazione.

### Configurare Campaign {#configure-campaign}

È necessario configurare l&#39;integrazione AEM-Adobe Campaign per consentire alle due soluzioni di comunicare.

* Configurare l’integrazione Adobe Campaign
   * Adobe Campaign Classic: [Integrazione con Adobe Campaign Classic](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html)
   * Adobe Campaign Standard: [Integrazione con Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html)
* [Collegare la configurazione dell’integrazione Adobe Campaign](/help/email/components/page.md#cloud-services-tab) alla pagina del contenuto in cui utilizzerai i componenti core e-mail

### Aggiungere un filtro del tipo di risorsa AEM per i componenti e-mail {#aem-resource-filter}

Affinché Adobe Campaign possa eseguire il rendering delle e-mail in base ai componenti core dell’e-mail, è necessario regolare un filtro in Campaign.

1. Accedi ad Adobe Campaign come amministratore utilizzando la console client.

1. Seleziona **Strumenti** -> **Esplora** dalla barra del menu.

1. Nell’esploratore, passa alla **Amministrazione** -> **Piattaforma** -> **Opzioni** nodo.

1. Seleziona la `AEMResourceTypeFilter` dall’elenco.

1. In **Valore** campo, aggiungi `core/email/components/page/<v1>/page` se non è già presente.

   * Sostituisci `<v1>` con la versione corrente dei componenti core e-mail [Componente pagina](/help/email/components/page.md) quali `v1`.
   * Tieni presente che i valori in **Valori** Il campo deve essere delimitato da virgole.

1. Fai clic su **Salva**.

## Utilizzo dei componenti core e-mail {#using-components}

Una volta installati i componenti e-mail e configurata l’integrazione con Adobe Campaign, puoi utilizzare i componenti e-mail per creare contenuti e-mail in AEM e inviarli ai destinatari utilizzando Adobe Campaign. Di seguito è riportata una panoramica del flusso di lavoro.

| Passaggio | Descrizione | Soluzione |
|---|---|---|
| 1 | Gli autori creano una struttura gerarchica libera di cartelle e contenuti e-mail come pagine. | AEM |
| 2 | Utilizzo della [editor di modelli,](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it) gli autori configurano un’intestazione e/o un piè di pagina e-mail da condividere tra tutte le pagine e-mail risultanti da questo modello di pagina. | AEM |
| 3 | Gli autori utilizzano [editor di pagine](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/editing-content.html) per creare contenuti e-mail utilizzando l’editor di testo, in cui è possibile scegliere le variabili di Adobe Campaign e utilizzare il componente Segmentazione per mostrare le informazioni condizionali se il destinatario soddisfa determinati criteri. | AEM |
| 4 | Al termine del contenuto dell’e-mail, [un flusso di lavoro viene eseguito](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/workflows/overview.html) per approvare il contenuto e inviarlo a Campaign. | AEM |
| 5 | Viene creata una consegna che definisce un elenco di destinatari. | Campaign |
| 6 | Il contenuto creato in AEM viene selezionato come contenuto della consegna. | Campaign |
| 7 | Il contenuto viene inviato ai destinatari, sostituendo le variabili Adobe Campaign con le informazioni personalizzate dei destinatari. | Campaign |

Per un esempio di creazione di contenuti e-mail in AEM e consegna in Adobe Campaign, consulta le seguenti risorse.

* AEM as a Cloud Service: [Creazione di newsletter di Campaign con AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/campaign/creating-newsletters.html)
* AEM 6.5: [Utilizzo di Adobe Campaign Classic e Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html)

