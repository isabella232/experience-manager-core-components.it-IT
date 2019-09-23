---
title: Componente pagina
seo-title: Componente pagina
description: Il componente Pagina è un componente di pagina estensibile progettato per funzionare con l’editor modelli e consente di assemblare con l’editor modelli i componenti di intestazione/piè di pagina e struttura della pagina.
seo-description: Il componente Pagina è un componente di pagina estensibile progettato per funzionare con l’editor modelli e consente di assemblare con l’editor modelli i componenti di intestazione/piè di pagina e struttura della pagina.
uuid: 7052a5b1-e7f1-4944-a55c-faf739b6e89c
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: cb1a745a-30c4-4ad6-a04f-fefb3666cd95
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# Componente pagina{#page-component}

Il componente Pagina è un componente di pagina estensibile progettato per funzionare con l’editor [](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) modelli e consente di assemblare con l’editor modelli i componenti di intestazione/piè di pagina e struttura della pagina.

## Utilizzo {#usage}

Il componente pagina costituisce la base di tutte le pagine progettate con i componenti core e modelli modificabili. Utilizzando il componente pagina, le intestazioni, i piè di pagina e la struttura della pagina possono essere definiti come un modello utilizzando gli altri componenti core.

Utilizzando la finestra di dialogo [di](#design-dialog)progettazione, potete definire librerie personalizzate sul lato client per la pagina. A differenza di altri componenti che dispongono di una finestra di dialogo di modifica accessibile direttamente dal componente, poiché il componente è la pagina stessa, la finestra di dialogo [di](#edit-dialog) modifica del componente pagina è la finestra delle proprietà della pagina.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pagina è v2, introdotta con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| [v2](page-v1.md) | Compatibile | Compatibile | Compatibile |
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

>[!NOTE]
>
>Per abilitare il reindirizzamento a `cq:Page` livello per la versione 2 del componente della pagina e AEM 6.3, è necessario [Service Pack 2](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp2-release-notes.html) o successivo. Tale reindirizzamento non era disponibile nelle versioni precedenti.

## Output componente di esempio {#sample-component-output}

Esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/chlimage_1.png)

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Pagina [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Edit Dialog {#edit-dialog}

Poiché il componente rappresenta l’intera pagina, le impostazioni che normalmente si trovano in una finestra di dialogo di modifica si trovano nella finestra Proprietà [](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-page-properties.html) pagina.

## Finestra di dialogo Progettazione {#design-dialog}

Poiché il componente rappresenta l’intera pagina, la finestra di dialogo della progettazione è accessibile tramite Informazioni **pagina &gt; Criteri** pagina durante la modifica del modello di pagina.

![](assets/screen_shot_2018-04-03at113410.png)

>[!NOTE]
>
>Nelle versioni precedenti di AEM, i criteri **** pagina erano denominati Progettazione **** pagina.

### Scheda Proprietà {#properties-tab}

La finestra Progettazione pagina consente di definire le librerie client da caricare, nonché la libreria delle risorse Web per la pagina.

* **Librerie** client Definisce le categorie della libreria client da caricare. JavaScript viene aggiunto alla fine del corpo e il CSS viene aggiunto all'intestazione della pagina.
* **Intestazione** pagina JavaScript delle librerie client Definisce le categorie di libreria client JavaScript da caricare nell'intestazione della pagina.
   * Le categorie qui definite che sono presenti anche nel campo **Client Libraries** avranno JavaScript caricato nell'intestazione della pagina invece che all'estremità del corpo.
   * Non verrà caricato alcun CSS a meno che la categoria non sia presente anche nel campo **Client Libraries** .

* **Libreria** client risorse Web La categoria della libreria client utilizzata per distribuire risorse Web come favicons.

![](assets/screenshot_2018-10-19at104949.png)

Le librerie possono essere configurate per i campi Head **di pagina JavaScript delle librerie** client e delle librerie **** client, come indicato di seguito:

* Per aggiungere un nuovo campo, fare clic o toccare il pulsante **Aggiungi** sotto i campi.
* Per rimuovere un campo, fare clic o toccare l'icona del cestino accanto al campo da rimuovere.
* Per riordinare l'ordine di caricamento, fare clic o toccare e trascinare la maniglia accanto al campo da spostare.

Per ulteriori informazioni sull'uso delle librerie lato client, consultate [Utilizzo delle librerie](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)lato client.

>[!CAUTION]
>
>La possibilità di definire separatamente le librerie client per l'intestazione di pagina è stata introdotta con la release 2.2.0 dei componenti core.

### Scheda Stili {#styles-tab}

Il componente Pagina supporta AEM [Style System](authoring.md#component-styling).