---
title: Componente Condivisione social network
description: Il componente core Condivisione social network è un widget di condivisione Facebook e Pinterest.
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Social Sharing Component{#social-sharing-component}

Il componente core Condivisione social network è un widget di condivisione Facebook e Pinterest.

## Utilizzo {#usage}

Il componente Condivisione social network aggiunge alla pagina i collegamenti di condivisione Facebook e Pinterest. Spesso è inclusa nelle intestazioni o nei piè di pagina della pagina.

A differenza di altri componenti, le impostazioni per il componente Condivisione social network vengono eseguite dall’autore del modello tramite le proprietà [Pagina](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) iniziale e dall’autore del contenuto tramite Proprietà [](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)pagina.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Condivisione social network è v1, introdotto con la release 1.0.0 dei componenti core, ed è descritto in questo documento.

Nella tabella seguente sono illustrate tutte le versioni supportate del componente e le versioni AEM con cui sono compatibili le versioni del componente.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Condivisione social network e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visitate la Libreria [](https://adobe.com/go/aem_cmp_library_sharing)componenti.

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Condivisione [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_sharing_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Edit Dialog {#edit-dialog}

![Finestra di dialogo di modifica del componente Condivisione](/help/assets/sharing-edit.png)

* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [](/help/developing/data-layer/overview.md)dati.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

Poiché la condivisione richiede intestazioni di pagina speciali, qualsiasi condivisione deve essere abilitata a livello di pagina. Pertanto, per l’autore del contenuto ulteriori opzioni di modifica per il componente Condivisione sono disponibili tramite la scheda Condivisione nelle proprietà [della](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)pagina.

## Finestra di dialogo Progettazione {#design-dialog}

Poiché la condivisione richiede intestazioni di pagina speciali, qualsiasi condivisione deve essere abilitata a livello di pagina. Di conseguenza, per l’autore del modello le opzioni di progettazione per il componente Condivisione sono disponibili tramite le proprietà [di pagina](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)iniziali.
