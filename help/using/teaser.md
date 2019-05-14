---
title: Componente teaser
seo-title: Componente teaser
description: Il componente teaser può mostrare un'immagine, un titolo, rich text ed eventualmente un collegamento a un altro contenuto.
seo-description: Il componente teaser può mostrare un'immagine, un titolo, rich text ed eventualmente un collegamento a un altro contenuto.
uuid: 46989314-df 37-448 b -8562-c 707043 f 2160
contentOwner: bohnert
content-type: riferimento
topic-tags: componenti core
discoiquuid: e 597 c 18 e -3643-41 be -9878-4 a 7872 f 1 ab 90
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# Componente teaser{#teaser-component}

Il componente Teaser componente core può mostrare un&#39;immagine, un titolo, rich text ed eventualmente un collegamento a un altro contenuto.

## Utilizzo {#usage}

Il componente Teaser consente all&#39;autore del contenuto di creare facilmente un teaser con un&#39;immagine, un titolo o un testo RTF e il collegamento a un altro contenuto o ad altre azioni.

L&#39;autore del modello può utilizzare la [finestra di dialogo](#design-dialog) di progettazione per definire se le opzioni per creare chiamate e aggiungere collegamenti sono disponibili, nonché disabilitare diverse opzioni di visualizzazione. L&#39;autore del contenuto può utilizzare la [finestra di dialogo](#configure-dialog) Configura per impostare un&#39;immagine, definire i CTAS, impostare titoli e descrizioni e configurare i collegamenti al singolo teaser. È possibile accedere alla [finestra di dialogo](image.md#edit-dialog) [di modifica del componente](image.md) Immagine per modificare l&#39;immagine teaser.

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Teaser è v 1, introdotta con la release 2.1.0 dei Componenti core a luglio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v1 | Compatibile | Compatibile | Compatibile |

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/screen_shot_2018-07-04at145042.png)

### Libreria componenti

Per provare il componente Teaser e vedere alcuni esempi delle opzioni di configurazione e l&#39;output HTML e JSON, visitare la [Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library/teaser.html).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente [Teaser è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Configura finestra di dialogo {#configure-dialog}

L&#39;autore del contenuto può utilizzare la finestra di dialogo Configura per definire le proprietà del singolo teaser. È inoltre disponibile una [finestra di dialogo](#edit-dialog) di modifica per modificare l&#39;immagine teaser, se selezionata.

### Immagine {#image}

![](assets/screen_shot_2018-07-03at104125.png)

* **Risorsa immagine**
   * Rilasciate una risorsa dal Browser [risorse](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) o toccate l&#39;opzione **di ricerca** da caricare da un file system locale.
   * Tocca o fai clic su **Cancella** per deselezionare l&#39;immagine correntemente selezionata.
   * Toccate o fate clic **su Modifica** per [gestire i rendering della risorsa](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) nell&#39;editor risorse.

### Testo {#text}

![](assets/screen_shot_2018-07-03at104138.png)

* **Titolo**
Definisce un titolo da visualizzare come intestazione del teaser.
* **Ottieni titolo dalla pagina
collegata** Quando questa opzione è selezionata, il titolo verrà popolato con il titolo della pagina collegata.
* **Descrizione**
Definisce una descrizione da visualizzare come sottoinsieme del teaser.
* **Ottieni descrizione dalla pagina
collegata** Quando questa opzione è selezionata, la descrizione verrà compilata con la descrizione della pagina collegata.

### Collegamenti e azioni {#links-actions}

![](assets/screen_shot_2018-07-03at104146.png)

* **** Collegamento collegamento applicato al teaser. Utilizzate il browser Percorsi per selezionare la destinazione del collegamento.
* **Abilita chiamata-azioni** quando questa opzione è selezionata, abilita la definizione di Call-to-Actions. Il primo collegamento Call-to-Action nell&#39;elenco viene usato come collegamento per altri elementi teaser.

## Finestra di dialogo di modifica {#edit-dialog}

Il componente Teaser delega il rendering delle immagini al componente [Immagine](image.md). Pertanto, la [finestra di dialogo]di modifica (image. md # edit-dialog del componente Immagine è disponibile per l&#39;autore del contenuto per manipolare l&#39;immagine teaser.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire le opzioni teaser che l&#39;autore del contenuto ha quando si utilizza questo componente.

### Scheda Teaser {#teaser-tab}

![](assets/screen_shot_2018-07-03at105958.png)

* **Inviti all&#39;azione**
   * **Disable Call-to-Actions**
Hide the **Call-to-Actions** option for content authors
* **Elementi**
   * **Nascondi titolo**
      * Nasconde l&#39;opzione **Titolo** per gli autori di contenuto
      * Quando è selezionato il tipo **** di titolo, viene nascosto
   * **Nascondi descrizione**
Nasconde l&#39;opzione **Descrizione** per gli autori di contenuto
* **Tipo
titolo** Definisce il tag H da utilizzare dal titolo del teaser.
* **Collegamenti**
   * **Non collegare l&#39;immagine**
Quando selezionata, l&#39;immagine teaser non è collegata
   * **Non collegare il titolo**
quando selezionato, il titolo del teaser non è collegato

### Scheda Stili {#styles-tab}

Il componente Teaser supporta il sistema [di stile AEM](authoring.md#component-styling).
