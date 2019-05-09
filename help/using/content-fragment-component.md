---
title: Componente frammento di contenuto
seo-title: Componente frammento di contenuto
description: 'null'
seo-description: Il componente Frammento di contenuto componente core consente di visualizzare un frammento di contenuto.
uuid: ec 807 de 9-f 76 c -4850-9 ece-c 3 e 439 a 1 d 626
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: f 093 f 58 e -9755-4 a 4 f -803 a-ab 93 a 50 e 6870
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# Componente frammento di contenuto{#content-fragment-component}

Il componente Frammento di contenuto componente core consente di visualizzare un [frammento di contenuto](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html).

>[!NOTE]
>
>Prima della release 2.4.0 dei componenti core, il componente Frammento di contenuto era disponibile come estensione ai componenti core e doveva essere scaricato e attivato esplicitamente.

## Utilizzo {#usage}

Il componente Frammento di contenuto del componente core consente di includere un frammento [di contenuto](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html) su una pagina.

* Il frammento e le relative proprietà possono essere selezionate nella finestra di dialogo [Configura](#configure-dialog).
* I tipi di risorse per gestire determinate immagini e griglie possono essere definiti nella finestra di dialogo [di progettazione](#design-dialog).
* L&#39;opzione di modifica consente di aprire il frammento selezionato nell&#39;editor frammento [di contenuto](https://helpx.adobe.com/content/help/en/experience-manager/6-5/assets/using/content-fragments.html).

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento di contenuto è v 1, introdotta con la release 1.1.0 dei componenti core a ottobre 2017, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Per provare il componente Frammento di contenuto e vedere alcuni esempi delle opzioni di configurazione e l&#39;output HTML e JSON, visita la [Libreria componenti](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente [Frammento di contenuto è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragment/v1/contentfragment).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo Configura consente all&#39;autore del contenuto di definire il frammento di contenuto e gli elementi del frammento da includere.

![](assets/chlimage_1-87.png)

* **Frammento di contenuto**

   * Percorso del frammento di contenuto desiderato
   * La finestra di dialogo **Selezione** può essere usata per individuare il frammento

* **Elemento** : elemento del frammento di contenuto da includere
* **Variante** - Variazione del frammento di contenuto da utilizzare (impostazione predefinita **: Master**)

* **Paragrafi**

   * **Tutti** - Visualizza tutti i paragrafi
   * **Intervallo**

      * Specificare intervalli di paragrafi da visualizzare, separati da punto e virgola
      * Ad esempio `1;3-5;7;9-*` , per includere 1 st, tra 3 e 5 °, il 7 e il 9 per i paragrafi finali

* **Gestione dell&#39;intestazione come paragrafi propri**

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire i tipi di risorse utilizzati per gestire immagini miste e griglie reattive.

![](assets/chlimage_1-88.png)

* **Tipo di immagine da file multimediali diversi**

   * Tipo di risorse Sling utilizzato per il rendering di immagini da file multimediali diversi

* **Griglia reattiva interna**

   * Tipo di risorsa Sling utilizzato per la griglia reattiva interna