---
title: Componente Breadcrumb (v1)
description: Il componente di base Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.
index: n
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 1%

---


# Componente Breadcrumb (v1) {#breadcrumb-component-v}

Il componente di base Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.

## Utilizzo {#usage}

Il componente Breadcrumb visualizza la posizione della pagina corrente all’interno della gerarchia del sito, consentendo ai visitatori della pagina di spostarsi nella gerarchia di pagina dalla posizione corrente. Questa funzione è spesso integrata nelle intestazioni o nei piè di pagina della pagina.

Le opzioni disponibili, come il livello di navigazione predefinito e la possibilità di mostrare la pagina corrente o le pagine nascoste, possono essere definite dall&#39;autore del modello nella finestra di dialogo di progettazione [](#design-dialog). L&#39;editor dei contenuti può quindi scegliere se visualizzare o meno le pagine nascoste e il livello di navigazione effettivo per il componente nella finestra di dialogo di [modifica](#edit-dialog).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la v1 del componente Breadcrumb, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è elencata la compatibilità di v1 del componente Breadcrumb.

| Versione di AEM | Breadcrumb Component v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Breadcrumb.
>Per informazioni dettagliate sulla versione corrente del componente Breadcrumb, consultare il documento [Breadcrumb Component](/help/components/breadcrumb.md).

## Esempio di output del componente {#sample-component-output}

Esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>L’esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, vedere le [informazioni sulla compatibilità per i componenti core v1](/help/versions.md).

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di eliminare le pagine nascoste e attive nelle breadcrumb e la profondità nella gerarchia che dovrebbe visualizzare.

![](/help/assets/chlimage_1-34.png)

* **Livello di navigazione per iniziare**  - Punto della gerarchia in cui il componente breadcrumb deve iniziare a camminare verso il basso fino alla pagina corrente. Ad esempio in We.Retail:

   * 1 inizia a `/content/we-retail`
   * 2 inizia da `/content/we-retail/<country>`

* **Mostra nascosto** : mostra le pagine contrassegnate come nascoste nel percorso di navigazione (per impostazione predefinita non vengono visualizzate)
* **Nascondi corrente**: elimina la pagina corrente nel percorso di navigazione (per impostazione predefinita verrà visualizzata)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire i valori predefiniti per le opzioni che consentono di eliminare le pagine nascoste e attive nelle breadcrumb, nonché la profondità nella gerarchia che dovrebbe visualizzare.

![](/help/assets/chlimage_1-35.png)

* **Livello di navigazione per iniziare**  - Definisce il valore predefinito per dove nella gerarchia il componente breadcrumb deve iniziare a camminare verso il basso fino alla pagina corrente quando il componente breadcrumb viene aggiunto a una pagina.
* **Mostra nascosto**  - Definisce il valore predefinito dell’opzione  **Mostra** nascosto quando il componente breadcrumb viene aggiunto a una pagina.

   * Non attiva o disattiva l’opzione per l’autore. Imposta solo il valore predefinito.

* **Nascondi corrente** : definisce il valore predefinito dell&#39;opzione  **Nascondi** corrente quando il componente breadcrumb viene aggiunto a una pagina.

   * Non attiva o disattiva l’opzione per l’autore. Imposta solo il valore predefinito.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Breadcrumb [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).
