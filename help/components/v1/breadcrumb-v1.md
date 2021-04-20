---
title: Componente Breadcrumb (v1)
description: Il componente di base Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.
index: n
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 1%

---


# Componente Breadcrumb (v1) {#breadcrumb-component-v}

Il componente di base Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.

## Utilizzo {#usage}

Il componente Breadcrumb visualizza la posizione della pagina corrente all’interno della gerarchia del sito, consentendo ai visitatori della pagina di spostarsi nella gerarchia della pagina dalla posizione corrente. Questo è spesso integrato nelle intestazioni o nei piè di pagina.

Le opzioni disponibili, come il livello di navigazione predefinito e la possibilità di mostrare la pagina corrente o le pagine nascoste, possono essere definite dall’autore del modello nella finestra di dialogo [progettazione](#design-dialog). L’editor dei contenuti può quindi scegliere se visualizzare o meno le pagine nascoste e il livello di navigazione effettivo per il componente nella finestra di dialogo [modifica](#edit-dialog).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Breadcrumb, originariamente introdotto con la versione 1.0.0 dei componenti core con AEM 6.3.

La tabella seguente elenca la compatibilità della v1 del componente Breadcrumb.

| Versione di AEM | Componente Breadcrumb v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Breadcrumb.
>Per informazioni dettagliate sulla versione corrente del componente Breadcrumb, consulta il documento [Breadcrumb Component](/help/components/breadcrumb.md) .

## Output componente di esempio {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](/help/assets/chlimage_1-33.png)

### HTML {#html}

```
<div class="cmp cmp-breadcrumb aem-GridColumn aem-GridColumn--default--12">

<ol class="breadcrumb">
    <li class="breadcrumb-item ">
        <a href="/content/we-retail/us.html">
            United States
        </a>
    </li>

    <li class="breadcrumb-item ">
        <a href="/content/we-retail/us/en.html">
            English
        </a>
    </li>

    <li class="breadcrumb-item active">
        
            Experience
        
    </li>
</ol>
 
</div>
```

### JSON {#json}

```
"breadcrumb": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              ":type": "weretail/components/content/breadcrumb"
            }
```

>[!NOTE]
>
>L’esportazione JSON dai componenti core richiede la versione 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le [informazioni sulla compatibilità per i componenti core v1](/help/versions.md) .

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di eliminare le pagine nascoste e attive nelle breadcrumb e la profondità nella gerarchia che deve visualizzare.

![](/help/assets/chlimage_1-34.png)

* **Livello di navigazione da iniziare** : dove nella gerarchia il componente breadcrumb deve iniziare a spostarsi verso il basso fino alla pagina corrente. Ad esempio in We.Retail:

   * 1 inizia a `/content/we-retail`
   * 2 inizia a `/content/we-retail/<country>`

* **Mostra nascosto** : mostra le pagine contrassegnate come nascoste nel breadcrumb (per impostazione predefinita non vengono visualizzate)
* **Nascondi corrente**: consente di eliminare la pagina corrente nel breadcrumb (per impostazione predefinita verrà visualizzata).

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire i valori predefiniti per le opzioni di eliminazione delle pagine nascoste e attive nelle breadcrumb, nonché la profondità nella gerarchia da visualizzare.

![](/help/assets/chlimage_1-35.png)

* **Livello di navigazione per iniziare** : definisce il valore predefinito per la posizione nella gerarchia in cui il componente breadcrumb deve iniziare a spostarsi verso il basso nella pagina corrente quando il componente breadcrumb viene aggiunto a una pagina.
* **Mostra nascosto**  - Definisce il valore predefinito dell’opzione  **Mostra** nascosto quando il componente breadcrumb viene aggiunto a una pagina.

   * Non attiva o disattiva l’opzione per l’autore. Imposta solo il valore predefinito.

* **Nascondi corrente** : definisce il valore predefinito dell’opzione  **Nascondi** corrente quando il componente breadcrumb viene aggiunto a una pagina.

   * Non attiva o disattiva l’opzione per l’autore. Imposta solo il valore predefinito.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Breadcrumb [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .
