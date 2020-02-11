---
title: Componente pulsante
description: Il componente Pulsante componente core consente di creare e visualizzare un pulsante.
translation-type: tm+mt
source-git-commit: 65f900ad6759206a13f2bda6169900f62d968d8d

---


# Componente pulsante{#button-component}

Il componente Pulsante componente di base consente la configurazione e la visualizzazione di un pulsante su una pagina.

## Utilizzo {#usage}

Il componente Pulsante componente di base consente di includere un pulsante in una pagina.

* Le proprietà del pulsante possono essere selezionate nella finestra di dialogo [di](#configure-dialog)configurazione.
* Gli stili per il componente Pulsante possono essere definiti nella finestra di dialogo [di](#design-dialog)progettazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pulsante è v1, introdotto con la release 2.5.0 dei componenti core a giugno 2019, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM come servizio cloud |
|--- |--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Pulsante e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](https://adobe.com/go/aem_cmp_library_button)Componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Button [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_button_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il pulsante e il comportamento del visitatore e la sua visualizzazione sulla pagina.

### Scheda Proprietà {#properties-tab}

![](assets/screen-shot-2019-08-29-12.19.32.png)

* **Testo** - Testo da visualizzare sul pulsante
* **Collegamento** : collegamento a una pagina di contenuto all’interno di AEM, una risorsa esterna o un ancoraggio
   * Utilizzate la finestra di dialogo **di** selezione per scegliere un percorso in AEM.
* **Icona** - Identificatore per la visualizzazione di un&#39;icona nel pulsante

### Scheda Accessibilità {#accessibility-tab}

![](assets/screen-shot-2019-08-29-12.19.43.png)

Nella scheda **Accessibilità** , è possibile impostare i valori per le etichette di accessibilità [](https://www.w3.org/WAI/standards-guidelines/aria/) ARIA per il componente.

* **Etichetta** - Valore di un attributo etichetta ARIA per il componente

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Immagine supporta AEM [Style System](authoring.md#component-styling).
