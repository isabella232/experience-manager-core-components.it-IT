---
title: Componente Segmentazione e-mail
description: Componente Segmentazione e-mail
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 16%

---


# Componente Segmentazione e-mail {#email-segmentation-component}

Il componente Segmentazione e-mail utilizza le variabili di Adobe Campaign per mostrare e nascondere il contenuto in base al destinatario del contenuto.

## Utilizzo {#usage}

Il componente Segmentazione e-mail consente all’autore del contenuto di nascondere e mostrare il contenuto in base alle condizioni soddisfatte dalle variabili del destinatario fornite da Adobe Campaign. In questo modo, i destinatari del contenuto visualizzano il contenuto in base alla loro segmentazione.

* L’autore del modello può utilizzare il [finestra di dialogo di progettazione](#design-dialog) per definire quali componenti possono essere aggiunti come segmenti.
* L’autore del contenuto può utilizzare [finestra di dialogo configura](#configure-dialog) per aggiungere componenti come segmenti e configurare quali segmenti vengono visualizzati in base alle variabili di Adobe Campaign.

In alternativa all’utilizzo della finestra di dialogo di configurazione, una volta che l’autore del contenuto ha aggiunto il componente Segmentazione e-mail a una pagina di contenuto, l’autore del contenuto può quindi trascinare e rilasciare componenti aggiuntivi sui componenti Segmentazione e-mail per creare nuovi segmenti.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Segmentazione e-mail è v1, introdotto con la versione x dei componenti core e-mail nell’ottobre 2022, ed è descritto in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile | Compatibile |

## Esempio di output del componente {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente Segmentazione e-mail e dell’output di HTML e JSON, visita il [Libreria dei componenti.](https://adobe.com/go/aem_cmp_library_email_segmentation)

### Dettagli tecnici {#technical-details}

Documentazione tecnica più recente sul componente E-mail Teaser [si trova su GitHub.](https://adobe.com/go/aem_cmp_tech_email_segmentation_v1)

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core.](/help/developing/overview.md)

## Finestra di dialogo per la configurazione {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di creare, rinominare e ridisporre i segmenti e di definire il segmento attivo. Nel componente Segmentazione e-mail, un segmento è semplicemente un altro componente nascosto o visualizzato in base alle condizioni soddisfatte dal destinatario del contenuto. Puoi confrontarlo con il [Componente della scheda Componenti core,](/help/components/tabs.md) ma nel componente Segmentazione viene visualizzato solo il contenuto della scheda che soddisfa le condizioni.

### Scheda Elementi {#items-tab}

![Scheda degli elementi della finestra di dialogo di configurazione del componente Segmentazione e-mail](/help/email/assets/email-segmentation-configure-items.png)

Utilizza la **Aggiungi segmento** per aprire il selettore dei componenti e scegliere quale componente aggiungere come segmento. Una volta aggiunta, una voce viene aggiunta all’elenco, che contiene i seguenti elementi:

* **Icona** - Icona del tipo di componente del segmento per una facile identificazione nell’elenco. Passa il puntatore del mouse sulla voce per visualizzare il nome completo del componente sotto forma di descrizione comando.
* **Condizione** - La condizione che deve essere soddisfatta perché questo segmento venga mostrato al destinatario del contenuto.
   * Le condizioni disponibili sono definite nel [finestra di dialogo di progettazione.](#design-dialog)
   * **Predefinito** - Definisce il segmento predefinito da mostrare se non sono soddisfatte altre condizioni
   * **Personalizzato** - Consente all’autore di definire una condizione
      * Le condizioni sono basate su variabili di personalizzazione Adobe Campaign
      * [Consulta qui per le risorse di personalizzazione Adobe Campaign Standard.](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
      * [Consulta qui per le risorse di personalizzazione Adobe Campaign Classic.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)
* **Elimina** - Tocca o fai clic per eliminare il segmento dal componente Segmentazione e-mail.
* **Ridisponi** - Tocca o fai clic e trascina per ridisporre i segmenti.

>[!TIP]
>
>Se la visualizzazione del contenuto viene ridotta in modo che la finestra di dialogo di modifica diventi a schermo intero, la **Aggiungi** il pulsante sarà nascosto. I componenti possono ancora essere aggiunti al componente Segmentazione e-mail da [trascinando dal browser Componenti e rilasciando il componente Segmentazione e-mail nell’editor dei contenuti.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=it#inserting-a-component)

### Scheda Proprietà {#properties-tab}

![Scheda delle proprietà della finestra di dialogo di configurazione del componente Segmentazione e-mail](/help/email/assets/email-segmentation-configure-properties.png)

* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente in HTML.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando il contenuto risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sui CSS.

### Scheda Accessibilità {#accessibility-tab}

![Scheda della finestra di dialogo di accesso facilitato del componente Segmentazione e-mail](/help/email/assets/email-segmentation-configure-accessibility.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette di [accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente.

* **Etichetta**: il valore di un attributo dell’etichetta ARIA del componente

### Scheda Stili {#styles-tab-edit}

Il componente Segmentazione e-mail supporta il AEM [Sistema di stili.](/help/get-started/authoring.md#component-styling)

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nel [finestra di dialogo di progettazione](#design-dialog) affinché la scheda sia disponibile.

## Seleziona pannello {#select-panel}

L’autore del contenuto può utilizzare **Pannello Seleziona** sulla barra degli strumenti del componente per passare a un segmento diverso per la modifica e per ridisporre facilmente i segmenti.

![Icona Seleziona pannello](/help/email/assets/select-panel-icon.png)

Una volta selezionato il **Pannello Seleziona** nella barra degli strumenti del componente, i segmenti configurati vengono visualizzati come un elenco a discesa.

* L’elenco è ordinato dalla disposizione assegnata dei segmenti e si riflette nella numerazione.
* Il tipo di componente del segmento viene visualizzato per primo, seguito dalla descrizione del segmento con font più chiaro.

![Finestra a comparsa selezione pannello](/help/email/assets/select-panel-popover.png)

* Toccando o facendo clic su una voce nel menu a discesa, la visualizzazione nell’editor passa a quel segmento.
* I segmenti possono essere ridisposti in posizione utilizzando le maniglie di trascinamento.

>[!NOTE]
>
>I segmenti vengono sottoposti a rendering come schede all’interno dell’editor di pagine per mostrare che sono presenti più opzioni per il contenuto finale. Queste schede non sono selezionabili dall’autore all’interno dell’editor pagina. Utilizza il pannello di selezione per passare da un segmento all’altro.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire quali componenti possono essere aggiunti come segmenti al componente Segmentazione e-mail e di definire quali stili personalizzati sono disponibili per l’autore del contenuto.

### Scheda Componenti consentiti {#allowed-components-tab}

La **Componenti consentiti** viene utilizzata per definire quali componenti possono essere aggiunti dall’autore del contenuto come segmenti al componente Segmentazione e-mail.

La **Componenti consentiti** la scheda funziona come la scheda dello stesso nome quando [definizione dei criteri e delle proprietà di un Contenitore di layout nell’Editor modelli.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it)

### Scheda Stili {#styles-tab}

Il componente Segmentazione e-mail supporta il AEM [Sistema di stili.](/help/get-started/authoring.md#component-styling)

### Scheda Condizioni definite {#defined-conditions}

Utilizzo della **Condizioni definite** , l’editor modelli può definire quali condizioni sono disponibili per l’autore dei contenuti da selezionare durante la creazione dei segmenti.

![Scheda Condizioni definite della finestra di dialogo Progettazione](/help/email/assets/email-segmentation-design-defined-conditions.png)

Tocca o fai clic sul pulsante **Aggiungi** per creare nuove condizioni.

* **Nome della condizione del segmento** - Descrizione della condizione
* **Condizione del segmento** - La condizione effettiva che deve essere soddisfatta, in base alle variabili di personalizzazione Adobe Campaign
   * [Consulta qui per le risorse di personalizzazione Adobe Campaign Standard.](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
   * [Consulta qui per le risorse di personalizzazione Adobe Campaign Classic.](https://experienceleague.adobe.com/docs/)
* **Rimuovi** - Tocca per fare clic per rimuovere la condizione
* **Ridisponi** - Tocca o fai clic e trascina per ridisporre l’ordine delle condizioni
