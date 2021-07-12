---
title: Componente Frammento di contenuto
description: Il componente Frammento di contenuto del componente core consente la visualizzazione di un frammento di contenuto.
role: Architect, Developer, Admin, User
exl-id: 551ff2a1-f8db-490c-84a3-4255b364fc83
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 7%

---

# Componente Frammento di contenuto{#content-fragment-component}

Il componente Frammento di contenuto del componente core consente la visualizzazione di un [frammento di contenuto](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/assets/content-fragments/content-fragments.html).

>[!NOTE]
>
>Prima della versione 2.4.0 dei componenti core, il componente Frammento di contenuto era disponibile come estensione per i componenti core e doveva essere scaricato separatamente e abilitato in modo esplicito.

## Utilizzo {#usage}

Il componente di base Frammento di contenuto consente l’inclusione di un [frammento di contenuto](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) in una pagina.

* Il frammento e le relative proprietà possono essere selezionati nella finestra di dialogo [configura](#configure-dialog).
* I tipi di risorse per gestire determinate immagini e griglie possono essere definiti nella finestra di dialogo [progettazione](#design-dialog).
* L’opzione di modifica aprirà il frammento selezionato all’interno dell’ [editor frammento di contenuto](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento di contenuto è la v1, introdotta con la versione 1.1.0 dei componenti core a ottobre 2017, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

>[!NOTE]
>
>Prima della versione 2.4.0, il componente Frammento di contenuto si trovava nella cartella delle estensioni.
>
> `apps/core/wcm/extension/components/contentfragment/v1/contentfragment`
> 
>Dalla versione 2.4.0 è stato spostato nella seguente posizione.
>
>`apps/core/wcm/components/contentfragment/v1/contentfragment`
>
>Anche se entrambi sono v1, qualsiasi componente Frammento di contenuto utilizzato dalla cartella delle estensioni richiederà una migrazione dei relativi componenti proxy per utilizzare il nuovo tipo di risorsa durante l’aggiornamento alla versione 2.4.0 o successiva dei componenti core.

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente Frammento di contenuto e dell’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_cf) .

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Frammento di contenuto [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_cf_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Configura {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il frammento di contenuto e gli elementi del frammento da includere.

### Scheda Proprietà {#properties-tab}

![Componente Frammento di contenuto](/help/assets/content-fragment-edit-properties.png)

* **Frammento di contenuto**

   * Percorso del frammento di contenuto desiderato
   * Per individuare il frammento è possibile utilizzare la finestra di dialogo di selezione **a1/>**

* **Modalità di visualizzazione**
   * **Elemento**  di testo singolo: abilita la selezione di un elemento di testo su più righe e abilita le opzioni di controllo del paragrafo
   * **Più elementi** : consente di selezionare uno o più elementi del frammento di contenuto selezionato
* **Elemento** : elemento o elementi del frammento di contenuto da includere
* **Variazione** : variante del frammento di contenuto da utilizzare (impostazione predefinita:  **Master**)

* **Paragrafi**

   * **Tutti**  - Visualizza tutti i paragrafi
   * **Intervallo**

      * Specificare gli intervalli di paragrafi da visualizzare, separati da punto e virgola
      * Ad esempio `1;3-5;7;9-*` per includere il primo, il terzo e il quinto, il settimo e il nono nei paragrafi finali
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

### Scheda Controllo Paragrafo {#paragraph-control-tab}

Questa scheda non è disponibile quando è selezionata la modalità **Elementi multipli** .

![Componente Frammento di contenuto](/help/assets/content-fragment-edit-paragraph.png)

* **Paragrafi** : consente la selezione di tutti i paragrafi o di un intervallo
* **Tratta l’intestazione come paragrafi propri**

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire i tipi di risorse utilizzate per gestire le immagini con file multimediali diversi e le griglie reattive.

![Finestra di dialogo Progettazione del componente Frammento di contenuto](/help/assets/content-fragment-design.png)

* **Griglia reattiva interna**

   * Tipo di risorsa Sling utilizzato per la griglia reattiva interna

## Livello dati client di Adobe {#data-layer}

Il componente Frammento di contenuto supporta [Livello dati client di Adobe.](/help/developing/data-layer/overview.md)
