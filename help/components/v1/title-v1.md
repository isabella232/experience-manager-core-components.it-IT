---
title: Componente Titolo (v1)
description: Il componente core Titolo è un componente di intestazione di sezione che offre funzioni di modifica diretta.
index: n
role: Architect, Developer, Admin, User
exl-id: 79549ac0-82f2-4ea0-9cce-d534d0b47b5c
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '337'
ht-degree: 100%

---

# Componente Titolo (v1) {#title-component-v}

Il componente core Titolo è un componente di intestazione di sezione che offre funzioni di modifica diretta.

## Utilizzo {#usage}

Il componente Titolo deve essere utilizzato come titolo o intestazione di una sezione di contenuto.

I livelli di intestazione disponibili possono essere definiti dall’autore del modello nella [finestra di dialogo per progettazione](#design-dialog). L’editor di contenuto può selezionare tra i livelli di intestazione disponibili nella [finestra di dialogo per modifica](#edit-dialog). Per maggiore comodità, è disponibile anche una semplice modifica diretta del testo dell’intestazione.

## Versione e compatibilità {#version-and-compatibility}

Questo documento descrive la versione 1 del componente Titolo, originariamente introdotto con la versione 1.0.0 dei Componenti core in AEM 6.3.

La tabella che segue riporta la compatibilità della versione 1 del componente Titolo.

| Versione di AEM | Componente Titolo v1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Titolo.
>
>Per informazioni dettagliate sulla versione corrente del componente Titolo, vedi il documento [Componente Titolo](/help/components/title.md).

## Esempio di output del componente {#sample-component-output}

Di seguito è riportato un esempio tratto da [We.Retail](https://experienceleague.adobe.com/docs/experience-manager-64/developing/bestpractices/we-retail/we-retail.html?lang=it).

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
>L’esportazione JSON dai Componenti core richiede la versione 1.1.0 dei Componenti core. Per ulteriori informazioni, vedi le [informazioni sulla compatibilità dei Componenti core v1](/help/versions.md).

## Finestra di dialogo per modifica {#edit-dialog}

La finestra di dialogo per modifica consente all’autore di contenuto di definire il testo del titolo e selezionare il livello dell’intestazione.

>[!NOTE]
>
>Se non viene specificato alcun titolo, viene visualizzato automaticamente il titolo della pagina.

![](/help/assets/chlimage_1-91.png)

L’editor locale può essere utilizzato anche per modificare il testo del componente Titolo.

![](/help/assets/chlimage_1-37.png)

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire il livello di intestazione predefinito dei componenti Titolo che vengono creati dagli autori di contenuto.

![](/help/assets/chlimage_1-92.png)

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Titolo [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title).

L’intero progetto dei Componenti core può essere scaricato da GitHub.

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).
