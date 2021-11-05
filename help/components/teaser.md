---
title: Componente Teaser
description: Il componente Teaser può mostrare un’immagine, un titolo, un testo RTF e opzionalmente un collegamento ad altro contenuto.
role: Architect, Developer, Admin, User
exl-id: ec75e168-6f3b-4dff-8df6-06ca7dc18688
source-git-commit: d435e82d5950336c66997399829e3baf23f170c0
workflow-type: ht
source-wordcount: '771'
ht-degree: 100%

---

# Componente Teaser {#teaser-component}

Il componente core Teaser può mostrare un’immagine, un titolo, un testo RTF e opzionalmente un collegamento ad altro contenuto.

## Utilizzo {#usage}

Il componente Teaser consente all’autore di contenuto di creare facilmente un teaser per ampliare il contenuto utilizzando un’immagine, un titolo o un testo RTF e anche collegamenti ad altro contenuto o altre azioni.

L’autore del modello può utilizzare la [finestra di dialogo per progettazione](#design-dialog) per definire la disponibilità o meno di opzioni per la creazione di inviti all’azione e collegamenti nonché per disabilitare varie opzioni di visualizzazione. L’autore di contenuto può utilizzare la [finestra di dialogo per configurazione](#configure-dialog) per impostare un’immagine, definire inviti all’azione, impostare titoli e descrizioni e configurare collegamenti al singolo teaser. Per modificare l’immagine del teaser è possibile accedere alla [finestra di dialogo per modifica](image.md#edit-dialog) del [componente Immagine](image.md).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Teaser è la v1, introdotta con la versione 2.1.0 dei Componenti core a luglio 2018, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Compatibile | Compatibile | Compatibile |

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Teaser e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_teaser_it).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Teaser [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_teaser_v1_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per configurazione {#configure-dialog}

L’autore di contenuto può utilizzare la finestra di dialogo per configurazione per definire le proprietà del singolo teaser. È inoltre disponibile una [finestra di dialogo per modifica](#edit-dialog) che consente di modificare l’immagine del teaser, se ne è stata selezionata una.

### Immagine {#image}

![Scheda Immagine della finestra di dialogo per modifica del componente Teaser](/help/assets/teaser-edit-image.png)

* **Risorsa immagine**
   * Rilascia una risorsa dal [browser di risorse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=it) oppure tocca l’opzione **Sfoglia** per caricarla da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * Tocca o fai clic su **Modifica** per [gestire i rendering della risorsa](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=it) nell’editor risorse.

>[!NOTE]
>
>Le [funzioni di Dynamic Media](image.md#dynamic-media) non sono attualmente disponibili nel componente Teaser.

### Testo {#text}

![Scheda Testo della finestra di dialogo per modifica del componente Teaser](/help/assets/teaser-edit-text.png)

* **Pretitolo**: il pretitolo viene visualizzato prima del titolo del teaser.
* **Title**: definisce un titolo da visualizzare come intestazione del teaser.
   * **Ottieni titolo da pagina collegata**: se questa opzione è selezionata, il titolo diventa quello della pagina collegata.
* **Descrizione**: è una descrizione da visualizzare come sottotitolo del teaser.
   * **Ottieni descrizione da pagina collegata**: se questa opzione è selezionata, la descrizione diventa quella della pagina collegata.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

### Collegamento e azioni {#links-actions}

![Scheda Collegamento e azioni della finestra di dialogo per modifica del componente Teaser](/help/assets/teaser-edit-link.png)

* **Collegamento**: collegamento applicato al teaser. Utilizza il browser di percorsi per selezionare la destinazione del collegamento.
* **Abilita inviti all’azione**: se questa opzione è selezionata, abilita la definizione di inviti all’azione. Il primo collegamento di invito all’azione presente nell’elenco viene utilizzato come collegamento per altri teaser.

## Finestra di dialogo per modifica {#edit-dialog}

Il componente Teaser delega il rendering dell’immagine al [componente Immagine](image.md). Pertanto, la [finestra di dialogo per modifica] (image.md#edit-dialog) del componente Immagine è disponibile per consentire all’autore di contenuto di manipolare l’immagine del teaser.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire le opzioni del teaser disponibili per l’autore di contenuto quando utilizza questo componente.

### Scheda Teaser {#teaser-tab}

![Finestra di dialogo per progettazione del componente Teaser](/help/assets/teaser-design.png)

* **Inviti all’azione**
   * **Disabili Inviti all’azione**: nasconde **Inviti all’azione** di agli autori di contenuto
* **Elementi**
   * **Nascondi pretitolo**: nasconde l’opzione **Pretitolo** agli autori di contenuto
   * **Nascondi titolo**: nasconde l’opzione **Titolo** agli autori di contenuto
      * Quando è selezionata, il **tipo di titolo** è nascosto
   * **Nascondi descrizione**: consente di nascondere l’opzione **Descrizione** a gli autori di contenuto
* **Tipo di titolo**: definisce il tag H da utilizzare per il titolo del teaser.
* **Collegamenti**
   * **Non collegare l’immagine**: se selezionata, l’immagine del teaser non viene collegata
   * **Non collegare il titolo**: se selezionata, il titolo del teaser non viene collegato
* **Delegato immagine**: visualizzazione informativa che indica a quale componente il Teaser delega la gestione dell’immagine.

### Scheda Stili {#styles-tab}

Il componente Teaser supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

## Adobe Client Data Layer {#data-layer}

Il componente Teaser supporta [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
