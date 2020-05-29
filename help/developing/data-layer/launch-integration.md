---
title: Utilizzo di Adobe Client Data Layer per integrare i componenti core e Adobe Launch
description: Come configurare Adobe Launch per la registrazione degli eventi dei componenti core mediante Adobe Launch
translation-type: tm+mt
source-git-commit: f930a0d6004a29369b189137dd9c52e637ea3a61
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 2%

---


# Utilizzo di Adobe Client Data Layer per integrare i componenti core e Adobe Launch {#launch-integration}

I componenti core possono essere integrati con Adobe Launch utilizzando Adobe Client Data Layer. Questo documento descrive come configurare Adobe Launch per tenere traccia degli eventi click per i componenti immagine come esempio.

Quando è configurata, Launch genera il seguente output nella console del browser quando si fa clic su un componente Immagine principale.

![Esempio di output della console](/help/assets/launch-console-output.png)

## Integrazione di Launch con AEM {#launch-aem}

Primo avvio Adobe deve essere integrato con il sito AEM.

### Passaggio 1 - Creazione di un&#39;integrazione in Adobe I/O {#create-io-integration}

Effettuate prima l&#39;accesso ad Adobe I/O per avviare la configurazione di un&#39;integrazione.

1. Passa a `https://console.adobe.io`.
1. Effettuate l&#39;accesso con il vostro Adobe ID.
1. Nella sezione Avvio rapido, fate clic su **Crea integrazione**.
1. Select **Access an API** and click **Continue**.
1. Seleziona l’API **di avvio della piattaforma** Experience **sotto Adobe Experience Platform e fai clic su** Continue (Continua).

### Passaggio 2 - Creazione di una configurazione IMS in AEM {#ims-configuration}

In AEM è necessario definire l’integrazione che hai iniziato a configurare in Adobe I/O.

1. Vai alla home page di AEM, fai clic su **Strumenti > Protezione > Configurazioni** Adobe IMS.
1. Fai clic su **Crea**.
1. Come soluzione **** Cloud, seleziona **Adobe Launch**.
1. Selezionare **Crea nuovo certificato**.
1. Inserite un alias per il certificato, ad esempio **aem-launch-certificate**.
1. Fate clic su **Crea certificato** e, nella finestra a comparsa, fate clic su **OK** per creare il certificato.
1. Fate clic su **Scarica chiave** pubblica e, nel menu a comparsa, fate clic su **Scarica**.

### Passaggio 3 - Fine della configurazione di I/O Adobe {#finish-io}

Con il certificato e la chiave creati nella configurazione AEM IMS, potete completare la configurazione di I/O Adobe.

1. Tornate alla console Adobe I/O come nel [passaggio 1.](#create-io-integration)
1. Nella finestra **Crea nuova integrazione** , immetti un nome e una descrizione come il livello **dati di avvio** AEM.
1. In Certificati **di chiavi** pubbliche caricate il certificato creato al [passaggio 2.](#ims-configuration)
1. Selezionate il profilo **Launch - Prod**.
1. Click **Create integration**.
1. Fate clic su **Continua per visualizzare i dettagli** dell&#39;integrazione. In seguito, per completare la configurazione IMS nell’istanza di AEM, saranno necessari i seguenti dettagli.

### Passaggio 4 - Fine della configurazione IMS {#finish-ims}

Con i dettagli di integrazione I/O di Adobe, puoi completare la configurazione di AEM IMS.

1. Nella scheda AEM, nella scheda Configurazione **account tecnico** Adobe IMS del [passaggio 2,](#ims-configuration) fate clic su **Avanti**.
1. Immetti un titolo come la configurazione **IMS per Adobe Launch**.
1. Nella scheda I/O di Adobe, copiate la chiave **API (ID client)**.
1. Nella scheda AEM, incollate la chiave precedentemente copiata nel campo **Chiave** API.
1. In Adobe I/O, fate clic su **Recupera Segreto** cliente e copiatelo.
1. Nella scheda AEM incollatela nel campo Segreto **cliente** .
1. Nella scheda Adobe I/O, selezionate la scheda **JWT** e copiate l’URL come `https://ims-na1.adobelogin.com`.
1. Nella scheda AEM, incollate l’URL nel campo **Server** di autorizzazione.
1. Nella scheda I/O di Adobe, copiate il payload JWT (il codice tra le parentesi).
1. Nella scheda AEM, incollatela nel campo **Payload** .
1. Fate clic su **Crea** per creare la configurazione IMS in AEM.

### Passaggio 5a - Creazione di una proprietà in Adobe Launch {#create-property}

Una proprietà definisce le funzioni che Launch può inserire nel sito.

1. Vai ad Adobe Launch all&#39;indirizzo `https://launch.adobe.com`.
1. Effettuate l&#39;accesso con il vostro Adobe ID.
1. Fate clic su **Nuova proprietà**.
1. Immettete un nome, ad esempio **Avvia livello** dati AEM.
1. Immettete il vostro dominio.
1. Fai clic su **Salva**.

### Passaggio 5b - Crea una regola in Launch {#launch-rule}

Utilizzando la proprietà creata, è possibile definire una regola che specifica cosa deve accadere quando si verifica un&#39;azione.

1. Fai clic sulla nuova proprietà aggiunta dal [passaggio 5](#create-property) **Avvia livello** dati AEM.
1. Selezionate la scheda **Regole** e fate clic su **Crea nuova regola**.
1. Immettete un nome, ad esempio fate clic **sull’** immagine.
1. Fate clic sul pulsante **+** sotto **Eventi**.
1. Selezionate **Core** as **Extension**, **fate clic** come tipo **di** evento e immettete **.cmp-image** **** come selettore CSS.
1. Fare clic su **Mantieni modifiche**.
1. Fare clic sul pulsante **+** sotto **Azioni**.
1. Selezionate **Core** as **Extension**, **Custom Code** as **Action Type** (Core **come estensione) e fate clic su** Open Editor (Apri editor).
1. Nell’editor, immettete il seguente codice: `console.log("DOM click event tracked by Launch for image: ", event.target.src);`
1. Fai clic su **Salva**.
1. Fare clic su **Mantieni modifiche**.
1. Fate clic su **Salva** per creare la nuova regola.

### Passaggio 6 - Pubblicare la regola di avvio {#publish-rule}

Per rendere disponibile la nuova regola per il sito AEM, è necessario pubblicarla.

1. Nella scheda **Adobe Launch** , selezionate la scheda **Publishing** .
1. Fate clic su **Aggiungi nuova libreria**.
1. Immettete un **nome** come appropriato, ad esempio **demo-1**.
1. In **Ambiente** , selezionate le opzioni appropriate, ad esempio **Sviluppo (sviluppo)**.
1. Fate clic su **Aggiungi una risorsa**.
1. Selezionare **Regole -> Image-click -> Ultime** e fare clic su **Seleziona e crea una nuova revisione**.
1. Fai clic su **Salva e genera per sviluppo**.
1. Nella finestra a comparsa, fate clic su **Applica aggiornamenti e continua**.
1. Quando la libreria è generata, fate clic sull&#39;icona con i puntini di sospensione e selezionate **Invia per approvazione**.
1. Nella finestra a comparsa, fate clic su **Invia**.
1. Fate clic sull&#39;icona con i puntini di sospensione e selezionate **Genera per l&#39;area di visualizzazione**.
1. Al termine della creazione, fate clic sull&#39;icona con i puntini di sospensione e selezionate **Approva per la pubblicazione**.
1. Fare clic su **Approva** nella finestra a comparsa.
1. Fate clic sull&#39;icona con i puntini di sospensione e selezionate **Genera e pubblica in produzione**.
1. Nella finestra a comparsa fate clic su **Pubblica**.

### Passaggio 7 - Abilita configurazioni cloud per il tuo sito {#enable-configurations}

Per utilizzare l’integrazione, è necessario assegnarla in AEM come configurazione cloud.

1. Nella console AEM, fate clic su **Strumenti > Generale > Browser** di configurazione.
1. Controllare gli esempi **dei componenti** core e fare clic su **Proprietà**.
1. Controlla le configurazioni **** cloud e fai clic su **Salva e chiudi**.

### Passaggio 8 - Creare un’integrazione di Launch con il sito in AEM {#create-launch-integration}

Per poter utilizzare AEM con Launch, è necessaria un’integrazione Launch

1. Nella console AEM, fai clic su **Strumenti > Servizi cloud > Configurazioni** di Adobe Launch.
1. Selezionate Esempi **di componenti** core e fate clic su **Crea**.
1. Immettete un **titolo** , ad esempio la configurazione **** Launch.
1. Selezionate la configurazione IMS creata al [punto 4.](#finish-ims)
1. Come **Azienda** seleziona il caso.
1. Come **proprietà** , seleziona la nuova proprietà Launch creata al [punto 5.](#create-property)
1. Spostate il cursore **Includi codice produzione sull&#39;autore** a destra e fate clic su **Avanti**.
1. Fai clic su **Avanti**.
1. Fai clic su **Avanti**.
1. Fai clic su **Crea**.

### Passaggio 9 - Collegate il sito AEM all&#39;integrazione Launch {#connect-aem}

Per poter utilizzare l’integrazione Launch, AEM deve essere assegnato come configurazione cloud.

1. Nella console AEM, fate clic su **Siti** e selezionate il sito **** Componenti di base.
1. Fate clic su **Proprietà**.
1. Select the **Advanced** tab.
1. Come Configurazione **** cloud, seleziona gli esempi **di componenti** core e fai clic su **Seleziona**.
1. Click **Save &amp; Close**.

### Passaggio 10 - Verificare che la logica di avvio sia applicata alla pagina {#verify-launch}

Verificate che i passaggi finora eseguiti siano stati efficaci.

1. Aprite la pagina Immagine della Libreria componenti core in modalità di anteprima: `http://<lhost&gt;:<port&gt;/editor.html/content/core-components-examples/library/page-authoring/image.html`
1. Fate clic su un’immagine e verificate che il messaggio `A Core Image was clicked` sia visualizzato nella console del browser.

## Avvia l’integrazione con AEM e il livello dati {#data-layer-launch}

Ora che è stata configurata l’integrazione tra AEM e Launch, possiamo effettuare l’integrazione con il livello dati.

### Passaggio 1 - Creazione di una regola in Adobe Launch {#create-rule}

Ripetete i passaggi del [passaggio 5](#launch-rule) per aggiungere una nuova regola in Adobe Launch utilizzando i valori seguenti.

* Nome: `image-click-data-layer`
* EVENTI:
   * Estensione: Core
   * Tipo evento: DOM Ready
* AZIONI:
   * Estensione: Core
   * Tipo azione: Codice personalizzato
   * Codice:

      ```
        function onImageClick(event) {
          console.log("Data layer click event tracked by Launch for image: " + event.info.path);
          console.log("dataLayer.getState(): ", adobeDataLayer.getState()); 
        }
        adobeDataLayer.addEventListener('image clicked', onImageClick);
      ```

### Passaggio 2 - Pubblicate la regola di avvio per renderla disponibile nel sito AEM {#publish-rule-2}

Ripetete i passaggi del [passaggio 6](#publish-rule) per pubblicare la nuova regola.

### Passaggio 3 - Verificare che la logica di avvio sia applicata alla pagina {#verify}

1. Aprite la pagina Immagine della Libreria componenti core in modalità di anteprima: `http://<host&gt;:<port&gt;/editor.html/content/core-components-examples/library/page-authoring/image.html`
1. Fate clic su un’immagine e verificate che nella console del browser sia visualizzato il seguente messaggio:

   ![Uscita console livello dati](/help/assets/data-layer-console-output.png)
