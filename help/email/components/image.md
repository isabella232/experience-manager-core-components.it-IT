---
title: Componente immagine e-mail
description: Il componente Immagine e-mail è un componente immagine adattivo che offre funzioni di modifica diretta.
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 63%

---


# Componente immagine e-mail {#email-image-component}

Il componente Immagine e-mail è un componente immagine adattivo che offre funzioni di modifica diretta.

## Utilizzo {#usage}

Il componente Immagine e-mail offre una selezione adattiva delle immagini e un comportamento reattivo con caricamento lento per il visitatore della pagina, nonché un posizionamento e una configurazione semplici delle immagini con trascinamento per l’autore del contenuto.

* Le larghezze delle immagini e le altre impostazioni possono essere definiti dall’autore del modello nella [finestra di dialogo per progettazione.](#design-dialog)
* L’editor dei contenuti può caricare o selezionare le risorse nella [finestra di dialogo di configurazione.](#configure-dialog)

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Immagine e-mail è v1, introdotto con la versione x dei componenti core e-mail nell’ottobre 2022, ed è descritto in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core e-mail](/help/email/versions.md).

## Funzioni reattive {#responsive-features}

Il componente Immagine e-mail viene fornito con solide funzioni reattive pronte all’uso. A livello di modello della pagina, si può utilizzare la [finestra di dialogo per Progettazione](#design-dialog) per definire le larghezze predefinite della risorsa immagine. Il componente Immagine e-mail carica quindi automaticamente la larghezza corretta da visualizzare in base alle dimensioni della finestra del browser. Quando la finestra viene ridimensionata, il componente Immagine e-mail carica dinamicamente la dimensione corretta dell’immagine. Gli sviluppatori di componenti non devono preoccuparsi di definire query multimediali personalizzate, in quanto il componente Immagine e-mail è già ottimizzato per caricare il contenuto.

Inoltre, il componente Immagine e-mail supporta il caricamento lento per posticipare il caricamento della risorsa immagine effettiva fino a renderla visibile nel browser, aumentando la reattività del contenuto.

>[!TIP]
>
>Per impostazione predefinita, il componente Immagine e-mail è alimentato dal servlet Immagine adattiva. Per informazioni dettagliate su come funziona, consulta il documento [Adaptive Image Servlet](#adaptive-image-servlet).

## Supporto di Dynamic Media {#dynamic-media}

Il componente Immagine e-mail supporta [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=it#dynamicmedia) risorse. [Se abilitate,](#design-dialog) queste funzioni consentono di aggiungere risorse immagine di Dynamic Media con una semplice azione di trascinamento e rilascio della selezione oppure tramite il browser delle risorse, esattamente come faresti con qualsiasi altra immagine. Sono inoltre supportati modificatori di immagini, immagini preimpostate e ritaglio avanzato.

Le tue esperienze e-mail create con i componenti core e-mail possono offrire funzionalità Dynamic Media Image avanzate, basate su Sensei, solide, ad alte prestazioni e multipiattaforma.

## Supporto di SVG {#svg-support}

La grafica vettoriale scalabile (SVG) è supportata dal componente Immagine e-mail.

* Il trascinamento e rilascio di una risorsa SVG da DAM e il caricamento di un file SVG da un file system locale sono entrambi supportati.
* Il file SVG originale viene inviato in streaming (le trasformazioni vengono ignorate).
* Per un’immagine SVG, le “immagini avanzate” e le “dimensioni avanzate” sono impostate su un array vuoto nel modello di immagine.

### Sicurezza {#security}

Per motivi di sicurezza, il file SVG originale non viene mai richiamato direttamente dall’editor di immagini. Viene richiamato tramite `<img src=“path-to-component”>`. Ciò impedisce al browser di eseguire eventuali script incorporati nel file SVG.

## Esempio di output del componente {#sample-component-output}

Per scoprire il componente Immagine e-mail e visualizzare esempi delle relative opzioni di configurazione, nonché l’output di HTML e JSON, visita il [Libreria dei componenti.](https://adobe.com/go/aem_cmp_library_email_image)

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Immagine e-mail [si trova su GitHub.](https://adobe.com/go/aem_cmp_tech_email_image_v1)

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core.](/help/developing/overview.md)

Il componente Immagine supporta [i microdati schema.org.](https://schema.org)

## Finestra di dialogo per la configurazione {#configure-dialog}

Il componente Immagine e-mail offre una finestra di dialogo di configurazione in cui l’immagine stessa è definita insieme alla relativa descrizione e alle proprietà di base.

### Scheda Risorsa {#asset-tab}

![Scheda Risorsa della finestra di dialogo di configurazione del componente Immagine e-mail](/help/email/assets/email-image-configure-asset.png)

* **Eredita immagine in primo piano dalla pagina**: Questa opzione utilizza [l’immagine in primo piano della pagina collegata](page.md) o l’immagine in primo piano della pagina corrente se l’immagine non è collegata.

* **Testo alternativo per l’accessibilità**: Questo campo consente di definire una descrizione dell’immagine per gli utenti ipovedenti.

   * **Eredita testo alternativo dalla pagina**: Questa opzione utilizza la descrizione alternativa del valore della risorsa collegata dei metadati `dc:description` in DAM o nella pagina corrente se non è collegata alcuna risorsa.

* **Risorsa immagine**
   * Rilascia una risorsa dal [browser di risorse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=it) oppure tocca l’opzione **Sfoglia** per caricarla da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * Tocca o fai clic su **Modifica** a [gestire le rappresentazioni della risorsa](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=it) nell’Editor risorse.

* **Non fornire testo alternativo**: Questa opzione contrassegna l’immagine da ignorare da tecnologie per l’accessibilità, come gli assistenti vocali, nei casi in cui l’immagine sia puramente decorativa o in altro modo non trasmetta informazioni aggiuntive alla pagina.

* **Disattiva il caricamento lento** - Questa opzione precarica tutti i componenti immagine senza caricare se necessario.

### Scheda Metadati {#metadata-tab}

![Scheda Metadati della finestra di dialogo per configurazione del componente Immagine](/help/email/assets/email-image-configure-metadata.png)

* **Tipo di predefinito**: definisce i tipi di immagini preimpostate disponibili, **Predefinito immagine** o **Ritaglio avanzato**, ed è disponibile solo se [le funzioni di Dynamic Media](#dynamic-meida) sono abilitate.
   * **Predefinito immagine** - Quando **Tipo predefinito** di **Predefinito immagine** è selezionato, il menu a discesa **Predefinito immagine** è disponibile e consente la selezione dai predefiniti Dynamic Media disponibili. Questa opzione è disponibile solo se per la risorsa selezionata esistono dei predefiniti.
   * **Ritaglio avanzato** - Quando **Tipo predefinito** di **Ritaglio avanzato** è selezionato dal menu a discesa **Rendering** è disponibile e consente di selezionare le rappresentazioni disponibili della risorsa selezionata. Questa opzione è disponibile solo se per la risorsa selezionata sono definiti rendering.
   * **Modificatori immagine** - Ulteriori comandi di gestione delle immagini Dynamic Media possono essere definiti qui separati da `&`, indipendentemente dal quale **Tipo predefinito** è selezionato.
* **Didascalia**: informazioni aggiuntive sull’immagine, per impostazione predefinita viene visualizzata sotto l’immagine.
   * **Ottieni didascalia da DAM**: se questa opzione è selezionata, come didascalia dell’immagine verrà inserito il valore dei `dc:title`metadati in DAM. Disponibile solo quando una risorsa viene selezionata dal DAM.
   * **Visualizza didascalia come nota a comparsa**: se questa opzione è selezionata, la didascalia non verrà visualizzata sotto l’immagine, ma, in alcuni browser, come nota a comparsa quando si passa il puntatore sull’immagine.
* **Collegamento**: collega l’immagine a un’altra risorsa.
   * Utilizza la finestra di dialogo per selezione per stabilire il collegamento con un’altra risorsa AEM.
   * Se non stabilisci il collegamento con un’altra risorsa AEM, immetti l’URL assoluto. Gli URL non assoluti vengono interpretati come relativi ad AEM.
   * **Apri collegamento in una nuova scheda**: Questa opzione apre il collegamento in una nuova finestra del browser.
* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente in HTML.
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sui CSS.
* **Corretto con** - Questa opzione definisce la larghezza in pixel dell’immagine.
* **Adatta immagine alla larghezza disponibile** - Questa opzione si applica `"width":"100%"` all’attributo stile immagine.

>[!TIP]
>
>Le opzioni **Ritaglio avanzato** e **Predefinito immagine** si escludono a vicenda. Se un autore deve utilizzare un predefinito immagine insieme a al rendering di un ritaglio avanzato, deve utilizzare i **modificatori immagine** per aggiungere manualmente i predefiniti.

### Scheda Stili {#styles-tab-edit}

![Scheda Stili della finestra di dialogo di modifica del componente Immagine e-mail](/help/assets/image-configure-styles.png)

Il componente Immagine e-mail supporta il AEM [Sistema di stili.](/help/get-started/authoring.md#component-styling)

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nel [finestra di dialogo di progettazione](#design-dialog) affinché la scheda sia disponibile.

## Finestra di dialogo per la progettazione {#design-dialog}

### Scheda Principale {#main-tab}

![Scheda Principale della finestra di dialogo per progettazione del componente Immagine](/help/email/assets/email-image-design-main.png)

* **Abilita funzioni DM**: Se questa opzione è selezionata, sono disponibili [le funzioni di Dynamic Media](#dynamic-media).
   * Questa opzione viene visualizzata solo quando Dynamic Media è abilitato nell’ambiente.
* **Abilita immagini ottimizzate per il web**: quando questa opzione è selezionata, il [servizio di consegna delle immagini ottimizzate per il web](/help/developing/web-optimized-image-delivery.md) fornisce immagini in formato WebP, riducendone in media le dimensioni del 25%.
   * Questa opzione è disponibile solo in AEMaaCS.
   * Se non è selezionato o se il servizio di distribuzione delle immagini ottimizzato per il Web non è disponibile il [Servlet immagine adattivo](/help/developing/adaptive-image-servlet.md) viene utilizzato.
* **L’immagine è decorativa**: consente di definire se l’opzione dell’immagine decorativa è abilitata automaticamente quando si aggiunge il componente Immagine a una pagina.
* **Ottieni testo alternativo da DAM**: consente di definire se l’opzione per recuperare il testo alternativo dal DAM è abilitata automaticamente quando si aggiunge il componente Immagine a una pagina.
* **Ottieni didascalia da DAM**: consente di definire se l’opzione per recuperare la didascalia dal DAM è abilitata automaticamente quando si aggiunge il componente Immagine a una pagina.
* **Visualizza didascalia come nota a comparsa**: consente di definire se l’opzione per visualizzare la didascalia dell’immagine come nota a comparsa è abilitata automaticamente quando si aggiunge il componente Immagine a una pagina.
* **Larghezza di ridimensionamento**: Questo valore viene utilizzato per ridimensionare la larghezza delle immagini di base che sono risorse DAM.
   * Le proporzioni delle immagini vengono mantenute.
   * Se il valore è maggiore della larghezza effettiva dell’immagine, questo valore non avrà alcun effetto.
   * Questo valore non ha alcun effetto sulle immagini di SVG.

Nella scheda Principale puoi definire un elenco di larghezze consentite, espresse in pixel, in modo che l’immagine e il componente possano automaticamente caricare la larghezza appropriata in base alle dimensioni della finestra del browser. Questa è una parte importante del [funzioni reattive](#responsive-features) del componente Immagine e-mail.

* **Larghezze**: consente di definire un elenco di larghezze, espresse in pixel, in modo che l’immagine e il componente possano automaticamente caricare la larghezza appropriata in base alle dimensioni della finestra del browser.
   * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere un’altra dimensione.
      * Utilizzare le maniglie per ridisporre l&#39;ordine delle dimensioni.
      * Utilizza l’icona **Elimina** per rimuovere una larghezza.
   * Per impostazione predefinita, il caricamento delle immagini viene differito fino a quando non diventano visibili.
      * Seleziona l’opzione **Disattiva il caricamento lento** per caricare le immagini al caricamento della pagina.
* **Qualità JPEG**: fattore di qualità, espresso come percentuale tra 0 e 100, per le immagini JPEG trasformate, ad esempio ridimensionate o ritagliate.
* **Larghezza predefinita** - Larghezza predefinita delle immagini in pixel da utilizzare nella finestra di dialogo di progettazione

>[!TIP]
>
>Consulta il documento [Adaptive Image Servlet](/help/developing/adaptive-image-servlet.md) per suggerimenti su come ottimizzare la selezione delle rappresentazioni definendone con attenzione le dimensioni.

### Scheda Stili {#styles-tab}

Il componente Immagine e-mail supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).
