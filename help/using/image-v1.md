---
title: Componente immagine (v1)
seo-title: Componente immagine (v1)
description: Il componente di base Immagine è un componente di immagine adattivo che consente di modificare direttamente il contenuto.
seo-description: Il componente di base Immagine è un componente di immagine adattivo che consente di modificare direttamente il contenuto.
uuid: 20ea7921-511d-4d3a-b3df-c2f2c1d8455d
content-type: riferimento
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: ab9041ab-e29e-4277-b326-85ab37df8413
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# Componente immagine (v1){#image-component-v}

Il componente di base Immagine è un componente di immagine adattivo che consente di modificare direttamente il contenuto.

## Utilizzo {#usage}

Il componente Immagine consente di posizionare facilmente le risorse di immagine e offre funzioni di modifica diretta. Offre selezione adattiva delle immagini con caricamento lento e ritaglio per l’autore del contenuto.

Le larghezze di immagine consentite, il ritaglio e impostazioni aggiuntive possono essere definiti dall’autore del modello nella finestra di dialogo [](image-v1.md#main-pars_title_1995166862)della progettazione. L’editor del contenuto può caricare o selezionare le risorse nella finestra di dialogo [di](image-v1.md#main-pars_title_55926120) configurazione e ritagliare l’immagine nella finestra di dialogo [di](image-v1.md#main-pars_title)modifica. Per maggiore comodità, è disponibile anche una semplice modifica locale dell’immagine.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Immagine, introdotta originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è elencata la compatibilità di v1 del componente Immagine.

| Versione di AEM | Componente immagine v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Immagine.
>
>Per informazioni dettagliate sulla versione corrente del componente Immagine, consultate il documento sul componente [](image.md) Immagine.

## Output componente di esempio {#sample-component-output}

Esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/chlimage_1-7.png)

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
>L’esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le informazioni sulla [compatibilità per i componenti core v1](versions.md#main-pars_title_236368006) .

## Configura finestra di dialogo {#configure-dialog}

Oltre alla finestra di dialogo [standard per la](image-v1.md#main-pars_title) modifica e la [](image-v1.md#main-pars_title_1995166862)progettazione, il componente Immagine offre una finestra di dialogo di configurazione in cui l’immagine stessa è definita insieme alla descrizione e alle proprietà di base.

![](assets/chlimage_1-50.png)

* **Risorsa immagine**
   * Trascinate una risorsa dal browser [delle](https://helpx.adobe.com/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title) risorse o toccate l'opzione **Sfoglia** per caricarla da un file system locale.
   * Toccate o fate clic su **Cancella** per deselezionare l'immagine attualmente selezionata.
   * Toccate o fate clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://helpx.adobe.com/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19) nell’editor risorse.

* **L'immagine è decorativa** - Verificare se l'immagine deve essere ignorata dalla tecnologia di supporto e quindi non richiede un testo alternativo. Questo vale solo per le immagini decorative.
* **Testo** alternativo: alternativa testuale al significato o alla funzione dell'immagine, per lettori ipovedenti.
* **Collegamento**
   * Collegare l’immagine a un’altra risorsa.
   * Utilizzate la finestra di dialogo di selezione per collegarvi a un’altra risorsa AEM.
   * Se non effettuate il collegamento a una risorsa AEM, immettete l’URL assoluto. Gli URL non soluti verranno interpretati come relativi ad AEM.

* **Didascalia** - Per impostazione predefinita, sotto l’immagine vengono visualizzate ulteriori informazioni sull’immagine.
* **Visualizza la didascalia come pop-up** - Se questa opzione è selezionata, la didascalia non verrà visualizzata sotto l'immagine, ma come pop-up visualizzato da alcuni browser quando si passa il puntatore sull'immagine.

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di ritagliare, modificare la mappa del lancio e ingrandire l’immagine.

![](assets/chlimage_1-8.png)

* Avvia ritaglio

   ![](assets/chlimage_1-9.png)

   Selezionando questa opzione si apre un elenco a discesa per le proporzioni di ritaglio predefinite.

   * Scegliete l’opzione Mano **** libera per definire il ritaglio personalizzato.
   * Scegliete l’opzione **Rimuovi ritaglio** per visualizzare la risorsa originale.
   Una volta selezionata l’opzione di ritaglio, usate le maniglie blu per ridimensionare il ritaglio sull’immagine.

   ![](assets/chlimage_1-10.png)

* Ruota a destra

   ![](assets/chlimage_1-11.png)

   Usate questa opzione per ruotare l’immagine di 90° verso destra (in senso orario).

* Avvia mappa

   ![](assets/chlimage_1-12.png)

   Utilizzate questa opzione per applicare una mappa di lancio all'immagine. Selezionando questa opzione si apre una nuova finestra che consente all'utente di selezionare la forma della mappa:

   * **Aggiungi mappa rettangolare**
   * **Aggiungi mappa circolare**
   * **Aggiungi mappa poligono**

      * Per impostazione predefinita, aggiunge una mappa a triangolo. Fare doppio clic su una linea della forma per aggiungere una nuova maniglia di ridimensionamento blu su un nuovo lato.
   Una volta selezionata, la forma mappa viene sovrapposta all'immagine per il ridimensionamento. Trascinate e rilasciate le maniglie di ridimensionamento blu per regolare la forma.

   ![](assets/chlimage_1-13.png)

   Dopo aver ridimensionato la mappa del lancio, fate clic su di essa per aprire una barra degli strumenti mobile e definire il percorso del collegamento.

   * **Percorso**
      * Utilizzate l'opzione Selettore percorso per selezionare un percorso in AEM
      * Se il percorso non è in AEM, usate l’URL assoluto. I percorsi non assoluti verranno interpretati in relazione ad AEM.

      * **Testo** Alt Descrizione alternativa della destinazione del percorso
      * **Destinazione**
         * **Stessa scheda**
         * **Nuova scheda**
         * **Frame principale**
         * **Frame superiore**
   Toccate o fate clic sul segno di spunta blu per salvare, sulla x nera per annullare e sul cestino rosso per eliminare la mappa.

   ![](assets/chlimage_1-14.png)

* Ripristina zoom

   ![](assets/chlimage_1-15.png)

   Se l’immagine è già stata ingrandita, usate questa opzione per ripristinare il livello di zoom.

* Apri cursore zoom

   ![](assets/chlimage_1-16.png)

   Usate questa opzione per visualizzare un cursore per controllare il livello di zoom dell’immagine.

   ![](assets/chlimage_1-17.png)

L’editor locale può anche essere usato per modificare l’immagine. A causa di limiti di spazio, sono disponibili solo opzioni di base in linea. Per le opzioni di modifica completa, utilizzate la modalità a schermo intero.

![](assets/chlimage_1-18.png)

>[!NOTE]
>
>Le operazioni di modifica delle immagini (ritaglio, capovolgimento, rotazione) non sono supportate per le immagini GIF. Eventuali modifiche apportate in modalità di modifica ai GIF non verranno mantenute.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire i caricamenti di ritaglio, caricamento e rotazione eseguiti dall’autore del contenuto quando utilizza questo componente.

### Principale {#main}

On the **Main** tab you can define a list of allowed widths in pixels for the image to automatically load the most appropriate width from the list.

![](assets/chlimage_1-51.png)

Toccate o fate clic sul pulsante Aggiungi per aggiungere un’altra dimensione.

* Utilizzare le maniglie per riordinare l'ordine delle dimensioni.
* Utilizzate l'icona delete per rimuovere una larghezza.

Per impostazione predefinita, il caricamento delle immagini viene differito finché non diventano visibili. Selezionate l’opzione **Disattiva caricamento** lento per caricare le immagini al caricamento della pagina.

### Funzioni {#features}

Nella scheda **Funzioni** potete definire le opzioni disponibili per gli autori dei contenuti quando utilizzano il componente, incluse le opzioni di caricamento, orientamento e ritaglio.

* Origine

   ![](assets/chlimage_1-19.png)

   Selezionate l’opzione **Consenti caricamento risorse dal file system** per consentire agli autori di contenuti di caricare immagini dal computer locale. Per obbligare gli autori di contenuti a selezionare solo le risorse da AEM, deselezionate questa opzione.

* Orientamento

   ![](assets/chlimage_1-20.png)

   * **Ruota** - Utilizzate questa opzione per consentire all'autore del contenuto di utilizzare l'opzione **Ruota a destra** .
   * **Capovolgi** Utilizzate questa opzione per consentire all’autore del contenuto di utilizzare le opzioni **Rifletti in orizzontale** e **Rifletti in verticale** .
   >[!CAUTION]
   >
   >Per impostazione predefinita, l’opzione **Rifletti** è disattivata. Attivando questa opzione, i pulsanti **Rifletti in verticale** e **Rifletti in orizzontale** vengono visualizzati nella finestra di dialogo di modifica del componente immagine. Tuttavia, al momento la funzione non è supportata da AEM e le modifiche apportate con queste opzioni non vengono mantenute.

<!-- 
Comment Type: remark
Last Modified By: Chris Bohnert (bohnert)
Last Modified Date: 2017-11-20T05:51:34.378-0500

<p>Added caution based on CQDOC-11457. Hid the flip options in the procedure using the <strong>Draft</strong> option so that when this feature is implemented in CQ-4221539, the <strong>Draft</strong> property can simply be removed along with the caution.</p>
-->

* Ritaglio

   ![](assets/chlimage_1-21.png)

   Selezionate l’opzione **Consenti ritaglio** per consentire all’autore del contenuto di ritagliare l’immagine nel componente nella finestra di dialogo di modifica.
   * Fate clic su **Aggiungi** per aggiungere proporzioni di ritaglio predefinite.
   * Immettete un nome descrittivo che verrà visualizzato nel menu a discesa **Avvia ritaglio** .
   * Immettete il rapporto numerico dell’aspetto.
   * Usate le maniglie di trascinamento per riordinare l’ordine delle proporzioni
   * Usate l’icona del cestino per eliminare le proporzioni.
   >[!CAUTION]
   >
   >Note that in AEM, crop aspect ratios are defined as **height/width**. Ciò è diverso dalla definizione convenzionale di larghezza/altezza ed è fatto per motivi di compatibilità legacy. Gli autori dei contenuti non saranno a conoscenza di alcuna differenza, purché sia indicato un nome chiaro del rapporto, dal momento che il nome viene visualizzato nell’interfaccia utente e non il rapporto stesso.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Immagine [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.
