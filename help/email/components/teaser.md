---
title: Componente teaser e-mail
description: Il componente E-mail Teaser può mostrare un’immagine, un titolo, un testo RTF ed eventualmente un collegamento ad altro contenuto.
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '1056'
ht-degree: 53%

---


# Componente teaser e-mail {#email-teaser-component}

Il componente E-mail Teaser può mostrare un’immagine, un titolo, un testo RTF ed eventualmente un collegamento ad altro contenuto.

## Utilizzo {#usage}

Il componente teaser e-mail consente all’autore del contenuto di creare facilmente un teaser utilizzando un’immagine, un titolo o un testo RTF e di collegarsi a ulteriori contenuti o altre azioni.

* L’autore di modelli può utilizzare la [finestra di dialogo per la progettazione](#design-dialog) per definire la disponibilità o meno di opzioni per la creazione di inviti all’azione e collegamenti nonché per disabilitare varie opzioni di visualizzazione.
* L’autore di contenuti può utilizzare la [finestra di dialogo per la configurazione](#configure-dialog) per impostare un’immagine, definire inviti all’azione, impostare titoli e descrizioni e configurare collegamenti verso uno specifico teaser.
* La [finestra di dialogo modifica](image.md#edit-dialog) del [Componente immagine e-mail](image.md) è accessibile per modificare l’immagine teaser.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente E-mail Teaser è v1, introdotta con la versione x dei componenti core e-mail nell’ottobre 2022, ed è descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile | Compatibile |

## Esempio di output del componente {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente e-mail Teaser e dell’output di HTML e JSON, visita il [Libreria dei componenti.](https://adobe.com/go/aem_cmp_library_email_teaser)

### Dettagli tecnici {#technical-details}

Documentazione tecnica più recente sul componente E-mail Teaser [si trova su GitHub.](https://adobe.com/go/aem_cmp_tech_email_teaser_v1)

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core.](/help/developing/overview.md)

## Finestra di dialogo per la configurazione {#configure-dialog}

L’autore di contenuti può utilizzare la finestra di dialogo per la configurazione per definire le proprietà del singolo teaser. È inoltre disponibile una [finestra di dialogo per la modifica](#edit-dialog) che consente di modificare l’immagine del teaser, se ne è stata selezionata una.

### Scheda Collegamenti {#links-tab}

![Scheda dei collegamenti della finestra di dialogo di modifica del componente Teaser e-mail](/help/email/assets/email-teaser-edit-links.png)

Il titolo, la descrizione e l’immagine del teaser possono essere ereditati dal contenuto collegato o dal contenuto collegato nella prima chiamata all’azione. Se non viene specificato né un collegamento né una chiamata all’azione, il titolo, la descrizione e l’immagine verranno ereditati dal contenuto corrente.

* **Collegamento** - Questo file è collegato a contenuto, URL esterno o ancoraggio.
   * Fai clic sull’icona Campagna per aprire la [Seleziona variabile Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.
* **Invito all’azione** - Questa opzione consente il collegamento a più destinazioni.
   * La pagina collegata nella prima chiamata all’azione viene utilizzata per ereditare il titolo, la descrizione o l’immagine del teaser.
   * Fai clic sull’icona Campagna per aprire la [Seleziona variabile Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.

### Scheda Testo {#text-tab}

![Scheda della finestra di dialogo di modifica del componente Teaser e-mail](/help/email/assets/email-teaser-edit-text.png)

* **Pretitolo**: il pretitolo viene visualizzato prima del titolo del teaser.
* **Titolo**: definisce un testo da visualizzare come titolo del teaser.
   * Fai clic sull’icona Campagna per aprire la [Seleziona variabile Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.
   * **Ottieni titolo da pagina collegata**: se questa opzione è selezionata, viene utilizzato il titolo della pagina collegata.
* **Descrizione**: è una descrizione da visualizzare come sottotitolo del teaser.
   * Fai clic sul pulsante **Seleziona variabile Adobe Campaign** per aprire [Seleziona variabile Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.
   * **Ottieni descrizione da pagina collegata**: se questa opzione è selezionata, viene utilizzata la descrizione della pagina collegata.
* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente in HTML.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando il contenuto risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sui CSS.

### Scheda Risorsa {#asset-tab}

![Scheda immagine della finestra di dialogo di modifica del componente Teaser e-mail](/help/email/assets/email-teaser-edit-image.png)

* **Eredita immagine in primo piano dalla pagina** - Se non ne viene trovata alcuna, utilizza l’immagine definita nelle proprietà della pagina collegata o della pagina corrente.
* **Risorsa immagine** - Rilascia una risorsa dal [browser di risorse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=it) oppure tocca l’opzione **Sfoglia** per caricarla da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l’immagine attualmente selezionata.
   * Tocca o fai clic su **Modifica** a [gestire le rappresentazioni della risorsa](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=it) nell’Editor risorse.
* **Testo alternativo per l’accessibilità**: Questo campo consente di definire una descrizione dell’immagine per gli utenti ipovedenti.
   * **Eredita testo alternativo dalla pagina** - Questa opzione utilizza la descrizione alternativa del valore della risorsa collegata dei metadati `dc:description` in DAM o nella pagina corrente se non è collegata alcuna risorsa.
* **Non fornire testo alternativo** - Questa opzione contrassegna l’immagine da ignorare da tecnologie per l’accessibilità, come gli assistenti vocali, nei casi in cui l’immagine sia puramente decorativa o in altro modo non trasmetta informazioni aggiuntive alla pagina.

>[!NOTE]
>
>Le [funzioni di Dynamic Media](image.md#dynamic-media) non sono attualmente disponibili nel componente Teaser.

### Scheda Stili {#styles-tab-edit}

Il componente E-mail Teaser supporta l’AEM [Sistema di stili.](/help/get-started/authoring.md#component-styling)

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nel [finestra di dialogo di progettazione](#design-dialog) affinché la scheda sia disponibile.

## Finestra di dialogo per la modifica {#edit-dialog}

Il componente E-mail Teaser delega il rendering delle immagini al [Componente immagine](image.md). Pertanto, la [finestra di dialogo per la modifica](image.md#edit-dialog) del componente Immagine è disponibile per consentire all’autore del contenuto di manipolare l’immagine del teaser.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente all’autore di modelli di definire le opzioni del teaser disponibili per l’autore di contenuti quando utilizza questo componente.

### Scheda Teaser {#teaser-tab}

![Finestra di dialogo di progettazione del componente e-mail Teaser](/help/email/assets/email-teaser-design.png)

* **Elementi di intestazione consentiti** - Utilizza l’elenco a discesa per definire l’intestazione degli elementi HTML che possono essere selezionati da un autore per il tipo di titolo del teaser.
* **Elemento titolo predefinito del titolo** - Elemento HTML titolo predefinito utilizzato per il tipo di titolo del teaser
* **Inviti all’azione**
   * **Disabilita inviti all&#39;azione**: nasconde l’opzione **Inviti all’azione** agli autori di contenuti
* **Elementi**
   * **Nascondi pretitolo**: nasconde l’opzione **Pretitolo** agli autori di contenuti
   * **Nascondi titolo**: nasconde l’opzione **Titolo** agli autori di contenuti
      * Quando è selezionata, il **tipo di titolo** è nascosto
   * **Mostra tipo di titolo**
   * **Nascondi descrizione**: nasconde l’opzione **Descrizione** agli autori di contenuti
* **Delega immagini** - Visualizzazione informativa che indica a quale componente il teaser e-mail delega la gestione delle immagini.

### Scheda Stili {#styles-tab}

Il componente E-mail Teaser supporta l’AEM [Sistema di stili.](/help/get-started/authoring.md#component-styling)
