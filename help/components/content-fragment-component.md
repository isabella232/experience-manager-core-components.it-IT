---
title: Componente frammento di contenuto
description: Il componente Frammento di contenuto del componente di base consente la visualizzazione di un frammento di contenuto.
translation-type: tm+mt
source-git-commit: d3ebcea5fa1523c1a986841cd3d1a64e16e85f6d
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 4%

---


# Componente frammento di contenuto{#content-fragment-component}

Il componente Frammento di contenuto del componente principale consente la visualizzazione di un [frammento di contenuto](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html).

>[!NOTE]
>
>Prima della release 2.4.0 dei componenti core, il componente Frammento di contenuto era disponibile come estensione per i componenti core e doveva essere scaricato separatamente e abilitato in modo esplicito.

## Utilizzo {#usage}

Il componente di base Frammento di contenuto del componente consente di includere in una pagina un [frammento di contenuto](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html).

* È possibile selezionare il frammento e le relative proprietà nella finestra di dialogo [Configura](#configure-dialog).
* I tipi di risorse per gestire determinate immagini e griglie possono essere definiti nella finestra di dialogo [progettazione](#design-dialog).
* L&#39;opzione di modifica consente di aprire il frammento selezionato all&#39;interno dell&#39;editor [frammento di contenuto](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento di contenuto è v1, introdotto con la release 1.1.0 dei componenti core a ottobre 2017, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
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
>Anche se entrambi sono v1, qualsiasi componente Frammento di contenuto utilizzato dalla cartella delle estensioni richiederà una migrazione dei componenti proxy correlati per utilizzare il nuovo tipo di risorsa quando si esegue l&#39;aggiornamento alla release 2.4.0 o successiva dei componenti core.

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente frammento di contenuto e per vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visita la [Libreria componenti](https://adobe.com/go/aem_cmp_library_cf).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente frammento di contenuto [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_cf_v1).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all&#39;autore del contenuto di definire il frammento di contenuto e gli elementi del frammento da includere.

### Scheda Proprietà {#properties-tab}

![Componente frammento di contenuto](/help/assets/content-fragment-edit-properties.png)

* **Frammento di contenuto**

   * Percorso del frammento di contenuto desiderato
   * Per individuare il frammento è possibile utilizzare la finestra di dialogo **Selezione**

* **Modalità di visualizzazione**
   * **Singolo elemento**  di testo - Abilita la selezione di un elemento di testo su più righe e abilita le opzioni di controllo del paragrafo
   * **Più elementi**  - Consente di selezionare uno o più elementi del frammento di contenuto selezionato
* **Elemento** : elemento o elementi del frammento di contenuto da includere
* **Variazione**  - Variazione del frammento di contenuto da utilizzare (impostazione predefinita:  **Master**)

* **Paragrafi**

   * **All** - Visualizza tutti i paragrafi
   * **Intervallo**

      * Specificare intervalli di paragrafi da visualizzare, separati da punto e virgola
      * Ad esempio `1;3-5;7;9-*` per includere il primo, il terzo il quinto, il settimo e il nono ai paragrafi finali
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [ ](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

### Scheda Controllo paragrafo {#paragraph-control-tab}

Questa scheda non è disponibile se è selezionata la modalità **Elementi multipli**.

![Componente frammento di contenuto](/help/assets/content-fragment-edit-paragraph.png)

* **Paragrafi** : consente la selezione di tutti i paragrafi o di un intervallo
* **Tratta il titolo come paragrafi propri**

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire i tipi di risorse utilizzati per gestire le immagini multimediali e le griglie reattive.

![Finestra di dialogo Progettazione del componente Frammento di contenuto](/help/assets/content-fragment-design.png)

* **Griglia reattiva interna**

   * Tipo di risorsa Sling utilizzato per la griglia reattiva interna

## Livello dati client  Adobe {#data-layer}

Il componente Frammento di contenuto supporta il [ livello dati client Adobe.](/help/developing/data-layer/overview.md)
