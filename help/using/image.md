---
title: Componente immagine
seo-title: Componente immagine
description: Il componente Immagine componente core è una funzione di modifica locale delle funzioni dei componenti immagine.
seo-description: Il componente Immagine componente core è una funzione di modifica locale delle funzioni dei componenti immagine.
uuid: 1 a 229 d 42-2428-43 aa -895 a -9 b 7 c 1 bf 02834
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: d 4684 f 33-2 fb 5-4 f 32-866 f -7136 cf 1800 d 7
translation-type: tm+mt
source-git-commit: 34ae30ca8be3ad290924b986acfac11d960f2ee0

---


# Componente immagine{#image-component}

Il componente Immagine componente core è un componente immagine adattivo che funzioni in funzione di modifica locale.

## Utilizzo {#usage}

Il componente Immagine offre selezioni immagine adattive e comportamenti reattivi con caricamento lazy per il visitatore della pagina, nonché facile posizionamento delle immagini e ritaglio per l'autore del contenuto.

Le larghezze delle immagini e il ritaglio e le impostazioni aggiuntive possono essere definiti dall'autore del modello nella finestra di dialogo [di progettazione](#design-dialog). L'editor di contenuto può caricare o selezionare le risorse nella finestra di dialogo [Configura](#configure-dialog) e ritagliare l'immagine nella finestra di dialogo [di modifica](#edit-dialog). Per maggiore praticità è disponibile anche una semplice modifica diretta dell'immagine.

## Funzioni reattive {#responsive-features}

Il componente Immagine viene fornito con solide funzioni reattive pronte all'esterno della casella. A livello di modello pagina, potete [usare la finestra di dialogo](#design-dialog) di progettazione per definire le larghezze predefinite della risorsa immagine. Il componente Immagine carica quindi automaticamente la larghezza corretta in base alle dimensioni della finestra del browser. Quando la finestra viene ridimensionata, il componente Imaage carica in modo dinamico le dimensioni immagine corrette al momento. Non è necessario che gli sviluppatori di componenti siano in grado di definire le query di media media in quanto il componente Immagine è già ottimizzato per caricare i contenuti.

Inoltre, il componente Immagine supporta il caricamento lazy per differire il caricamento della risorsa immagine effettiva finché non è visibile nel browser, aumentando la capacità di reindirizzamento delle pagine.

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Immagine è v 2, introdotta con la release 2.0.0 dei Componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](image-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Supporto SVG {#svg-support}

Il componente Immagine vettoriale scalabile (SVG) è supportato dal componente Immagine.

* È supportata la funzione di trascinamento di una risorsa SVG da DAM e il caricamento di un file SVG da un file system locale.
* Nei flussi immagine adattiva viene trasmesso il file SVG originale (le trasformazioni vengono ignorate).
* Per un'immagine SVG, le «immagini sensibili» e le «dimensioni sensibili» sono impostate su un array vuoto nel modello di immagine.

### Protezione {#security}

Per motivi di sicurezza, il formato SVG originale non viene mai chiamato direttamente dall'Editor immagini. `<img src=“path-to-component”>`Viene richiamata. In questo modo il browser non può eseguire alcuno script incorporato nel file SVG.

>[!CAUTION]
>
>Il supporto SVG richiede la versione 2.1.0 dei componenti core, oltre a [service pack 2](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) per AEM 6.4 o [service pack 3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) per AEM 6.3 o service pack per supportare [nuove funzioni Editor immagini](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/image-editor.html) in AEM.

## Output componente campione {#sample-component-output}

Per provare il componente Immagine e vedere alcuni esempi delle opzioni di configurazione e l'output HTML e JSON, visitare la [Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library/image.html).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente [Immagine è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/image/v2/image).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

>[!NOTE]
>
>Nella release 2.1.0 dei componenti core, il componente Immagine supporta [schema.org microdati](https://schema.org).

## Configura finestra di dialogo {#configure-dialog}

Oltre alla finestra di dialogo di [modifica standard](#edit-dialog) e [alla finestra di dialogo di progettazione](#design-dialog), il componente Immagine offre una finestra di dialogo di configurazione in cui viene definito l'immagine stessa insieme alla descrizione e alle proprietà di base.

### Scheda Risorse {#asset-tab}

![](assets/screen_shot_2018-01-08at114245.png)

* **Risorsa immagine**
   * Rilasciate una risorsa dal Browser [risorse](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) o toccate l'opzione **di ricerca** da caricare da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l'immagine correntemente selezionata.
   * Toccate o fate clic **su Modifica** per [gestire i rendering della risorsa](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) nell'editor risorse.

### Scheda Metadati {#metadata-tab}

![](assets/screen_shot_2018-01-08at114527.png)

* **L'immagine è decorativa**
Se l'immagine deve essere ignorata dalla tecnologia di accessibilità e quindi non richiede un testo alternativo. Ciò si applica solo alle immagini decorative.
* **Alternative**testuali alternative
rispetto al significato o alla funzione dell'immagine, per i lettori ipovedenti.
   * Ottieni testo alternativo da DAM - Se questa opzione è selezionata, il testo alternativo dell'immagine verrà popolato con il valore dei `dc:description` metadati in DAM.

* **Didascalia**
Ulteriori informazioni sull'immagine, visualizzate sotto l'immagine per impostazione predefinita.
   * **Ottieni didascalia da DAM**
Quando questa opzione è selezionata, il testo della didascalia dell'immagine verrà popolato con il valore dei `dc:title` metadati in DAM.
   * **Visualizza didascalia come a comparsa** Quando questa opzione è selezionata, la didascalia non viene visualizzata sotto l'immagine, ma come pop-up visualizzato da alcuni browser quando si passa il mouse sull'immagine.

* **Collegamento**
   * Collegate l'immagine a un'altra risorsa.
   * Utilizza la finestra di dialogo di selezione per collegare un'altra risorsa AEM.
   * Se non collegate una risorsa AEM, immettete l'URL assoluto. Gli URL non soliti verranno interpretati come relativi ad AEM.

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all'autore del contenuto di ritagliare, modificare la mappa di lancio e applicare lo zoom all'immagine.

![](assets/chlimage_1-8.png)

* Avvia ritaglio

   ![](assets/chlimage_1-9.png)

   Selezionando questa opzione si apre un menu a discesa per le proporzioni di ritaglio predefinite.

   * Scegliete l'opzione **Mano libera** per definire il ritaglio.
   * Scegliete l'opzione **Rimuovi ritaglio** per visualizzare la risorsa originale.
   Una volta selezionata l'opzione Ritaglio, usate le maniglie blu per ridimensionare il ritaglio sull'immagine.

   ![](assets/chlimage_1-10.png)

* Ruota a destra

   ![](assets/chlimage_1-11.png)

   Utilizzare questa opzione per ruotare l'immagine di 90 ° a destra (in senso orario).

* Rifletti in orizzontale

   ![](assets/screen_shot_2018-04-16at091404.png)

   Usate questa opzione per riflettere l'immagine in orizzontale o ruotare l'immagine di 180 ° lungo l'asse y.

* Rifletti in verticale

   ![](assets/screen_shot_2018-04-16at091410.png)

   Utilizzate questa opzione per riflettere l'immagine in verticale o ruotare l'immagine di 180 ° lungo l'asse x.

* Mappa lancio

   >[!CAUTION]
   >
   >La funzione Mappa mappa richiede la versione 2.1.0 dei componenti core, oltre a [Service Pack 2](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) per AEM 6.4 o [Service Pack 3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) per AEM 6.3 o service pack per supportare [nuove funzioni Editor immagini](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/image-editor.html) in AEM.

   ![](assets/chlimage_1-12.png)

   Utilizzate questa opzione per applicare una mappa di lancio all'immagine. Selezionate questa opzione per aprire una nuova finestra che consente all'utente di selezionare la forma della mappa:

   * **Aggiungi mappa rettangolare**
   * **Aggiungi mappa circolare**
   * **Aggiungi mappa poligono**
      * Per impostazione predefinita, viene aggiunta una mappa triangolare. Fare doppio clic su una riga della forma per aggiungere una nuova maniglia di ridimensionamento blu su un nuovo lato.
   Una volta selezionata la forma della mappa, questa viene sovrapposta all'immagine che consente il ridimensionamento. Trascinare e rilasciare le maniglie di ridimensionamento blu per regolare la forma.

   ![](assets/chlimage_1-13.png)

   Dopo aver ridimensionato la mappa di avvio, fare clic su di essa per aprire una barra degli strumenti mobile per definire il percorso del collegamento.

   * **Percorso**
      * Utilizzare l'opzione Selettore percorso per selezionare un percorso in AEM
      * Se il percorso non è in AEM, usate l'URL assoluto. I percorsi non assoluti verranno interpretati in base ad AEM.
   * **Testo**
Alt Descrizione alternativa della destinazione del percorso
   * **Destinazione**
      * **Stessa scheda**
      * **Nuova scheda**
      * **Frame principale**
      * **Frame superiore**
   Toccate o fate clic sulla spunta blu da salvare, sulla x nera da annullare e sul cestino rosso per eliminare la mappa.

   ![](assets/chlimage_1-14.png)

* Ripristina zoom

   ![](assets/chlimage_1-15.png)

   Se l'immagine è già stata ingrandita, usate questa opzione per ripristinare il livello di zoom.

* Apri cursore zoom

   ![](assets/chlimage_1-16.png)

   Usate questa opzione per visualizzare un cursore per controllare il livello di zoom dell'immagine.

   ![](assets/chlimage_1-17.png)

L'editor locale può essere usato anche per modificare l'immagine. A causa di limiti di spazio, sono disponibili solo le opzioni di base. Per le opzioni di modifica complete, utilizzate la modalità schermo intero.

![](assets/chlimage_1-18.png)

>[!NOTE]
>
>Le operazioni di modifica delle immagini (ritaglio, capovolgimento, rotazione) non sono supportate per le immagini GIF. Tutte le modifiche apportate in modalità di modifica a GIF non saranno persistenti.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all'autore del modello di definire il ritaglio, il caricamento e le opzioni di rotazione e caricamento che l'autore del contenuto ha quando si utilizza questo componente.

### Scheda Principale {#main-tab}

Nella scheda **Principale** è possibile definire un elenco di larghezze in pixel per l'immagine e il componente carica automaticamente la larghezza più appropriata in base alle dimensioni del browser. Questa è una parte importante delle funzioni [reattive](#responsive-features) del componente Immagine.

Inoltre, è possibile definire quali opzioni generali vengono visualizzate o disattivate quando l'autore aggiunge il componente a una pagina.

![](assets/screenshot_2018-10-19at102756.png)

* **Abilita caricamento
lazy** Definisce se l'opzione di caricamento lazy viene attivata automaticamente quando si aggiunge il componente Immagine a una pagina.
* **L'immagine è decorativa**
se l'opzione Immagine decorativa viene attivata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Ottenete testo alternativo da DAM**
Definire se l'opzione per recuperare il testo alternativo da DAM viene attivata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Ottenere didascalia da DAM**
Definire se l'opzione per recuperare la didascalia dal DAM viene attivata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Visualizza didascalia come a comparsa** Definite se l'opzione per visualizzare la didascalia immagine come pop-up viene attivata automaticamente quando si aggiunge il componente immagine a una pagina.
* **Disabilita controllo tracciamento**
UUID per disattivare il tracciamento dell'UUID della risorsa immagine.

* **Larghezze**
Definisce un elenco di larghezze in pixel per l'immagine e il componente carica automaticamente la larghezza più appropriata in base alle dimensioni del browser.
   * Toccate o fate clic sul **pulsante Aggiungi** per aggiungere un'altra dimensione.
      * Utilizzare le maniglie di acquisizione per riordinare l'ordine delle dimensioni.
      * Usate l'icona **Elimina** per rimuovere una larghezza.
   * Per impostazione predefinita, il caricamento delle immagini viene eseguito fino a quando non diventa visibile.
      * Selezionate l'opzione **Disattiva caricamento lento** per caricare le immagini al caricamento della pagina.
* **Qualità**
JPEG Il fattore di qualità (in percentuale da 0 e 100) per le immagini JPEG trasformate (ad es. ridimensionate o ritagliate).

>[!CAUTION]
>
>L'opzione Qualità JPEG è disponibile a partire dalla versione 2.2.0 dei componenti core.

>[!NOTE]
>
>Dalla release 2.2.0 dei componenti core, il componente Immagine aggiunge l'attributo UUID univoco `data-asset-id` alla risorsa immagine per consentire il tracciamento e l'analisi del numero di visualizzazioni ricevute da singole risorse.

### Scheda Funzioni {#features-tab}

Nella scheda **Funzioni** potete definire le opzioni disponibili per gli autori di contenuto quando si utilizza il componente, quali opzioni di caricamento, orientamento e ritaglio.

* Origine

   ![](assets/chlimage_1-19.png)

   Selezionate l'opzione **Consenti caricamento risorse dal file system** per consentire agli autori di contenuto di caricare le immagini dal proprio computer locale. Per obbligare gli autori di contenuto a selezionare solo risorse da AEM, deselezionate questa opzione.

* Orientamento

   ![](assets/chlimage_1-20.png)

* **Rotazione**
Consente di utilizzare questa opzione per consentire all'autore del contenuto di utilizzare l'opzione **Ruota diritto.**
* **Rifletti**
Utilizzate questa opzione per consentire all'autore del contenuto di utilizzare le opzioni **Rifletti in orizzontale** e **Rifletti in verticale** .

   >[!CAUTION]
   >
   >L'opzione **Rifletti** è disattivata per impostazione predefinita. Attivando i pulsanti **Rifletti in verticale** e **Capovolgi orizzontalmente** nella finestra di dialogo di modifica del componente Immagine, la funzione non è supportata da AEM e tutte le modifiche apportate utilizzando queste opzioni non vengono mantenute.

<!-- 
Comment Type: remark
Last Modified By: Chris Bohnert (bohnert)
Last Modified Date: 2017-11-20T05:51:34.378-0500

<p>Added caution based on CQDOC-11457. Hid the flip options in the procedure using the <strong>Draft</strong> option so that when this feature is implemented in CQ-4221539, the <strong>Draft</strong> property can simply be removed along with the caution.</p>
 -->

* Ritaglio

   ![](assets/chlimage_1-21.png)

   Selezionate l'opzione **Consenti ritaglio** per consentire all'autore del contenuto di ritagliare l'immagine nel componente nella finestra di dialogo di modifica.
   * Fate clic su **Aggiungi** per aggiungere proporzioni di ritaglio predefinite.
   * Inserite un nome descrittivo che verrà mostrato nel menu a discesa **Avvia ritaglio** .
   * Inserite il rapporto numerico dell'aspetto.
   * Utilizzare le maniglie trascinate per riordinare l'ordine delle proporzioni
   * Usate l'icona del cestino per eliminare le proporzioni.
   >[!CAUTION]
   >
   >Note that in AEM, crop aspect ratios are defined as **height/width**. Ciò si differenzia dalla definizione convenzionale di larghezza/altezza e viene effettuata per motivi di compatibilità precedenti. Gli autori di contenuto non saranno a conoscenza di alcuna differenza purché sia indicato un nome chiaro del rapporto, in quanto il nome viene visualizzato nell'interfaccia utente e non il rapporto stesso.

### Scheda Stili {#styles-tab-1}

Il componente Immagine supporta il sistema [di stile AEM](authoring.md#component-styling).