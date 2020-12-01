---
title: Componente immagine (v1)
description: Il componente di base Immagine è un componente di immagine adattivo che consente di modificare direttamente il contenuto.
index: n
translation-type: tm+mt
source-git-commit: 78202dc777b90f795f66873921c55e21ef8a239c
workflow-type: tm+mt
source-wordcount: '1229'
ht-degree: 3%

---


# Componente immagine (v1) {#image-component-v}

Il componente di base Immagine è un componente di immagine adattivo che consente di modificare direttamente il contenuto.

## Utilizzo {#usage}

Il componente Immagine permette di posizionare facilmente le risorse di immagine e di effettuare operazioni di modifica diretta. Offre selezione adattiva delle immagini con caricamento lento e ritaglio per l’autore del contenuto.

Le larghezze di immagine consentite, nonché il ritaglio e impostazioni aggiuntive possono essere definiti dall&#39;autore del modello nella finestra di dialogo [progettazione](#design-dialog). L&#39;editor dei contenuti può caricare o selezionare le risorse nella finestra di dialogo [configura](#configure-dialog) e ritagliare l&#39;immagine nella finestra di dialogo di modifica [a3/>. ](#edit-dialog) Per maggiore comodità, è disponibile anche una semplice modifica locale dell’immagine.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la v1 del componente Immagine, introdotta originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è elencata la compatibilità di v1 del componente Immagine.

| Versione di AEM | Componente immagine v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Immagine.
>
>Per informazioni dettagliate sulla versione corrente del componente Immagine, consultate il documento [Image Component](/help/components/image.md).

## Esempio di output del componente {#sample-component-output}

Esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](/help/assets/chlimage_1-7.png)

### HTML {#html}

```
<div class="cmp cmp-image aem-GridColumn aem-GridColumn--default--12">
 
        <noscript data-cmp-image="{&#34;smartImages&#34;:[],&#34;smartSizes&#34;:[],&#34;lazyEnabled&#34;:true}">
            <img src="/content/we-retail/us/en/equipment/_jcr_content/root/responsivegrid/image.img.jpg" alt="Surfboard"/>
        </noscript>

</div>
```

### JSON {#json}

```
"image": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "smartSizes": [],
              "smartImages": [],
              "lazyEnabled": true,
              "src": "/content/we-retail/us/en/equipment/equipment/jcr%3acontent/root/responsivegrid/image.img.jpeg",
              ":type": "weretail/components/content/image"
            }
```

>[!NOTE]
>
>L’esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, vedere le [informazioni sulla compatibilità per i componenti core v1](/help/versions.md).

## Configura finestra di dialogo {#configure-dialog}

Oltre alla finestra di dialogo [modifica ](#edit-dialog) e alla finestra di dialogo di progettazione [standard](#design-dialog), il componente immagine offre una finestra di dialogo di configurazione in cui l&#39;immagine stessa è definita insieme alla relativa descrizione e alle proprietà di base.

![](/help/assets/chlimage_1-50.png)

* **Risorsa immagine**
   * Rilasciate una risorsa dal [browser delle risorse](https://helpx.adobe.com/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title) o toccate l&#39;opzione **Browse** per caricarla da un file system locale.
   * Toccate o fate clic su **Cancella** per deselezionare l&#39;immagine attualmente selezionata.
   * Toccate o fate clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://helpx.adobe.com/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19) nell&#39;editor risorse.

* **L&#39;immagine è decorativa**  - Verificare se l&#39;immagine deve essere ignorata dalla tecnologia di supporto e quindi non richiede un testo alternativo. Questo vale solo per le immagini decorative.
* **Testo**  alternativo: alternativa testuale al significato o alla funzione dell&#39;immagine, per lettori ipovedenti.
* **Collegamento**
   * Collegate l’immagine a un’altra risorsa.
   * Utilizzare la finestra di dialogo di selezione per collegarsi a un&#39;altra risorsa AEM.
   * Se non effettuate il collegamento a una risorsa AEM, immettete l’URL assoluto. Gli URL non soluti verranno interpretati come relativi a AEM.

* **Didascalia**  - Per impostazione predefinita vengono visualizzate informazioni aggiuntive sull&#39;immagine visualizzata sotto l&#39;immagine.
* **Visualizza la didascalia come pop-up**  - Se questa opzione è selezionata, la didascalia non viene visualizzata sotto l&#39;immagine, ma come pop-up visualizzato da alcuni browser quando si passa il puntatore sull&#39;immagine.

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di ritagliare, modificare la mappa del lancio e ingrandire l’immagine.

![](/help/assets/chlimage_1-8.png)

* Avvia ritaglio

   ![](/help/assets/chlimage_1-9.png)

   Selezionando questa opzione si apre un elenco a discesa per le proporzioni di ritaglio predefinite.

   * Scegliere l&#39;opzione **Mano libera** per definire il proprio ritaglio.
   * Scegliete l’opzione **Rimuovi ritaglio** per visualizzare la risorsa originale.

   Una volta selezionata l’opzione di ritaglio, usate le maniglie blu per ridimensionare il ritaglio sull’immagine.

   ![](/help/assets/chlimage_1-10.png)

* Ruota a destra

   ![](/help/assets/chlimage_1-11.png)

   Usate questa opzione per ruotare l’immagine di 90° verso destra (in senso orario).

* Avvia mappa

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
      * Se il percorso non è AEM, utilizza l’URL assoluto. I percorsi non assoluti verranno interpretati in relazione ai AEM.

      * **Alt**
textDescrizione alternativa della destinazione del percorso
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

La finestra di dialogo Progettazione consente all’autore del modello di definire i caricamenti di ritaglio, caricamento e rotazione eseguiti dall’autore del contenuto quando utilizza questo componente.

### Principale {#main}

Nella scheda **Principale** è possibile definire un elenco di larghezze consentite in pixel affinché l&#39;immagine possa caricare automaticamente la larghezza più appropriata dall&#39;elenco.

![](/help/assets/chlimage_1-51.png)

Toccate o fate clic sul pulsante Aggiungi per aggiungere un’altra dimensione.

* Utilizzare le maniglie per riordinare l&#39;ordine delle dimensioni.
* Utilizzate l&#39;icona delete per rimuovere una larghezza.

Per impostazione predefinita, il caricamento delle immagini viene differito finché non diventano visibili. Selezionate l&#39;opzione **Disattiva caricamento pigro** per caricare le immagini al caricamento della pagina.

### Funzioni {#features}

Nella scheda **Funzioni** è possibile definire le opzioni disponibili per gli autori dei contenuti quando utilizzano il componente, incluse le opzioni di caricamento, orientamento e ritaglio.

* Origine

   ![](/help/assets/chlimage_1-19.png)

   Selezionate l&#39;opzione **Consenti caricamento risorse da file system** per consentire agli autori di contenuti di caricare immagini dal proprio computer locale. Per obbligare gli autori del contenuto a selezionare solo le risorse da AEM, deselezionate questa opzione.

* Orientamento

   ![](/help/assets/chlimage_1-20.png)

   * **Ruota**  - Utilizzate questa opzione per consentire all&#39;autore del contenuto di utilizzare l&#39;opzione  **Ruota a** destra.
   * ****
CapovolgiUtilizzate questa opzione per consentire all&#39;autore del contenuto di utilizzare il pulsante 
**Capovolgi** orizzontalmente e  **Rifletti** verticalmente.
   >[!CAUTION]
   >
   >Per impostazione predefinita, l&#39;opzione **Capovolgi** è disattivata. Attivando questa opzione, i pulsanti **Rifletti in verticale** e **Rifletti in orizzontale** vengono visualizzati nella finestra di dialogo di modifica del componente immagine, ma la funzione non è attualmente supportata da AEM e le modifiche apportate con queste opzioni non vengono mantenute.

* Ritaglio

   ![](/help/assets/chlimage_1-21.png)

   Selezionate l&#39;opzione **Consenti ritaglio** per consentire all&#39;autore del contenuto di ritagliare l&#39;immagine nel componente nella finestra di dialogo di modifica.
   * Fate clic su **Aggiungi** per aggiungere proporzioni di ritaglio predefinite.
   * Immettere un nome descrittivo che verrà visualizzato nel menu a discesa **Avvia ritaglio**.
   * Immettete il rapporto numerico dell’aspetto.
   * Usate le maniglie di trascinamento per riordinare l’ordine delle proporzioni
   * Usate l’icona del cestino per eliminare le proporzioni.

   >[!CAUTION]
   >
   >In AEM, le proporzioni del ritaglio sono definite come **altezza/larghezza**. Questo differisce dalla definizione tradizionale di larghezza/altezza, per ragioni di compatibilità con versioni precedenti. Gli autori dei contenuti non saranno a conoscenza di alcuna differenza, purché sia stato specificato un nome chiaro per il rapporto, dal momento che il nome viene visualizzato nell’interfaccia utente e non per il rapporto stesso.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Immagine [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).
