---
title: Componente immagine (v 1)
seo-title: Componente immagine (v 1)
description: Il componente Immagine componente core è una funzione di modifica locale delle funzioni dei componenti immagine.
seo-description: Il componente Immagine componente core è una funzione di modifica locale delle funzioni dei componenti immagine.
uuid: 20 ea 7921-511 d -4 d 3 a-b 3 df-c 2 f 2 c 1 d 8455 d
content-type: riferimento
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: ab 9041 ab-e 29 e -4277-b 326-85 ab 37 df 8413
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# Componente immagine (v 1){#image-component-v}

Il componente Immagine componente core è una funzione di modifica locale delle funzioni dei componenti immagine.

## Utilizzo {#usage}

Il componente Immagine permette di posizionare facilmente risorse di immagini e offerte locali. Offre selezioni immagine adattive con caricamento lazy e ritaglio per l&#39;autore del contenuto.

Le larghezze delle immagini consentite e il ritaglio e le impostazioni aggiuntive possono essere definiti dall&#39;autore del modello nella finestra di dialogo [di progettazione](image-v1.md#main-pars_title_1995166862). L&#39;editor di contenuto può caricare o selezionare le risorse nella finestra di dialogo [Configura](image-v1.md#main-pars_title_55926120) e ritagliare l&#39;immagine nella finestra di dialogo [di modifica](image-v1.md#main-pars_title). Per maggiore praticità è disponibile anche una semplice modifica diretta dell&#39;immagine.

## Versione e Compatibilità {#version-and-compatibility}

Questo documento descrive v 1 del componente Immagine, originariamente introdotto con la release 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità della release v 1 del componente Immagine.

| Versione di AEM | Componente immagine v 1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la v 1 del componente Immagine.
>
>Per informazioni dettagliate sulla versione corrente del componente Immagine, consultate [il documento Componente](image.md) Immagine.

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>L&#39;esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consultate le informazioni [di compatibilità per i componenti core v 1](versions.md#main-pars_title_236368006) .

## Configura finestra di dialogo {#configure-dialog}

Oltre alla finestra di dialogo di [modifica standard](image-v1.md#main-pars_title) e [alla finestra di dialogo di progettazione](image-v1.md#main-pars_title_1995166862), il componente Immagine offre una finestra di dialogo di configurazione in cui viene definito l&#39;immagine stessa insieme alla descrizione e alle proprietà di base.

![](assets/chlimage_1-50.png)

* **Risorsa immagine**
   * Rilasciate una risorsa dal Browser [risorse](https://helpx.adobe.com/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title) o toccate l&#39;opzione **di ricerca** da caricare da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l&#39;immagine correntemente selezionata.
   * Toccate o fate clic **su Modifica** per [gestire i rendering della risorsa](https://helpx.adobe.com/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19) nell&#39;editor risorse.

* **L&#39;immagine è decorativa** - Controlla se l&#39;immagine deve essere ignorata dalla tecnologia di accessibilità e quindi non richiede un testo alternativo. Ciò si applica solo alle immagini decorative.
* **Testo alternativo** - Alternative testuali rispetto al significato o alla funzione dell&#39;immagine, per i lettori ipovedenti.
* **Collegamento**
   * Collegate l&#39;immagine a un&#39;altra risorsa.
   * Utilizza la finestra di dialogo di selezione per collegare un&#39;altra risorsa AEM.
   * Se non collegate una risorsa AEM, immettete l&#39;URL assoluto. Gli URL non soliti verranno interpretati come relativi ad AEM.

* **Didascalia** : le informazioni aggiuntive sull&#39;immagine visualizzate sotto l&#39;immagine sono predefinite.
* **Visualizza didascalia come pop-up** - Quando questa opzione è selezionata, la didascalia non viene visualizzata sotto l&#39;immagine, ma come pop-up visualizzato da alcuni browser quando si passa il mouse sull&#39;immagine.

## Finestra di dialogo di modifica {#edit-dialog}

La finestra di dialogo di modifica consente all&#39;autore del contenuto di ritagliare, modificare la mappa di lancio e applicare lo zoom all&#39;immagine.

![](assets/chlimage_1-8.png)

* Avvia ritaglio

   ![](assets/chlimage_1-9.png)

   Selezionando questa opzione si apre un menu a discesa per le proporzioni di ritaglio predefinite.

   * Scegliete l&#39;opzione **Mano libera** per definire il ritaglio.
   * Scegliete l&#39;opzione **Rimuovi ritaglio** per visualizzare la risorsa originale.
   Una volta selezionata l&#39;opzione Ritaglio, usate le maniglie blu per ridimensionare il ritaglio sull&#39;immagine.

   ![](assets/chlimage_1-10.png)

* Ruota a destra

   ![](assets/chlimage_1-11.png)

   Utilizzare questa opzione per ruotare l&#39;immagine di 90 ° a destra (in senso orario).

* Mappa lancio

   ![](assets/chlimage_1-12.png)

   Utilizzate questa opzione per applicare una mappa di lancio all&#39;immagine. Selezionate questa opzione per aprire una nuova finestra che consente all&#39;utente di selezionare la forma della mappa:

   * **Aggiungi mappa rettangolare**
   * **Aggiungi mappa circolare**
   * **Aggiungi mappa poligono**

      * Per impostazione predefinita, viene aggiunta una mappa triangolare. Fare doppio clic su una riga della forma per aggiungere una nuova maniglia di ridimensionamento blu su un nuovo lato.
   Una volta selezionata la forma della mappa, questa viene sovrapposta all&#39;immagine che consente il ridimensionamento. Trascinare e rilasciare le maniglie di ridimensionamento blu per regolare la forma.

   ![](assets/chlimage_1-13.png)

   Dopo aver ridimensionato la mappa di avvio, fare clic su di essa per aprire una barra degli strumenti mobile per definire il percorso del collegamento.

   * **Percorso**
      * Utilizzare l&#39;opzione Selettore percorso per selezionare un percorso in AEM
      * Se il percorso non è in AEM, usate l&#39;URL assoluto. I percorsi non assoluti verranno interpretati in base ad AEM.

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

   Se l&#39;immagine è già stata ingrandita, usate questa opzione per ripristinare il livello di zoom.

* Apri cursore zoom

   ![](assets/chlimage_1-16.png)

   Usate questa opzione per visualizzare un cursore per controllare il livello di zoom dell&#39;immagine.

   ![](assets/chlimage_1-17.png)

L&#39;editor locale può essere usato anche per modificare l&#39;immagine. A causa di limiti di spazio, sono disponibili solo le opzioni di base. Per le opzioni di modifica complete, utilizzate la modalità schermo intero.

![](assets/chlimage_1-18.png)

>[!NOTE]
>
>Le operazioni di modifica delle immagini (ritaglio, capovolgimento, rotazione) non sono supportate per le immagini GIF. Tutte le modifiche apportate in modalità di modifica a GIF non saranno persistenti.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire i caricamenti di ritaglio, caricamento e rotazione con il componente.

### Principale {#main}

Nella scheda **Principale** è possibile definire un elenco di larghezze consentite in pixel affinché l&#39;immagine carichi automaticamente la larghezza più appropriata dall&#39;elenco.

![](assets/chlimage_1-51.png)

Toccate o fate clic sul pulsante Aggiungi per aggiungere un&#39;altra dimensione.

* Utilizzare le maniglie di acquisizione per riordinare l&#39;ordine delle dimensioni.
* Usate l&#39;icona Elimina per rimuovere una larghezza.

Per impostazione predefinita, il caricamento delle immagini viene differito finché non diventa visibile. Selezionate l&#39;opzione **Disattiva caricamento lento** per caricare le immagini al caricamento della pagina.

### Funzioni {#features}

Nella scheda **Funzioni** potete definire le opzioni disponibili per gli autori di contenuto quando si utilizza il componente, quali opzioni di caricamento, orientamento e ritaglio.

* Origine

   ![](assets/chlimage_1-19.png)

   Selezionate l&#39;opzione **Consenti caricamento risorse dal file system** per consentire agli autori di contenuto di caricare le immagini dal proprio computer locale. Per obbligare gli autori di contenuto a selezionare solo risorse da AEM, deselezionate questa opzione.

* Orientamento

   ![](assets/chlimage_1-20.png)

   * **Rotate** - Use this option to allow the content author to use the **Rotate Right** option.
   * **Rifletti**
Utilizzate questa opzione per consentire all&#39;autore del contenuto di utilizzare le opzioni **Rifletti in orizzontale** e **Rifletti in verticale** .
   >[!CAUTION]
   >
   >L&#39;opzione **Rifletti** è disattivata per impostazione predefinita. Attivando i pulsanti **Rifletti in verticale** e **Capovolgi orizzontalmente** nella finestra di dialogo di modifica del componente Immagine, la funzione non è supportata da AEM e tutte le modifiche apportate utilizzando queste opzioni non vengono mantenute.

<!-- 
Comment Type: remark
Last Modified By: Chris Bohnert (bohnert)
Last Modified Date: 2017-11-20T05:51:34.378-0500

<p>Added caution based on CQDOC-11457. Hid the flip options in the procedure using the <strong>Draft</strong> option so that when this feature is implemented in CQ-4221539, the <strong>Draft</strong> property can simply be removed along with the caution.</p>
-->

* Ritaglio

   ![](assets/chlimage_1-21.png)

   Selezionate l&#39;opzione **Consenti ritaglio** per consentire all&#39;autore del contenuto di ritagliare l&#39;immagine nel componente nella finestra di dialogo di modifica.
   * Fate clic su **Aggiungi** per aggiungere proporzioni di ritaglio predefinite.
   * Inserite un nome descrittivo che verrà mostrato nel menu a discesa **Avvia ritaglio** .
   * Inserite il rapporto numerico dell&#39;aspetto.
   * Utilizzare le maniglie trascinate per riordinare l&#39;ordine delle proporzioni
   * Usate l&#39;icona del cestino per eliminare le proporzioni.
   >[!CAUTION]
   >
   >In AEM, le proporzioni ritagliate sono definite **come altezza/larghezza**. Ciò si differenzia dalla definizione convenzionale di larghezza/altezza e viene effettuata per motivi di compatibilità precedenti. Gli autori di contenuto non saranno a conoscenza di alcuna differenza purché sia indicato un nome chiaro del rapporto, in quanto il nome viene visualizzato nell&#39;interfaccia utente e non il rapporto stesso.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente [Immagine è disponibile su github](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image).

L&#39;intero progetto componenti core può essere scaricato da github.

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).
