---
title: Componente teaser
description: Il componente teaser può mostrare un’immagine, un titolo, un testo RTF ed eventualmente un collegamento ad altri contenuti.
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 2%

---


# Componente teaser {#teaser-component}

Il componente di base Teaser può mostrare un’immagine, un titolo, un testo RTF ed eventualmente un collegamento ad altro contenuto.

## Utilizzo {#usage}

Il componente Teaser consente all’autore del contenuto di creare facilmente un teaser per ulteriore contenuto utilizzando un’immagine, un titolo o un rich text e di collegarsi a ulteriori contenuti o altre azioni.

L’autore del modello può utilizzare la finestra di dialogo di progettazione [progettazione](#design-dialog) per definire se sono disponibili le opzioni per creare le azioni di chiamata e aggiungere collegamenti, nonché per disabilitare diverse opzioni di visualizzazione. L’autore del contenuto può utilizzare la finestra di dialogo [configura](#configure-dialog) per impostare un’immagine, definire CTA, impostare titoli e descrizioni e configurare collegamenti al singolo teaser. Per modificare l’immagine teaser è possibile accedere alla finestra di dialogo di modifica [modifica](image.md#edit-dialog) del [componente immagine](image.md).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Teaser è v1, introdotta con la versione 2.1.0 dei componenti core a luglio 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Compatibile | Compatibile | Compatibile |

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente Teaser e dell’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_teaser) .

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Teaser [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_teaser_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Configura finestra di dialogo {#configure-dialog}

L’autore del contenuto può utilizzare la finestra di dialogo di configurazione per definire le proprietà del singolo teaser. È inoltre disponibile una [finestra di dialogo di modifica](#edit-dialog) per modificare l’immagine teaser, se selezionata.

### Immagine {#image}

![Scheda immagine della finestra di dialogo di modifica del componente teaser](/help/assets/teaser-edit-image.png)

* **Risorsa immagine**
   * Rilascia una risorsa dal [browser Risorse](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) o tocca l’opzione **Sfoglia** per caricarla da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * Tocca o fai clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) nell’editor risorse.

>[!NOTE]
>
>[Le ](image.md#dynamic-media) funzioni di Dynamic Media non sono attualmente disponibili nel componente Teaser.

### Testo {#text}

![Scheda della finestra di dialogo di modifica del componente teaser](/help/assets/teaser-edit-text.png)

* **Prefisso** : il titolo viene visualizzato prima del titolo del teaser.
* **Titolo**  - Definisce un titolo da visualizzare come titolo del teaser.
   * **Ottieni titolo dalla pagina**  collegata: se questa opzione è selezionata, il titolo viene popolato con il titolo della pagina collegata.
* **Descrizione**  - Definisce una descrizione da visualizzare come sottovoce del teaser.
   * **Ottieni descrizione dalla pagina**  collegata: se questa opzione è selezionata, la descrizione della pagina collegata viene compilata con la relativa descrizione.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

### Collegamenti e azioni {#links-actions}

![Scheda del collegamento della finestra di dialogo di modifica del componente teaser](/help/assets/teaser-edit-link.png)

* **Collegamento** : collegamento applicato al teaser. Utilizza il browser percorsi per selezionare la destinazione del collegamento.
* **Abilita le azioni**  di chiamata-a- Se questa opzione è selezionata, abilita la definizione delle azioni di chiamata-a-azione. Il primo collegamento Invito all’azione presente nell’elenco viene utilizzato come collegamento per altri elementi teaser.

## Finestra di dialogo Modifica {#edit-dialog}

Il componente Teaser delega il rendering delle immagini al [componente immagine](image.md). Pertanto, la [finestra di dialogo di modifica](image.md#edit-dialog of the Image Component è disponibile all’autore del contenuto per manipolare l’immagine teaser.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire le opzioni teaser disponibili per l’autore del contenuto quando si utilizza questo componente.

### Scheda teaser {#teaser-tab}

![Finestra di dialogo di progettazione del componente teaser](/help/assets/teaser-design.png)

* **Inviti all&#39;azione**
   * **Disattiva le azioni di chiamata**  - Nascondi l’ **azione** di chiamata per gli autori di contenuti
* **Elementi**
   * **Nascondi pretitolo** : nasconde l’opzione  **** Retitleoption per gli autori di contenuti
   * **Nascondi titolo** : nasconde l’opzione  **** Titolo per gli autori di contenuti
      * Quando è selezionato, il **tipo di titolo** è nascosto
   * **Nascondi descrizione** : consente di nascondere l’opzione  **** Descrizione per gli autori di contenuti
* **Tipo di titolo**  - Definisce il tag H da utilizzare per il titolo del teaser.
* **Collegamenti**
   * **Non collegare l’immagine** : se selezionata, l’immagine teaser non è collegata
   * **Non collegare il titolo** : se selezionato, il titolo del teaser non è collegato
* **Delega immagini** : visualizzazione informativa che indica a quale componente il teaser delega la gestione delle immagini.

### Scheda Stili {#styles-tab}

Il componente Teaser supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

## Livello dati client di Adobe {#data-layer}

Il componente Teaser supporta [Livello dati client di Adobe.](/help/developing/data-layer/overview.md)
