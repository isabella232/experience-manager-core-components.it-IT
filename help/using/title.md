---
title: Componente titolo
seo-title: Componente titolo
description: 'null'
seo-description: Il componente Titolo componente core è un componente di intestazione della sezione che offre funzioni di modifica locale.
uuid: cf 190861-e 5 cd -42 b 8-9193-842 b 8 df 8 c 5 c 6
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: 243 efc 75-fcf 9-427 d -9303-9642 b 0602991
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# Componente titolo{#title-component}

Il componente Titolo componente core è un componente di intestazione della sezione che offre funzioni di modifica locale.

## Utilizzo {#usage}

Il componente Titolo deve essere usato come titolo o intestazione di una sezione di contenuto. I livelli di intestazione disponibili possono essere definiti dall&#39;autore del modello nella finestra di dialogo [di progettazione](#design-dialog). L&#39;Editor di contenuto può selezionare i livelli dei titoli disponibili nella finestra di dialogo [di modifica](#edit-dialog). Per maggiore praticità, è disponibile anche una semplice modifica diretta del testo dell&#39;intestazione.

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Titolo è v 2, introdotta con la release 2.0.0 dei Componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](title-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/chlimage_1-36.png)

### Libreria componenti

Per provare il componente Titolo e vedere alcuni esempi delle opzioni di configurazione e l&#39;output HTML e JSON, visita la [Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library/title.html).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente [Titolo è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/title/v2/title).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Finestra di dialogo di modifica {#edit-dialog}

La finestra di dialogo di modifica consente all&#39;autore del contenuto di definire il testo del titolo e di selezionare il livello di intestazione.

* **Titolo** : se vuoto, verrà utilizzato il titolo della pagina
* **Tipo/Dimensione** : definisce il livello di intestazione del titolo
* **Collegamento** : definisce il contenuto a cui verrà collegato il titolo. Può essere un percorso a una pagina di contenuto, un URL esterno o un ancoraggio di pagina.

![](assets/screenshot_2018-10-19at110055.png)

>[!CAUTION]
>
>La capacità di definire un collegamento per il titolo è stata introdotta con la release 2.2.0 dei componenti core.

L&#39;editor locale può essere usato anche per modificare il testo del componente Titolo.

![](assets/chlimage_1-37.png)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire il livello di intestazione predefinito che i componenti titolo avranno quando creati dagli autori dei contenuti.

### scheda Dimensioni {#sizes-tab}

![](assets/screenshot_2018-10-19at110120.png)

* **Tipi/dimensioni consentiti per autori** - Abilita o disabilita i tipi di intestazione che saranno disponibili per gli autori di contenuto quando utilizzano il componente Titolo.
* **Tipo/Dimensione predefinito**: definisce il tipo di intestazione che verrà assegnato automaticamente quando un autore aggiunge il componente Titolo a una pagina.
* **Disattiva collegamento**: disabilitate il supporto per i collegamenti nel componente Titolo per impedire agli autori di contenuto di collegarsi dai titoli.

>[!CAUTION]
>
>La capacità di definire un collegamento per il titolo è stata introdotta con la release 2.2.0 dei componenti core.

### Scheda Stili {#styles-tab}

Il componente Titolo supporta il sistema [di stile AEM](authoring.md#component-styling).