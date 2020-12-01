---
title: Componente immagine
description: Il componente di base Immagine è un componente di immagine adattivo che consente di modificare direttamente il contenuto.
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '1921'
ht-degree: 2%

---


# Componente immagine{#image-component}

Il componente Immagine componente di base è un componente immagine adattivo che offre funzioni di modifica diretta.

## Utilizzo {#usage}

Il componente Immagine offre una selezione adattiva delle immagini e un comportamento reattivo, con caricamento pigro per il visitatore della pagina e posizionamento e ritaglio semplificati delle immagini per l’autore del contenuto.

Le larghezze delle immagini, il ritaglio e impostazioni aggiuntive possono essere definiti dall&#39;autore del modello nella finestra di dialogo di progettazione [](#design-dialog). L&#39;editor dei contenuti può caricare o selezionare le risorse nella finestra di dialogo [configura](#configure-dialog) e ritagliare l&#39;immagine nella finestra di dialogo di modifica [a3/>. ](#edit-dialog) Per maggiore comodità, è disponibile anche una semplice modifica locale dell’immagine.

## Funzioni reattive {#responsive-features}

Il componente Immagine è dotato di robuste funzioni reattive pronte all&#39;uso. A livello di modello di pagina, la finestra di dialogo di progettazione [può essere utilizzata per definire le larghezze predefinite della risorsa immagine. ](#design-dialog) Il componente Immagine caricherà automaticamente la larghezza corretta da visualizzare a seconda delle dimensioni della finestra del browser. Quando la finestra viene ridimensionata, il componente Immagine carica automaticamente le dimensioni corrette. Non è necessario che gli sviluppatori di componenti si preoccupino di definire query multimediali personalizzate, dal momento che il componente Immagine è già ottimizzato per caricare il contenuto.

Inoltre, il componente Immagine supporta il caricamento lento per posticipare il caricamento della risorsa immagine effettiva fino a quando non sarà visibile nel browser, aumentando la reattività delle pagine.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Immagine è v2, introdotta con la release 2.0.0 dei componenti core a gennaio 2018, ed è descritta in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](v1/image-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Supporto SVG {#svg-support}

La grafica vettoriale scalabile (SVG) è supportata dal componente Immagine.

* Sono supportati il trascinamento di una risorsa SVG da DAM e il caricamento di un file SVG da un file system locale.
* Il Servlet immagine adattivo trasferisce in streaming il file SVG originale (le trasformazioni vengono ignorate).
* Per un’immagine SVG, le &quot;immagini intelligenti&quot; e le &quot;dimensioni avanzate&quot; sono impostate su un array vuoto nel modello di immagine.

### Sicurezza {#security}

Per motivi di sicurezza, l’SVG originale non viene mai chiamato direttamente dall’Editor immagine. Viene chiamato tramite `<img src=“path-to-component”>`. Ciò impedisce al browser di eseguire eventuali script incorporati nel file SVG.

>[!CAUTION]
>
>Il supporto per SVG richiede la release 2.1.0 dei componenti core o successiva insieme a [service pack 2](https://docs.adobe.com/content/help/it-IT/experience-manager-64/release-notes/sp-release-notes.html) per AEM 6.4 o superiore per supportare le funzionalità di [editor di immagini](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/image-editor.html) all&#39;interno di AEM.

## Esempio di output del componente {#sample-component-output}

Per provare il componente Immagine e vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library_image).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Immagine [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_image_v2).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

>[!NOTE]
>
>Dalla release 2.1.0 dei componenti core, il componente immagine supporta i microdati [schema.org](https://schema.org).

## Configura finestra di dialogo {#configure-dialog}

Oltre alla finestra di dialogo [modifica ](#edit-dialog) e alla finestra di dialogo di progettazione [standard](#design-dialog), il componente immagine offre una finestra di dialogo di configurazione in cui l&#39;immagine stessa è definita insieme alla relativa descrizione e alle proprietà di base.

### Scheda Risorsa {#asset-tab}

![Scheda Risorsa della finestra di dialogo di configurazione del componente Immagine](/help/assets/image-configure-asset.png)

* **Risorsa immagine**
   * Rilasciate una risorsa dal [browser delle risorse](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) o toccate l&#39;opzione **Browse** per caricarla da un file system locale.
   * Toccate o fate clic su **Cancella** per deselezionare l&#39;immagine attualmente selezionata.
   * Toccate o fate clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) nell&#39;editor risorse.

### Scheda Metadati {#metadata-tab}

![Scheda Metadati della finestra di dialogo di configurazione del componente Immagine](/help/assets/image-configure-metadata.png)

* **L&#39;immagine è**
decorativaVerificare se l&#39;immagine deve essere ignorata dalla tecnologia di supporto e quindi non richiede un testo alternativo. Questo vale solo per le immagini decorative.
* **Testo**
alternativo: alternativa testuale al significato o alla funzione dell’immagine per lettori ipovedenti.
   * Ottieni testo alternativo da DAM: se questa opzione è attivata, il testo alternativo dell&#39;immagine verrà popolato con il valore dei metadati `dc:description` in DAM.

* ****
DidascaliaUlteriori informazioni sull’immagine, visualizzate per impostazione predefinita sotto l’immagine.
   * **Ottieni didascalia da**
DAMWquando è selezionata, il testo della didascalia dell’immagine viene popolato con il valore del 
`dc:title` in DAM.
   * **Visualizza la didascalia come pop-**
upSe questa opzione è selezionata, la didascalia non verrà visualizzata sotto l&#39;immagine, ma come pop-up visualizzato da alcuni browser quando si passa il puntatore sull&#39;immagine.

* **Collegamento**
   * Collegate l’immagine a un’altra risorsa.
   * Utilizzare la finestra di dialogo di selezione per collegarsi a un&#39;altra risorsa AEM.
   * Se non effettuate il collegamento a una risorsa AEM, immettete l’URL assoluto. Gli URL non soluti verranno interpretati come relativi a AEM.

* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di ritagliare, modificare la mappa del lancio e ingrandire l’immagine.

![Finestra di dialogo di modifica del componente immagine](/help/assets/image-edit.png)

* Avvia ritaglio

   ![Icona di ritaglio iniziale](/help/assets/image-start-crop.png)

   Selezionando questa opzione si apre un elenco a discesa per le proporzioni di ritaglio predefinite.

   * Scegliere l&#39;opzione **Mano libera** per definire il proprio ritaglio.
   * Scegliete l’opzione **Rimuovi ritaglio** per visualizzare la risorsa originale.

   Una volta selezionata l’opzione di ritaglio, usate le maniglie blu per ridimensionare il ritaglio sull’immagine.

   ![Opzioni di ritaglio](/help/assets/image-crop-options.png)

* Ruota a destra

   ![Icona Ruota a destra](/help/assets/image-rotate-right.png)

   Usate questa opzione per ruotare l’immagine di 90° verso destra (in senso orario).

* Rifletti orizzontalmente

   ![Icona Rifletti in orizzontale](/help/assets/image-flip-horizontal.png)

   Usate questa opzione per riflettere l’immagine in orizzontale o ruotare l’immagine di 180° lungo l’asse y.

* Rifletti in verticale

   ![Icona Rifletti in verticale](/help/assets/image-flip-vertical.png)

   Usate questa opzione per riflettere l’immagine in verticale o ruotare l’immagine di 180° lungo l’asse x.

* Ripristina zoom

   ![Icona Ripristina zoom](/help/assets/image-reset-zoom.png)

   Se l’immagine è già stata ingrandita, usate questa opzione per ripristinare il livello di zoom.

* Apri cursore zoom

   ![Apri icona cursore zoom](/help/assets/image-zoom.png)

   Usate questa opzione per visualizzare un cursore per controllare il livello di zoom dell’immagine.

   ![Controllo cursore Zoom](/help/assets/image-zoom-slider.png)

L’editor locale può anche essere usato per modificare l’immagine. A causa di limiti di spazio, sono disponibili solo opzioni di base in linea. Per le opzioni di modifica completa, utilizzate la modalità a schermo intero.

![Opzioni di modifica diretta immagine](/help/assets/image-in-place-edit.png)

>[!NOTE]
>
>Le operazioni di modifica delle immagini (ritaglio, capovolgimento, rotazione) non sono supportate per le immagini GIF. Eventuali modifiche apportate in modalità di modifica ai GIF non verranno mantenute.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire le opzioni di ritaglio, caricamento, rotazione e caricamento disponibili per l’autore del contenuto quando utilizza questo componente.

### Scheda principale {#main-tab}

Nella scheda **Principale** è possibile definire un elenco di larghezze in pixel per l&#39;immagine e il componente caricherà automaticamente la larghezza più appropriata in base alle dimensioni del browser. Si tratta di una parte importante delle [funzioni reattive](#responsive-features) del componente Immagine.

Inoltre, è possibile definire quali opzioni generali del componente vengono automaticamente o disattivate quando l’autore aggiunge il componente a una pagina.

![Scheda principale della finestra di dialogo Progettazione del componente Immagine](/help/assets/image-design-main.png)

* **Abilita**
caricamento lento: consente di definire se l’opzione di caricamento pigro è abilitata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Immagine è**
decorativaConsente di definire se l’opzione per l’immagine decorativa è abilitata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Ottenete testo alternativo da**
DAMDefine se l&#39;opzione per recuperare il testo alternativo da DAM è abilitata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Ottieni didascalia da**
DAMDefine se l’opzione per recuperare la didascalia da DAM è abilitata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Visualizza la didascalia come**
pop-upConsente di definire se l’opzione per visualizzare la didascalia immagine come pop-up è abilitata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Disattiva UUID**
TrackingCheck per disattivare il tracciamento dell’UUID della risorsa immagine.

* ****
LarghezzeDefinisce un elenco di larghezze in pixel per l’immagine e il componente carica automaticamente la larghezza più appropriata in base alle dimensioni del browser.
   * Toccate o fate clic sul pulsante **Aggiungi** per aggiungere un&#39;altra dimensione.
      * Utilizzare le maniglie per riordinare l&#39;ordine delle dimensioni.
      * Utilizzare l&#39;icona **Elimina** per rimuovere una larghezza.
   * Per impostazione predefinita, il caricamento delle immagini viene differito finché non diventano visibili.
      * Selezionate l&#39;opzione **Disattiva caricamento pigro** per caricare le immagini al caricamento della pagina.
* **Qualità JPEG**
Fattore di qualità (in percentuale da 0 e 100) per le immagini JPEG trasformate (ad es. ridimensionate o ritagliate).

>[!NOTE]
>
>L’opzione Qualità JPEG è disponibile a partire dalla release 2.2.0 dei componenti core.

>[!NOTE]
>
>A partire dalla release 2.2.0 dei componenti core, il componente Immagine aggiunge alla risorsa immagine l’attributo UUID univoco `data-asset-id` per consentire il tracciamento e l’analisi del numero di visualizzazioni ricevute dalle singole risorse.

### Scheda Funzioni {#features-tab}

Nella scheda **Funzioni** è possibile definire le opzioni disponibili per gli autori dei contenuti quando utilizzano il componente, incluse le opzioni di caricamento, orientamento e ritaglio.

* Origine

   ![Scheda Funzioni della finestra di dialogo Progettazione del componente Immagine](/help/assets/image-design-features-source.png)

   Selezionate l&#39;opzione **Consenti caricamento risorse da file system** per consentire agli autori di contenuti di caricare immagini dal proprio computer locale. Per obbligare gli autori del contenuto a selezionare solo le risorse da AEM, deselezionate questa opzione.

* Orientamento

   ![Scheda Funzioni della finestra di dialogo Progettazione del componente Immagine](/help/assets/image-design-features-orientation.png)

* ****
Ruota: utilizzate questa opzione per consentire all&#39;autore del contenuto di utilizzare il pulsante 
**Ruota a** destra.
* ****
CapovolgiUtilizzate questa opzione per consentire all&#39;autore del contenuto di utilizzare il pulsante 
**Capovolgi** orizzontalmente e  **Rifletti** verticalmente.

   >[!CAUTION]
   >
   >Per impostazione predefinita, l&#39;opzione **Capovolgi** è disattivata. Attivando questa opzione, i pulsanti **Rifletti in verticale** e **Rifletti in orizzontale** vengono visualizzati nella finestra di dialogo di modifica del componente immagine, ma la funzione non è attualmente supportata da AEM e le modifiche apportate con queste opzioni non vengono mantenute.

* Ritaglio

   ![Scheda Funzioni della finestra di dialogo Progettazione del componente Immagine](/help/assets/image-design-features-cropping.png)

   Selezionate l&#39;opzione **Consenti ritaglio** per consentire all&#39;autore del contenuto di ritagliare l&#39;immagine nel componente nella finestra di dialogo di modifica.
   * Fate clic su **Aggiungi** per aggiungere proporzioni di ritaglio predefinite.
   * Immettere un nome descrittivo che verrà visualizzato nel menu a discesa **Avvia ritaglio**.
   * Immettete il rapporto numerico dell’aspetto.
   * Usate le maniglie di trascinamento per riordinare l’ordine delle proporzioni
   * Usate l’icona del cestino per eliminare le proporzioni.

   >[!CAUTION]
   >
   >In AEM, le proporzioni del ritaglio sono definite come **altezza/larghezza**. Questo differisce dalla definizione tradizionale di larghezza/altezza, per ragioni di compatibilità con versioni precedenti. Gli autori dei contenuti non saranno a conoscenza di alcuna differenza, purché sia stato specificato un nome chiaro per il rapporto, dal momento che il nome viene visualizzato nell’interfaccia utente e non per il rapporto stesso.

### Scheda Stili {#styles-tab-1}

Il componente Immagine supporta il AEM [Sistema di stile](/help/get-started/authoring.md#component-styling).

## Servlet immagine adattiva {#adaptive-image-servlet}

Il componente Immagine utilizza il servlet immagine adattivo del componente principale. [I ](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) servlet adattivi per immagini sono responsabili dell’elaborazione e dello streaming delle immagini e possono essere utilizzati dagli sviluppatori nelle  [personalizzazioni dei componenti](/help/developing/customizing.md) core.

>[!NOTE]
>
>Le richieste condizionali effettuate tramite l&#39;intestazione `Last-Modified` sono supportate dal servlet immagine adattivo, ma la memorizzazione nella cache dell&#39; `Last-Modified` intestazione [ deve essere abilitata nel dispatcher](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#caching-http-response-headers).
>
>[La configurazione del Dispatcher di esempio di AEM Project Archetype](/help/developing/archetype/overview.md) contiene già questa configurazione.
