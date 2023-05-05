---
title: Componente Contenitore e-mail
description: Il componente Contenitore e-mail consente di creare un contenitore per più componenti aggiuntivi nel contenuto dell’e-mail.
role: Architect, Developer, Admin, User
exl-id: 3b271e95-0093-4cb1-bb83-8446ba12a821
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: ht
source-wordcount: '797'
ht-degree: 100%

---


# Componente Contenitore e-mail {#email-container-component}

Il componente Contenitore e-mail consente di creare un contenitore per più componenti aggiuntivi nel contenuto dell’e-mail.

## Utilizzo {#usage}

Il componente Contenitore e-mail consente di creare un contenitore per più componenti aggiuntivi nel contenuto dell’e-mail e può essere utilizzato per raggruppare altri componenti e applicare uno stile o un layout comune.

* Le proprietà del Contenitore possono essere selezionate nella [finestra di dialogo per la configurazione.](#configure-dialog)
* Le impostazioni predefinite del componente Contenitore e-mail, quando lo si aggiunge a una pagina, possono essere definite nella [finestra di dialogo per la progettazione.](#design-dialog)

Una volta che il componente Contenitore e-mail è stato aggiunto a una pagina, un autore del contenuto può trascinarvi i componenti aggiuntivi.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Contenitore e-mail è la v1, introdotta con la versione x dei Componenti core e-mail a ottobre 2022, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile  | - |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei componenti core E-mail, consulta il documento [Versioni dei componenti core E-mail.](/help/email/versions.md)

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Contenitore [è disponibile su GitHub.](https://adobe.com/go/aem_cmp_tech_email_container_v1)

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core.](/help/developing/overview.md)

## Finestra di dialogo per la configurazione {#configure-dialog}

La finestra di dialogo per la configurazione consente all’autore del contenuto di definire l’elemento contenitore, il suo comportamento e come si presenta nel contenuto.

![Finestra di dialogo per la modifica del componente Contenitore e-mail](/help/email/assets/email-container-configure.png)

* **Layout**: questa opzione definisce il comportamento o il comportamento del layout del componente Contenitore e-mail.
   * **larghezza intera**
   * **mezzo|mezzo**
   * **un terzo|due terzi**
   * **due terzi|un terzo**
   * **terzo|terzo|terzo|terzo**
* **Colore di sfondo**: definibile utilizzando i valori RGB in forma libera o utilizzando il selettore colore, [a seconda della configurazione](#container-settings-tab)
* **Immagine di sfondo**: definisce l’immagine di sfondo del Contenitore, [a seconda della configurazione](#container-settings-tab)
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nell’HTML.
   * Se non specificato, viene generato automaticamente un ID univoco reperibile esaminando il contenuto risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sulle CSS.

### Scheda Stili {#styles-tab-edit}

Il componente Contenitore e-mail supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nella [finestra di dialogo per la progettazione](#design-dialog) affinché la scheda sia disponibile.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore dei contenuti che utilizza il componente Contenitore e-mail.

### Scheda Componenti consentiti {#allowed-components-tab}

La scheda **Componenti consentiti** viene utilizzata per definire quali componenti possono essere aggiunti al componente Contenitore e-mail dall’autore del contenuto.

La scheda **Componenti consentiti** funziona come la scheda con lo stesso nome utilizzata per [definire i criteri e le proprietà di un Contenitore di layout nell’Editor di modelli.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it)

### Scheda Componenti predefiniti {#default-components-tab}

La scheda **Componenti predefiniti** consente di definire quale componente viene aggiunto al componente quando un particolare tipo di risorsa viene rilasciato sul Contenitore stesso, in modo analogo a [come vengono definiti i componenti predefiniti nel modello di pagina.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it)

### Scheda Impostazioni contenitore {#container-settings-tab}

La scheda **Impostazioni contenitore** definisce se l’autore può definire un’immagine o un colore di sfondo.

![Scheda Impostazioni contenitore della finestra di dialogo per la progettazione del componente Contenitore e-mail](/help/email/assets/email-container-design-container-settings.png)

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
   * **Ridisponi**: tocca o fai clic e trascina per riordinare i campioni.

### Scheda Stili {#styles-tab}

Il componente Contenitore e-mail supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
