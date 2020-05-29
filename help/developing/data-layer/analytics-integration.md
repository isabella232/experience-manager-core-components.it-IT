---
title: Utilizzo di Adobe Client Data Layer per integrare i componenti core e Adobe Analytics
description: Come configurare Adobe Analytics per la registrazione degli eventi dei componenti core
translation-type: tm+mt
source-git-commit: f930a0d6004a29369b189137dd9c52e637ea3a61
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 2%

---


# Utilizzo di Adobe Client Data Layer per integrare i componenti core e Adobe Analytics {#analytics-integration}

Questo documento descrive come impostare una configurazione end-to-end basata su AEM, Adobe Client Data Layer, Adobe Launch e Adobe Analytics per tenere traccia di:

* L&#39;ID pagina memorizzato nel livello dati Adobe Client quando viene caricata una pagina
* Percorso dell&#39;immagine memorizzato in Adobe Client Data Layer quando si fa clic su un&#39;immagine

Questo utilizza i componenti core come esempio, ma può essere utilizzato per i componenti personalizzati.

##  Passaggio 1 - Creazione della suite di rapporti in Adobe Analytics {#create-report-suite}

Per aggregare e analizzare i dati, è prima necessario creare una suite di rapporti.

1. Passa a `https://analytics.adobe.com`.
1. Effettuate l&#39;accesso con il vostro Adobe ID.
1. Click the **Analytics** icon.
1. Vai ad **Admin -> Suite** di rapporti.
1. Fate clic su **Crea nuovo -> Suite** di rapporti.
1. Compilare il modulo:
   1. **ID suite per report**: `yourSuiteID`
   1. **Titolo** sito: `Your suite description`
   1. **Fuso** orario: Se necessario
   1. **Vai alla data** in diretta: data odierna o, se del caso
   1. **Viste stimate per pagina al giorno**: 100 o
1. Fate clic su **Crea suite** di rapporti.

In caso di esito positivo riceverai il seguente messaggio in verde: `Report Suite <yourReportSuite> has been successfully created.`

## Passaggio 2 - Rendere la suite di rapporti visibile {#make-visible}

Per utilizzare la nuova suite di rapporti, deve essere visibile.

1. Passa a `https://adminconsole.adobe.com`.
1. Effettuate l&#39;accesso con il vostro Adobe ID.
1. Fate clic sulla scheda **Adobe Analytics - &lt;yourSite>**
1. Fai clic sul collegamento **Adobe Analytics - &lt;yourSite>**
1. Select the **Permissions** tab
1. Fate clic sul pulsante **Modifica** della riga **Suite** di rapporti
1. Fate clic sul pulsante **+** della suite di rapporti creata nel [passaggio 1](#create-report-suite) per aggiungerla alla categoria **Elementi** autorizzazione inclusi.
1. Fai clic su **Salva**.

## Passaggio 3 - Integrazione del sito AEM con Adobe Launch {#integrate-launch}

Launch deve essere integrato con il sito AEM per generare dati.

Segui i passaggi descritti nel documento [Utilizzo di Adobe Client Data Layer per integrare i componenti core e Adobe Launch](launch-integration.md) .

## Passaggio 4 - Installazione e configurazione dell’estensione Adobe Analytics in Adobe Launch {#install-extension}

Adobe Analytics Extension consente l&#39;integrazione di Analytics con Launch.

1. In Adobe Launch, seleziona la nuova proprietà aggiunta creata al [punto 3.](#integrate-launch)
1. Passate alla scheda **Estensioni** e selezionate **Catalogo**.
1. Cercate **Adobe Analytics**.
1. Fate clic su **Installa**.
1. Configurare l’estensione.
   1. Immettete l&#39;ID **della suite di rapporti di** Analytics creato nel [passaggio 1](#create-report-suite) per gli ambienti appropriati
   1. Imposta set **di** caratteri su UTF-8
1. Fai clic su Salva

## Passaggio 5 - Crea un elemento dati in Adobe Launch per l’ID pagina {#create-data-element}

Per poter tenere traccia dell’ID pagina, in Launch è necessario un elemento dati.

1. In Adobe Launch selezionate la proprietà creata al [punto 3.](#integrate-launch)
1. Selezionate la scheda **Elementi** dati e fate clic su **Aggiungi elemento** dati:
   1. **Nome**: `dl-page-id`
   1. **Estensione**: **Core**
   1. **Tipo** elemento dati: **Codice personalizzato**
1. Fare clic su **Apri editor**
1. Nell’editor, immettete il codice: `return adobeDataLayer.getState().page.id;`
1. Fai clic su **Salva**.
1. Fate clic su **Salva** per creare l’elemento dati.

## Passaggio 6 - Crea una regola in Adobe Launch per tenere traccia dell’ID pagina in Analytics {#track-page}

Le regole consentono il tracciamento degli attributi di navigazione come ID pagina in Analytics.

Ripetete i passaggi della parte 5b del documento [Utilizzo di Adobe Client Data Layer per integrare i componenti core e Adobe Launch](launch-integration.md#launch-rule) per aggiungere la regola seguente in Adobe Launch:

* **Nome**: `track-dl-page-id`
* EVENTI:
   * **Estensione**: **Core**
   * **Tipo** evento: **Page Bottom**
* AZIONE 1:
   * **Estensione**: **Adobe Analytics**
   * **Tipo** azione: **Imposta variabili**
   * **prop1**: `%dl-page-id%`
* AZIONE 2:
   * **Estensione**: **Adobe Analytics**
   * **Tipo** azione: **Invia beacon**
   * Check **s.t(): Inviare dati ad Adobe Analytics e trattarli come visualizzazione di pagina**

## Passaggio 7 - Crea una regola in Adobe Launch per registrare l’evento Click sull’immagine {#register-click}

Le regole consentono il tracciamento degli attributi di navigazione come gli eventi di clic in Analytics.

Ripetete i passaggi della parte 5b del documento [Utilizzo di Adobe Client Data Layer per integrare i componenti core e Adobe Launch](launch-integration.md#launch-rule) per aggiungere la regola seguente in Adobe Launch:

* **Nome**: `register-dl-image-click`
* EVENTI:
   * **Estensione**: **Core**
   * **Tipo** evento: **Page Bottom**
* AZIONE 1:
   * **Estensione**: **Core**
   * **Tipo** azione: **Codice personalizzato**
   * Editor: Immettere il codice seguente

      ```
      var myListener = function(event) {
        _satellite.track('dlImageClicked', event.info.path);
      };
      adobeDataLayer.addEventListener('image clicked', myListener());
      ```

## Passaggio 8 - Crea una regola in Adobe Launch per tenere traccia dell’evento Click sull’immagine in Analytics {#track-click}

Le regole consentono il tracciamento degli attributi di navigazione come gli eventi di clic in Analytics.

Ripetete i passaggi della parte 5b del documento [Utilizzo di Adobe Client Data Layer per integrare i componenti core e Adobe Launch](launch-integration.md#launch-rule) per aggiungere la regola seguente in Adobe Launch:

* **Nome**: `track-dl-image-click`
* EVENTI:
   * **Estensione**: **Core**
   * **Tipo** evento: **Chiamata diretta**
   * **Identificatore**: `dlImageClicked`
* AZIONE 1:
   * **Estensione**: **Adobe Analytics**
   * **Tipo** azione: **Imposta variabili**
   * **prop2**: Imposta come `%event.detail%`
* AZIONE 2:
   * **Estensione**: **Adobe Analytics**
   * **Tipo** azione: **Invia beacon**
   * Check **s.t(): Inviare dati ad Adobe Analytics e trattarli come visualizzazione di pagina**

## Passaggio 9 - Pubblicare il codice di avvio sul sito Web {#publish-launch}

Per abilitare il tracciamento di queste regole e proprietà in Launch, il codice deve essere pubblicato.

1. Nella scheda **Adobe Launch** , selezionate la scheda **Publishing** .
1. Fate clic su **Aggiungi nuova libreria**.
1. Come **nome** immettete: `data-layer-analytics-1`.
1. In **Ambiente** selezionate **Sviluppo (sviluppo)**.
1. Fate clic su **Aggiungi tutte le risorse** modificate.
1. Per ciascuna delle tre regole (`track-dl-page-id`, `register-dl-image-click` e `track-dl-image-click`):
1. Selezionare **Regole > Regola > Ultime** e fare clic su **Seleziona e crea una nuova revisione**.
1. Fai clic su **Salva e genera per sviluppo**.

## Passaggio 10: attiva la pagina per inviare informazioni ad Adobe Analytics {#trigger-page}

In questo passaggio si installa l&#39;estensione Chrome **Launch e DTM Switch**. Con questa estensione è necessario solo creare e distribuire il codice Launch nell&#39;ambiente di sviluppo. Non è necessario implementare gli ambienti Staging e Production.

1. Installate l&#39;estensione Chrome **Launch e DTM Switch** da Discovery.
1. Fate clic sull&#39;icona **Avvia switch** e impostate Debug su *ON*.
1. Ricarica la pagina `http://<host>:<port>/content/core-components-examples/library/image.html`.
1. Aprite la console del browser ed è possibile visualizzare una procedura simile a quella riportata di seguito.

![Output della console di Analytics](/help/assets/analytics-console-output.png)

>[!TIP]
>
>Puoi anche installare l’estensione **Experience Cloud Debugger** per Chrome per visualizzare informazioni specifiche su Adobe Launch e Analytics.

## Passaggio 11 - Visualizzare le informazioni rilevate in Adobe Analytics {#view-info}

Ora puoi visualizzare gli eventi attivati in Adobe Analytics.

1. Passa a `https://analytics.adobe.com`.
1. Effettuate l&#39;accesso con il vostro Adobe ID.
1. Click the **Analytics** icon.
1. Select the **Reports** tab.
1. Nel menu a discesa in alto a destra, selezionate la suite di rapporti creata nel [passaggio 1.](#create-report-suite)
1. Nella prima colonna, selezionate Traffico **personalizzato -> Traffico personalizzato 1-10 -> Custom Insight 1** per visualizzare gli ID pagina tracciati (percorsi) memorizzati nel Livello dati. Deve essere simile al seguente.

   ![Approfondimenti personalizzati 1](/help/assets/custom-insight-1.png)

1. Accedi a **Custom Insight 2** per visualizzare i percorsi immagine tracciati memorizzati nel Livello dati. Deve essere simile al seguente.

   ![Approfondimenti personalizzati 2](/help/assets/custom-insight-2.png)
