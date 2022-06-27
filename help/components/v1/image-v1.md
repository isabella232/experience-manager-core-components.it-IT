---
title: Componente Immagine (v1)
description: Il componente core Immagine è un componente immagine adattivo che offre funzioni di modifica diretta.
index: n
role: Architect, Developer, Admin, User
exl-id: 625ce8de-5c4a-476d-b749-895493d169b1
source-git-commit: 5f25aee6ebcb7a5c6b8db0df5b8b853f15af97d0
workflow-type: tm+mt
source-wordcount: '1323'
ht-degree: 92%

---

# Componente Immagine (v1) {#image-component-v}

Il componente core Immagine è un componente immagine adattivo che offre funzioni di modifica diretta.

## Utilizzo {#usage}

Il componente Immagine permette di posizionare facilmente le immagini e modificarle direttamente una volta posizionate. Consente all’autore di contenuto la selezione adattiva delle immagini con caricamento lento e il ritaglio delle immagini.

Le larghezze consentite delle immagini e il ritaglio nonché le altre impostazioni possono essere definiti dall’autore del modello nella [finestra di dialogo per progettazione](#design-dialog). L’editor di contenuto può caricare o selezionare le risorse nella [finestra di dialogo per configurazione](#configure-dialog) e ritagliare l’immagine nella [finestra di dialogo per modifica](#edit-dialog). Per maggiore comodità, è disponibile anche una semplice modifica diretta dell’immagine.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Immagine, originariamente introdotto con la versione 1.0.0 dei Componenti core in AEM 6.3.

La tabella che segue riporta la compatibilità della versione 1 del componente Immagine.

| Versione di AEM | Componente Immagine v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Immagine.
>
>Per informazioni dettagliate sulla versione corrente del componente Immagine, vedi il documento [Componente Immagine](/help/components/image.md).

## Esempio di output del componente {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://experienceleague.adobe.com/docs/experience-manager-64/developing/bestpractices/we-retail/we-retail.html?lang=it).

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
>L’esportazione JSON dai Componenti core richiede la versione 1.1.0 dei Componenti core. Per ulteriori informazioni, vedi le [informazioni sulla compatibilità dei Componenti core v1](/help/versions.md).

## Finestra di dialogo per configurazione {#configure-dialog}

Oltre alla normale [finestra di dialogo per modifica](#edit-dialog) e [finestra di dialogo per progettazione](#design-dialog), il componente Immagine offre anche una finestra di dialogo per configurazione, in cui l’immagine stessa viene definita insieme alla sua descrizione e alle sue proprietà di base.

![](/help/assets/chlimage_1-50.png)

* **Risorsa immagine**
   * Rilascia una risorsa dal [browser di risorse](https://helpx.adobe.com/it/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title) oppure tocca l’opzione **Sfoglia** per caricarla da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * Tocca o fai clic su **Modifica** per [gestire i rendering della risorsa](https://helpx.adobe.com/it/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19) nell’editor risorse.

* **L’immagine è decorativa**: controlla se l’immagine deve essere ignorata dalla tecnologia per l’accessibilità e quindi non richiede un testo alternativo. Questo vale solo per le immagini decorative.
* **Testo alternativo**: alternativa testuale del significato o della funzione dell’immagine per utenti ipovedenti.
* **Collegamento**
   * Collega l’immagine a un’altra risorsa.
   * Utilizza la finestra di dialogo per selezione per stabilire il collegamento con un’altra risorsa AEM.
   * Se non stabilisci il collegamento con un’altra risorsa AEM, immetti l’URL assoluto. Gli URL non assoluti vengono interpretati come relativi ad AEM.

* **Didascalia**: informazioni aggiuntive sull’immagine, per impostazione predefinita viene visualizzata sotto l’immagine.
* **Visualizza didascalia come nota a comparsa**: se questa opzione è selezionata, la didascalia non verrà visualizzata sotto l’immagine, ma, in alcuni browser, come nota a comparsa quando si passa il puntatore sull’immagine.

## Finestra di dialogo per modifica {#edit-dialog}

La finestra di dialogo per modifica consente all’autore di contenuto di ritagliare, modificare la mappa di lancio ed eseguire lo zoom dell’immagine.

![](/help/assets/chlimage_1-8.png)

* Avvia ritaglio

   ![](/help/assets/chlimage_1-9.png)

   Selezionando questa opzione si apre un elenco a discesa per le proporzioni predefinite del ritaglio.

   * Scegli l’opzione **Free Hand** per definire il ritaglio desiderato.
   * Scegli l’opzione **Rimuovi Ritaglio** per visualizzare la risorsa originale.

   Una volta selezionata un’opzione di ritaglio, utilizza le maniglie blu per dimensionare il ritaglio sull’immagine.

   ![](/help/assets/chlimage_1-10.png)

* Ruota a destra

   ![](/help/assets/chlimage_1-11.png)

   Utilizza questa opzione per ruotare l’immagine di 90° verso destra (in senso orario).

* Mappa di lancio

   ![](/help/assets/chlimage_1-12.png)

   Utilizza questa opzione per applicare una mappa di lancio all’immagine. Selezionando questa opzione si apre una nuova finestra che consente all’utente di selezionare la forma della mappa:

   * **Aggiungi mappa rettangolare**
   * **Aggiungi mappa circolare**
   * **Aggiungi mappa poligonale**

      * Per impostazione predefinita, aggiunge una mappa triangolare. Fare doppio clic su una linea della forma per aggiungere una nuova maniglia di ridimensionamento blu su un nuovo lato.

   Una volta selezionata, la forma della mappa viene sovrapposta all’immagine per consentire il ridimensionamento. Trascinare e rilasciare le maniglie di ridimensionamento blu per adattare la forma.

   ![](/help/assets/chlimage_1-13.png)

   Dopo aver ridimensionato la mappa di lancio, fai clic su di essa per aprire una barra degli strumenti mobile e definire il percorso del collegamento.

   * **Percorso**
      * Utilizza l’opzione Selettore percorso per selezionare un percorso in AEM
      * Se il percorso non è in AEM, utilizza l’URL assoluto. I percorsi non assoluti vengono interpretati come relativi ad AEM.

      * **Testo alt**
Descrizione alternativa della destinazione del percorso
      * **Destinazione**
         * **Stessa scheda**
         * **Nuova scheda**
         * **Frame principale**
         * **Frame superiore**

   Tocca o fai clic sul segno di spunta blu per salvare, sulla x nera per annullare e sul cestino rosso per eliminare la mappa.

   ![](/help/assets/chlimage_1-14.png)

* Reimposta zoom

   ![](/help/assets/chlimage_1-15.png)

   Se l’immagine è già stata ingrandita, utilizza questa opzione per reimpostare il livello di zoom.

* Apri cursore Zoom

   ![](/help/assets/chlimage_1-16.png)

   Utilizza questa opzione per visualizzare un cursore che permette di controllare il livello di zoom dell’immagine.

   ![](/help/assets/chlimage_1-17.png)

L’editor locale può essere utilizzato anche per modificare l’immagine. A causa di limiti di spazio, in linea sono disponibili solo opzioni di base. Per le opzioni di modifica completa, utilizza la modalità a schermo intero.

![](/help/assets/chlimage_1-18.png)

>[!NOTE]
>
>Le funzioni di modifica delle immagini (ritaglio, riflessione, rotazione) non sono supportate per le immagini GIF. Tutte le modifiche apportate in modalità di modifica alle immagini GIF non verranno mantenute.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire le opzioni di ritaglio, caricamento e rotazione disponibili per l’autore di contenuto quando utilizza questo componente.

### Principale {#main}

Nella scheda **Principale** puoi definire un elenco di larghezze consentite, espresse in pixel, in modo che l’immagine possa automaticamente caricare la larghezza giusta tra quelle in elenco.

![](/help/assets/chlimage_1-51.png)

Tocca o fai clic sul pulsante Aggiungi per aggiungere un’altra dimensione.

* Utilizza le maniglie per modificare l’ordine delle dimensioni.
* Utilizza l’icona Elimina per rimuovere una larghezza.

Per impostazione predefinita, il caricamento delle immagini viene differito fino a quando non diventano visibili. Deseleziona l’opzione **Attiva il caricamento lento** per caricare le immagini al caricamento della pagina.

* **Abilita immagini ottimizzate per il web** - Se selezionato, il [servizio di distribuzione delle immagini ottimizzato per il web](/help/developing/web-optimized-image-delivery.md) Le immagini verranno distribuite in formato WebP, riducendo in media le dimensioni delle immagini del 25%.
   * Questa opzione è disponibile solo in AEMaaCS.
   * Se non è selezionato o il servizio di distribuzione delle immagini ottimizzato per il Web non è disponibile il [Servlet immagine adattivo](/help/developing/adaptive-image-servlet.md) viene utilizzato.

### Funzioni {#features}

Nella scheda **Funzioni** è possibile definire le opzioni disponibili per gli autori di contenuto quando utilizzano il componente, incluse le opzioni di caricamento, orientamento e ritaglio.

* **Abilita immagini ottimizzate per il web** - se selezionato, il servizio di distribuzione delle immagini ottimizzato per il Web distribuirà le immagini in formato WebP, riducendo le dimensioni delle immagini in media del 25%.
   * Questa opzione è disponibile solo in AEMaaCS.
   * Se non è selezionato o il servizio di distribuzione delle immagini ottimizzato per il Web non è disponibile il [Servlet immagine adattivo](/help/developing/adaptive-image-servlet.md) viene utilizzato.

* Origine

   ![](/help/assets/chlimage_1-19.png)

   Seleziona l’opzione **Consenti caricamento risorse dal file system** per consentire agli autori di contenuto di caricare immagini dal proprio computer locale. Per forzare gli autori di contenuto a selezionare solo le risorse da AEM, deseleziona questa opzione.

* Orientamento

   ![](/help/assets/chlimage_1-20.png)

   * **Rotazione**: utilizza questa opzione per consentire all’autore di contenuto di utilizzare l’opzione **Ruota a destra**.
   * **Riflessione**
Seleziona questa opzione per consentire all’autore di contenuto di utilizzare 
le opzioni **Riflessione orizzontale** e **Riflessione verticale**.
   >[!CAUTION]
   >
   >L’opzione **Riflessione** è disabilitata per impostazione predefinita. Attivando questa opzione, i pulsanti **Riflessione verticale** e **Riflessione orizzontale** vengono visualizzati nella finestra di dialogo per modifica del componente Immagine, ma questa funzione non è attualmente supportata da AEM e le modifiche effettuate utilizzando queste opzioni non verranno mantenute.

* Ritaglio

   ![](/help/assets/chlimage_1-21.png)

   Seleziona l’opzione **Consenti ritaglio** per consentire all’autore di contenuto di ritagliare l’immagine nella finestra di dialogo per modifica del componente.
   * Fai clic su **Aggiungi** per aggiungere una proporzione predefinita per il ritaglio.
   * Immetti un nome descrittivo che verrà visualizzato nel menu a discesa **Avvia ritaglio**.
   * Immetti il rapporto numerico per la proporzione.
   * Utilizza le maniglie di trascinamento per modificare l’ordine delle proporzioni
   * Utilizza l’icona cestino per eliminare una proporzione.

   >[!CAUTION]
   >
   >In AEM, i rapporti di proporzione del ritaglio sono definiti come **altezza/larghezza**. Ciò differisce dalla definizione tradizionale di larghezza/altezza e viene fatto per ragioni di compatibilità con le versioni precedenti. Gli autori di contenuto non noteranno alcuna differenza, purché venga fornito un nome chiaro per la proporzione, in quanto il nome viene visualizzato nell’interfaccia utente e non nella proporzione stessa.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Immagine [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image).

L’intero progetto dei Componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).
