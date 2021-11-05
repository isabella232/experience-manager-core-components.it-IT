---
title: Componente Immagine
description: Il componente core Immagine è un componente immagine adattivo che offre funzioni di modifica diretta.
role: Architect, Developer, Admin, User
exl-id: c5e57f4b-139f-40e7-8d79-be9a74360b63
source-git-commit: d435e82d5950336c66997399829e3baf23f170c0
workflow-type: ht
source-wordcount: '2162'
ht-degree: 100%

---

# Componente Immagine{#image-component}

Il componente core Immagine è un componente immagine adattivo che offre funzioni di modifica diretta.

## Utilizzo {#usage}

Il componente Immagine offre all’autore di contenuto una selezione adattiva delle immagini e un comportamento reattivo con caricamento lento per il visitatore della pagina, nonché una facilità di posizionamento e ritaglio delle immagini.

Le larghezze delle immagini e il ritaglio nonché le altre impostazioni possono essere definiti dall’autore del modello nella [finestra di dialogo per progettazione](#design-dialog). L’editor di contenuto può caricare o selezionare le risorse nella [finestra di dialogo per configurazione](#configure-dialog) e ritagliare l’immagine nella [finestra di dialogo per modifica](#edit-dialog). Per maggiore comodità, è disponibile anche una semplice modifica diretta dell’immagine.

## Funzioni reattive {#responsive-features}

Il componente Immagine è dotato di solide funzioni reattive pronte per l’uso. A livello di modello della pagina, si può utilizzare la [finestra di dialogo per Progettazione](#design-dialog) per definire le larghezze predefinite della risorsa immagine. Il componente Immagine carica quindi automaticamente la larghezza corretta da visualizzare, in base alle dimensioni della finestra del browser. Quando la finestra viene ridimensionata, il componente Immagine carica dinamicamente la dimensione corretta dell’immagine. Gli sviluppatori di componenti non devono preoccuparsi di definire query multimediali personalizzate, in quanto il componente Immagine è già ottimizzato per caricare il contenuto.

Inoltre, il componente Immagine supporta il caricamento lento per posticipare il caricamento della risorsa immagine effettiva fino a quando non sarà visibile nel browser, aumentando la reattività delle pagine.

## Supporto di Dynamic Media {#dynamic-media}

Il componente Immagine (a partire dalla [versione 2.13.0](/help/versions.md)) supporta le risorse di [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=it#dynamicmedia). [Se abilitate,](#design-dialog) queste funzioni consentono di aggiungere risorse immagine di Dynamic Media con una semplice azione di trascinamento e rilascio della selezione oppure tramite il browser delle risorse, esattamente come faresti con qualsiasi altra immagine. Sono inoltre supportati modificatori di immagini, immagini preimpostate e ritaglio avanzato.

La tua esperienza del web costruita con i Componenti core ora si arricchisce delle molte funzionalità per le immagini offerte da Dynamic Media, efficienti, performanti, multipiattaforma e con tecnologia Sensei.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Immagine è la v2, introdotta con la versione 2.0.0 dei Componenti core a gennaio 2018, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](v1/image-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Supporto di SVG {#svg-support}

Il componente Immagine supporta la grafica vettoriale scalabile (SVG).

* Il trascinamento e rilascio di una risorsa SVG da DAM e il caricamento di un file SVG da un file system locale sono entrambi supportati.
* L’Adaptive Image Servlet trasmette in streaming il file SVG originale (le trasformazioni vengono ignorate).
* Per un’immagine SVG, le “immagini intelligenti” e le “dimensioni intelligenti” sono impostate su un array vuoto nel modello di immagine.

### Sicurezza {#security}

Per motivi di sicurezza, il file SVG originale non viene mai richiamato direttamente dall’editor di immagini. Viene richiamato tramite `<img src=“path-to-component”>`. Ciò impedisce al browser di eseguire eventuali script incorporati nel file SVG.

>[!CAUTION]
>
>Il supporto SVG richiede la versione 2.1.0 o successiva dei Componenti core insieme al [service pack 2](https://experienceleague.adobe.com/docs/experience-manager-64/release-notes/sp-release-notes.html?lang=it) per AEM 6.4 o versioni successive per supportare le [funzioni dell’editor di immagini](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/components-templates/image-editor.html?lang=it) in AEM.

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Immagine e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_image_it).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Immagine [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_image_v2_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

Il componente Immagine supporta [i microdati schema.org](https://schema.org).

## Finestra di dialogo per configurazione {#configure-dialog}

Oltre alla normale [finestra di dialogo per modifica](#edit-dialog) e [finestra di dialogo per progettazione](#design-dialog), il componente Immagine offre anche una finestra di dialogo per configurazione, in cui l’immagine stessa viene definita insieme alla sua descrizione e alle sue proprietà di base.

### Scheda Risorsa {#asset-tab}

![Scheda Risorsa della finestra di dialogo per configurazione del componente Immagine](/help/assets/image-configure-asset.png)

* **Risorsa immagine**
   * Rilascia una risorsa dal [browser di risorse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=it) oppure tocca l’opzione **Sfoglia** per caricarla da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * Tocca o fai clic su **Modifica** per [gestire i rendering della risorsa](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=it) nell’editor risorse.

### Scheda Metadati {#metadata-tab}

![Scheda Metadati della finestra di dialogo per configurazione del componente Immagine](/help/assets/image-configure-metadata.png)

* **Tipo di predefinito**: definisce i tipi di immagini preimpostate disponibili, **Predefinito immagine** o **Ritaglio avanzato**, ed è disponibile solo se [le funzioni di Dynamic Media](#dynamic-meida) sono abilitate.
   * **Predefinito immagine**: se per **Tipo di predefinito** è selezionata l’opzione **Predefinito immagine**, è disponibile l’elenco a discesa **Predefinito immagine** che consente di selezionare i predefiniti di Dynamic Media disponibili. Questa opzione è disponibile solo se per la risorsa selezionata esistono dei predefiniti.
   * **Ritaglio avanzato**: quando per **Tipo di predefinito** è selezionata l’opzione **Ritaglio avanzato**, avanzato, è disponibile l’elenco a discesa **Rendering** che consente di selezionare i rendering disponibili della risorsa selezionata. Questa opzione è disponibile solo se per la risorsa selezionata sono definiti rendering.
   * **Modificatori immagine**: qui si possono definire comandi Dynamic Media aggiuntivi per la gestione delle immagini, separati da `&`, indipendentemente da qualunque cosa sia selezionata per **Tipo di predefinito**.
* **L’immagine è decorativa**: controlla se l’immagine deve essere ignorata dalla tecnologia per l’accessibilità e quindi non richiede un testo alternativo. Questo vale solo per le immagini decorative.
* **Testo alternativo**: alternativa testuale del significato o della funzione dell’immagine per utenti ipovedenti.
   * **Ottieni testo alternativo da DAM**: se questa opzione è selezionata, come testo alternativo dell’immagine verrà inserito il valore dei `dc:description`metadati in DAM.
* **Didascalia**: informazioni aggiuntive sull’immagine, per impostazione predefinita viene visualizzata sotto l’immagine.
   * **Ottieni didascalia da DAM**: se questa opzione è selezionata, come didascalia dell’immagine verrà inserito il valore dei `dc:title`metadati in DAM.
   * **Visualizza didascalia come nota a comparsa**: se questa opzione è selezionata, la didascalia non verrà visualizzata sotto l’immagine, ma, in alcuni browser, come nota a comparsa quando si passa il puntatore sull’immagine.
* **Collegamento**: collega l’immagine a un’altra risorsa.
   * Utilizza la finestra di dialogo per selezione per stabilire il collegamento con un’altra risorsa AEM.
   * Se non stabilisci il collegamento con un’altra risorsa AEM, immetti l’URL assoluto. Gli URL non assoluti vengono interpretati come relativi ad AEM.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

>[!TIP]
>
>Le opzioni **Ritaglio avanzato** e **Predefinito immagine** si escludono a vicenda. Se un autore deve utilizzare un predefinito immagine insieme a al rendering di un ritaglio avanzato, deve utilizzare i **modificatori immagine** per aggiungere manualmente i predefiniti.

## Finestra di dialogo per modifica {#edit-dialog}

La finestra di dialogo per modifica consente all’autore di contenuto di ritagliare, modificare la mappa di lancio ed eseguire lo zoom dell’immagine.

>[!NOTE]
>
>Le funzioni di ritaglio, rotazione e zoom non sono applicabili alle risorse Dynamic Media. Se le [funzioni di Dynamic Media](#dynamic-media) sono abilitate, tutte le modifiche apportate alle risorse Dynamic Media devono essere eseguite tramite la [finestra di dialogo per configurazione.](#configure-dialog)

![Finestra di dialogo per modifica del componente Immagine](/help/assets/image-edit.png)

* Avvia ritaglio

   ![Icona Avvia ritaglio](/help/assets/image-start-crop.png)

   Selezionando questa opzione si apre un elenco a discesa per le proporzioni predefinite del ritaglio.

   * Scegli l’opzione **Free Hand** per definire il ritaglio desiderato.
   * Scegli l’opzione **Rimuovi Ritaglio** per visualizzare la risorsa originale.

   Una volta selezionata un’opzione di ritaglio, utilizza le maniglie blu per dimensionare il ritaglio sull’immagine.

   ![Opzioni di ritaglio](/help/assets/image-crop-options.png)

* Ruota a destra

   ![Icona Ruota a destra](/help/assets/image-rotate-right.png)

   Utilizza questa opzione per ruotare l’immagine di 90° verso destra (in senso orario).

* Riflessione orizzontale

   ![Icona Riflessione orizzontale](/help/assets/image-flip-horizontal.png)

   Utilizza questa opzione per capovolgere l’immagine orizzontalmente o ruotarla di 180° lungo l’asse y.

* Riflessione verticale

   ![Icona Riflessione verticale](/help/assets/image-flip-vertical.png)

   Utilizza questa opzione per capovolgere l’immagine verticalmente o ruotarla 180° lungo l’asse x.

* Reimposta zoom

   ![Icona Reimposta zoom](/help/assets/image-reset-zoom.png)

   Se l’immagine è già stata ingrandita, utilizza questa opzione per reimpostare il livello di zoom.

* Apri cursore Zoom

   ![Icona Apri cursore zoom](/help/assets/image-zoom.png)

   Utilizza questa opzione per visualizzare un cursore che permette di controllare il livello di zoom dell’immagine.

   ![Controllo cursore dello zoom](/help/assets/image-zoom-slider.png)

L’editor locale può essere utilizzato anche per modificare l’immagine. A causa di limiti di spazio, in linea sono disponibili solo opzioni di base. Per le opzioni di modifica completa, utilizza la modalità a schermo intero.

![Opzioni di modifica diretta dell’immagine](/help/assets/image-in-place-edit.png)

>[!NOTE]
>
>Le funzioni di modifica delle immagini (ritaglio, riflessione, rotazione) non sono supportate per le immagini GIF. Tutte le modifiche apportate in modalità di modifica alle immagini GIF non verranno mantenute.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire le opzioni di ritaglio, caricamento e rotazione disponibili per l’autore di contenuto quando utilizza questo componente.

### Scheda Principale {#main-tab}

Nella scheda **Principale** puoi definire un elenco di larghezze consentite, espresse in pixel, in modo che l’immagine e il componente possano automaticamente caricare la larghezza appropriata in base alle dimensioni della finestra del browser. Questa è una parte importante delle [funzioni reattive](#responsive-features) del componente Immagine.

Inoltre, puoi definire quali opzioni generali del componente vengono automaticamente abilitate o disabilitate quando l’autore aggiunge il componente a una pagina.

![Scheda Principale della finestra di dialogo per progettazione del componente Immagine](/help/assets/image-design-main.png)

* **Abilita funzioni DM**: se questa opzione è selezionata, sono disponibili le funzioni di [Dynamic Media](#dynamic-media).
* **Attiva il caricamento lento**: consente di definire se l’opzione di caricamento lento è abilitata automaticamente quando si aggiunge il componente Immagine a una pagina.
* **L’immagine è decorativa**: consente di definire se l’opzione dell’immagine decorativa è abilitata automaticamente quando si aggiunge il componente Immagine a una pagina.
* **Ottieni testo alternativo da DAM**: consente di definire se l’opzione per recuperare il testo alternativo dal DAM è abilitata automaticamente quando si aggiunge il componente Immagine a una pagina.
* **Ottieni didascalia da DAM**: consente di definire se l’opzione per recuperare la didascalia dal DAM è abilitata automaticamente quando si aggiunge il componente Immagine a una pagina.
* **Visualizza didascalia come nota a comparsa**: consente di definire se l’opzione per visualizzare la didascalia dell’immagine come nota a comparsa è abilitata automaticamente quando si aggiunge il componente Immagine a una pagina.
* **Disabilita tracciamento UUID**: consente di disabilitare il tracciamento dell’UUID della risorsa immagine.
* **Larghezze**: consente di definire un elenco di larghezze, espresse in pixel, in modo che l’immagine e il componente possano automaticamente caricare la larghezza appropriata in base alle dimensioni della finestra del browser.
   * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere un’altra dimensione.
      * Utilizza le maniglie per modificare l’ordine delle dimensioni.
      * Utilizza l’icona **Elimina** per rimuovere una larghezza.
   * Per impostazione predefinita, il caricamento delle immagini viene differito fino a quando non diventano visibili.
      * Deseleziona l’opzione **Attiva il caricamento lento** per caricare le immagini al caricamento della pagina.
* **Qualità JPEG**: fattore di qualità, espresso come percentuale tra 0 e 100, per le immagini JPEG trasformate, ad esempio ridimensionate o ritagliate.

### Scheda Funzioni {#features-tab}

Nella scheda **Funzioni** è possibile definire le opzioni disponibili per gli autori di contenuto quando utilizzano il componente, incluse le opzioni di caricamento, orientamento e ritaglio.

* Origine

   ![Scheda Funzioni della finestra di dialogo per progettazione del componente Immagine](/help/assets/image-design-features-source.png)

   Seleziona l’opzione **Consenti caricamento risorse dal file system** per consentire agli autori di contenuto di caricare immagini dal proprio computer locale. Per forzare gli autori di contenuto a selezionare solo le risorse da AEM, deseleziona questa opzione.

* Orientamento

   ![Scheda Funzioni della finestra di dialogo per progettazione del componente Immagine](/help/assets/image-design-features-orientation.png)

* **Rotazione**
Seleziona questa opzione per consentire all’autore di contenuto di utilizzare l’opzione 
**Ruota a destra**.
* **Riflessione**
Seleziona questa opzione per consentire all’autore di contenuto di utilizzare 
le opzioni **Riflessione orizzontale** e **Riflessione verticale**.

   >[!CAUTION]
   >
   >L’opzione **Riflessione** è disabilitata per impostazione predefinita. Attivando questa opzione, i pulsanti **Riflessione verticale** e **Riflessione orizzontale** vengono visualizzati nella finestra di dialogo per modifica del componente Immagine, ma questa funzione non è attualmente supportata da AEM e le modifiche effettuate utilizzando queste opzioni non verranno mantenute.

* Ritaglio

   ![Scheda Funzioni della finestra di dialogo per progettazione del componente Immagine](/help/assets/image-design-features-cropping.png)

   Seleziona l’opzione **Consenti ritaglio** per consentire all’autore di contenuto di ritagliare l’immagine nella finestra di dialogo per modifica del componente.
   * Fai clic su **Aggiungi** per aggiungere una proporzione predefinita per il ritaglio.
   * Immetti un nome descrittivo che verrà visualizzato nel menu a discesa **Avvia ritaglio**.
   * Immetti il rapporto numerico per la proporzione.
   * Utilizza le maniglie di trascinamento per modificare l’ordine delle proporzioni
   * Utilizza l’icona cestino per eliminare una proporzione.

   >[!CAUTION]
   >
   >In AEM, i rapporti di proporzione del ritaglio sono definiti come **altezza/larghezza**. Ciò differisce dalla definizione tradizionale di larghezza/altezza e viene fatto per ragioni di compatibilità con le versioni precedenti. Gli autori di contenuto non noteranno alcuna differenza, purché venga fornito un nome chiaro per la proporzione, in quanto il nome viene visualizzato nell’interfaccia utente e non nella proporzione stessa.

### Scheda Stili {#styles-tab-1}

Il componente Immagine supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

## Adaptive Image Servlet {#adaptive-image-servlet}

Il componente Immagine utilizza l’Adaptive Image Servlet dei Componente core. [L’Adaptive Image Servlet](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) è responsabile dell’elaborazione e dello streaming delle immagini e può essere utilizzato dagli sviluppatori nelle loro [personalizzazioni dei Componenti core](/help/developing/customizing.md).

>[!NOTE]
>
>Le richieste condizionali tramite l’intestazione `Last-Modified` sono supportate dall’Adaptive Image Servlet, ma il caching dell’intestazione `Last-Modified` [deve essere abilitato in Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=it#caching-http-response-headers).
>
>L’esempio di configurazione di Dispatcher in [Archetipo progetto AEM](/help/developing/archetype/overview.md) già include questa configurazione.

## Adobe Client Data Layer {#data-layer}

Il componente Immagine supporta [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
