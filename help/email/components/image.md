---
title: Componente Immagine e-mail
description: Il componente Immagine e-mail è un componente immagine adattivo che offre funzioni di modifica diretta.
role: Architect, Developer, Admin, User
exl-id: f5d40047-3082-4edd-a5f6-6ab3e33997f9
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: ht
source-wordcount: '1645'
ht-degree: 100%

---


# Componente Immagine e-mail {#email-image-component}

Il componente Immagine e-mail è un componente immagine adattivo che offre funzioni di modifica diretta.

## Utilizzo {#usage}

Per chi visita la pagina, il componente Immagine e-mail offre la selezione adattiva delle immagini e un comportamento reattivo con caricamento lazy; per chi crea i contenuti, offre la possibilità di inserire le immagini mediante trascinamento e di configurarle con facilità.

* Le larghezze delle immagini e le altre impostazioni possono essere definite dall’autore del modello nella [finestra di dialogo per la progettazione.](#design-dialog)
* L’editor dei contenuti può caricare o selezionare le risorse nella [finestra di dialogo di configurazione.](#configure-dialog)

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Immagine e-mail è la versione 1, introdotta con la versione x dei componenti core E-mail a ottobre 2022, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile  | - |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, consulta il documento [Versioni dei Componenti core e-mail](/help/email/versions.md).

## Funzioni reattive {#responsive-features}

Il componente Immagine e-mail è dotato di solide funzioni reattive pronte per l’uso. A livello di modello della pagina, si può utilizzare la [finestra di dialogo per la progettazione](#design-dialog) per definire le larghezze predefinite della risorsa immagine. Il componente Immagine e-mail carica quindi automaticamente la larghezza corretta da visualizzare, in base alle dimensioni della finestra del browser. Quando la finestra viene ridimensionata, il componente Immagine e-mail carica dinamicamente la dimensione corretta dell’immagine. Gli sviluppatori di componenti non devono preoccuparsi di definire query multimediali personalizzate, in quanto il componente Immagine e-mail è già ottimizzato per caricare il contenuto.

Inoltre, il componente Immagine e-mail supporta il caricamento lazy, in modo che la risorsa venga caricata solo quando l’immagine entra effettivamente nell’area visibile della finestra del browser, aumentando la reattività del contenuto.

>[!TIP]
>
>Per impostazione predefinita, il componente Immagine e-mail è gestito da Adaptive Image Servlet. Per informazioni dettagliate su come funziona, consulta il documento [Adaptive Image Servlet](#adaptive-image-servlet).

## Supporto di Dynamic Media {#dynamic-media}

Il componente Immagine e-mail supporta le risorse [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=it#dynamicmedia). [Se abilitate,](#design-dialog) queste funzioni consentono di aggiungere risorse immagine di Dynamic Media con una semplice azione di trascinamento e rilascio della selezione oppure tramite il browser delle risorse, esattamente come faresti con qualsiasi altra immagine. Sono inoltre supportati modificatori di immagini, immagini preimpostate e ritaglio avanzato.

Le esperienze e-mail realizzate con i componenti core E-mail ora si arricchiscono delle solide funzionalità per immagini Dynamic Media, performanti, multipiattaforma e con tecnologia Sensei.

## Supporto di SVG {#svg-support}

Il componente Immagine e-mail supporta il formato SVG per grafica vettoriale scalabile.

* L’inserimento tramite trascinamento di una risorsa SVG da DAM e il caricamento di un file SVG da un file system locale sono entrambi supportati.
* Il file SVG originale viene inviato in streaming (le trasformazioni vengono ignorate).
* Per un’immagine SVG, le “immagini avanzate” e le “dimensioni avanzate” sono impostate su un array vuoto nel modello di immagine.

### Sicurezza {#security}

Per motivi di sicurezza, il file SVG originale non viene mai richiamato direttamente dall’editor di immagini. Viene richiamato tramite `<img src=“path-to-component”>`. Ciò impedisce al browser di eseguire eventuali script incorporati nel file SVG.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Immagine e-mail [è disponibile su GitHub.](https://adobe.com/go/aem_cmp_tech_email_image_v1)

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core.](/help/developing/overview.md)

Il componente Immagine supporta [i microdati schema.org.](https://schema.org)

## Finestra di dialogo per la configurazione {#configure-dialog}

Il componente Immagine e-mail offre una finestra di dialogo di configurazione in cui l’immagine stessa è definita insieme alla relativa descrizione e alle proprietà di base.

### Scheda Risorsa {#asset-tab}

![Scheda Risorsa della finestra di dialogo per la configurazione del componente Immagine e-mail](/help/email/assets/email-image-configure-asset.png)

* **Eredita immagine in primo piano dalla pagina**: Questa opzione utilizza [l’immagine in primo piano della pagina collegata](page.md) o l’immagine in primo piano della pagina corrente se l’immagine non è collegata.

* **Testo alternativo per accessibilità**: Questo campo consente di definire una descrizione dell’immagine per gli utenti ipovedenti.

   * **Eredita testo alternativo dalla pagina**: Questa opzione utilizza la descrizione alternativa del valore della risorsa collegata dei metadati `dc:description` in DAM o nella pagina corrente se non è collegata alcuna risorsa.

* **Risorsa immagine**
   * Rilascia una risorsa dal [browser di risorse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=it) oppure tocca l’opzione **Sfoglia** per caricarla da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * Tocca o fai clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=it) nell’Editor risorse.

* **Non fornire testo alternativo**: questa opzione contrassegna l’immagine da ignorare da tecnologie per l’accessibilità, come gli assistenti vocali, nei casi in cui l’immagine sia puramente decorativa o in altro modo non trasmetta informazioni aggiuntive alla pagina.

* **Disattiva il caricamento lento**: questa opzione precarica tutti i componenti immagine senza caricamento in base alle esigenze.

### Scheda Metadati {#metadata-tab}

![Scheda Metadati della finestra di dialogo per configurazione del componente Immagine](/help/email/assets/email-image-configure-metadata.png)

* **Tipo di predefinito**: definisce i tipi di immagini preimpostate disponibili, **Predefinito immagine** o **Ritaglio avanzato**, ed è disponibile solo se [le funzioni di Dynamic Media](#dynamic-meida) sono abilitate.
   * **Predefinito immagine**: se per **Tipo di predefinito** è selezionata l’opzione **Predefinito immagine**, è disponibile l’elenco a discesa **Predefinito immagine** che consente di selezionare i predefiniti di Dynamic Media disponibili. Questa opzione è disponibile solo se per la risorsa selezionata esistono dei predefiniti.
   * **Ritaglio avanzato**: quando viene selezionato **Tipo di predefinito** di **Ritaglio avanzato**, è disponibile l’elenco a discesa della **Rappresentazione** che consente di selezionare le rappresentazioni disponibili della risorsa selezionata. Questa opzione è disponibile solo se per la risorsa selezionata sono definiti rendering.
   * **Modificatori immagine**: qui è possibile definire comandi Dynamic Media aggiuntivi per la gestione delle immagini, separati da `&`, indipendentemente dal **Tipo di predefinito** selezionato.
* **Didascalia**: informazioni aggiuntive sull’immagine, per impostazione predefinita viene visualizzata sotto l’immagine.
   * **Ottieni didascalia da DAM**: se questa opzione è selezionata, come didascalia dell’immagine verrà inserito il valore dei `dc:title` metadati in DAM. Disponibile solo quando una risorsa viene selezionata da DAM.
   * **Visualizza didascalia come nota a comparsa**: se questa opzione è selezionata, la didascalia non verrà visualizzata sotto l’immagine, ma, in alcuni browser, come nota a comparsa quando si passa il puntatore sull’immagine.
* **Collegamento**: collega l’immagine a un’altra risorsa.
   * Utilizza la finestra di dialogo per selezione per stabilire il collegamento con un’altra risorsa AEM.
   * Se non stabilisci il collegamento con un’altra risorsa AEM, immetti l’URL assoluto. Gli URL non assoluti vengono interpretati come relativi ad AEM.
   * **Apri il collegamento in una nuova scheda**: Questa opzione apre il collegamento in una nuova finestra del browser.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nell’HTML.
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sulle CSS.
* **Fisso con**: questa opzione definisce la larghezza in pixel dell’immagine.
* **Adatta immagine alla larghezza disponibile**: questa opzione si applica `"width":"100%"` all’attributo di stile dell’immagine.

>[!TIP]
>
>Le opzioni **Ritaglio avanzato** e **Predefinito immagine** si escludono a vicenda. Se un autore deve utilizzare un predefinito immagine insieme a al rendering di un ritaglio avanzato, deve utilizzare i **modificatori immagine** per aggiungere manualmente i predefiniti.

### Scheda Stili {#styles-tab-edit}

![Scheda Stili della finestra di dialogo per la modifica del componente Immagine e-mail](/help/assets/image-configure-styles.png)

Il componente Immagine e-mail supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nella [finestra di dialogo per la progettazione](#design-dialog) affinché la scheda sia disponibile.

## Finestra di dialogo per la progettazione {#design-dialog}

### Scheda Principale {#main-tab}

![Scheda Principale della finestra di dialogo per progettazione del componente Immagine](/help/email/assets/email-image-design-main.png)

* **Abilita funzioni DM**: Se questa opzione è selezionata, sono disponibili [le funzioni di Dynamic Media](#dynamic-media).
   * Questa opzione viene visualizzata solo quando Dynamic Media è abilitato nell’ambiente.
* **Abilita immagini ottimizzate per il web**: quando questa opzione è selezionata, il [servizio di consegna delle immagini ottimizzate per il web](/help/developing/web-optimized-image-delivery.md) fornisce immagini in formato WebP, riducendone in media le dimensioni del 25%.
   * Questa opzione è disponibile solo in AEMaaCS.
   * Se non è selezionata o se il servizio di consegna delle immagini ottimizzate per il web non è disponibile, viene utilizzato [Adaptive Image Servlet](/help/developing/adaptive-image-servlet.md).
* **L’immagine è decorativa**: consente di definire se l’opzione dell’immagine decorativa è abilitata automaticamente quando si aggiunge il componente Immagine a una pagina.
* **Ottieni testo alternativo da DAM**: consente di definire se l’opzione per recuperare il testo alternativo dal DAM è abilitata automaticamente quando si aggiunge il componente Immagine a una pagina.
* **Ottieni didascalia da DAM**: consente di definire se l’opzione per recuperare la didascalia dal DAM è abilitata automaticamente quando si aggiunge il componente Immagine a una pagina.
* **Visualizza didascalia come nota a comparsa**: consente di definire se l’opzione per visualizzare la didascalia dell’immagine come nota a comparsa è abilitata automaticamente quando si aggiunge il componente Immagine a una pagina.
* **Larghezza di ridimensionamento**: Questo valore viene utilizzato per ridimensionare la larghezza delle immagini di base che sono risorse DAM.
   * Le proporzioni delle immagini vengono mantenute.
   * Se il valore è maggiore della larghezza effettiva dell’immagine, questo valore non avrà alcun effetto.
   * Questo valore non ha alcun effetto sulle immagini di SVG.

Nella scheda Principale puoi definire un elenco di larghezze consentite, espresse in pixel, in modo che l’immagine e il componente possano automaticamente caricare la larghezza appropriata in base alle dimensioni della finestra del browser. Questa è una parte importante delle [funzioni reattive](#responsive-features) del componente Immagine e-mail.

* **Larghezze**: consente di definire un elenco di larghezze, espresse in pixel, in modo che l’immagine e il componente possano automaticamente caricare la larghezza appropriata in base alle dimensioni della finestra del browser.
   * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere un’altra dimensione.
      * Utilizza le maniglie per ridisporre l’ordine delle dimensioni.
      * Utilizza l’icona **Elimina** per rimuovere una larghezza.
   * Per impostazione predefinita, il caricamento delle immagini viene differito fino a quando non diventano visibili.
      * Seleziona l’opzione **Disattiva il caricamento lento** per caricare le immagini al caricamento della pagina.
* **Qualità JPEG**: fattore di qualità, espresso come percentuale tra 0 e 100, per le immagini JPEG trasformate, ad esempio ridimensionate o ritagliate.
* **Larghezza predefinita**: la larghezza predefinita delle immagini in pixel che verrà utilizzata nella finestra di dialogo per la progettazione

>[!TIP]
>
>Consulta il documento [Adaptive Image Servlet](/help/developing/adaptive-image-servlet.md) per suggerimenti su come ottimizzare la selezione delle rappresentazioni definendone con attenzione le dimensioni.

### Scheda Stili {#styles-tab}

Il componente Immagine e-mail supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
