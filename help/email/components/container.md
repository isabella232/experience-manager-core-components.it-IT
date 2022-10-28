---
title: Componente contenitore e-mail
description: Il componente Contenitore e-mail consente di creare un contenitore per più componenti aggiuntivi nel contenuto dell’e-mail.
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 40%

---


# Componente contenitore e-mail {#email-container-component}

Il componente Contenitore e-mail consente di creare un contenitore per più componenti aggiuntivi nel contenuto dell’e-mail.

## Utilizzo {#usage}

Il componente Contenitore e-mail consente di creare un contenitore per più componenti aggiuntivi nel contenuto dell’e-mail e può essere utilizzato per raggruppare altri componenti e applicare uno stile o un layout comune.

* Le proprietà del Contenitore possono essere selezionate nella [finestra di dialogo per configurazione.](#configure-dialog)
* I valori predefiniti per il componente Contenitore e-mail quando lo si aggiunge a una pagina possono essere definiti nella [finestra di dialogo di progettazione.](#design-dialog)

Una volta aggiunto un componente Contenitore e-mail a una pagina, un autore di contenuti può trascinarvi altri componenti.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Contenitore e-mail è v1, introdotta con la versione X dei componenti core e-mail nell’ottobre 2022, ed è descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e le versioni dei componenti core e-mail, consulta il documento [Versioni dei componenti core di e-mail.](/help/email/versions.md)

## Esempio di output del componente {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente Contenitore e-mail e dell’output di HTML e JSON, visita il [Libreria dei componenti.](https://adobe.com/go/aem_cmp_library_email_container)

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Contenitore [è disponibile su GitHub.](https://adobe.com/go/aem_cmp_tech_email_container_v1)

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core.](/help/developing/overview.md)

## Finestra di dialogo per la configurazione {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire l’elemento contenitore e il suo funzionamento e la sua visualizzazione nel contenuto.

![Finestra di dialogo Modifica del componente contenitore e-mail](/help/email/assets/email-container-configure.png)

* **Layout** - Questa opzione definisce il comportamento o il comportamento del layout del componente Contenitore e-mail.
   * **a larghezza intera**
   * **mezzo|mezzo**
   * **un terzo|due terzi**
   * **due terzi|un terzo**
   * **terzo|terzo|terzo|terzo**
* **Colore sfondo**: definibile utilizzando i valori RGB in forma libera o utilizzando il selettore colore, [a seconda della configurazione](#container-settings-tab)
* **Immagine di sfondo** - Definisce un&#39;immagine di sfondo per il contenitore, [a seconda della configurazione](#container-settings-tab)
* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente in HTML.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando il contenuto risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sui CSS.

### Scheda Stili {#styles-tab-edit}

Il componente Contenitore e-mail supporta il AEM [Sistema di stili.](/help/get-started/authoring.md#component-styling)

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nel [finestra di dialogo di progettazione](#design-dialog) affinché la scheda sia disponibile.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore del contenuto che utilizza il componente Contenitore e-mail.

### Scheda Componenti consentiti {#allowed-components-tab}

La **Componenti consentiti** La scheda viene utilizzata per definire quali componenti possono essere aggiunti dall’autore del contenuto come elementi al componente Contenitore e-mail.

La **Componenti consentiti** la scheda funziona come la scheda dello stesso nome quando [definizione dei criteri e delle proprietà di un Contenitore di layout nell’Editor modelli.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it)

### Scheda Componenti standard {#default-components-tab}

La **Componenti predefiniti** viene utilizzata per definire quale componente viene aggiunto al componente quando un particolare tipo di risorsa viene rilasciato sul contenitore, in modo analogo a [modalità di definizione dei componenti predefiniti nel modello di pagina.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Scheda Impostazioni contenitore {#container-settings-tab}

La **Impostazioni dei contenitori** definisce se l’autore può definire un’immagine o un colore di sfondo.

![Scheda Impostazioni contenitore della finestra di dialogo di progettazione del componente Contenitore e-mail](/help/email/assets/email-container-design-container-settings.png)

* **Immagine di sfondo**
   * **Abilita immagine di sfondo**: seleziona questa opzione per consentire all’autore di contenuto di definire un’immagine di sfondo per il Contenitore.
* **Colore sfondo**
   * **Abilita colore di sfondo**: seleziona questa opzione per consentire all’autore di contenuto di definire un colore di sfondo per il Contenitore.
   * **Solo campioni**: seleziona questa opzione per consentire all’autore di contenuto di selezionare il colore di sfondo del Contenitore solo da campioni di colore predefiniti.
      * Disponibile solo se è selezionata l’opzione **Abilita colore di sfondo**
* **Campioni consentiti**: consente di definire colori predefiniti da cui l’autore di contenuto può selezionare il colore di sfondo del Contenitore
   * Utilizza il pulsante **Aggiungi** per aggiungere un campione di colore predefinito. Una volta aggiunto, all’elenco viene aggiunta una voce che contiene le seguenti colonne:
   * **Valore**: consente di definire manualmente il colore utilizzando i valori RGB
      * Tocca o fai clic sul selettore colore per selezionare più facilmente un colore regolando i singoli valori RGB o definendo un valore esadecimale.
   * **Elimina**: tocca o fai clic su un campione per eliminarlo.
   * **Ridisponi** - Tocca o fai clic e trascina per riordinare i campioni.

### Scheda Stili {#styles-tab}

Il componente Contenitore e-mail supporta il AEM [Sistema di stili.](/help/get-started/authoring.md#component-styling)