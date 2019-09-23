---
title: Componente teaser
seo-title: Componente teaser
description: Il componente teaser può visualizzare un’immagine, un titolo, un testo RTF ed eventualmente un collegamento ad altri contenuti.
seo-description: Il componente teaser può visualizzare un’immagine, un titolo, un testo RTF ed eventualmente un collegamento ad altri contenuti.
uuid: 46989314-df37-448b-8562-c707043f2160
contentOwner: bohnert
content-type: riferimento
topic-tags: core-components
discoiquuid: e597c18e-3643-41be-9878-4a7872f1ab90
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Componente teaser{#teaser-component}

Il componente core Teaser può visualizzare un’immagine, un titolo, testo RTF e, facoltativamente, un collegamento ad altro contenuto.

## Utilizzo {#usage}

Il componente Teaser consente all’autore del contenuto di creare facilmente un teaser per ulteriore contenuto utilizzando un’immagine, un titolo o un RTF e collegando altri contenuti o altre azioni.

L’autore del modello può utilizzare la finestra di dialogo [di](#design-dialog) progettazione per definire se sono disponibili le opzioni per creare le azioni di chiamata e aggiungere collegamenti, nonché per disattivare diverse opzioni di visualizzazione. L’autore del contenuto può utilizzare la finestra di dialogo [di](#configure-dialog) configurazione per impostare un’immagine, definire CTA, impostare titoli e descrizioni e configurare collegamenti al singolo teaser. Per modificare l’immagine teaser è possibile accedere alla finestra di dialogo [di](image.md#edit-dialog) modifica del componente [](image.md) immagine.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Teaser è v1, introdotto con la release 2.1.0 dei componenti core nel luglio 2018, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v1 | Compatibile | Compatibile | Compatibile |

## Output componente di esempio {#sample-component-output}

Per provare il componente Teaser e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la libreria [dei](http://opensource.adobe.com/aem-core-wcm-components/library/teaser.html)componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Teaser [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Configura finestra di dialogo {#configure-dialog}

L’autore del contenuto può utilizzare la finestra di dialogo di configurazione per definire le proprietà del singolo teaser. È inoltre disponibile una finestra di dialogo [di](#edit-dialog) modifica per modificare l’immagine teaser se questa è selezionata.

### Immagine {#image}

![](assets/screen_shot_2018-07-03at104125.png)

* **Risorsa immagine**
   * Trascinate una risorsa dal browser [delle](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) risorse o toccate l'opzione **Sfoglia** per caricarla da un file system locale.
   * Toccate o fate clic su **Cancella** per deselezionare l'immagine attualmente selezionata.
   * Toccate o fate clic su **Modifica** per [gestire le rappresentazioni della risorsa](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) nell’editor risorse.

### Testo {#text}

![](assets/screen_shot_2018-07-03at104138.png)

* **Titolo** Definisce un titolo da visualizzare come titolo del teaser.
* **Ottieni titolo dalla pagina** collegata Se questa opzione è selezionata, il titolo verrà popolato con il titolo della pagina collegata.
* **Descrizione** Definisce una descrizione da visualizzare come sottovoce del teaser.
* **Ottieni descrizione dalla pagina** collegata Se questa opzione è selezionata, la descrizione della pagina collegata verrà compilata con la relativa descrizione.

### Collegamenti e azioni {#links-actions}

![](assets/screen_shot_2018-07-03at104146.png)

* **Collegamento** Collegamento applicato al teaser. Utilizza il browser dei percorsi per selezionare la destinazione del collegamento.
* **Abilita Call-To-Actions** Se questa opzione è selezionata, abilita la definizione di Call-To-Actions. Il primo collegamento Invito all’azione nell’elenco viene usato come collegamento per altri elementi teaser.

## Edit Dialog {#edit-dialog}

Il componente Teaser delega il rendering delle immagini al componente [](image.md)Immagine. Pertanto, la finestra di dialogo [di]modifica (image.md#edit-dialog del componente Immagine) è disponibile per l’autore del contenuto e può manipolare l’immagine teaser.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire le opzioni teaser di cui dispone l’autore del contenuto quando utilizza questo componente.

### Scheda teaser {#teaser-tab}

![](assets/screen_shot_2018-07-03at105958.png)

* **Inviti all'azione**
   * **Disattiva Call-To-Actions** Nascondi l’opzione **Call-To-Actions** per gli autori dei contenuti
* **Elementi**
   * **Nascondi titolo**
      * Nasconde l’opzione **Titolo** per gli autori di contenuti
      * Quando è selezionato il tipo **di** titolo è nascosto
   * **Nascondi descrizione** Nascondi l’opzione **Descrizione** per gli autori del contenuto
* **Tipo** titolo Definisce il tag H da utilizzare per il titolo del teaser.
* **Collegamenti**
   * **Non collegare l’immagine** Se selezionata, l’immagine teaser non è collegata
   * **Non collegare il titolo** Quando è selezionato, il titolo del teaser non è collegato

### Scheda Stili {#styles-tab}

Il componente Teaser supporta AEM [Style System](authoring.md#component-styling).
