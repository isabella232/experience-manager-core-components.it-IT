---
title: Componente Schede
seo-title: Componente Schede
description: Il componente Schede consente di creare più schede per disporre il contenuto in una pagina.
seo-description: Il componente Schede consente di creare più schede per disporre il contenuto in una pagina.
uuid: 46 f 71233-8 b 12-4887-a 0 c 6-ad 24 dc 469 cb 1
content-type: riferimento
topic-tags: componenti core
discoiquuid: 966 d 47 fb-d 35 d -4103-b 29 d -4 ef 0 aa 739 f 24
translation-type: tm+mt
source-git-commit: 48d23edbcdf4c4ed70d590cf6c6e4ac1db14f852

---


# Componente Schede

Il componente Tabella componenti core consente di organizzare il contenuto su più schede.

## Utilizzo {#usage}

Il componente Schede consente all'autore del contenuto di organizzare il contenuto della pagina all'interno di più schede.

La [finestra di dialogo](#edit-dialog) di modifica consente all'autore del contenuto di definire più schede e impostare la scheda attiva. Mediante la finestra di dialogo [](#design-dialog)di progettazione, l'autore del modello può definire quali componenti aggiungere alle schede e personalizzare gli stili.

>[!NOTE]
>
>Sono supportati i componenti di schede nidificati (schede all'interno delle schede).
>
>I componenti semplici (non nidificati) possono essere posizionati/selezionati utilizzando la struttura ad albero [del contenuto](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html), ma le schede nidificate non possono esserlo.

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Tabs è v 1, introdotta con la release 2.2.0 dei componenti core a ottobre 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Per provare il componente Schede e vedere alcuni esempi delle opzioni di configurazione e l'output HTML e JSON, visitare la [Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library/tabs.html).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente [Tabs è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all'autore del contenuto di creare, rinominare e ridisporre le schede e definire la scheda attiva.

### Scheda Elementi {#items-tab}

![](assets/screen-shot-2019-08-29-12.28.16.png)

Per aprire il selettore componenti, usate il **pulsante Aggiungi** per scegliere quale componente aggiungere come scheda. Una volta aggiunta, all'elenco viene aggiunta una voce contenente le colonne seguenti:

* **Icona** : l'icona del tipo di componente della scheda per facilitarne l'identificazione. Passate il mouse per visualizzare il nome completo del componente come descrizione comando.
* **Descrizione** : descrizione utilizzata come testo della scheda, in base al nome del componente selezionato per la scheda.
* **Elimina** : toccate o fate clic per eliminare la scheda dal componente di tabulazione.
* **Ridisponi** : tocca o fai clic e trascina per riordinare l'ordine delle schede.

### Scheda Proprietà {#properties-tab}

![](assets/screen-shot-2019-08-29-12.28.32.png)

Nella scheda **Proprietà** , l'autore del contenuto può definire la scheda attiva quando la pagina viene caricata. Con l'opzione **Predefinito** , verrà selezionata la prima scheda.

### Scheda Accessibilità {#accessibility-tab}

![](assets/screen-shot-2019-08-29-12.28.40.png)

Nella scheda **Accessibilità** , è possibile impostare i valori per [le etichette di accessibilità](https://www.w3.org/WAI/standards-guidelines/aria/) AIR per il componente.

* **Etichetta** : valore di un attributo label AIR per il componente

## Select Panel {#select-panel}

L'autore del contenuto può utilizzare l'opzione **Seleziona pannello** nella barra degli strumenti del componente per passare a un altro pannello per la modifica e per riorganizzare facilmente l'ordine delle schede.

![](assets/screenshot_2018-10-11at165417.png)

Una volta selezionata l'opzione **Seleziona pannello** nella barra degli strumenti del componente, le schede configurate vengono visualizzate come a discesa.

* L'elenco è ordinato dalla disposizione assegnata delle schede e si riflette nella numerazione.
* Il tipo di componente della scheda viene visualizzato per primo, seguita dalla descrizione della scheda in font più chiaro.

![](assets/screenshot_2018-10-11at165154.png)

* Toccando o facendo clic su una voce nel menu a discesa, passa alla scheda nell'editor.
* Le schede possono essere ridisposte in posizione utilizzando le maniglie di trascinamento.

>[!NOTE]
>
>Le schede non sono selezionabili dall'autore in modalità **Modifica** . Utilizzate [**la modalità Anteprima**](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) o l'opzione **[Visualizza come pubblicato](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** per interagire con le schede come un lettore del contenuto pubblicato.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all'autore del modello di definire quali componenti aggiungere come elementi al componente Schede e quali stili personalizzati sono disponibili per l'autore del contenuto.

### Scheda Componenti consentiti {#allowed-components-tab}

La **scheda Componenti** consentiti viene utilizzata per definire quali componenti possono essere aggiunti al componente tabulazioni dall'autore del contenuto.

Le funzioni scheda Componenti consentiti funzionano come la scheda con lo stesso nome quando [si definisce il criterio e le proprietà di un Contenitore di layout nell'Editor modelli.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Scheda Stili {#styles-tab}

Il componente Tabulazioni supporta il sistema [di stile AEM](authoring.md#component-styling).
