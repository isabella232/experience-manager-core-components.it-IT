---
title: Componente Elenco frammenti di contenuto
description: Il componente Elenco frammenti di contenuto del componente core consente la visualizzazione di un elenco di frammenti di contenuto.
role: Architect, Developer, Admin, User
exl-id: 0f2295b1-d287-4f72-8ee4-fa98c4850e53
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 5%

---

# Componente Elenco frammenti di contenuto{#content-fragment-list-component}

Il componente Elenco frammenti di contenuto del componente core consente la visualizzazione di un elenco di [frammenti di contenuto](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/assets/content-fragments/content-fragments.html).

## Utilizzo {#usage}

Il componente di base Elenco frammenti di contenuto consente di includere un elenco di [frammenti di contenuto](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) in una pagina basata su un modello di frammento di contenuto. Questa funzione può essere particolarmente utile per creare [contenuto headless](https://helpx.adobe.com/it/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) che può essere facilmente utilizzato da altre applicazioni.

* L&#39;elenco e le relative proprietà possono essere selezionate nella finestra di dialogo [configura](#configure-dialog).
* Gli stili possono essere applicati al componente nella finestra di dialogo [progettazione](#design-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento di contenuto è la v1, introdotta con la versione 2.4.0 dei componenti core a maggio 2019, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente Elenco frammenti di contenuto e dell’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_cflist) .

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Elenco frammenti di contenuto [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_cflist_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Configura {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire i frammenti di contenuto che compongono l’elenco e gli elementi di tali frammenti da includere.

### Scheda Proprietà

La scheda **Proprietà** definisce quali frammenti di contenuto includere nell’elenco. Si basa principalmente su un modello di frammento di contenuto selezionato, ma sono disponibili altre opzioni di filtro.

![Scheda Proprietà della finestra di dialogo di modifica del componente Elenco frammenti di contenuto](/help/assets/content-fragment-list-properties.png)

* **Modello** : percorso del modello di frammento di contenuto su cui è basato l’elenco.
   * Per impostazione predefinita, tutti i frammenti di contenuto del modello definito come **Percorso modello** sono inclusi nell’elenco.
* **Percorso padre** : percorso principale da cui creare l’elenco.
   * I frammenti di contenuto basati sul **Percorso modello** selezionato verranno filtrati su quelli presenti nel **Percorso padre** specificato.
      * Tocca o fai clic sul pulsante **Apri finestra di dialogo di selezione** a destra del campo per specificare il percorso.
* **Tag** : l’elenco includerà solo i frammenti di contenuto con i tag specificati.
   * Tocca o fai clic sul pulsante **Apri finestra di dialogo di selezione** a destra del campo per specificare i tag.
   * Tocca o fai clic sulla X accanto ai tag selezionati per rimuoverli.
* **Ordine per** : campo del modello di frammento di contenuto in base al quale verrà ordinato l’elenco
   * È possibile selezionare solo i campi di testo (compresi i campi numerici, di data e di ora).
* **Ordina**  - Ordinamento dell&#39;elenco in base al campo  **Ordine** byte
   * Crescente o decrescente
* **Numero massimo elementi** : numero massimo di elementi da visualizzare nell&#39;elenco
   * Nessun valore restituirà tutti gli elementi.
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

>[!NOTE]
>Le opzioni **Ordina per**, **Ordina ordine** e **Max Items** sono state introdotte con la versione 2.7.0 dei componenti core.

### Scheda Elementi

Per impostazione predefinita, tutti gli elementi del modello di frammento di contenuto saranno inclusi nell’elenco (a meno che non sia limitato dal campo **Elementi massimi** ). La scheda **Elementi** consente di specificare solo elementi specifici da includere.

![Scheda Elementi della finestra di dialogo di modifica del componente Elenco frammenti di contenuto](/help/assets/content-fragment-list-elements.png)

* **Elementi**  - Verranno visualizzati solo gli elementi dei frammenti di contenuto nell’elenco specificato.
   * Tocca o fai clic sul pulsante **Aggiungi** per aggiungere un nuovo elemento.
   * Tocca o fai clic sul pulsante **Elimina** per rimuovere un elemento selezionato.
   * Trascinare la maniglia **Ordine** per ridisporre l&#39;ordine degli elementi.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire gli stili applicati al componente Elenco frammenti di contenuto .
