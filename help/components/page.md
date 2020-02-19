---
title: Componente pagina
description: Il componente Pagina è un componente di pagina estensibile progettato per funzionare con l’editor modelli e consente di assemblare con l’editor modelli i componenti di intestazione/piè di pagina e struttura della pagina.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Componente pagina{#page-component}

Il componente Pagina è un componente di pagina estensibile progettato per funzionare con l’editor [](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) modelli e consente di assemblare con l’editor modelli i componenti di intestazione/piè di pagina e struttura della pagina.

## Utilizzo {#usage}

Il componente pagina costituisce la base di tutte le pagine progettate con i componenti core e modelli modificabili. Utilizzando il componente pagina, le intestazioni, i piè di pagina e la struttura della pagina possono essere definiti come un modello utilizzando gli altri componenti core.

Utilizzando la finestra di dialogo [di](#design-dialog)progettazione, potete definire librerie personalizzate sul lato client per la pagina. A differenza di altri componenti che dispongono di una finestra di dialogo di modifica accessibile direttamente dal componente, poiché il componente è la pagina stessa, la finestra di dialogo [di](#edit-dialog) modifica del componente pagina è la finestra delle proprietà della pagina.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pagina è v2, introdotta con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM come servizio cloud |
|---|---|---|---|---|
| v2 | Compatibile | Compatibile | Compatibile | Compatibile |
| [v1](v1/page-v1.md) | Compatibile | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

>[!NOTE]
>
>Per abilitare il reindirizzamento a `cq:Page` livello per la versione 2 del componente della pagina e AEM 6.3, è necessario [Service Pack 2](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp2-release-notes.html) o successivo. Tale reindirizzamento non era disponibile nelle versioni precedenti.

## Output componente di esempio {#sample-component-output}

Esempio tratto da [We.Retail](https://docs.adobe.com/content/help/en/experience-manager-65/developing/bestpractices/we-retail/we-retail.html).

### Schermata {#screenshot}

![](/help/assets/chlimage_1.png)

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pagina [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_page_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Edit Dialog {#edit-dialog}

Poiché il componente rappresenta l’intera pagina, le impostazioni che normalmente si trovano in una finestra di dialogo di modifica si trovano nella finestra Proprietà [](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) pagina.

## Finestra di dialogo Progettazione {#design-dialog}

Poiché il componente rappresenta l’intera pagina, la finestra di dialogo della progettazione è accessibile tramite Informazioni **pagina > Criteri** pagina durante la modifica del modello di pagina.

![](/help/assets/screen_shot_2018-04-03at113410.png)

>[!NOTE]
>
>Nelle versioni precedenti di AEM, i criteri **** pagina erano denominati Progettazione **** pagina.

### Scheda Proprietà {#properties-tab}

La finestra Progettazione pagina consente di definire le librerie client da caricare, nonché la libreria delle risorse Web per la pagina.

* **Librerie** client Definisce le categorie della libreria client da caricare. JavaScript viene aggiunto alla fine del corpo e il CSS viene aggiunto all&#39;intestazione della pagina.
* **Intestazione** pagina JavaScript delle librerie client Definisce le categorie di libreria client JavaScript da caricare nell&#39;intestazione della pagina.
   * Le categorie qui definite che sono presenti anche nel campo **Client Libraries** avranno JavaScript caricato nell&#39;intestazione della pagina invece che all&#39;estremità del corpo.
   * Non verrà caricato alcun CSS a meno che la categoria non sia presente anche nel campo **Client Libraries** .

* **Libreria** client risorse Web La categoria della libreria client utilizzata per distribuire risorse Web come favicons.

![](/help/assets/screenshot_2018-10-19at104949.png)

Le librerie possono essere configurate per i campi Head **di pagina JavaScript delle librerie** client e delle librerie **** client, come indicato di seguito:

* Per aggiungere un nuovo campo, fare clic o toccare il pulsante **Aggiungi** sotto i campi.
* Per rimuovere un campo, fare clic o toccare l&#39;icona del cestino accanto al campo da rimuovere.
* Per riordinare l&#39;ordine di caricamento, fare clic o toccare e trascinare la maniglia accanto al campo da spostare.

Per ulteriori informazioni sull&#39;uso delle librerie lato client, consultate [Utilizzo delle librerie](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)lato client.

>[!CAUTION]
>
>La possibilità di definire separatamente le librerie client per l&#39;intestazione di pagina è stata introdotta con la release 2.2.0 dei componenti core.

### Scheda Stili {#styles-tab}

Il componente Pagina supporta AEM [Style System](/help/get-started/authoring.md#component-styling).
