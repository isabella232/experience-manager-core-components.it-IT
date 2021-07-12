---
title: Componente titolo (v1)
description: Il componente Titolo componente di base è un componente di intestazione di sezione che presenta funzioni di modifica diretta.
index: n
role: Architect, Developer, Admin, User
exl-id: 79549ac0-82f2-4ea0-9cce-d534d0b47b5c
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 2%

---

# Componente titolo (v1) {#title-component-v}

Il componente Titolo componente di base è un componente di intestazione di sezione che presenta funzioni di modifica diretta.

## Utilizzo {#usage}

Il componente Titolo deve essere utilizzato come titolo o intestazione di una sezione di contenuto.

I livelli di intestazione disponibili possono essere definiti dall&#39;autore del modello nella finestra di dialogo [progettazione](#design-dialog). L’editor dei contenuti può selezionare tra i livelli di intestazione disponibili nella finestra di dialogo [modifica](#edit-dialog). Per maggiore comodità, è disponibile anche una semplice modifica diretta del testo dell’intestazione.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Titolo, originariamente introdotto con la versione 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità di v1 del componente Titolo.

| Versione di AEM | Componente titolo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Titolo .
>
>Per informazioni dettagliate sulla versione corrente del componente Titolo, consulta il documento [Componente titolo](/help/components/title.md) .

## Output componente di esempio {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](/help/assets/chlimage_1-36.png)

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
>L’esportazione JSON dai componenti core richiede la versione 1.1.0 dei componenti core. Per ulteriori informazioni, consulta le [informazioni sulla compatibilità per i componenti core v1](/help/versions.md) .

## Finestra di dialogo Modifica {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di definire il testo del titolo e selezionare il livello del titolo.

>[!NOTE]
>
>Se si specifica un valore vuoto per il titolo, viene visualizzato il titolo della pagina.

![](/help/assets/chlimage_1-91.png)

L’editor locale può essere utilizzato anche per modificare il testo del componente titolo.

![](/help/assets/chlimage_1-37.png)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire il livello di intestazione predefinito che i componenti titolo avranno quando creati dagli autori dei contenuti.

![](/help/assets/chlimage_1-92.png)

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Titolo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title).

L’intero progetto dei componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .
