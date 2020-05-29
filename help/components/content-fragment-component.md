---
title: Componente frammento di contenuto
description: Il componente Frammento di contenuto del componente di base consente la visualizzazione di un frammento di contenuto.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 5%

---


# Componente frammento di contenuto{#content-fragment-component}

Il componente Frammento di contenuto del componente di base consente la visualizzazione di un frammento di [contenuto](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html).

>[!NOTE]
>
>Prima della release 2.4.0 dei componenti core, il componente Frammento di contenuto era disponibile come estensione per i componenti core e doveva essere scaricato separatamente e abilitato in modo esplicito.

## Utilizzo {#usage}

Il componente di base Frammento di contenuto del componente consente di includere un frammento di [contenuto](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) in una pagina.

* È possibile selezionare il frammento e le relative proprietà nella finestra di dialogo [di](#configure-dialog)configurazione.
* I tipi di risorse per gestire determinate immagini e griglie possono essere definiti nella finestra di dialogo [di](#design-dialog)progettazione.
* L&#39;opzione Modifica consente di aprire il frammento selezionato nell&#39;editor [frammento di](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html)contenuto.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento di contenuto è v1, introdotto con la release 1.1.0 dei componenti core a ottobre 2017, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

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

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Frammento di contenuto e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](https://adobe.com/go/aem_cmp_library_cf)componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Frammento di contenuto [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_cf_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all&#39;autore del contenuto di definire il frammento di contenuto e gli elementi del frammento da includere.

### Scheda Proprietà {#properties-tab}

![Componente frammento di contenuto](/help/assets/content-fragment-edit-properties.png)

* **Frammento di contenuto**

   * Percorso del frammento di contenuto desiderato
   * La finestra di dialogo **** Selezione consente di individuare il frammento

* **Modalità di visualizzazione**
   * **Singolo elemento** di testo - Abilita la selezione di un elemento di testo su più righe e abilita le opzioni di controllo del paragrafo
   * **Più elementi** - Consente di selezionare uno o più elementi del frammento di contenuto selezionato
* **Elemento** - L&#39;elemento o gli elementi del frammento di contenuto da includere
* **Variazione** - Variazione del frammento di contenuto da utilizzare (impostazione predefinita: **Master**)

* **Paragrafi**

   * **Tutto** - Visualizza tutti i paragrafi
   * **Intervallo**

      * Specificare intervalli di paragrafi da visualizzare, separati da punto e virgola
      * Ad esempio, `1;3-5;7;9-*` per includere il primo, il terzo e il quinto, il settimo e il nono fino agli ultimi paragrafi
* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

### Scheda Controllo paragrafo {#paragraph-control-tab}

Questa scheda non è disponibile quando è selezionata la modalità **Più elementi** .

![Componente frammento di contenuto](/help/assets/content-fragment-edit-paragraph.png)

* **Paragrafi** - Consenti selezione di tutti i paragrafi o di un intervallo
* **Tratta il titolo come paragrafi propri**

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire i tipi di risorse utilizzati per gestire le immagini multimediali e le griglie reattive.

![Finestra di dialogo Progettazione del componente Frammento di contenuto](/help/assets/content-fragment-design.png)

* **Griglia reattiva interna**

   * Tipo di risorsa Sling utilizzato per la griglia reattiva interna

