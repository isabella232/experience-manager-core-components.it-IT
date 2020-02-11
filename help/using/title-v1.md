---
title: Componente titolo (v1)
description: Il componente Titolo componente di base è un componente di intestazione di sezione che include la modifica locale.
index: n
translation-type: tm+mt
source-git-commit: 945381996db443c227aa31f0aacb963071165681

---


# Componente titolo (v1){#title-component-v}

Il componente Titolo componente di base è un componente di intestazione di sezione che include la modifica locale.

## Utilizzo {#usage}

Il componente Titolo è destinato a essere utilizzato come titolo o intestazione di una sezione di contenuto.

I livelli di intestazione disponibili possono essere definiti dall’autore del modello nella finestra di dialogo [di](title-v1.md#main-pars_title_1995166862)progettazione. L’editor del contenuto può selezionare i livelli di intestazione disponibili nella finestra di dialogo [di](title-v1.md#main-pars_title)modifica. Per maggiore comodità, è disponibile anche la semplice modifica locale del testo dell’intestazione.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la v1 del componente Titolo, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

La tabella seguente elenca la compatibilità di v1 del componente Titolo.

| Versione di AEM | Componente titolo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Titolo.
>
>Per informazioni dettagliate sulla versione corrente del componente Titolo, consultare il documento [Titolo componente](title.md) .

## Output componente di esempio {#sample-component-output}

Esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/chlimage_1-36.png)

### HTML {#html}

```
<div class="cmp cmp-title aem-GridColumn aem-GridColumn--default--12">
     <h2>Welcome! This is our finest equipment!</h2>
</div>
```

### JSON {#json}

```
"title": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              ":type": "weretail/components/content/title",
              "jcr:title": "Welcome! This is our finest equipment!",
              "type": "h2"
            }
```

>[!NOTE]
>
>L’esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le informazioni sulla [compatibilità per i componenti core v1](versions.md#main-pars_title_236368006) .

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di definire il testo del titolo e selezionare il livello del titolo.

>[!NOTE]
>
>Un valore vuoto per il titolo causerà la visualizzazione del titolo della pagina.

![](assets/chlimage_1-91.png)

L’editor locale può essere utilizzato anche per modificare il testo del componente titolo.

![](assets/chlimage_1-37.png)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire il livello di intestazione predefinito che i componenti titolo avranno al momento della creazione da parte degli autori dei contenuti.

![](assets/chlimage_1-92.png)

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Titolo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.
