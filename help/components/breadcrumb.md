---
title: Componente Breadcrumb
description: Il componente core Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia del contenuto.
role: Architect, Developer, Admin, User
exl-id: 19d65b9d-a407-4f50-9c55-8de0f12222ed
source-git-commit: 16930ccaa281f9d9c4ddbb890d4222e128557580
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 100%

---

# Componente Breadcrumb{#breadcrumb-component}

Il componente core Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia del contenuto.

## Utilizzo {#usage}

Il componente Breadcrumb visualizza la posizione della pagina corrente all’interno della gerarchia del sito, consentendo ai visitatori della pagina di spostarsi nella gerarchia delle pagine dalla posizione corrente. Questo componente è spesso integrato nelle intestazioni o nei piè di pagina.

Le opzioni disponibili, ad esempio il livello di navigazione predefinito e la possibilità di visualizzare la pagina corrente o le pagine nascoste, possono essere definite dall’autore del modello nella [finestra di dialogo per progettazione](#design-dialog). L’editor di contenuto può quindi scegliere se visualizzare o meno le pagine nascoste e il livello di navigazione effettivo del componente nella [finestra di dialogo per modifica](#edit-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Breadcrumb è la v3, introdotta con la versione 2.18.0 dei Componenti core a febbraio 2022, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- | --- |--- |---|
| v3 | - | Compatibile | Compatibile |
| [v2](v2/breadcrumb.md) | Compatibile | Compatibile | Compatibile |
| [v1](v1/breadcrumb-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, vedi il documento [Versioni dei Componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Breadcrumb e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_breadcrumb_it).

>[!NOTE]
>
>A partire dalla versione 2.1.0 dei Componenti core, il componente Breadcrumb supporta i [microdati schema.org](https://schema.org/BreadcrumbList).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Breadcrumb [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2_it).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per modifica {#edit-dialog}

La finestra di dialogo per modifica consente all’autore di contenuto di eliminare le pagine nascoste e attive nelle breadcrumb e l’annidamento nella gerarchia che deve visualizzare.

## Scheda Proprietà {#properties-tab}

![Finestra di dialogo per modifica del componente Breadcrumb](/help/assets/breadcrumb-edit.png)

* **Livello di navigazione iniziale**: il punto nella gerarchia da cui il componente Breadcrumb deve iniziare a scendere fino alla pagina corrente. Esempio:

   * 0 inizia da `/content`
   * 1 inizia da `/content/<yourSite>`
   * 2 inizia da `/content/<yourSite>/<country>`

* **Mostra elementi di navigazione nascosti**: mostra le pagine contrassegnate come nascoste nella breadcrumb (per impostazione predefinita non verranno visualizzate)
* **Nascondi pagina corrente**: consente di eliminare la pagina corrente nella breadcrumb (per impostazione predefinita verrà visualizzata)
* **Disattiva ombreggiatura**: se la pagina nella gerarchia è reindirizzata, viene visualizzato il nome della pagina di reindirizzamento al posto della pagina di destinazione. Per ulteriori informazioni, vedi [Supporto per la struttura del sito ombra](navigation.md#shadow-structure) del componente Navigazione.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e in [Data Layer](/help/developing/data-layer/overview.md).
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

### Scheda Stili {#styles-tab-edit}

![Scheda Stili della finestra di dialogo di modifica del componente Elenco breadcrumb](/help/assets/breadcrumb-edit-styles.png)

Il componente Breadcrumb supporta il [sistema di stili di AEM](/help/get-started/authoring.md#component-styling).

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nella [finestra di dialogo di progettazione](#design-dialog) affinché il menu a discesa sia disponibile.

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire i valori predefiniti per le opzioni di eliminazione delle pagine nascoste e attive nelle breadcrumb e l’annidamento nella gerarchia che deve visualizzare.

### Scheda Principale {#main-tab}

![](/help/assets/breadcrumb-design.png)

* **Livello di navigazione iniziale**: definisce il valore predefinito per il punto nella gerarchia da cui il componente Breadcrumb deve iniziare a scendere fino alla pagina corrente, quando il componente Breadcrumb viene aggiunto a una pagina.
* **Mostra elementi di navigazione nascosti**: definisce il valore predefinito dell’opzione **Mostra elementi di navigazione nascosti** quando il componente Breadcrumb viene aggiunto a una pagina.

   * Non abilita o disabilita l’opzione per l’autore. Imposta solo il valore predefinito.

* **Nascondi pagina corrente**: definisce il valore predefinito dell’opzione **Nascondi pagina corrente** quando il componente Breadcrumb viene aggiunto a una pagina.

   * Non abilita o disabilita l’opzione per l’autore. Imposta solo il valore predefinito.

* **Disattiva ombreggiatura**: definisce il valore predefinito dell’opzione **Disattiva ombreggiatura** quando il componente Breadcrumb viene aggiunto a una pagina.

### Scheda Stili {#styles-tab}

Il componente Breadcrumb supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

## Adobe Client Data Layer {#data-layer}

Il componente Breadcrumb supporta [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
