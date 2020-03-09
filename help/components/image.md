---
title: Componente immagine
description: Il componente di base Immagine è un componente di immagine adattivo che consente di modificare direttamente il contenuto.
translation-type: tm+mt
source-git-commit: 6be0028c45ce9f8b36ea278f8e569f3d6a626ae2

---


# Componente immagine{#image-component}

Il componente Immagine componente di base è un componente immagine adattivo che offre funzioni di modifica diretta.

## Utilizzo {#usage}

Il componente Immagine offre una selezione adattiva delle immagini e un comportamento reattivo, con caricamento pigro per il visitatore della pagina e posizionamento e ritaglio semplificati delle immagini per l’autore del contenuto.

Le larghezze delle immagini, il ritaglio e altre impostazioni possono essere definiti dall’autore del modello nella finestra di dialogo [](#design-dialog)della progettazione. L’editor del contenuto può caricare o selezionare le risorse nella finestra di dialogo [di](#configure-dialog) configurazione e ritagliare l’immagine nella finestra di dialogo [di](#edit-dialog)modifica. Per maggiore comodità, è disponibile anche una semplice modifica locale dell’immagine.

## Funzioni reattive {#responsive-features}

Il componente Immagine è dotato di robuste funzioni reattive pronte all&#39;uso. A livello di modello di pagina, la finestra di dialogo [di](#design-dialog) progettazione può essere utilizzata per definire le larghezze predefinite della risorsa immagine. Il componente Immagine caricherà automaticamente la larghezza corretta da visualizzare a seconda delle dimensioni della finestra del browser. Quando la finestra viene ridimensionata, il componente Immagine carica automaticamente le dimensioni corrette. Non è necessario che gli sviluppatori di componenti si preoccupino di definire query multimediali personalizzate, dal momento che il componente Immagine è già ottimizzato per caricare il contenuto.

Inoltre, il componente Immagine supporta il caricamento lento per posticipare il caricamento della risorsa immagine effettiva fino a quando non sarà visibile nel browser, aumentando la reattività delle pagine.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Immagine è v2, introdotta con la release 2.0.0 dei componenti core a gennaio 2018, ed è descritta in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile | Compatibile |
| [v1](v1/image-v1.md) | Compatibile | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Supporto SVG {#svg-support}

La grafica vettoriale scalabile (SVG) è supportata dal componente Immagine.

* Sono supportati il trascinamento di una risorsa SVG da DAM e il caricamento di un file SVG da un file system locale.
* Il Servlet immagine adattivo trasferisce in streaming il file SVG originale (le trasformazioni vengono ignorate).
* Per un’immagine SVG, le &quot;immagini intelligenti&quot; e le &quot;dimensioni avanzate&quot; sono impostate su un array vuoto nel modello di immagine.

### Sicurezza {#security}

Per motivi di sicurezza, l’SVG originale non viene mai chiamato direttamente dall’Editor immagine. Viene chiamato attraverso `<img src=“path-to-component”>`. Ciò impedisce al browser di eseguire eventuali script incorporati nel file SVG.

>[!CAUTION]
>
>Il supporto per SVG richiede la release 2.1.0 dei componenti core o versioni successive insieme al [service pack 2](https://docs.adobe.com/content/help/en/experience-manager-64/release-notes/sp-release-notes.html) per AEM 6.4 o al [service pack 3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) per AEM 6.3 o versioni successive per supportare le [nuove funzioni](https://docs.adobe.com/content/help/en/experience-manager-64/developing/components/image-editor.html) dell’editor di immagini in AEM.

## Output componente di esempio {#sample-component-output}

Per provare il componente Immagine e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](https://adobe.com/go/aem_cmp_library_image)Componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Immagine [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_image_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

>[!NOTE]
>
>Dalla release 2.1.0 di Core Components, il componente Immagine supporta i microdati [](https://schema.org)schema.org.

## Configura finestra di dialogo {#configure-dialog}

Oltre alla finestra di dialogo [standard per la](#edit-dialog) modifica e la [](#design-dialog)progettazione, il componente Immagine offre una finestra di dialogo di configurazione in cui l’immagine stessa è definita insieme alla descrizione e alle proprietà di base.

### Scheda Risorsa {#asset-tab}

![](/help/assets/screen_shot_2018-01-08at114245.png)

* **Risorsa immagine**
   * Trascinate una risorsa dal browser [delle](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) risorse o toccate l&#39;opzione **Sfoglia** per caricarla da un file system locale.
   * Toccate o fate clic su **Cancella** per deselezionare l&#39;immagine attualmente selezionata.
   * Toccate o fate clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) nell’editor risorse.

### Scheda Metadati {#metadata-tab}

![](/help/assets/screen_shot_2018-01-08at114527.png)

* **L&#39;immagine è decorativa** Controllare se l&#39;immagine deve essere ignorata dalla tecnologia di supporto e quindi non richiede un testo alternativo. Questo vale solo per le immagini decorative.
* **Testo** alternativo Alternativo testuale del significato o della funzione dell&#39;immagine per lettori ipovedenti.
   * Ottieni testo alternativo da DAM: se questa opzione è attivata, il testo alternativo dell&#39;immagine verrà popolato con il valore dei `dc:description` metadati in DAM.

* **Didascalia** Ulteriori informazioni sull’immagine, visualizzate per impostazione predefinita sotto l’immagine.
   * **Ottieni didascalia da DAM** Se questa opzione è selezionata, il testo della didascalia dell’immagine verrà popolato con il valore dei `dc:title` metadati in DAM.
   * **Visualizza la didascalia come pop-up** Se questa opzione è selezionata, la didascalia non verrà visualizzata sotto l&#39;immagine, ma come pop-up visualizzato da alcuni browser quando si passa il puntatore sull&#39;immagine.

* **Collegamento**
   * Collegate l’immagine a un’altra risorsa.
   * Utilizzate la finestra di dialogo di selezione per collegarvi a un’altra risorsa AEM.
   * Se non effettuate il collegamento a una risorsa AEM, immettete l’URL assoluto. Gli URL non soluti verranno interpretati come relativi ad AEM.

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di ritagliare, modificare la mappa del lancio e ingrandire l’immagine.

![](/help/assets/chlimage_1-8.png)

* Avvia ritaglio

   ![](/help/assets/chlimage_1-9.png)

   Selezionando questa opzione si apre un elenco a discesa per le proporzioni di ritaglio predefinite.

   * Scegliete l’opzione Mano **** libera per definire il ritaglio personalizzato.
   * Scegliete l’opzione **Rimuovi ritaglio** per visualizzare la risorsa originale.
   Una volta selezionata l’opzione di ritaglio, usate le maniglie blu per ridimensionare il ritaglio sull’immagine.

   ![](/help/assets/chlimage_1-10.png)

* Ruota a destra

   ![](/help/assets/chlimage_1-11.png)

   Usate questa opzione per ruotare l’immagine di 90° verso destra (in senso orario).

* Rifletti orizzontalmente

   ![](/help/assets/screen_shot_2018-04-16at091404.png)

   Usate questa opzione per riflettere l’immagine in orizzontale o ruotare l’immagine di 180° lungo l’asse y.

* Rifletti in verticale

   ![](/help/assets/screen_shot_2018-04-16at091410.png)

   Usate questa opzione per riflettere l’immagine in verticale o ruotare l’immagine di 180° lungo l’asse x.

* Avvia mappa

   >[!CAUTION]
   >
   >La funzione Mappa di avvio richiede la release 2.1.0 dei componenti core o successiva insieme al [service pack 2](https://docs.adobe.com/content/help/en/experience-manager-64/release-notes/sp-release-notes.html) per AEM 6.4 o al [service pack 3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) per AEM 6.3 o versione successiva per supportare le [nuove funzioni](https://docs.adobe.com/content/help/en/experience-manager-64/developing/components/image-editor.html) di editor di immagini in AEM.

   ![](/help/assets/chlimage_1-12.png)

   Utilizzate questa opzione per applicare una mappa di lancio all&#39;immagine. Selezionando questa opzione si apre una nuova finestra che consente all&#39;utente di selezionare la forma della mappa:

   * **Aggiungi mappa rettangolare**
   * **Aggiungi mappa circolare**
   * **Aggiungi mappa poligonale**
      * Per impostazione predefinita, aggiunge una mappa a triangolo. Fare doppio clic su una linea della forma per aggiungere una nuova maniglia di ridimensionamento blu su un nuovo lato.
   Una volta selezionata, la forma mappa viene sovrapposta all&#39;immagine per il ridimensionamento. Trascinate e rilasciate le maniglie di ridimensionamento blu per regolare la forma.

   ![](/help/assets/chlimage_1-13.png)

   Dopo aver ridimensionato la mappa del lancio, fate clic su di essa per aprire una barra degli strumenti mobile e definire il percorso del collegamento.

   * **Percorso**
      * Utilizzate l&#39;opzione Selettore percorso per selezionare un percorso in AEM
      * Se il percorso non è in AEM, usate l’URL assoluto. I percorsi non assoluti verranno interpretati in relazione ad AEM.
   * **Testo** Alt Descrizione alternativa della destinazione del percorso
   * **Destinazione**
      * **Stessa scheda**
      * **Nuova scheda**
      * **Frame principale**
      * **Frame superiore**
   Toccate o fate clic sul segno di spunta blu per salvare, sulla x nera per annullare e sul cestino rosso per eliminare la mappa.

   ![](/help/assets/chlimage_1-14.png)

* Ripristina zoom

   ![](/help/assets/chlimage_1-15.png)

   Se l’immagine è già stata ingrandita, usate questa opzione per ripristinare il livello di zoom.

* Apri cursore zoom

   ![](/help/assets/chlimage_1-16.png)

   Usate questa opzione per visualizzare un cursore per controllare il livello di zoom dell’immagine.

   ![](/help/assets/chlimage_1-17.png)

L’editor locale può anche essere usato per modificare l’immagine. A causa di limiti di spazio, sono disponibili solo opzioni di base in linea. Per le opzioni di modifica completa, utilizzate la modalità a schermo intero.

![](/help/assets/chlimage_1-18.png)

>[!NOTE]
>
>Le operazioni di modifica delle immagini (ritaglio, capovolgimento, rotazione) non sono supportate per le immagini GIF. Eventuali modifiche apportate in modalità di modifica ai GIF non verranno mantenute.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire le opzioni di ritaglio, caricamento, rotazione e caricamento disponibili per l’autore del contenuto quando utilizza questo componente.

### Scheda Principale {#main-tab}

Nella scheda **Principale** potete definire un elenco di larghezze in pixel per l’immagine e il componente caricherà automaticamente la larghezza più appropriata in base alle dimensioni del browser. Si tratta di una parte importante delle funzioni [](#responsive-features) reattive del componente Immagine.

Inoltre, è possibile definire quali opzioni generali del componente vengono automaticamente o disattivate quando l’autore aggiunge il componente a una pagina.

![](/help/assets/screenshot_2018-10-19at102756.png)

* **Abilita caricamento** lento Consente di definire se l’opzione di caricamento pigro è abilitata automaticamente quando si aggiunge il componente immagine a una pagina.
* **L’immagine è decorativa** Consente di definire se l’opzione per l’immagine decorativa è abilitata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Ottieni testo alternativo da DAM** Definisci se l’opzione per recuperare il testo alternativo da DAM è abilitata automaticamente quando aggiungi il componente immagine a una pagina.
* **Ottieni didascalia da DAM** Definisci se l’opzione per recuperare la didascalia da DAM è abilitata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Visualizza la didascalia come pop-up** Definisci se l’opzione per visualizzare la didascalia immagine come pop-up è abilitata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Disattiva il controllo tracciamento** UUUID per disattivare il tracciamento dell’UUID della risorsa immagine.

* **Larghezza** Definisce un elenco di larghezze in pixel per l’immagine e il componente carica automaticamente la larghezza più appropriata in base alle dimensioni del browser.
   * Toccate o fate clic sul pulsante **Aggiungi** per aggiungere un’altra dimensione.
      * Utilizzare le maniglie per riordinare l&#39;ordine delle dimensioni.
      * Utilizzate l&#39;icona **Elimina** per rimuovere una larghezza.
   * Per impostazione predefinita, il caricamento delle immagini viene differito finché non diventano visibili.
      * Selezionate l’opzione **Disattiva caricamento** lento per caricare le immagini al caricamento della pagina.
* **Qualità** JPEG Fattore di qualità (in percentuale da 0 e 100) per le immagini JPEG trasformate (ad es. ridimensionate o ritagliate).

>[!CAUTION]
>
>L’opzione Qualità JPEG è disponibile a partire dalla release 2.2.0 dei componenti core.

>[!NOTE]
>
>A partire dalla release 2.2.0 dei componenti core, il componente Immagine aggiunge alla risorsa immagine l’attributo UUID univoco `data-asset-id` per consentire il tracciamento e l’analisi del numero di visualizzazioni ricevute dalle singole risorse.

### Features Tab {#features-tab}

Nella scheda **Funzioni** è possibile definire le opzioni disponibili per gli autori dei contenuti quando utilizzano il componente, incluse le opzioni di caricamento, orientamento e ritaglio.

* Origine

   ![](/help/assets/chlimage_1-19.png)

   Selezionate l’opzione **Consenti caricamento risorse dal file system** per consentire agli autori di contenuti di caricare immagini dal computer locale. Per obbligare gli autori di contenuti a selezionare solo le risorse da AEM, deselezionate questa opzione.

* Orientamento

   ![](/help/assets/chlimage_1-20.png)

* **Ruota** Utilizzate questa opzione per consentire all&#39;autore del contenuto di utilizzare l&#39;opzione **Ruota a destra** .
* **Capovolgi** Utilizzate questa opzione per consentire all’autore del contenuto di utilizzare le opzioni **Rifletti in orizzontale** e **Rifletti in verticale** .

   >[!CAUTION]
   >
   >Per impostazione predefinita, l’opzione **Rifletti** è disattivata. Attivando questa opzione, i pulsanti **Rifletti in verticale** e **Rifletti in orizzontale** vengono visualizzati nella finestra di dialogo di modifica del componente immagine. Tuttavia, al momento la funzione non è supportata da AEM e le modifiche apportate con queste opzioni non vengono mantenute.

* Ritaglio

   ![](/help/assets/chlimage_1-21.png)

   Selezionate l’opzione **Consenti ritaglio** per consentire all’autore del contenuto di ritagliare l’immagine nel componente nella finestra di dialogo di modifica.
   * Fate clic su **Aggiungi** per aggiungere proporzioni di ritaglio predefinite.
   * Immettete un nome descrittivo che verrà visualizzato nel menu a discesa **Avvia ritaglio** .
   * Immettete il rapporto numerico dell’aspetto.
   * Usate le maniglie di trascinamento per riordinare l’ordine delle proporzioni
   * Usate l’icona del cestino per eliminare le proporzioni.
   >[!CAUTION]
   >
   >Note that in AEM, crop aspect ratios are defined as **height/width**. Questo differisce dalla definizione tradizionale di larghezza/altezza, per ragioni di compatibilità con versioni precedenti. Gli autori dei contenuti non saranno a conoscenza di alcuna differenza, purché sia stato specificato un nome chiaro per il rapporto, dal momento che il nome viene visualizzato nell’interfaccia utente e non per il rapporto stesso.

### Scheda Stili {#styles-tab-1}

Il componente Immagine supporta AEM [Style System](/help/get-started/authoring.md#component-styling).

## Servlet immagine adattiva {#adaptive-image-servlet}

Il componente Immagine utilizza il servlet immagine adattivo del componente principale. [Il Servlet](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) immagine adattivo è responsabile dell’elaborazione e dello streaming delle immagini e può essere utilizzato dagli sviluppatori nelle [personalizzazioni dei componenti](/help/developing/customizing.md)core.

>[!NOTE]
>
>Le richieste condizionali effettuate tramite l’ `Last-Modified` intestazione sono supportate dal servlet immagine adattivo, ma la memorizzazione nella cache dell’ `Last-Modified` intestazione [deve essere abilitata nel dispatcher](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#caching-http-response-headers).
>
>[La configurazione del Dispatcher di esempio di AEM Project Archetype](/help/developing/archetype/overview.md)contiene già questa configurazione.
