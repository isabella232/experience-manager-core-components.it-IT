---
title: Componente Pagina e-mail
description: Il componente Pagina e-mail
role: Architect, Developer, Admin, User
exl-id: 17fd0f5e-2b85-41a1-abaf-8ad190a5341a
source-git-commit: c16dd8696e89f89c7b178ece11f57a565d73588b
workflow-type: ht
source-wordcount: '803'
ht-degree: 100%

---


# Componente Pagina e-mail {#email-page-component}

Il componente Pagina e-mail è un componente pagina estensibile concepito per funzionare con l’[Editor modelli](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it) e consentire l’assemblaggio di intestazione/piè di pagina e altri componenti della struttura della pagina, in modo adatto alla creazione di contenuti Adobe Campaign.

## Utilizzo {#usage}

Il componente Pagina e-mail costituisce la base di tutte le pagine progettate con i componenti core E-mail e i modelli modificabili. Utilizzando il componente Pagina e-mail, le intestazioni, i piè di pagina e la struttura della pagina possono essere definiti come modello utilizzando gli altri componenti core E-mail.

* Nella [finestra di dialogo per la progettazione](#design-dialog) è possibile definire le librerie client della pagina.
* A differenza di altri componenti che dispongono di una finestra di dialogo per la modifica accessibile direttamente dal componente, poiché il componente Pagina e-mail è la pagina stessa, la sua [finestra di dialogo per la modifica](#edit-dialog) corrisponde alla finestra delle proprietà della pagina.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pagina e-mail è la v1, introdotta con la versione X dei componenti core E-mail a ottobre 2022, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile  | - |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei componenti core E-mail, vedi il documento [Versioni dei Componenti core E-mail](/help/email/versions.md)

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pagina [è disponibile su GitHub.](https://adobe.com/go/aem_cmp_tech_email_page_v1)

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per modifica {#edit-dialog}

Poiché il componente rappresenta l’intera pagina, le impostazioni normalmente presenti in una finestra di dialogo per modifica si trovano invece nella finestra [Proprietà della pagina](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html?lang=it).

### Scheda Servizi cloud {#cloud-services}

Affinché i componenti core E-mail possano recuperare le variabili e i dati di Campaign, la pagina deve essere collegata a una configurazione di Adobe Campaign.

![Proprietà di Pagina e-mail](/help/email/assets/email-page-properties.png)

Sotto l’intestazione **Configurazione servizio cloud**, nel menu a discesa seleziona **Aggiungi configurazione**.

Sotto l’intestazione **Adobe Campaign** seleziona la configurazione per l’integrazione con Adobe Campaign.

Per ulteriori informazioni sulla configurazione di questi componenti core, consulta il documento [Utilizzo dei componenti core E-mail](/help/email/using.md).

### Scheda E-mail {#email-tab}

La scheda E-mail definisce le proprietà delle e-mail inviate tramite Adobe Campaign in base al contenuto di questa pagina, ad esempio l’oggetto dell’e-mail e il contenuto di testo normale.

![Proprietà di Pagina e-mail](/help/email/assets/email-page-properties-email.png)

* **Oggetto**: oggetto dell’e-mail inviata da Adobe Campaign in base a questa pagina
   * Fai clic sul pulsante **Seleziona variabile di Adobe Campaign** per aprire la finestra di dialogo [Seleziona variabile di Adobe Campaign](/help/email/campaign-variables.md) e inserire contenuto dinamico da Adobe Campaign.
* **Pre-intestazione**
   * Fai clic sul pulsante **Seleziona variabile di Adobe Campaign** per aprire la finestra di dialogo [Seleziona variabile di Adobe Campaign](/help/email/campaign-variables.md) e inserire contenuto dinamico da Adobe Campaign.
* **Testo normale**: versione in testo normale dell’e-mail inviata da Adobe Campaign
   * Fai clic sul pulsante **Seleziona variabile di Adobe Campaign** per aprire la finestra di dialogo [Seleziona variabile di Adobe Campaign](/help/email/campaign-variables.md) e inserire contenuto dinamico da Adobe Campaign.
* **URL di riferimento**

## Finestra di dialogo per progettazione {#design-dialog}

Poiché il componente rappresenta l’intera pagina, la finestra di dialogo per progettazione è accessibile tramite **Informazioni pagina -> Criterio pagina** durante la modifica del modello della pagina.

![Criterio pagina](/help/assets/page-policy.png)

### Scheda Proprietà {#properties-tab}

La finestra per progettazione della pagina consente di definire le librerie client da caricare e la libreria di risorse web della pagina.

![Finestra di dialogo per la progettazione del componente Pagina e-mail](/help/email/assets/email-page-design.png)

* **Librerie client**: definisce le categorie di librerie client da caricare. JavaScript viene aggiunto alla fine del corpo della pagina e CSS viene aggiunto all’intestazione della pagina.
* **Intestazione pagina JavaScript per librerie client**: definisce le categorie di librerie client JavaScript da caricare nell’intestazione della pagina.
   * Le categorie definite in questo campo che sono presenti anche nel campo **Librerie client** avranno JavaScript caricato nell’intestazione invece che alla fine del corpo della pagina.
   * Non verrà caricato alcun CSS, a meno che la categoria non sia presente anche nel campo **Librerie client**.
* **Caricare librerie JavaScript in modo asincrono**: se questa opzione è abilitata, le librerie JavaScript personalizzate verranno caricate in modo asincrono.
* **Libreria client risorse web**: categoria di librerie client utilizzate per fornire risorse web come le favicons (favorite icons).
* **Selettore per passare all’elemento del contenuto principale**: utilizzato come funzione di accessibilità per passare direttamente al contenuto principale della pagina

Le librerie possono essere configurate per i campi **Librerie client** e **Intestazione pagina JavaScript per librerie client**, come segue:

* Per aggiungere un nuovo campo, tocca o fai clic sul pulsante **Aggiungi** sotto i campi.
* Per rimuovere un campo, tocca o fai clic sull’icona cestino accanto al campo da rimuovere.
* Per cambiare l’ordine di caricamento, tocca o fai clic e trascina la maniglia che si trova accanto al campo da spostare.

Per ulteriori informazioni sull’utilizzo delle librerie client, consulta [Utilizzo delle librerie client.](https://helpx.adobe.com/it/experience-manager/6-5/sites/developing/using/clientlibs.html)

### Scheda Stili {#styles-tab}

Il componente Pagina supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
