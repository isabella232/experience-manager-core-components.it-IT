---
title: Componente Pagina e-mail
description: Componente Pagina e-mail
role: Architect, Developer, Admin, User
exl-id: 17fd0f5e-2b85-41a1-abaf-8ad190a5341a
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 40%

---


# Componente Pagina e-mail {#email-page-component}

Il componente Pagina e-mail è un componente di pagina estensibile progettato per funzionare con [editor modelli](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it) e consente di assemblare i componenti di intestazione/piè di pagina e struttura con l’editor modelli, specifici per la creazione di contenuti Adobe Campaign.

## Utilizzo {#usage}

Il componente Pagina e-mail costituisce la base di tutte le pagine progettate con i componenti core e-mail e i modelli modificabili. Utilizzando il componente Pagina e-mail, le intestazioni, i piè di pagina e la struttura della pagina possono essere definiti come un modello utilizzando gli altri componenti core e-mail.

* Utilizzo della [finestra di dialogo di progettazione,](#design-dialog) è possibile definire librerie personalizzate lato client per la pagina.
* A differenza di altri componenti che dispongono di una finestra di dialogo di modifica accessibile direttamente dal componente, poiché il componente Pagina e-mail è la pagina stessa, il [finestra di dialogo modifica](#edit-dialog) del componente Pagina e-mail è la finestra delle proprietà della pagina.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pagina e-mail è v1, introdotto con la versione X dei componenti core e-mail nell’ottobre 2022, ed è descritto in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e le versioni dei componenti core e-mail, consulta il documento [Versioni dei componenti core e-mail](/help/email/versions.md)

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pagina [è disponibile su GitHub.](https://adobe.com/go/aem_cmp_tech_email_page_v1)

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per modifica {#edit-dialog}

Poiché il componente rappresenta l’intera pagina, le impostazioni normalmente presenti in una finestra di dialogo per modifica si trovano invece nella finestra [Proprietà della pagina](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html?lang=it).

### Scheda Cloud Services {#cloud-services}

Affinché i componenti core e-mail possano recuperare le variabili e i dati della campagna, la pagina deve essere collegata a una configurazione di Adobe Campaign.

![Proprietà pagina e-mail](/help/email/assets/email-page-properties.png)

Sotto **Configurazione Cloud Service** intestazione, nel menu a discesa seleziona **Aggiungi configurazione**.

Sotto **Adobe Campaign** seleziona la configurazione per l’integrazione con Adobe Campaign.

Vedere il documento [Utilizzo dei componenti core e-mail](/help/email/using.md) per ulteriori informazioni sulla configurazione dei componenti core e-mail.

### Scheda E-mail {#email-tab}

La scheda E-mail definisce le proprietà delle e-mail inviate tramite Adobe Campaign in base al contenuto di questa pagina, ad esempio l’oggetto dell’e-mail e il contenuto di testo normale.

![Proprietà pagina e-mail](/help/email/assets/email-page-properties-email.png)

* **Oggetto** - Oggetto dell’e-mail inviata da Adobe Campaign in base a questa pagina
   * Fai clic sul pulsante **Seleziona variabile Adobe Campaign** per aprire [Seleziona variabile Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.
* **Pre-intestazione**
   * Fai clic sul pulsante **Seleziona variabile Adobe Campaign** per aprire [Seleziona variabile Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.
* **Testo normale** - Versione in testo normale dell’e-mail inviata da Adobe Campaign
   * Fai clic sul pulsante **Seleziona variabile Adobe Campaign** per aprire [Seleziona variabile Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.
* **Url Di Riferimento**

## Finestra di dialogo per progettazione {#design-dialog}

Poiché il componente rappresenta l’intera pagina, la finestra di dialogo per progettazione è accessibile tramite **Informazioni pagina -> Criterio pagina** durante la modifica del modello della pagina.

![Criterio pagina](/help/assets/page-policy.png)

### Scheda Proprietà {#properties-tab}

La finestra per progettazione della pagina consente di definire le librerie client da caricare e la libreria di risorse web della pagina.

![Finestra di dialogo di progettazione del componente Pagina e-mail](/help/email/assets/email-page-design.png)

* **Librerie client**: definisce le categorie di librerie client da caricare. JavaScript viene aggiunto alla fine del corpo della pagina e CSS viene aggiunto all’intestazione della pagina.
* **Intestazione pagina JavaScript delle librerie client** - Definisce le categorie della libreria client JavaScript da caricare nell’intestazione della pagina.
   * Le categorie definite in questo campo che sono presenti anche nel campo **Librerie client** avranno JavaScript caricato nell’intestazione invece che alla fine del corpo della pagina.
   * Non verrà caricato alcun CSS, a meno che la categoria non sia presente anche nel campo **Librerie client**.
* **Caricare le librerie JavaScript in modo asincrono** - Se abilitata, le librerie JavaScript personalizzate verranno caricate in modo asincrono.
* **Libreria client risorse web**: categoria di librerie client utilizzate per fornire risorse web come le favicons (favorite icons).
* **Selettore per passare all’elemento del contenuto principale**: utilizzato come funzione di accessibilità per passare direttamente al contenuto principale della pagina

Le librerie possono essere configurate per i campi **Librerie client** e **Intestazione pagina JavaScript per librerie client**, nel modo che segue:

* Per aggiungere un nuovo campo, tocca o fai clic sul pulsante **Aggiungi** sotto i campi.
* Per rimuovere un campo, tocca o fai clic sull’icona del cestino accanto al campo da rimuovere.
* Per cambiare l’ordine di caricamento, tocca o fai clic e trascina la maniglia che si trova accanto al campo da spostare.

Per ulteriori informazioni sull’utilizzo delle librerie lato client, consulta [Utilizzo delle librerie lato client.](https://helpx.adobe.com/it/experience-manager/6-5/sites/developing/using/clientlibs.html)

### Scheda Stili {#styles-tab}

Il componente Pagina supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
