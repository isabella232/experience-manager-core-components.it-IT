---
title: Componente Teaser e-mail
description: Il componente Teaser e-mail può mostrare un’immagine, un titolo, un testo formattato e, opzionalmente, un collegamento ad altro contenuto.
role: Architect, Developer, Admin, User
exl-id: d6123b22-7cba-406c-986d-b6f00322d135
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 100%

---


# Componente Teaser e-mail {#email-teaser-component}

Il componente Teaser e-mail può mostrare un’immagine, un titolo, un testo formattato e, opzionalmente, un collegamento ad altro contenuto.

## Utilizzo {#usage}

Il componente Teaser e-mail consente all’autore di contenuti di creare facilmente un teaser per ampliare il contenuto utilizzando un’immagine, un titolo o un testo formattato e anche collegamenti ad altro contenuto o altre azioni.

* L’autore di modelli può utilizzare la [finestra di dialogo per la progettazione](#design-dialog) per definire la disponibilità o meno di opzioni per la creazione di inviti all’azione e l’aggiunta di collegamenti nonché per disabilitare varie opzioni di visualizzazione.
* L’autore di contenuti può utilizzare la [finestra di dialogo per la configurazione](#configure-dialog) per impostare un’immagine, definire inviti all’azione, impostare titoli e descrizioni e configurare collegamenti verso un singolo teaser.
* Per modificare l’immagine del teaser è possibile accedere alla [finestra di dialogo per la modifica](image.md#edit-dialog) del [componente immagine e-mail](image.md).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Teaser e-mail è la v1, introdotta con la versione x dei Componenti core e-mail a ottobre 2022, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile  | - |

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Teaser e-mail [è disponibile su GitHub.](https://adobe.com/go/aem_cmp_tech_email_teaser_v1)

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core.](/help/developing/overview.md)

## Finestra di dialogo per la configurazione {#configure-dialog}

L’autore di contenuti può utilizzare la finestra di dialogo per la configurazione per definire le proprietà del singolo teaser. È inoltre disponibile una [finestra di dialogo per la modifica](#edit-dialog) che consente di modificare l’immagine del teaser, se ne è stata selezionata una.

### Scheda Collegamenti {#links-tab}

![Scheda collegamento della finestra di dialogo per la modifica del componente Teaser e-mail](/help/email/assets/email-teaser-edit-links.png)

Il titolo, la descrizione e l’immagine del Teaser possono essere ereditati dal contenuto collegato o dal contenuto collegato nel primo invito all’azione. Se non viene specificato né un collegamento né un invito all’azione, il titolo, la descrizione e l’immagine verranno ereditati dal contenuto corrente.

* **Collegamento**: questo file collega ai contenuti, un URL esterno o un ancoraggio.
   * Fai clic sull’icona Campagna per aprire la finestra di dialogo [Seleziona variabile di Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.
* **Inviti all’azione** - Questa opzione consente il collegamento a più destinazioni.
   * La pagina collegata nella prima chiamata all’azione viene utilizzata per ereditare il titolo, la descrizione o l’immagine del teaser.
   * Fai clic sull’icona Campagna per aprire la finestra di dialogo [Seleziona variabile di Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.

### Scheda Testo {#text-tab}

![Scheda Testo della finestra di dialogo per la modifica del componente Teaser e-mail](/help/email/assets/email-teaser-edit-text.png)

* **Pretitolo**: il pretitolo viene visualizzato prima del titolo del teaser.
* **Titolo**: definisce un testo da visualizzare come titolo del teaser.
   * Fai clic sull’icona Campagna per aprire la finestra di dialogo [Seleziona variabile di Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.
   * **Ottieni titolo da pagina collegata**: se questa opzione è selezionata, viene utilizzato il titolo della pagina collegata.
* **Descrizione**: è una descrizione da visualizzare come sottotitolo del teaser.
   * Fai clic sull’icona **Seleziona variabile di Adobe Campaign** per aprire la finestra di dialogo [Seleziona variabile di Adobe Campaign](/help/email/campaign-variables.md) e inserire contenuto dinamico da Adobe Campaign.
   * **Ottieni descrizione da pagina collegata**: se questa opzione è selezionata, la descrizione verrà popolata utilizzando la descrizione della pagina collegata.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nell’HTML.
   * Se non specificato, viene generato automaticamente un ID univoco reperibile esaminando il contenuto risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sulle CSS.

### Scheda Risorsa {#asset-tab}

![Scheda Immagine della finestra di dialogo per la modifica del componente Teaser e-mail](/help/email/assets/email-teaser-edit-image.png)

* **Eredita immagine in primo piano dalla pagina** - Se non ne viene trovata alcuna, utilizza l’immagine definita nelle proprietà della pagina collegata o della pagina corrente.
* **Risorsa immagine** - Rilascia una risorsa dal [browser di risorse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=it) oppure tocca l’opzione **Sfoglia** per caricarla da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * Tocca o fai clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=it) nell’Editor risorse.
* **Testo alternativo per accessibilità**: Questo campo consente di definire una descrizione dell’immagine per gli utenti ipovedenti.
   * **Eredita testo alternativo dalla pagina** - Questa opzione utilizza la descrizione alternativa del valore della risorsa collegata dei metadati `dc:description` in DAM o nella pagina corrente se non è collegata alcuna risorsa.
* **Non fornire testo alternativo** - Questa opzione contrassegna l’immagine da ignorare da tecnologie per l’accessibilità, come gli assistenti vocali, nei casi in cui l’immagine sia puramente decorativa o in altro modo non trasmetta informazioni aggiuntive alla pagina.

>[!NOTE]
>
>Le [funzioni di Dynamic Media](image.md#dynamic-media) non sono attualmente disponibili nel componente Teaser.

### Scheda Stili {#styles-tab-edit}

Il componente Teaser e-mail supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nella [finestra di dialogo per la progettazione](#design-dialog) affinché la scheda sia disponibile.

## Finestra di dialogo per la modifica {#edit-dialog}

Il componente Teaser e-mail delega il rendering dell’immagine al [componente Immagine](image.md). Pertanto, la [finestra di dialogo per la modifica](image.md#edit-dialog) del componente Immagine è disponibile per consentire all’autore del contenuto di manipolare l’immagine del teaser.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente all’autore di modelli di definire le opzioni del teaser disponibili per l’autore di contenuti quando utilizza questo componente.

### Scheda Teaser {#teaser-tab}

![Finestra di dialogo per la progettazione del componente Teaser e-mail](/help/email/assets/email-teaser-design.png)

* **Elementi intestazione consentiti**: utilizza l’elenco a discesa per definire l’intestazione degli elementi HTML che possono essere selezionati da un autore per il tipo di titolo del teaser.
* **Elemento per titoli predefinito del titolo**: elemento HTML del titolo predefinito utilizzato per il tipo di titolo del teaser
* **Inviti all’azione**
   * **Disabilita inviti all&#39;azione**: nasconde l’opzione **Inviti all’azione** agli autori di contenuti
* **Elementi**
   * **Nascondi pretitolo**: nasconde l’opzione **Pretitolo** agli autori di contenuti
   * **Nascondi titolo**: nasconde l’opzione **Titolo** agli autori di contenuti
      * Quando è selezionata, il **tipo di titolo** è nascosto
   * **Mostra tipo di titolo**
   * **Nascondi descrizione**: nasconde l’opzione **Descrizione** agli autori di contenuti
* **Delegato immagine**: visualizzazione informativa che indica a quale componente il Teaser e-mail delega la gestione dell’immagine.

### Scheda Stili {#styles-tab}

Il componente Teaser e-mail supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
