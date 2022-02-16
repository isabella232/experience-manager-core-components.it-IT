---
title: Componente Frammento di contenuto
description: Il componente core Frammento di contenuto consente la visualizzazione di un frammento di contenuto.
role: Architect, Developer, Admin, User
exl-id: 551ff2a1-f8db-490c-84a3-4255b364fc83
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 99%

---

# Componente Frammento di contenuto {#content-fragment-component}

Il componente core Frammento di contenuto consente la visualizzazione di un [frammento di contenuto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=it).

>[!NOTE]
>
>Prima della versione 2.4.0 dei Componenti core, il componente Frammento di contenuto era disponibile come estensione dei Componenti core e doveva essere scaricato separatamente e abilitato in modo esplicito.

## Utilizzo {#usage}

Il componente core Frammento di contenuto consente l’inclusione di un [frammento di contenuto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) in una pagina.

* Il frammento e le relative proprietà possono essere selezionati nella [finestra di dialogo per configurazione](#configure-dialog).
* I tipi di risorse per gestire determinate immagini e griglie possono essere definiti nella [finestra di dialogo per progettazione](#design-dialog).
* L’opzione Modifica apre il frammento selezionato all’interno dell’[editor di frammenti di contenuto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html?lang=it).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento di contenuto è la v1, introdotta con la versione 1.1.0 dei Componenti core a ottobre 2017, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile con<br>[versione 2.17.4](/help/versions.md) e precedenti | Compatibile | Compatibile |

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
>Anche se entrambi sono v1, ogni componente Frammento di contenuto che era stato utilizzato dalla cartella delle estensioni richiederà la migrazione dei relativi componenti proxy, per poter utilizzare il nuovo tipo di risorsa, durante l’aggiornamento alla versione 2.4.0 o successive dei Componenti core.

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Frammento di contenuto e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_cf_it).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Frammento di contenuto [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_cf_v1_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuto di definire il frammento di contenuto e gli elementi di quel frammento da includere.

### Scheda Proprietà {#properties-tab}

![Componente Frammento di contenuto](/help/assets/content-fragment-edit-properties.png)

* **Frammento di contenuto**

   * Il percorso del Frammento di contenuto desiderato
   * Per individuare il Frammento è possibile utilizzare la **finestra di dialogo per selezione**

* **Modalità di visualizzazione**
   * **Elemento di testo singolo**: consente la selezione di un elemento di testo su più righe e abilita le opzioni di controllo del paragrafo
   * **Più elementi**: consente di selezionare uno o più elementi del Frammento di contenuto selezionato
* **Elemento**: l’elemento o gli elementi del Frammento di contenuto da includere
* **Variante**: la variante del Frammento di contenuto da utilizzare (l’impostazione predefinita è **Principale**)

* **Paragrafi**

   * **Tutti**: visualizza tutti i paragrafi
   * **Intervallo**

      * Specificare gli intervalli di paragrafi da visualizzare, separati da punto e virgola
      * Ad esempio, specificare `1;3-5;7;9-*` per includere il primo, dal terzo al quinto, il settimo e il nono nei paragrafi finali
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

### Scheda Controllo paragrafo {#paragraph-control-tab}

Questa scheda non è disponibile quando è selezionata la modalità **Più elementi**.

![Componente Frammento di contenuto](/help/assets/content-fragment-edit-paragraph.png)

* **Paragrafi**: consente di selezionare tutti o un intervallo di paragrafi
* **Tratta le intestazioni come paragrafi**

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire i tipi di risorse utilizzati per gestire file multimediali e griglie reattive.

![Finestra di dialogo per progettazione del componente Frammento di contenuto](/help/assets/content-fragment-design.png)

* **Griglia reattiva interna**

   * Tipo di risorsa Sling utilizzato per la griglia reattiva interna

## Adobe Client Data Layer {#data-layer}

Il componente Frammento di contenuto supporta [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
