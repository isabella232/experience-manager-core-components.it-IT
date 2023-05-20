---
title: Componente Teaser
description: Il componente Teaser può mostrare un’immagine, un titolo, un testo RTF e opzionalmente un collegamento ad altro contenuto.
role: Architect, Developer, Admin, User
exl-id: ec75e168-6f3b-4dff-8df6-06ca7dc18688
source-git-commit: cfc86203051739cbcdc30be0fb10ccffa7d583a5
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 100%

---

# Componente Teaser {#teaser-component}

Il componente core Teaser può mostrare un’immagine, un titolo, un testo RTF e opzionalmente un collegamento ad altro contenuto.

## Utilizzo {#usage}

Il componente Teaser consente all’autore di contenuti di creare facilmente un teaser per promuovere i contenuti utilizzando un’immagine, un titolo o un testo formattato e anche collegamenti verso altri contenuti o altre azioni.

L’autore di modelli può utilizzare la [finestra di dialogo per la progettazione](#design-dialog) per definire la disponibilità o meno di opzioni per la creazione di inviti all’azione e collegamenti nonché per disabilitare varie opzioni di visualizzazione. L’autore di contenuti può utilizzare la [finestra di dialogo per la configurazione](#configure-dialog) per impostare un’immagine, definire inviti all’azione, impostare titoli e descrizioni e configurare collegamenti verso uno specifico teaser. Per modificare l’immagine del teaser è possibile accedere alla [finestra di dialogo per la modifica](image.md#edit-dialog) del [componente Immagine](image.md).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Teaser è la v2, introdotta con la versione 2.18.0 dei Componenti core di febbraio 2022, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v2 | - | Compatibile | Compatibile |
| [v1](v1/teaser.md) | Compatibile | Compatibile | Compatibile |

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Teaser e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_teaser_it).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Teaser [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_teaser_v1_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

L’autore di contenuti può utilizzare la finestra di dialogo per la configurazione per definire le proprietà del singolo teaser. È inoltre disponibile una [finestra di dialogo per la modifica](#edit-dialog) che consente di modificare l’immagine del teaser, se ne è stata selezionata una.

### Scheda Collegamenti {#links-tab}

![Scheda collegamento della finestra di dialogo per modifica del componente Teaser](/help/assets/teaser-edit-links.png)

Il titolo, la descrizione e l’immagine del teaser possono essere ereditati dalla pagina collegata oppure dalla pagina collegata del primo invito all’azione. In assenza di un collegamento e di un invito all’azione, verranno ereditati dalla pagina corrente.

* **Collegamento** - Questo file collega a una pagina di contenuti, un URL esterno o un ancoraggio pagina.
* **Apri collegamento in una nuova scheda** - Se attivato, il collegamento si aprirà in una nuova scheda del browser.
* **Invito all’azione** - Questa opzione consente il collegamento a più destinazioni.
   * La pagina collegata nella prima chiamata all’azione viene utilizzata per ereditare il titolo, la descrizione o l’immagine del teaser.

### Scheda Testo {#text-tab}

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

### Scheda Risorsa {#asset-tab}

![Scheda Immagine della finestra di dialogo per modifica del componente Teaser](/help/assets/teaser-edit-image.png)

* **Eredita immagine in primo piano dalla pagina** - Se non ne viene trovata alcuna, utilizza l’immagine definita nelle proprietà della pagina collegata o della pagina corrente.
* **Risorsa immagine** - Rilascia una risorsa dal [browser di risorse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=it) oppure tocca l’opzione **Sfoglia** per caricarla da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * Tocca o fai clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=it) nell’Editor risorse.
* **Testo alternativo per l’accessibilità** - Questo campo consente di definire una descrizione dell’immagine per gli utenti ipovedenti.
   * **Eredita testo alternativo dalla pagina** - Questa opzione utilizza la descrizione alternativa del valore della risorsa collegata dei metadati `dc:description` in DAM o nella pagina corrente se non è collegata alcuna risorsa.
* **Non fornire testo alternativo** - Questa opzione contrassegna l’immagine da ignorare da tecnologie per l’accessibilità, come gli assistenti vocali, nei casi in cui l’immagine sia puramente decorativa o in altro modo non trasmetta informazioni aggiuntive alla pagina.

### Scheda Stili {#styles-tab-edit}

![Scheda Stili della finestra di dialogo di modifica del componente Elenco teaser](/help/assets/teaser-edit-styles.png)

Il componente Teaser supporta il [sistema di stili di AEM](/help/get-started/authoring.md#component-styling).

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nella [finestra di dialogo di progettazione](#design-dialog) affinché il menu a discesa sia disponibile.

## Finestra di dialogo per la modifica {#edit-dialog}

Il componente Teaser delega il rendering dell’immagine al [componente Immagine](image.md). Pertanto, la [finestra di dialogo per modifica](image.md#edit-dialog) del componente Immagine è disponibile per consentire all’autore di contenuto di manipolare l’immagine del teaser.

## Finestra di dialogo per progettazione {#design-dialog}

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
* **Tipo di titolo predefinito** - Definisce il tag H da utilizzare per il titolo del teaser.
* **Delegato immagine**: visualizzazione informativa che indica a quale componente il Teaser delega la gestione dell’immagine.

### Scheda Stili {#styles-tab}

Il componente Teaser supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

## Adobe Client Data Layer {#data-layer}

Il componente Teaser supporta [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
