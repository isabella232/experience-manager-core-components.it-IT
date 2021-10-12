---
title: Componente Breadcrumb (v1)
description: Il componente core Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia del contenuto.
index: n
role: Architect, Developer, Admin, User
exl-id: 4845e649-033a-43a8-b5ee-892a3f2a8b98
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '546'
ht-degree: 100%

---

# Componente Breadcrumb (v1) {#breadcrumb-component-v}

Il componente core Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia del contenuto.

## Utilizzo {#usage}

Il componente Breadcrumb visualizza la posizione della pagina corrente all’interno della gerarchia del sito, consentendo ai visitatori della pagina di spostarsi nella gerarchia delle pagine dalla posizione corrente. Questo componente è spesso integrato nelle intestazioni o nei piè di pagina.

Le opzioni disponibili, ad esempio il livello di navigazione predefinito e la possibilità di visualizzare la pagina corrente o le pagine nascoste, possono essere definite dall’autore del modello nella [finestra di dialogo per progettazione](#design-dialog). L’editor di contenuto può quindi scegliere se visualizzare o meno le pagine nascoste e il livello di navigazione effettivo del componente nella [finestra di dialogo per modifica](#edit-dialog).

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Breadcrumb, originariamente introdotto con la versione 1.0.0 dei Componenti core in AEM 6.3.

La tabella che segue riporta la compatibilità della versione 1 del componente Breadcrumb.

| Versione di AEM | Componente Breadcrumb v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Breadcrumb.
>Per informazioni dettagliate sulla versione corrente del componente Breadcrumb, vedi il documento [Componente Breadcrumb](/help/components/breadcrumb.md).

## Esempio di output del componente {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://experienceleague.adobe.com/docs/experience-manager-64/developing/bestpractices/we-retail/we-retail.html?lang=it).

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
>L’esportazione JSON dai Componenti core richiede la versione 1.1.0 dei Componenti core. Per ulteriori informazioni, vedi le [informazioni sulla compatibilità dei Componenti core v1](/help/versions.md).

## Finestra di dialogo per modifica {#edit-dialog}

La finestra di dialogo per modifica consente all’autore di contenuto di eliminare le pagine nascoste e attive nelle breadcrumb e l’annidamento nella gerarchia che deve visualizzare.

![](/help/assets/chlimage_1-34.png)

* **Livello di navigazione iniziale**: il punto nella gerarchia da cui il componente Breadcrumb deve iniziare scendere fino alla pagina corrente. Ad esempio, in We.Retail:

   * 1 inizia da `/content/we-retail`
   * 2 inizia da `/content/we-retail/<country>`

* **Mostra nascosti**: visualizza le pagine contrassegnate come nascoste nel breadcrumb (per impostazione predefinita non vengono visualizzate)
* **Nascondi corrente**: consente di eliminare la pagina corrente nella breadcrumb (per impostazione predefinita viene visualizzata)

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire i valori predefiniti per le opzioni di eliminazione delle pagine nascoste e attive nelle breadcrumb e l’annidamento nella gerarchia che deve visualizzare.

![](/help/assets/chlimage_1-35.png)

* **Livello di navigazione iniziale**: definisce il valore predefinito per il punto nella gerarchia da cui il componente Breadcrumb deve iniziare a scendere fino alla pagina corrente, quando il componente Breadcrumb viene aggiunto a una pagina.
* **Mostra nascosti**: definisce il valore predefinito dell’opzione **Mostra nascosti** quando il componente Breadcrumb viene aggiunto a una pagina.

   * Non abilita o disabilita l’opzione per l’autore. Imposta solo il valore predefinito.

* **Nascondi corrente**: definisce il valore predefinito dell’opzione **Nascondi corrente** quando il componente Breadcrumb viene aggiunto a una pagina.

   * Non abilita o disabilita l’opzione per l’autore. Imposta solo il valore predefinito.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Breadcrumb [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb).

L’intero progetto dei Componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).
