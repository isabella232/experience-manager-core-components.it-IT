---
title: Componente frammento di contenuto
seo-title: Componente frammento di contenuto
description: 'null'
seo-description: Il componente Frammento di contenuto del componente principale consente la visualizzazione di un frammento di contenuto.
uuid: ec807de9-f76c-4850-9ece-c3e439a1d626
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: f093f58e-9755-4a4f-803a-ab93a50e6870
translation-type: tm+mt
source-git-commit: 548972c65751b594cd62234d4681634a60fa41e2

---


# Componente frammento di contenuto{#content-fragment-component}

Il componente Frammento di contenuto del componente principale consente la visualizzazione di un frammento di [contenuto](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html).

>[!NOTE]
>
>Prima della release 2.4.0 dei componenti core, il componente Frammento di contenuto era disponibile come estensione per i componenti core e doveva essere scaricato separatamente e abilitato in modo esplicito.

## Utilizzo {#usage}

Il componente di base Frammento di contenuto del componente consente di includere un frammento di [contenuto](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html) in una pagina.

* È possibile selezionare il frammento e le relative proprietà nella finestra di dialogo [di](#configure-dialog)configurazione.
* I tipi di risorse per gestire determinate immagini e griglie possono essere definiti nella finestra di dialogo [di](#design-dialog)progettazione.
* L'opzione Modifica consente di aprire il frammento selezionato nell'editor [frammento di](https://helpx.adobe.com/content/help/en/experience-manager/6-5/assets/using/content-fragments.html)contenuto.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento di contenuto è v1, introdotto con la release 1.1.0 dei componenti core a ottobre 2017, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

>[!NOTE]
>
>Prima della release 2.4.0, il componente Frammento di contenuto si trovava nella cartella delle estensioni.
>
> `apps/core/wcm/extension/components/contentfragment/v1/contentfragment`
> 
>Dal 2.4.0 è stato spostato nel seguente percorso.
>
>`apps/core/wcm/components/contentfragment/v1/contentfragment`
>
>Anche se entrambi sono v1, qualsiasi componente Frammento di contenuto utilizzato dalla cartella delle estensioni richiederà una migrazione dei componenti proxy correlati per utilizzare il nuovo tipo di risorsa quando si esegue l'aggiornamento alla release 2.4.0 o successiva dei componenti core.

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Frammento di contenuto e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Frammento di contenuto [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/contentfragment/v1/contentfragment).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all'autore del contenuto di definire il frammento di contenuto e gli elementi del frammento da includere.

![](assets/chlimage_1-87.png)

* **Frammento di contenuto**

   * Percorso del frammento di contenuto desiderato
   * La finestra di dialogo **** Selezione consente di individuare il frammento

* **Elemento** - L'elemento del frammento di contenuto da includere
* **Variazione** - Variazione del frammento di contenuto da utilizzare (impostazione predefinita: **Master**)

* **Paragrafi**

   * **Tutto** - Visualizza tutti i paragrafi
   * **Intervallo**

      * Specificare intervalli di paragrafi da visualizzare, separati da punto e virgola
      * Ad esempio, `1;3-5;7;9-*` per includere il primo, il terzo e il quinto, il settimo e il nono ai paragrafi finali

* **Tratta il titolo come paragrafi propri**

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire i tipi di risorse utilizzati per gestire le immagini multimediali e le griglie reattive.

![](assets/chlimage_1-88.png)

* **Tipo di immagine da file multimediali diversi**

   * Tipo di risorse Sling utilizzato per il rendering di immagini da file multimediali diversi

* **Griglia reattiva interna**

   * Tipo di risorsa Sling utilizzato per la griglia reattiva interna