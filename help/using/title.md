---
title: Componente titolo
seo-title: Componente titolo
description: 'null'
seo-description: Il componente Titolo componente di base è un componente di intestazione di sezione che include la modifica locale.
uuid: cf190861-e5cd-42b8-9193-842b8df8c5c6
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 243efc75-fcf9-427d-9303-9642b0602991
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Componente titolo{#title-component}

Il componente Titolo componente di base è un componente di intestazione di sezione che include la modifica locale.

## Utilizzo {#usage}

Il componente Titolo è destinato a essere utilizzato come titolo o intestazione di una sezione di contenuto. I livelli di intestazione disponibili possono essere definiti dall’autore del modello nella finestra di dialogo [di](#design-dialog)progettazione. L’editor del contenuto può selezionare i livelli di intestazione disponibili nella finestra di dialogo [di](#edit-dialog)modifica. Per maggiore comodità, è disponibile anche la semplice modifica locale del testo dell’intestazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Titolo è v2, introdotta con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](title-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Titolo e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](http://opensource.adobe.com/aem-core-wcm-components/library/title.html)Componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Titolo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/title/v2/title).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di definire il testo del titolo e selezionare il livello del titolo.

* **Titolo** - Se vuoto, verrà utilizzato il titolo della pagina
* **Tipo/Dimensione** - Definisce il livello di intestazione del titolo
* **Collegamento** - Definisce il contenuto a cui verrà collegato il titolo. Può essere un percorso a una pagina di contenuto, un URL esterno o un ancoraggio di pagina.

![](assets/screenshot_2018-10-19at110055.png)

>[!CAUTION]
>
>La possibilità di definire un collegamento per il titolo è stata introdotta con la release 2.2.0 dei componenti core.

L’editor locale può essere utilizzato anche per modificare il testo del componente titolo.

![](assets/chlimage_1-37.png)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire il livello di intestazione predefinito che i componenti titolo avranno al momento della creazione da parte degli autori dei contenuti.

### Scheda Dimensioni {#sizes-tab}

![](assets/screenshot_2018-10-19at110120.png)

* **Tipi/dimensioni consentiti per gli autori** - Abilitare o disabilitare i tipi di intestazione che saranno disponibili per gli autori di contenuti quando utilizzano il componente Titolo.
* **Tipo/Dimensione** predefinita: consente di definire il tipo di intestazione che verrà assegnato automaticamente quando un autore di contenuto aggiunge il componente Titolo a una pagina.
* **Disattiva collegamento**- Disattiva il supporto per i collegamenti nel componente titolo per impedire agli autori di contenuti di collegare i titoli.

>[!CAUTION]
>
>La possibilità di definire un collegamento per il titolo è stata introdotta con la release 2.2.0 dei componenti core.

### Scheda Stili {#styles-tab}

Il componente Titolo supporta AEM [Style System](authoring.md#component-styling).