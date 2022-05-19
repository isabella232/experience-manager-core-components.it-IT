---
title: Componente teaser (v1)
description: Il componente Teaser può mostrare un’immagine, un titolo, un testo formattato e opzionalmente un collegamento verso altri contenuti.
role: Architect, Developer, Admin, User
exl-id: 48e56938-660a-43e7-9e62-8069283ae73f
source-git-commit: 84e09fa64b3a7ae40ff3ff1a04ea1c7504db29d2
workflow-type: ht
source-wordcount: '745'
ht-degree: 100%

---

# Componente Teaser (v1) {#teaser-component}

Il componente core Teaser può mostrare un’immagine, un titolo, un testo formattato e opzionalmente un collegamento verso altri contenuti.

## Utilizzo {#usage}

Il componente Teaser consente all’autore di contenuti di creare facilmente un teaser per promuovere i contenuti utilizzando un’immagine, un titolo o un testo formattato e anche collegamenti verso altri contenuti o altre azioni.

L’autore di modelli può utilizzare la [finestra di dialogo per la progettazione](#design-dialog) per definire la disponibilità o meno di opzioni per la creazione di inviti all’azione e collegamenti nonché per disabilitare varie opzioni di visualizzazione. L’autore di contenuti può utilizzare la [finestra di dialogo per la configurazione](#configure-dialog) per impostare un’immagine, definire inviti all’azione, impostare titoli e descrizioni e configurare collegamenti verso uno specifico teaser. Per modificare l’immagine del teaser è possibile accedere alla [finestra di dialogo per la modifica](image-v1.md#edit-dialog) del [componente Immagine](image-v1.md).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Teaser, introdotta con la versione 2.1.0 dei componenti core a luglio 2018.

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Teaser.
>
>Per informazioni dettagliate sulla versione corrente del componente Teaser, consulta il documento [Componente Teaser](/help/components/teaser.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Teaser e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_teaser_it).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Teaser [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_teaser_v1_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

L’autore di contenuti può utilizzare la finestra di dialogo per la configurazione per definire le proprietà del singolo teaser. È inoltre disponibile una [finestra di dialogo per la modifica](#edit-dialog) che consente di modificare l’immagine del teaser, se ne è stata selezionata una.

### Immagine {#image}

![Scheda Immagine della finestra di dialogo per la modifica del componente Teaser](/help/assets/teaser-edit-image.png)

* **Risorsa immagine**
   * Rilascia una risorsa dal [browser di risorse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=it) oppure tocca l’opzione **Sfoglia** per caricarla da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * Tocca o fai clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=it) nell’Editor risorse.

>[!NOTE]
>
>Le [funzioni di Dynamic Media](image-v1.md#dynamic-media) non sono attualmente disponibili nel componente Teaser.

### Testo {#text}

![Scheda Testo della finestra di dialogo per la modifica del componente Teaser](/help/assets/teaser-edit-text.png)

* **Pretitolo**: il pretitolo viene visualizzato prima del titolo del teaser.
* **Titolo**: definisce un testo da visualizzare come titolo del teaser.
   * **Ottieni titolo da pagina collegata**: se questa opzione è selezionata, viene utilizzato il titolo della pagina collegata.
* **Descrizione**: è una descrizione da visualizzare come sottotitolo del teaser.
   * **Ottieni descrizione da pagina collegata**: se questa opzione è selezionata, viene utilizzata la descrizione della pagina collegata.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e nel [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

### Collegamento e azioni {#links-actions}

![Scheda Collegamento e azioni della finestra di dialogo per la modifica del componente Teaser](/help/assets/teaser-edit-link.png)

* **Collegamento**: collegamento applicato al teaser. Utilizza il browser di percorsi per selezionare la destinazione del collegamento.
* **Abilita inviti all’azione**: se questa opzione è selezionata, abilita la definizione di inviti all’azione. Il primo collegamento di invito all’azione presente nell’elenco viene utilizzato come collegamento per altri elementi del teaser.

## Finestra di dialogo per la modifica {#edit-dialog}

Il componente Teaser delega il rendering dell’immagine al [componente Immagine](image-v1.md). Pertanto, la [finestra di dialogo per la modifica](image-v1.md#edit-dialog) del componente Immagine è disponibile per consentire all’autore del contenuto di manipolare l’immagine del teaser.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente all’autore di modelli di definire le opzioni del teaser disponibili per l’autore di contenuti quando utilizza questo componente.

### Scheda Teaser {#teaser-tab}

![Finestra di dialogo per la progettazione del componente Teaser](/help/assets/teaser-design.png)

* **Inviti all’azione**
   * **Disabilita inviti all&#39;azione**: nasconde l’opzione **Inviti all’azione** agli autori di contenuti
* **Elementi**
   * **Nascondi pretitolo**: nasconde l’opzione **Pretitolo** agli autori di contenuti
   * **Nascondi titolo**: nasconde l’opzione **Titolo** agli autori di contenuti
      * Quando è selezionata, il **tipo di titolo** è nascosto
   * **Nascondi descrizione**: nasconde l’opzione **Descrizione** agli autori di contenuti
* **Tipo di titolo**: definisce il tag H da utilizzare per il titolo del teaser.
* **Collegamenti**
   * **Non collegare l’immagine**: se selezionata, l’immagine del teaser non viene collegata
   * **Non collegare il titolo**: se selezionata, il titolo del teaser non viene collegato
* **Delegato immagine**: visualizzazione informativa che indica a quale componente il Teaser delega la gestione dell’immagine.

### Scheda Stili {#styles-tab}

Il componente Teaser supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

## Adobe Client Data Layer {#data-layer}

Il componente Teaser supporta [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
