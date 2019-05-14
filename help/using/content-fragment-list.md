---
title: Componente Elenco frammenti di contenuto
seo-title: Componente Elenco frammenti di contenuto
description: 'null'
seo-description: Il componente Elenco frammenti di contenuto di base consente la visualizzazione di un elenco di frammenti di contenuto.
contentOwner: bohnert
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
translation-type: tm+mt
source-git-commit: d683f8110b514860bba11e08e6923be49e92652f

---


# Componente Elenco frammenti di contenuto{#content-fragment-list-component}

Il componente Elenco frammenti di contenuto di base consente la visualizzazione di un elenco di frammenti [di contenuto](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html).

## Utilizzo {#usage}

Il componente Elenco frammenti di contenuto di base consente di includere un elenco di frammenti [di contenuto](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html) su una pagina in base a un modello di frammento di contenuto. Questo può essere particolarmente utile per creare [contenuti](https://helpx.adobe.com/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) headless che possono essere facilmente utilizzati da altre applicazioni.

* L&#39;elenco e le relative proprietà possono essere selezionate nella finestra di dialogo [Configura](#configure-dialog).
* Gli stili possono essere applicati al componente nella finestra di dialogo [di progettazione](#design-dialog).

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento di contenuto è v 1, introdotta con la release 2.4.0 dei componenti core a maggio 2019, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Per provare il componente Elenco frammenti di contenuto e visualizzare esempi di opzioni di configurazione e output HTML e JSON, visita la [Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment-list.html).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente relativa al componente [Elenco frammenti di contenuto è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/contentfragmentlist/v1/contentfragmentlist).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo Configura consente all&#39;autore del contenuto di definire i frammenti di contenuto che contengono l&#39;elenco e gli elementi di tali frammenti da includere.

### Scheda Proprietà

Nella **scheda Proprietà** sono definiti i frammenti di contenuto inclusi nell&#39;elenco. Questa funzione si basa principalmente su un modello di frammento di contenuto selezionato, ma sono disponibili altre opzioni filtro.

![](assets/screen-shot-2019-05-08-10.47.19.png)

* **Modello** - Percorso del modello di frammento di contenuto su cui si basa l&#39;elenco.
   * Per impostazione predefinita, tutti i frammenti di contenuto del modello definito come **Percorso** modello sono inclusi nell&#39;elenco.
* **Percorso padre** - Percorso padre da cui deve essere creato l&#39;elenco.
   * I frammenti di contenuto basati sul percorso **modello selezionato** verranno filtrati a quelli presenti sul percorso **principale specificato**.
   * Tocca o fai clic sul **pulsante Apri finestra di dialogo** Selezione a destra del campo per specificare il percorso.
* **Tag** - Verranno inclusi nell&#39;elenco solo i frammenti di contenuto con i tag specificati.
   * Tocca o fai clic sul **pulsante Apri finestra di dialogo** Selezione a destra del campo per specificare i tag.
   * Tocca o fai clic sulla X accanto ai tag selezionati per rimuoverli.


### Scheda Elementi

Per impostazione predefinita, tutti gli elementi del modello di frammento di contenuto saranno inclusi nell&#39;elenco. **Gli elementi** consentono di specificare solo gli elementi specifici da includere.

![](assets/screen-shot-2019-05-08-10.47.34.png)

* **Elementi** - Verranno visualizzati solo gli elementi dei frammenti di contenuto nell&#39;elenco specificato.
   * Tocca o fai clic sul **pulsante Aggiungi** per aggiungere un nuovo elemento
   * Tocca o fai clic sul **pulsante Elimina** per rimuovere un elemento selezionato
   * Trascinate la **maniglia Ordine** per riordinare l&#39;ordine degli elementi.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire gli stili applicati al componente Elenco frammenti di contenuto.