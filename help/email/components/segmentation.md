---
title: Componente segmentazione e-mail
description: Il componente Segmentazione e-mail
role: Architect, Developer, Admin, User
exl-id: 6c88b8c5-189a-40c0-ab28-04d37dc5fbac
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '1133'
ht-degree: 100%

---


# Componente segmentazione e-mail {#email-segmentation-component}

Il componente Segmentazione e-mail utilizza le variabili di Adobe Campaign per mostrare e nascondere il contenuto in base al destinatario.

## Utilizzo {#usage}

Il componente Segmentazione e-mail consente all’autore del contenuto di nascondere e mostrare il contenuto in base alle condizioni soddisfatte dalle variabili riguardo al destinatario fornite da Adobe Campaign. In questo modo, i destinatari del contenuto lo possono visualizzare in base alla loro segmentazione.

* L’autore del modello può utilizzare la [finestra di dialogo per la progettazione](#design-dialog) per definire quali componenti possono essere aggiunti come segmenti.
* L’autore del contenuto può utilizzare la [finestra di dialogo di configurazione](#configure-dialog) per aggiungere componenti come segmenti e configurare quali segmenti vengono visualizzati in base alle variabili di Adobe Campaign.

In alternativa all’utilizzo della finestra di dialogo di configurazione, dopo aver aggiunto il componente Segmentazione e-mail a una pagina di contenuto, l’autore del contenuto può quindi inserire tramite trascinamento ulteriori componenti sul componente Segmentazione e-mail per creare nuovi segmenti.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Segmentazione e-mail è la v1, introdotta con la versione x dei Componenti core e-mail a ottobre 2022, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile  | - |

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Teaser e-mail [è disponibile su GitHub.](https://adobe.com/go/aem_cmp_tech_email_segmentation_v1)

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core.](/help/developing/overview.md)

## Finestra di dialogo per la configurazione {#configure-dialog}

La finestra di dialogo per la configurazione consente all’autore del contenuto di creare, rinominare e ridisporre i segmenti e di definire i segmenti attivi. Nel componente Segmentazione e-mail, un segmento è semplicemente un altro componente nascosto o visualizzato in base alle condizioni soddisfatte dal destinatario del contenuto. Puoi confrontarlo con il [Componente della scheda Componenti core,](/help/components/tabs.md) ma nel componente Segmentazione viene visualizzato solo il contenuto della scheda che soddisfa le condizioni.

### Scheda Elementi {#items-tab}

![Scheda degli elementi della finestra di dialogo di configurazione del componente Segmentazione e-mail](/help/email/assets/email-segmentation-configure-items.png)

Utilizza il pulsante **Aggiungi segmento** per aprire il selettore componenti e scegliere quale componente aggiungere come segmento. Una volta aggiunto, all’elenco viene aggiunta una voce che contiene i seguenti elementi:

* **Icona**: l’icona del tipo di componente del segmento per identificarlo facilmente nell’elenco. Passa il puntatore del mouse sulla voce per visualizzare il nome completo del componente sotto forma di descrizione comando.
* **Condizione**: la condizione che deve essere soddisfatta perché questo segmento venga mostrato al destinatario del contenuto.
   * Le condizioni disponibili sono definite nella [finestra di dialogo per la progettazione.](#design-dialog)
   * **Predefinito**: definisce il segmento predefinito da mostrare se non sono soddisfatte altre condizioni
   * **Personalizzato**: consente all’autore di definire una condizione
      * Le condizioni sono basate sulle variabili di personalizzazione Adobe Campaign
      * [Consulta qui per le risorse di personalizzazione di Adobe Campaign Standard.](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?lang=it)
      * [Consulta qui per le risorse di personalizzazione di Adobe Campaign Classic.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html?lang=it)
* **Elimina**: tocca o fai clic per eliminare il segmento dal componente Segmentazione e-mail.
* **Ridisponi**: tocca o fai clic e trascina per ridisporre i segmenti.

>[!TIP]
>
>Se la visualizzazione del contenuto viene ridotta in modo che la finestra di dialogo per la modifica diventi a schermo intero, il pulsante **Aggiungi** sarà nascosto. I componenti possono comunque essere aggiunti al componente Segmentazione e-mail [trascinandoli dal browser dei componenti e inserendoli nel componente Segmentazione e-mail nell’editor di contenuto.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=it#inserting-a-component)

### Scheda Proprietà {#properties-tab}

![Scheda delle proprietà della finestra di dialogo per la configurazione del componente Segmentazione e-mail](/help/email/assets/email-segmentation-configure-properties.png)

* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nell’HTML.
   * Se non specificato, viene generato automaticamente un ID univoco reperibile esaminando il contenuto risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sulle CSS.

### Scheda Accessibilità {#accessibility-tab}

![Scheda accessibilità della finestra di dialogo per la configurazione del componente Segmentazione e-mail](/help/email/assets/email-segmentation-configure-accessibility.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette di [accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente.

* **Etichetta**: il valore di un attributo dell’etichetta ARIA del componente

### Scheda Stili {#styles-tab-edit}

Il componente Segmentazione e-mail supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nella [finestra di dialogo per progettazione](#design-dialog) affinché la scheda sia disponibile.

## Seleziona pannello {#select-panel}

L’autore del contenuto può utilizzare l’opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a un segmento diverso da modificare e per cambiare facilmente l’ordine dei segmenti.

![Icona Seleziona pannello](/help/email/assets/select-panel-icon.png)

Dopo aver selezionato l’opzione **Seleziona pannello** nella barra degli strumenti del componente, i segmenti configurati vengono visualizzati come un elenco a discesa.

* L’elenco viene ordinato in base alla disposizione assegnata ai segmenti che viene riportata nella numerazione.
* Il tipo di componente del segmento viene visualizzato per primo, seguito dalla descrizione in font più chiaro.

![Finestra popover Seleziona pannello](/help/email/assets/select-panel-popover.png)

* Toccando o facendo clic su una voce nel menu a discesa, nell’editor viene visualizzato il segmento corrispondente.
* I segmenti possono essere ridisposti tramite le maniglie di trascinamento.

>[!NOTE]
>
>I segmenti vengono visualizzati come schede all’interno dell’Editor pagina per mostrare che sono presenti più opzioni per il contenuto finale. Queste schede non sono selezionabili dall’autore all’interno dell’editor pagina. Per passare da un segmento all’altro, utilizza il pannello di selezione.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente all’autore del modello di definire quali componenti possono essere aggiunti come segmenti al componente Segmentazione e-mail e quali stili personalizzati sono disponibili per l’autore di contenuto.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** viene utilizzata per definire quali componenti possono essere aggiunti dall’autore del contenuto come segmenti del componente Segmentazione e-mail.

La scheda **Componenti consentiti** funziona come la scheda con lo stesso nome utilizzata per [definire i criteri e le proprietà di un Contenitore di layout nell’Editor modelli.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it)

### Scheda Stili {#styles-tab}

Il componente Segmentazione e-mail supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

### Scheda Condizioni definite {#defined-conditions}

Utilizzando la scheda **Condizioni definite**, l’Editor modelli può definire quali condizioni sono disponibili per la selezione per l’autore dei contenuti durante la creazione dei segmenti.

![Scheda Condizioni definite della finestra di dialogo per la progettazione](/help/email/assets/email-segmentation-design-defined-conditions.png)

Tocca o fai clic sul pulsante **Aggiungi** per creare nuove condizioni.

* **Nome della condizione del segmento**: descrizione della condizione
* **Condizione del segmento**: la condizione effettiva che deve essere soddisfatta, in base alle variabili di personalizzazione di Adobe Campaign
   * [Consulta qui per le risorse di personalizzazione di Adobe Campaign Standard.](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?lang=it)
   * [Consulta qui per le risorse di personalizzazione di Adobe Campaign Classic.](https://experienceleague.adobe.com/docs/
* **Rimuovi**: tocca o fai clic per rimuovere la condizione
* **Ridisponi**: tocca o fai clic e trascina per modificare l’ordine delle condizioni
