---
title: Componente pagina
seo-title: Componente pagina
description: Il componente Pagina è un componente di pagina estensibile progettato per funzionare con l'editor modelli e consente l'assemblaggio di componenti header/piè di pagina e struttura con l'editor modelli.
seo-description: Il componente Pagina è un componente di pagina estensibile progettato per funzionare con l'editor modelli e consente l'assemblaggio di componenti header/piè di pagina e struttura con l'editor modelli.
uuid: 7052 a 5 b 1-e 7 f 1-4944-a 55 c-faf 739 b 6 e 89 c
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: cb 1 a 745 a -30 c 4-4 ad 6-a 04 f-fefb 3666 cd 95
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# Componente pagina{#page-component}

Il componente Pagina è un componente di pagina estensibile progettato per funzionare con l&#39;editor [modelli](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) e consente la raccolta di componenti header/piè di pagina e struttura con l&#39;editor modelli.

## Utilizzo {#usage}

Il componente Pagina costituisce la base di tutte le pagine progettate con i componenti core e i modelli modificabili. Utilizzando il componente pagina, le intestazioni, i piè di pagina e la struttura della pagina è possibile definire un modello utilizzando gli altri componenti core.

Mediante la finestra di dialogo [Progettazione](#design-dialog), è possibile definire per la pagina librerie lato client personalizzate. A differenza degli altri componenti con finestra di dialogo di modifica accessibili direttamente dal componente, poiché il componente è la stessa pagina, la finestra di dialogo [di modifica](#edit-dialog) del componente pagina è la finestra delle proprietà della pagina.

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Pagina è v 2, introdotta con la release 2.0.0 dei Componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| [v2](page-v1.md) | Compatibile | Compatibile | Compatibile |
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

>[!NOTE]
>
>Per abilitare il reindirizzamento a `cq:Page` livello per l&#39;implementazione del 2 del componente pagina e di AEM 6.3, [è necessario service pack 2](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp2-release-notes.html) o versione successiva. Tale reindirizzamento non era disponibile nelle versioni precedenti.

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/chlimage_1.png)

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente [Pagina è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Finestra di dialogo di modifica {#edit-dialog}

Poiché il componente rappresenta l&#39;intera pagina, le impostazioni che si trovano normalmente in una finestra di dialogo di modifica si trovano nella [finestra Proprietà](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-page-properties.html) pagina.

## Finestra di dialogo Progettazione {#design-dialog}

Poiché il componente rappresenta l&#39;intera pagina, si accede alla finestra di dialogo di progettazione tramite **Informazioni pagina -&gt; Criteri pagina** durante la modifica del modello di pagina.

![](assets/screen_shot_2018-04-03at113410.png)

>[!NOTE]
>
>Nelle versioni precedenti di AEM, il criterio **pagina** era denominato **Progettazione pagina**.

### Scheda Proprietà {#properties-tab}

Mediante la finestra Progettazione pagina potete definire le librerie client da caricare e la libreria delle risorse Web per la pagina.

* **Librerie**
client Definisce le categorie della libreria client da caricare. Javascript viene aggiunto al termine del corpo e il CSS viene aggiunto all&#39;intestazione della pagina.
* **Intestazione**
pagina javascript per librerie client Definisce le categorie della libreria Client javascript da caricare nell&#39;intestazione della pagina.
   * Le categorie definite qui sono presenti anche nel campo **Librerie** client, che conterrà javascript nell&#39;intestazione della pagina anziché nel corpo del corpo.
   * I CSS non vengono caricati solo se la categoria è presente nel **campo Librerie** client.

* **Libreria
client Risorse Web** La categoria libreria client utilizzata per distribuire risorse Web come preferiti.

![](assets/screenshot_2018-10-19at104949.png)

Le librerie possono essere configurate per i campi **Head Library** (Librerie client) **e Client Libraries javascript come** indicato di seguito:

* Per aggiungere un nuovo campo, tocca o fai clic sul **pulsante Aggiungi** sotto i campi.
* Per rimuovere un campo, tocca o fai clic sull&#39;icona del cestino accanto al campo da rimuovere.
* Per ridisporre l&#39;ordine di caricamento, toccate o trascinate la maniglia accanto al campo da spostare.

Per ulteriori informazioni sull&#39;uso delle librerie lato client, consultate [Utilizzo delle librerie lato client](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html).

>[!CAUTION]
>
>La capacità di definire separatamente le librerie client per l&#39;intestazione della pagina è stata introdotta con i componenti core versione 2.2.0.

### Scheda Stili {#styles-tab}

Il componente Pagina supporta il sistema [di stile AEM](authoring.md#component-styling).