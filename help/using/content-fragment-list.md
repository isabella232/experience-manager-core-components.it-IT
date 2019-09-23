---
title: Componente Elenco frammenti di contenuto
seo-title: Componente Elenco frammenti di contenuto
description: 'null'
seo-description: Il componente Elenco frammenti di contenuto del componente principale consente la visualizzazione di un elenco di frammenti di contenuto.
contentOwner: bohnert
content-type: riferimento
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
translation-type: tm+mt
source-git-commit: d683f8110b514860bba11e08e6923be49e92652f

---


# Componente Elenco frammenti di contenuto{#content-fragment-list-component}

Il componente Elenco frammenti di contenuto del componente principale consente la visualizzazione di un elenco di frammenti di [contenuto](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html).

## Utilizzo {#usage}

Il componente core Componente Elenco frammenti di contenuto consente di includere un elenco di frammenti di [contenuto](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html) in una pagina basata su un modello di frammento di contenuto. Questa funzione può essere particolarmente utile per creare contenuti [](https://helpx.adobe.com/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) headless che possono essere facilmente utilizzati da altre applicazioni.

* L’elenco e le relative proprietà possono essere selezionati nella finestra di dialogo [di](#configure-dialog)configurazione.
* Gli stili possono essere applicati al componente nella finestra di dialogo [della](#design-dialog)progettazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente frammento di contenuto è v1, introdotto con la release 2.4.0 dei componenti core a maggio 2019, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Elenco frammenti di contenuto e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment-list.html)componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Elenco frammenti di contenuto [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/contentfragmentlist/v1/contentfragmentlist).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire i frammenti di contenuto che compongono l’elenco e gli elementi di tali frammenti da includere.

### Scheda Proprietà

La scheda **Proprietà** definisce i frammenti di contenuto inclusi nell'elenco. Si basa principalmente su un modello di frammento di contenuto selezionato, ma sono disponibili altre opzioni di filtro.

![](assets/screen-shot-2019-05-08-10.47.19.png)

* **Modello** - Percorso del modello di frammento di contenuto su cui si basa l'elenco.
   * Per impostazione predefinita, tutti i frammenti di contenuto del modello definito come Percorso **** modello sono inclusi nell'elenco.
* **Percorso** padre - Percorso padre da cui creare l'elenco.
   * I frammenti di contenuto basati sul percorso **del** modello selezionato verranno filtrati in base a quelli presenti nel percorso **** principale specificato.
   * Tocca o fai clic sul pulsante **Apri finestra di dialogo** selezione a destra del campo per specificare il percorso.
* **Tag** - Solo i frammenti di contenuto con i tag specificati saranno inclusi nell'elenco.
   * Tocca o fai clic sul pulsante **Apri finestra di dialogo** selezione a destra del campo per specificare i tag.
   * Tocca o fai clic sulla X accanto ai tag selezionati per rimuoverli.


### Scheda Elementi

Per impostazione predefinita, tutti gli elementi del modello di frammento di contenuto saranno inclusi nell'elenco. Gli **elementi** consentono di specificare solo elementi specifici da includere.

![](assets/screen-shot-2019-05-08-10.47.34.png)

* **Elementi** - Vengono visualizzati solo gli elementi dei frammenti di contenuto nell'elenco specificato.
   * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere un nuovo elemento
   * Tocca o fai clic sul pulsante **Elimina** per rimuovere un elemento selezionato
   * Trascinate la maniglia **Ordine** per riordinare gli elementi.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all'autore del modello di definire gli stili applicati al componente Elenco frammenti di contenuto.