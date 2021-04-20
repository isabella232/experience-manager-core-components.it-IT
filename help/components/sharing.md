---
title: Componente di condivisione social network
description: Il componente di base per la condivisione social network è un widget di condivisione Facebook e Pinterest .
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 7%

---


# Componente di condivisione social network{#social-sharing-component}

Il componente di base per la condivisione social network è un widget di condivisione Facebook e Pinterest .

## Utilizzo {#usage}

Il componente Condivisione social aggiunge alla pagina i collegamenti di Facebook e Pinterest condivisi. Spesso è incluso nelle intestazioni o nei piè di pagina.

A differenza di altri componenti, le impostazioni per il componente Condivisione social vengono eseguite dall’autore del modello tramite [Proprietà pagina iniziale](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) e dall’autore del contenuto tramite [Proprietà pagina](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Condivisione social è la v1, introdotta con la versione 1.0.0 dei componenti core, ed è descritta in questo documento.

Nella tabella seguente sono descritte tutte le versioni supportate del componente e le versioni AEM con cui sono compatibili le versioni del componente.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per provare il componente Condivisione social e vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_sharing).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente di condivisione [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_sharing_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Modifica {#edit-dialog}

![Finestra di dialogo di modifica del componente Condivisione](/help/assets/sharing-edit.png)

* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

Poiché la condivisione richiede intestazioni di pagina speciali, qualsiasi condivisione deve essere abilitata a livello di pagina. Pertanto, per l’autore del contenuto sono disponibili opzioni di modifica aggiuntive per il componente di condivisione tramite la scheda di condivisione [proprietà pagina](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html).

## Finestra di dialogo Progettazione {#design-dialog}

Poiché la condivisione richiede intestazioni di pagina speciali, qualsiasi condivisione deve essere abilitata a livello di pagina. Pertanto, per l’autore del modello le opzioni di progettazione per il componente di condivisione sono disponibili tramite le [proprietà di pagina iniziale](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).
