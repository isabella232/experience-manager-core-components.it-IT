---
title: Utilizzo dei componenti core E-mail
description: Informazioni sull’installazione, la configurazione e l’utilizzo di base dei componenti core E-mail.
role: Architect, Developer, Admin, User
exl-id: 0e79ca8f-eb0a-4519-b1e8-a9d3b0b99987
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: ht
source-wordcount: '653'
ht-degree: 100%

---


# Utilizzo dei componenti core E-mail {#using}

Informazioni sull’installazione, la configurazione e l’utilizzo di base dei componenti core E-mail.

## Installazione dei componenti core E-mail {#installation}

I componenti core E-mail possono essere utilizzati con AEM 6.5. Consulta la [sezione Requisiti del documento di Introduzione ai componenti core E-mail](introduction.md#requirements) per ulteriori informazioni.

### Installare i componenti core {#core-components}

I componenti core E-mail sono basati sui componenti core di AEM. Poiché i Componenti core non sono forniti con AEM 6.5, è necessario installarli prima di installare i Componenti core E-mail.

Consulta la sezione [Scarica e installa](/help/get-started/using.md#download-and-install) del documento Utilizzo dei componenti core per informazioni dettagliate su come installarli.

### Installare i componenti core E-mail {#email-core-components}

Una volta che i Componenti core sono installati nell’istanza, è necessario installare anche i componenti core E-mail. I componenti core E-mail non fanno ancora parte dell’Archetipo di progetto AEM, quindi sarà necessario aggiungerli al progetto manualmente. Segui la documentazione nel [wiki GitHub sui componenti core E-mail per l’installazione.](https://github.com/adobe/aem-core-email-components/wiki/Adding-to-Existing-Project)

Puoi seguire queste stesse istruzioni se desideri adattare un progetto esistente all’utilizzo dei componenti core E-mail.

## Configurazione {#configuration}

Dopo aver installato i componenti core, devi completare due importanti passaggi di configurazione.

### Configurare Campaign {#configure-campaign}

È necessario configurare l’integrazione AEM in Adobe Campaign per consentire alle due soluzioni di comunicare.

* Configurare l’integrazione di Adobe Campaign
   * Adobe Campaign Classic: [integrazione con Adobe Campaign Classic](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html?lang=it)
   * Adobe Campaign Standard: [integrazione con Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=it)
* [Collega la configurazione dell’integrazione Adobe Campaign](/help/email/components/page.md#cloud-services-tab) alla pagina del contenuto in cui utilizzerai i componenti core E-mail

### Aggiungi un filtro del tipo di risorsa di AEM per i componenti E-mail {#aem-resource-filter}

Affinché Adobe Campaign possa eseguire il rendering delle e-mail in base ai componenti core E-mail, è necessario regolare un filtro in Campaign.

1. Accedi ad Adobe Campaign come amministratore utilizzando la console client.

1. Seleziona **Strumenti** -> **Esplora** dalla barra del menu.

1. In Esplora, passa al nodo **Amministrazione** -> **Platform** -> **Opzioni**.

1. Seleziona l’opzione `AEMResourceTypeFilter` desiderata dall’elenco.

1. Nel campo **Valore**, aggiungi `core/email/components/page/<v1>/page` se non è già presente.

   * Sostituisci `<v1>` con la versione corrente del [Componente pagina](/help/email/components/page.md) dei componenti core E-mail, quali `v1`.
   * Tieni presente che i valori nel campo **Valori** devono essere delimitati da virgole.

1. Fai clic su **Salva**.

## Utilizzo dei componenti core E-mail {#using-components}

Una volta che i componenti E-mail sono installati e l’integrazione con Adobe Campaign è stata configurata, puoi utilizzare questi componenti per creare contenuti e-mail in AEM e inviarli ai destinatari utilizzando Adobe Campaign. Di seguito è riportata una panoramica del flusso di lavoro.

| Passaggio | Descrizione | Soluzione |
|---|---|---|
| 1 | Gli autori creano una struttura gerarchica a forma libera di cartelle e contenuti e-mail come pagine. | AEM |
| 2 | Utilizzando l’[Editor modelli,](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it) gli autori configurano un’intestazione e/o un piè di pagina e-mail da condividere tra tutte le pagine e-mail risultanti da questo modello. | AEM |
| 3 | Gli autori utilizzano l’[Editor pagina](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/editing-content.html?lang=it) per creare contenuti e-mail utilizzando l’editor di testo, in cui è possibile scegliere le variabili di Adobe Campaign e utilizzare il componente Segmentazione per mostrare in modo condizionale le informazioni sui criteri soddisfatti dal destinatario. | AEM |
| 4 | Quando il contenuto dell’e-mail è completo, [viene eseguito un flusso di lavoro](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/workflows/overview.html?lang=it) per approvare il contenuto e inviarlo a Campaign. | AEM |
| 5 | Viene creata una consegna definendo un elenco di destinatari. | Campaign |
| 6 | Il contenuto creato in AEM viene selezionato come contenuto della consegna. | Campaign |
| 7 | Il contenuto viene inviato ai destinatari, sostituendo le variabili di Adobe Campaign con le informazioni personalizzate dei destinatari. | Campaign |

Per un esempio di creazione di contenuti e-mail in AEM e consegna in Adobe Campaign, consulta le seguenti risorse.

* AEM 6.5: [Utilizzo di Adobe Campaign Classic e Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html?lang=it)
