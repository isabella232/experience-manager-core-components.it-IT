---
title: Componente teaser
description: Il componente teaser può visualizzare un’immagine, un titolo, un testo RTF e, facoltativamente, un collegamento ad altri contenuti.
translation-type: tm+mt
source-git-commit: e7aeff3a24cff14fbcd468561632ee1927c07b4e
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 2%

---


# Componente teaser {#teaser-component}

Il componente core Teaser può visualizzare un’immagine, un titolo, testo RTF e, facoltativamente, un collegamento ad altro contenuto.

## Utilizzo {#usage}

Il componente Teaser consente all’autore del contenuto di creare facilmente un teaser per ulteriore contenuto utilizzando un’immagine, un titolo o un RTF e collegando altri contenuti o altre azioni.

L&#39;autore del modello può utilizzare la finestra di dialogo [progettazione](#design-dialog) per definire se sono disponibili le opzioni per creare le azioni di chiamata e aggiungere collegamenti, nonché per disattivare diverse opzioni di visualizzazione. L’autore del contenuto può utilizzare la finestra di dialogo [configurazione](#configure-dialog) per impostare un’immagine, definire CTA, impostare titoli e descrizioni e configurare collegamenti al singolo teaser. Per modificare l&#39;immagine teaser è possibile accedere alla finestra di dialogo [modifica](image.md#edit-dialog) del [componente immagine](image.md).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Teaser è v1, introdotto con la release 2.1.0 dei componenti core nel luglio 2018, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Compatibile | Compatibile | Compatibile |

## Esempio di output del componente {#sample-component-output}

Per provare il componente Teaser e vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library_teaser).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Teaser [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_teaser_v1).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Configura finestra di dialogo {#configure-dialog}

L’autore del contenuto può utilizzare la finestra di dialogo di configurazione per definire le proprietà del singolo teaser. È inoltre disponibile una [finestra di dialogo di modifica](#edit-dialog) per modificare l&#39;immagine teaser, se selezionata.

### Immagine {#image}

![Scheda immagine della finestra di dialogo di modifica del componente teaser](/help/assets/teaser-edit-image.png)

* **Risorsa immagine**
   * Rilasciate una risorsa dal [browser delle risorse](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) o toccate l&#39;opzione **Browse** per caricarla da un file system locale.
   * Toccate o fate clic su **Cancella** per deselezionare l&#39;immagine attualmente selezionata.
   * Toccate o fate clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) nell&#39;editor risorse.

>[!NOTE]
>
>[Al momento ](image.md#dynamic-media) le funzioni Dynamic Media non sono disponibili nel componente Teaser.

### Testo {#text}

![Scheda di testo della finestra di dialogo di modifica del componente teaser](/help/assets/teaser-edit-text.png)

* **Predefinito** : il titolo viene visualizzato prima del titolo del teaser.
* **Titolo**  - Definisce un titolo da visualizzare come titolo del teaser.
   * **Ottieni titolo dalla pagina**  collegata: se questa opzione è selezionata, il titolo verrà popolato con il titolo della pagina collegata.
* **Descrizione**  - Definisce una descrizione da visualizzare come sottovoce del teaser.
   * **Ottieni descrizione dalla pagina**  collegata: se questa opzione è selezionata, la descrizione della pagina collegata verrà compilata con la relativa descrizione.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

### Collegamenti e azioni {#links-actions}

![Scheda collegamento della finestra di dialogo di modifica del componente teaser](/help/assets/teaser-edit-link.png)

* **Collegamento** : collegamento applicato al teaser. Utilizza il browser dei percorsi per selezionare la destinazione del collegamento.
* **Abilita Call-To-Actions** : se questa opzione è selezionata, abilita la definizione delle Call-To-Actions. Il primo collegamento Invito all’azione nell’elenco viene usato come collegamento per altri elementi teaser.

## Finestra di dialogo Modifica {#edit-dialog}

Il componente Teaser delega il rendering delle immagini al [componente immagine](image.md). Pertanto, la finestra di dialogo [modifica](image.md#edit-dialog del componente Immagine è disponibile per l’autore del contenuto e può manipolare l’immagine teaser.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire le opzioni teaser di cui dispone l’autore del contenuto quando utilizza questo componente.

### Scheda teaser {#teaser-tab}

![Finestra di dialogo di progettazione del componente teaser](/help/assets/teaser-design.png)

* **Inviti all&#39;azione**
   * **Disattiva Call-To-Actions**  - Nascondi l’ **azione** Call-To-Action per gli autori dei contenuti
* **Elementi**
   * **Nascondi pretitolo**  - Nasconde l’ **** opzione Predefinito per gli autori del contenuto
   * **Nascondi titolo** : nasconde l’opzione  **** Titolo per gli autori di contenuti
      * Quando è selezionata l&#39;opzione **Tipo titolo** è nascosta
   * **Nascondi descrizione** : opzione  **** Descrizione per gli autori del contenuto
* **Tipo**  titolo - Definisce il tag H da utilizzare per il titolo del teaser.
* **Collegamenti**
   * **Non collegare l’immagine** : se selezionata, l’immagine teaser non è collegata
   * **Non collegare il titolo** : se questa opzione è selezionata, il titolo del teaser non è collegato
* **Delegato**  immagini - Visualizzazione informativa che indica a quale componente il teaser delega la gestione delle immagini.

### Scheda Stili {#styles-tab}

Il componente Teaser supporta il AEM [Style System](/help/get-started/authoring.md#component-styling).
