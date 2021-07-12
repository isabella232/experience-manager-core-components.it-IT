---
title: Componente immagine (v1)
description: Il componente immagine di base è un componente immagine adattivo che offre funzioni di modifica diretta.
index: n
role: Architect, Developer, Admin, User
exl-id: 625ce8de-5c4a-476d-b749-895493d169b1
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '1229'
ht-degree: 3%

---

# Componente immagine (v1) {#image-component-v}

Il componente immagine di base è un componente immagine adattivo che offre funzioni di modifica diretta.

## Utilizzo {#usage}

Il componente Immagine permette di inserire facilmente le risorse immagine e offre la possibilità di effettuare modifiche direttamente dalla propria posizione. Offre selezione adattiva delle immagini con caricamento lento e ritaglio per l’autore dei contenuti.

Le larghezze di immagine consentite, nonché il ritaglio e le impostazioni aggiuntive possono essere definiti dall&#39;autore del modello nella finestra di dialogo [progettazione](#design-dialog). L&#39;editor dei contenuti può caricare o selezionare le risorse nella finestra di dialogo [configura](#configure-dialog) e ritagliare l&#39;immagine nella finestra di dialogo [modifica](#edit-dialog). Per una maggiore comodità, è disponibile anche una semplice modifica diretta dell&#39;immagine.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la v1 del componente immagine, originariamente introdotto con la versione 1.0.0 dei componenti core con AEM 6.3.

La tabella seguente elenca la compatibilità della v1 del componente immagine.

| Versione di AEM | Componente immagine v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente immagine.
>
>Per informazioni dettagliate sulla versione corrente del componente immagine, consultare il documento [Componente immagine](/help/components/image.md) .

## Output componente di esempio {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>L’esportazione JSON dai componenti core richiede la versione 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le [informazioni sulla compatibilità per i componenti core v1](/help/versions.md) .

## Finestra di dialogo Configura {#configure-dialog}

Oltre alla finestra di dialogo standard [modifica](#edit-dialog) e [progettazione](#design-dialog), il componente immagine offre una finestra di dialogo di configurazione in cui l&#39;immagine stessa è definita insieme alla relativa descrizione e alle proprietà di base.

![](/help/assets/chlimage_1-50.png)

* **Risorsa immagine**
   * Rilascia una risorsa dal [browser Risorse](https://helpx.adobe.com/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title) o tocca l’opzione **Sfoglia** per caricarla da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * Tocca o fai clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://helpx.adobe.com/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19) nell’editor risorse.

* **L’immagine è decorativa**  - Controlla se l’immagine deve essere ignorata dalla tecnologia per l’accessibilità e quindi non richiede un testo alternativo. Questo vale solo per le immagini decorative.
* **Testo alternativo** : alternativa testuale al significato o alla funzione dell’immagine, per lettori ipovedenti.
* **Collegamento**
   * Collega l’immagine a un’altra risorsa.
   * Utilizza la finestra di dialogo di selezione per eseguire il collegamento a un’altra risorsa AEM.
   * Se non ti colleghi a una risorsa AEM, immetti l’URL assoluto. Gli URL non soluti vengono interpretati come relativi a AEM.

* **Didascalia**  - Per impostazione predefinita, sono disponibili ulteriori informazioni sull’immagine visualizzata sotto l’immagine.
* **Visualizza didascalia come a comparsa** : se questa opzione è selezionata, la didascalia non verrà visualizzata sotto l’immagine, ma come pop-up visualizzato da alcuni browser quando si passa il mouse sull’immagine.

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di ritagliare, modificare la mappa del lancio e ingrandire l’immagine.

![](/help/assets/chlimage_1-8.png)

* Avvia ritaglio

   ![](/help/assets/chlimage_1-9.png)

   Selezionando questa opzione si apre un elenco a discesa per le proporzioni predefinite del ritaglio.

   * Scegli l&#39;opzione **Mano libera** per definire il ritaglio desiderato.
   * Scegli l&#39;opzione **Rimuovi ritaglio** per visualizzare la risorsa originale.

   Una volta selezionata l’opzione Ritaglia, utilizzate le maniglie blu per ridimensionare il ritaglio sull’immagine.

   ![](/help/assets/chlimage_1-10.png)

* Ruota a destra

   ![](/help/assets/chlimage_1-11.png)

   Utilizzare questa opzione per ruotare l&#39;immagine di 90° verso destra (in senso orario).

* Mappa di Launch

   ![](/help/assets/chlimage_1-12.png)

   Utilizza questa opzione per applicare una mappa di lancio all&#39;immagine. Selezionando questa opzione si apre una nuova finestra che consente all&#39;utente di selezionare la forma della mappa:

   * **Aggiungi mappa rettangolare**
   * **Aggiungi mappa circolare**
   * **Aggiungi mappa poligonale**

      * Per impostazione predefinita aggiunge una mappa a triangolo. Fare doppio clic su una linea della forma per aggiungere un nuovo quadratino di ridimensionamento blu su un nuovo lato.

   Una volta selezionata, la forma mappa viene sovrapposta all&#39;immagine per consentire il ridimensionamento. Trascinare le maniglie di ridimensionamento blu per regolare la forma.

   ![](/help/assets/chlimage_1-13.png)

   Dopo aver ridimensionato la mappa di lancio, fai clic su di essa per aprire una barra degli strumenti mobile e definire il percorso del collegamento.

   * **Percorso**
      * Utilizza l’opzione Selettore percorso per selezionare un percorso in AEM
      * Se il percorso non è in AEM, utilizza l’URL assoluto. I percorsi non assoluti vengono interpretati in base a AEM.

      * **Testo AltDescrizione**
alternativa della destinazione del percorso
      * **Target**
         * **Stessa scheda**
         * **Nuova scheda**
         * **Frame principale**
         * **Frame superiore**

   Tocca o fai clic sul segno di spunta blu per salvare, la x nera per annullare e il cestino rosso per eliminare la mappa.

   ![](/help/assets/chlimage_1-14.png)

* Ripristina zoom

   ![](/help/assets/chlimage_1-15.png)

   Se l’immagine è già stata ingrandita, utilizza questa opzione per reimpostare il livello di zoom.

* Apri cursore Zoom

   ![](/help/assets/chlimage_1-16.png)

   Utilizzare questa opzione per visualizzare un cursore per controllare il livello di zoom dell&#39;immagine.

   ![](/help/assets/chlimage_1-17.png)

L’editor locale può essere utilizzato anche per modificare l’immagine. A causa di limiti di spazio, sono disponibili solo opzioni di base in linea. Per le opzioni di modifica completa, utilizzate la modalità a schermo intero.

![](/help/assets/chlimage_1-18.png)

>[!NOTE]
>
>Le operazioni di modifica delle immagini (ritaglio, capovolgimento, rotazione) non sono supportate per le immagini GIF. Tutte le modifiche apportate in modalità di modifica alle GIF non verranno mantenute.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire i caricamenti di ritaglio, caricamento e rotazione eseguiti dall’autore del contenuto quando utilizza questo componente.

### Principale {#main}

Nella scheda **Principale** è possibile definire un elenco di larghezze consentite in pixel affinché l&#39;immagine carichi automaticamente la larghezza più appropriata dall&#39;elenco.

![](/help/assets/chlimage_1-51.png)

Tocca o fai clic sul pulsante Aggiungi per aggiungere un’altra dimensione.

* Utilizzare le maniglie per ridisporre l&#39;ordine delle dimensioni.
* Utilizza l’icona Elimina per rimuovere una larghezza.

Per impostazione predefinita, il caricamento delle immagini viene differito fino a quando non diventano visibili. Seleziona l&#39;opzione **Disattiva il caricamento lento** per caricare le immagini al caricamento della pagina.

### Funzioni {#features}

Nella scheda **Funzioni** è possibile definire le opzioni disponibili per gli autori di contenuti quando utilizzano il componente, incluse le opzioni di caricamento, orientamento e ritaglio.

* Origine

   ![](/help/assets/chlimage_1-19.png)

   Seleziona l’opzione **Consenti caricamento risorse dal file system** per consentire agli autori di contenuti di caricare immagini dal proprio computer locale. Per forzare gli autori di contenuti a selezionare solo le risorse da AEM, deseleziona questa opzione.

* Orientamento

   ![](/help/assets/chlimage_1-20.png)

   * **Ruota** : utilizza questa opzione per consentire all’autore del contenuto di utilizzare l’opzione  **Ruota a** destra.
   * ****
FlipUtilizza questa opzione per consentire all’autore del contenuto di utilizzare la funzione 
**Capovolgi** orizzontalmente e  **capovolgi** verticalmente.
   >[!CAUTION]
   >
   >L&#39;opzione **Capovolgi** è disabilitata per impostazione predefinita. Attivando questa opzione, i pulsanti **Capovolgi verticalmente** e **Capovolgi orizzontalmente** verranno visualizzati nella finestra di dialogo di modifica del componente immagine, ma la funzione non è attualmente supportata da AEM e le modifiche effettuate utilizzando queste opzioni non verranno mantenute.

* Ritaglio

   ![](/help/assets/chlimage_1-21.png)

   Seleziona l’opzione **Consenti ritaglio** per consentire all’autore del contenuto di ritagliare l’immagine nel componente nella finestra di dialogo di modifica.
   * Fai clic su **Aggiungi** per aggiungere una proporzione di ritaglio predefinita.
   * Immetti un nome descrittivo che verrà visualizzato nel menu a discesa **Avvia ritaglio** .
   * Immettere il rapporto numerico dell&#39;aspetto.
   * Utilizzare le maniglie di trascinamento per ridisporre l&#39;ordine delle proporzioni
   * Utilizza l’icona del cestino per eliminare una proporzione.

   >[!CAUTION]
   >
   >In AEM, le proporzioni di ritaglio sono definite come **altezza/larghezza**. Questo differisce dalla definizione tradizionale di larghezza/altezza, per ragioni di compatibilità con versioni precedenti. Gli autori dei contenuti non sono a conoscenza di alcuna differenza, purché tu fornisca un nome chiaro per le proporzioni, poiché il nome viene visualizzato nell’interfaccia utente e non per le proporzioni stesse.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente immagine [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .
