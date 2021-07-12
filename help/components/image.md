---
title: Componente immagine
description: Il componente immagine di base è un componente immagine adattivo che offre funzioni di modifica diretta.
role: Architect, Developer, Admin, User
exl-id: c5e57f4b-139f-40e7-8d79-be9a74360b63
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '2170'
ht-degree: 2%

---

# Componente immagine{#image-component}

Il componente immagine di base è un componente immagine adattivo che offre funzioni di modifica diretta.

## Utilizzo {#usage}

Il componente Immagine offre una selezione adattiva delle immagini e un comportamento reattivo con caricamento lento per il visitatore della pagina, nonché un posizionamento e un ritaglio semplici delle immagini per l’autore del contenuto.

La larghezza dell&#39;immagine, il ritaglio e le impostazioni aggiuntive possono essere definiti dall&#39;autore del modello nella finestra di dialogo [progettazione](#design-dialog). L&#39;editor dei contenuti può caricare o selezionare le risorse nella finestra di dialogo [configura](#configure-dialog) e ritagliare l&#39;immagine nella finestra di dialogo [modifica](#edit-dialog). Per una maggiore comodità, è disponibile anche una semplice modifica diretta dell&#39;immagine.

## Funzioni reattive {#responsive-features}

Il componente Immagine è dotato di solide funzioni reattive pronte all’uso. A livello di modello di pagina, la [finestra di dialogo Progettazione](#design-dialog) può essere utilizzata per definire le larghezze predefinite della risorsa immagine. Il componente Immagine carica quindi automaticamente la larghezza corretta da visualizzare in base alle dimensioni della finestra del browser. Quando la finestra viene ridimensionata, il componente immagine carica dinamicamente al volo la dimensione corretta dell’immagine. Gli sviluppatori di componenti non devono preoccuparsi di definire query multimediali personalizzate, in quanto il componente immagine è già ottimizzato per caricare i contenuti.

Inoltre, il componente Immagine supporta il caricamento lento per posticipare il caricamento della risorsa immagine effettiva fino a quando non sarà visibile nel browser, aumentando la reattività delle pagine.

## Supporto Dynamic Media {#dynamic-media}

Il componente Immagine (a partire da [release 2.13.0](/help/versions.md)) supporta le risorse [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=en#dynamicmedia). [Quando abilitata, ](#design-dialog) queste funzioni consentono di aggiungere risorse di immagini Dynamic Media con una semplice azione di trascinamento della selezione o tramite il browser delle risorse, esattamente come faresti con qualsiasi altra immagine. Sono inoltre supportati modificatori di immagini, predefiniti immagine e ritaglio avanzato.

Le esperienze web create con i componenti core non possono utilizzare funzionalità avanzate, basate su tecnologia Sensei, solide, ad alte prestazioni, per immagini Dynamic Media multipiattaforma.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente immagine è v2, introdotta con la versione 2.0.0 dei componenti core a gennaio 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](v1/image-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Supporto SVG {#svg-support}

La grafica vettoriale scalabile (SVG) è supportata dal componente immagine.

* Sono entrambi supportati il trascinamento di una risorsa SVG da DAM e il caricamento di un file SVG da un file system locale.
* Il Servlet immagine adattiva trasmette in streaming il file SVG originale (le trasformazioni vengono saltate).
* Per un&#39;immagine SVG, le &quot;immagini intelligenti&quot; e le &quot;dimensioni intelligenti&quot; sono impostate su un array vuoto nel modello di immagine.

### Sicurezza {#security}

Per motivi di sicurezza, l’SVG originale non viene mai chiamato direttamente dall’Editor immagini. Viene chiamato tramite `<img src=“path-to-component”>`. Questo impedisce al browser di eseguire eventuali script incorporati nel file SVG.

>[!CAUTION]
>
>Il supporto SVG richiede la versione 2.1.0 dei componenti core o superiore insieme al [service pack 2](https://docs.adobe.com/content/help/it-IT/experience-manager-64/release-notes/sp-release-notes.html) per AEM 6.4 o versioni successive per supportare le [funzioni dell&#39;editor di immagini](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/image-editor.html) all&#39;interno di AEM.

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente immagine e dell’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_image) .

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente immagine [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_image_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

Il componente Immagine supporta i microdati [schema.org](https://schema.org).

## Finestra di dialogo Configura {#configure-dialog}

Oltre alla finestra di dialogo standard [modifica](#edit-dialog) e [progettazione](#design-dialog), il componente immagine offre una finestra di dialogo di configurazione in cui l&#39;immagine stessa è definita insieme alla relativa descrizione e alle proprietà di base.

### Scheda Risorsa {#asset-tab}

![Scheda Risorsa della finestra di dialogo di configurazione del componente immagine](/help/assets/image-configure-asset.png)

* **Risorsa immagine**
   * Rilascia una risorsa dal [browser Risorse](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) o tocca l’opzione **Sfoglia** per caricarla da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * Tocca o fai clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) nell’editor risorse.

### Scheda Metadati {#metadata-tab}

![Scheda Metadati della finestra di dialogo di configurazione del componente immagine](/help/assets/image-configure-metadata.png)

* **Tipo di predefinito** : definisce i tipi di predefiniti per immagini disponibili,  **Predefinito immagine o Ritaglio** avanzato **, ed è disponibile solo quando le funzioni di** Dynamic Media  [ ](#dynamic-meida) sono abilitate.
   * **Predefinito immagine** : se è selezionata l’opzione  **Predefinito** tipo di  **immagine** predefinita, è disponibile l’opzione  **Predefinito immagine** dal menu a discesa, che consente di selezionare i predefiniti Dynamic Media disponibili. Questa opzione è disponibile solo se per la risorsa selezionata sono definiti dei predefiniti.
   * **Ritaglio avanzato** : quando è selezionata l’opzione  **Tipo** predefinito di  **ritaglio** avanzato, è disponibile l’opzione  **** Rendering a discesa, che consente di selezionare i rendering disponibili della risorsa selezionata. Questa opzione è disponibile solo se per la risorsa selezionata sono definite rappresentazioni.
   * **Modificatori immagine**  - È possibile definire qui comandi aggiuntivi di gestione immagini Dynamic Media separati da  `&`, indipendentemente da quali tipi di  **predefiniti** siano selezionati.
* **L’immagine è decorativa**  - Controlla se l’immagine deve essere ignorata dalla tecnologia per l’accessibilità e quindi non richiede un testo alternativo. Questo vale solo per le immagini decorative.
* **Testo alternativo** : alternativa testuale al significato o alla funzione dell’immagine, per lettori ipovedenti.
   * **Ottieni testo alternativo da DAM** : se questa opzione è selezionata, il testo alternativo dell’immagine verrà popolato con il valore dei  `dc:description` metadati in DAM.
* **Didascalia**  - Informazioni aggiuntive sull’immagine, visualizzate per impostazione predefinita sotto l’immagine.
   * **Ottieni didascalia da DAM** : se questa opzione è selezionata, il testo della didascalia dell’immagine verrà popolato con il valore dei  `dc:title` metadati in DAM.
   * **Visualizza didascalia come a comparsa** : se questa opzione è selezionata, la didascalia non verrà visualizzata sotto l’immagine, ma come pop-up visualizzato da alcuni browser quando si passa il mouse sull’immagine.
* **Collegamento** : collega l’immagine a un’altra risorsa.
   * Utilizza la finestra di dialogo di selezione per eseguire il collegamento a un’altra risorsa AEM.
   * Se non ti colleghi a una risorsa AEM, immetti l’URL assoluto. Gli URL non soluti vengono interpretati come relativi a AEM.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

>[!TIP]
>
>**Le opzioni** di Smart Cropand  **Image** Preset si escludono a vicenda. Se un autore deve utilizzare un predefinito per immagini insieme a un rendering di ritaglio avanzato, deve utilizzare i **modificatori di immagine** per aggiungere manualmente i predefiniti.

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di ritagliare, modificare la mappa del lancio e ingrandire l’immagine.

>[!NOTE]
>
>Le funzioni di ritaglio, rotazione e zoom non sono applicabili alle risorse Dynamic Media. Se le [funzioni Dynamic Media](#dynamic-media) sono abilitate, tutte le modifiche apportate alle risorse Dynamic Media devono essere eseguite tramite la finestra di dialogo [Configura .](#configure-dialog)

![Finestra di dialogo di modifica del componente immagine](/help/assets/image-edit.png)

* Avvia ritaglio

   ![Icona di ritaglio](/help/assets/image-start-crop.png)

   Selezionando questa opzione si apre un elenco a discesa per le proporzioni predefinite del ritaglio.

   * Scegli l&#39;opzione **Mano libera** per definire il ritaglio desiderato.
   * Scegli l&#39;opzione **Rimuovi ritaglio** per visualizzare la risorsa originale.

   Una volta selezionata l’opzione Ritaglia, utilizzate le maniglie blu per ridimensionare il ritaglio sull’immagine.

   ![Opzioni di ritaglio](/help/assets/image-crop-options.png)

* Ruota a destra

   ![Icona Ruota a destra](/help/assets/image-rotate-right.png)

   Utilizzare questa opzione per ruotare l&#39;immagine di 90° verso destra (in senso orario).

* Capovolgi orizzontalmente

   ![Icona Capovolgi orizzontalmente](/help/assets/image-flip-horizontal.png)

   Utilizzare questa opzione per capovolgere l&#39;immagine orizzontalmente o ruotare l&#39;immagine di 180° lungo l&#39;asse y.

* Capovolgi verticalmente

   ![Icona Flip verticalmente](/help/assets/image-flip-vertical.png)

   Utilizzare questa opzione per capovolgere l&#39;immagine verticalmente o ruotare l&#39;immagine di 180° lungo l&#39;asse x.

* Ripristina zoom

   ![Icona Ripristina zoom](/help/assets/image-reset-zoom.png)

   Se l’immagine è già stata ingrandita, utilizza questa opzione per reimpostare il livello di zoom.

* Apri cursore Zoom

   ![Icona del cursore dello zoom aperto](/help/assets/image-zoom.png)

   Utilizzare questa opzione per visualizzare un cursore per controllare il livello di zoom dell&#39;immagine.

   ![Controllo cursore dello zoom](/help/assets/image-zoom-slider.png)

L’editor locale può essere utilizzato anche per modificare l’immagine. A causa di limiti di spazio, sono disponibili solo opzioni di base in linea. Per le opzioni di modifica completa, utilizzate la modalità a schermo intero.

![Opzioni di modifica diretta dell’immagine](/help/assets/image-in-place-edit.png)

>[!NOTE]
>
>Le operazioni di modifica delle immagini (ritaglio, capovolgimento, rotazione) non sono supportate per le immagini GIF. Tutte le modifiche apportate in modalità di modifica alle GIF non verranno mantenute.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire le opzioni di ritaglio, caricamento e rotazione e caricamento disponibili dall’autore del contenuto quando utilizza questo componente.

### Scheda principale {#main-tab}

Nella scheda **Principale** è possibile definire un elenco di larghezze in pixel per l’immagine e il componente carica automaticamente la larghezza più appropriata in base alle dimensioni del browser. Questa è una parte importante delle [funzioni reattive](#responsive-features) del componente immagine.

Inoltre, puoi definire quali opzioni generali del componente vengono automaticamente o disattivate quando l’autore aggiunge il componente a una pagina.

![Scheda principale della finestra di dialogo di progettazione del componente immagine](/help/assets/image-design-main.png)

* **Abilita funzioni DM** : se questa opzione è selezionata, sono disponibili le funzioni di abilitazione di  [Dynamic Media ](#dynamic-media) .
* **Abilita caricamento lento** : consente di definire se l’opzione di caricamento lento è abilitata automaticamente quando si aggiunge il componente immagine a una pagina.
* **L’immagine è decorativa** : consente di definire se l’opzione dell’immagine decorativa è abilitata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Ottieni testo alternativo da DAM**: definisci se l’opzione per recuperare il testo alternativo dal DAM è abilitata automaticamente quando aggiungi il componente immagine a una pagina.
* **Ottieni didascalia da DAM** : consente di definire se l’opzione per recuperare la didascalia dal DAM è abilitata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Visualizza didascalia come a comparsa** : consente di definire se l’opzione per visualizzare la didascalia immagine come pop-up è abilitata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Disabilita tracciamento UUID**  - Controlla di disabilitare il tracciamento dell&#39;UUID della risorsa immagine.
* **Larghezza**  - Definisce un elenco di larghezze in pixel per l&#39;immagine e il componente carica automaticamente la larghezza più appropriata in base alle dimensioni del browser.
   * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere un’altra dimensione.
      * Utilizzare le maniglie per ridisporre l&#39;ordine delle dimensioni.
      * Utilizza l&#39;icona **Elimina** per rimuovere una larghezza.
   * Per impostazione predefinita, il caricamento delle immagini viene differito fino a quando non diventano visibili.
      * Seleziona l&#39;opzione **Disattiva il caricamento lento** per caricare le immagini al caricamento della pagina.
* **Qualità JPEG** : fattore di qualità (in percentuale da 0 e 100) per le immagini JPEG trasformate (ad esempio ridimensionate o ritagliate).

### Scheda Funzioni {#features-tab}

Nella scheda **Funzioni** è possibile definire le opzioni disponibili per gli autori di contenuti quando utilizzano il componente, incluse le opzioni di caricamento, orientamento e ritaglio.

* Origine

   ![Scheda Funzioni della finestra di dialogo Progettazione del componente immagine](/help/assets/image-design-features-source.png)

   Seleziona l’opzione **Consenti caricamento risorse dal file system** per consentire agli autori di contenuti di caricare immagini dal proprio computer locale. Per forzare gli autori di contenuti a selezionare solo le risorse da AEM, deseleziona questa opzione.

* Orientamento

   ![Scheda Funzioni della finestra di dialogo Progettazione del componente immagine](/help/assets/image-design-features-orientation.png)

* ****
RuotaUtilizza questa opzione per consentire all’autore del contenuto di utilizzare la funzione 
**Ruota** a destra.
* ****
FlipUtilizza questa opzione per consentire all’autore del contenuto di utilizzare la funzione 
**Capovolgi** orizzontalmente e  **capovolgi** verticalmente.

   >[!CAUTION]
   >
   >L&#39;opzione **Capovolgi** è disabilitata per impostazione predefinita. Attivando questa opzione, i pulsanti **Capovolgi verticalmente** e **Capovolgi orizzontalmente** verranno visualizzati nella finestra di dialogo di modifica del componente immagine, ma la funzione non è attualmente supportata da AEM e le modifiche effettuate utilizzando queste opzioni non verranno mantenute.

* Ritaglio

   ![Scheda Funzioni della finestra di dialogo Progettazione del componente immagine](/help/assets/image-design-features-cropping.png)

   Seleziona l’opzione **Consenti ritaglio** per consentire all’autore del contenuto di ritagliare l’immagine nel componente nella finestra di dialogo di modifica.
   * Fai clic su **Aggiungi** per aggiungere una proporzione di ritaglio predefinita.
   * Immetti un nome descrittivo che verrà visualizzato nel menu a discesa **Avvia ritaglio** .
   * Immettere il rapporto numerico dell&#39;aspetto.
   * Utilizzare le maniglie di trascinamento per ridisporre l&#39;ordine delle proporzioni
   * Utilizza l’icona del cestino per eliminare una proporzione.

   >[!CAUTION]
   >
   >In AEM, le proporzioni di ritaglio sono definite come **altezza/larghezza**. Questo differisce dalla definizione tradizionale di larghezza/altezza, per ragioni di compatibilità con versioni precedenti. Gli autori dei contenuti non sono a conoscenza di alcuna differenza, purché tu fornisca un nome chiaro per le proporzioni, poiché il nome viene visualizzato nell’interfaccia utente e non per le proporzioni stesse.

### Scheda Stili {#styles-tab-1}

Il componente Immagine supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

## Servlet immagine adattivo {#adaptive-image-servlet}

Il componente immagine utilizza il servlet immagine adattivo del componente core. [L’Adaptive Image ](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) Servlets è responsabile dell’elaborazione e dello streaming delle immagini e può essere sfruttato dagli sviluppatori nelle loro  [personalizzazioni dei componenti](/help/developing/customizing.md) core.

>[!NOTE]
>
>Le richieste condizionali tramite l&#39;intestazione `Last-Modified` sono supportate da Adaptive Image Servlet, ma la memorizzazione in cache dell&#39; `Last-Modified` intestazione [deve essere abilitata nel Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=en#caching-http-response-headers).
>
>[La configurazione di Dispatcher di esempio di AEM Project Archetype](/help/developing/archetype/overview.md) contiene già questa configurazione.

## Livello dati client di Adobe {#data-layer}

Il componente Immagine supporta il [Livello dati client di Adobe.](/help/developing/data-layer/overview.md)
