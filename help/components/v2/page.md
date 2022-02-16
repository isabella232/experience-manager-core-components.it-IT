---
title: Componente Pagina (v2)
description: Il componente Pagina è una pagina estensibile concepita per funzionare con l’editor di modelli e consentire l’assemblaggio di intestazione/piè di pagina e altri componenti della struttura della pagina.
role: Architect, Developer, Admin, User
source-git-commit: e5251010ca41025eb2bb56b66164ecf4cc0145c8
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 97%

---


# Componente Pagina  (v2) {#page-component}

Il componente Pagina è una pagina estensibile concepita per funzionare con l’[editor di modelli](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it) e consentire l’assemblaggio di intestazione/piè di pagina e altri componenti della struttura della pagina.

## Utilizzo {#usage}

Il componente Pagina costituisce la base di tutte le pagine progettate con i Componenti core e i modelli modificabili. Utilizzando il componente Pagina, le intestazioni, i piè di pagina e la struttura della pagina possono essere definiti in un modello utilizzando gli altri Componenti core.

Nella [finestra di dialogo per progettazione](#design-dialog) è possibile definire le librerie client della pagina. A differenza di altri componenti che hanno una finestra di dialogo per modifica accessibile direttamente dal componente, poiché il componente Pagina è la pagina stessa, la [finestra di dialogo per modifica](#edit-dialog) del componente Pagina è la finestra delle proprietà della pagina.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 2 del componente Pagina , introdotto con la versione 2.0.0 dei componenti core a gennaio 2018.

>[!CAUTION]
>
>Questo documento descrive la versione 2 del componente Pagina.
>
>Per informazioni dettagliate sulla versione corrente del componente Pagina, vedi il documento [Componente Pagina](/help/components/page.md).

## Supporto di Progressive Web App {#pwa-support}

La versione 2.15.0 dei Componenti core ha introdotto il supporto delle [funzionalità di Progressive Web App (PWA) integrato in AEM as a Cloud Service.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/enable-pwa.html?lang=it)Con una semplice configurazione a livello di sito, puoi trasformare la tua esperienza AEM in un’esperienza PWA.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pagina [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_page_v2_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per modifica {#edit-dialog}

Poiché il componente rappresenta l’intera pagina, le impostazioni normalmente presenti in una finestra di dialogo per modifica si trovano invece nella finestra [Proprietà della pagina](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html?lang=it).

## Finestra di dialogo per progettazione {#design-dialog}

Poiché il componente rappresenta l’intera pagina, la finestra di dialogo per progettazione è accessibile tramite **Informazioni pagina -> Criterio pagina** durante la modifica del modello della pagina.

![Criterio pagina](/help/assets/page-policy.png)

>[!NOTE]
>
>Nelle versioni precedenti di AEM, **Criterio pagina** era denominato **Progettazione pagina**.

### Scheda Proprietà {#properties-tab}

La finestra per progettazione della pagina consente di definire le librerie client da caricare e la libreria di risorse web della pagina.

* **Librerie client**: definisce le categorie di librerie client da caricare. JavaScript viene aggiunto alla fine del corpo della pagina e CSS viene aggiunto all’intestazione della pagina.
* **Intestazione pagina JavaScript per librerie client**: definisce le categorie di librerie client JavaScript da caricare nell’intestazione della pagina.
   * Le categorie definite in questo campo che sono presenti anche nel campo **Librerie client** avranno JavaScript caricato nell’intestazione invece che alla fine del corpo della pagina.
   * Non verrà caricato alcun CSS, a meno che la categoria non sia presente anche nel campo **Librerie client**.

* **Libreria client risorse web**: categoria di librerie client utilizzate per fornire risorse web come le favicons (favorite icons).

* **Selettore per passare all’elemento del contenuto principale**: utilizzato come funzione di accessibilità per passare direttamente al contenuto principale della pagina

![Finestra di dialogo per progettazione del componente Pagina](/help/assets/page-design.png)

Le librerie possono essere configurate per i campi **Librerie client** e **Intestazione pagina JavaScript per librerie client**, nel modo che segue:

* Per aggiungere un nuovo campo, tocca o fai clic sul pulsante **Aggiungi** sotto ciascuno dei due campi.
* Per rimuovere un campo, tocca o fai clic sull’icona cestino accanto al campo da rimuovere.
* Per cambiare l’ordine di caricamento, tocca o fai clic e trascina la maniglia che si trova accanto al campo da spostare.

Per ulteriori informazioni sull’utilizzo delle librerie client, vedi [Utilizzo delle librerie client](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/clientlibs.html?lang=it).

>[!CAUTION]
>
>Con la versione 2.2.0 dei Componenti core è stata introdotta la possibilità di definire separatamente le librerie client per l’intestazione della pagina.

### Scheda Stili {#styles-tab}

Il componente Pagina supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

## Adobe Client Data Layer {#data-layer}

Il componente Pagina supporta [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
