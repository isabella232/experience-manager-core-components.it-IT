---
title: Componente Titolo (v 1)
seo-title: Componente Titolo (v 1)
description: Il componente Titolo componente core è un componente di intestazione della sezione che offre funzioni di modifica locale.
seo-description: Il componente Titolo componente core è un componente di intestazione della sezione che offre funzioni di modifica locale.
uuid: 5 c 4 d 276 c-f 0 be -4122-a 15 e -3 f 7443 d 8 b 209
content-type: riferimento
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: a 028 ebef -2957-410 c -9 bab-a 7040 c 350 f 2 f
index: n
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# Componente Titolo (v 1){#title-component-v}

Il componente Titolo componente core è un componente di intestazione della sezione che offre funzioni di modifica locale.

## Utilizzo {#usage}

Il componente Titolo deve essere usato come titolo o intestazione di una sezione di contenuto.

I livelli di intestazione disponibili possono essere definiti dall&#39;autore del modello nella finestra di dialogo [di progettazione](title-v1.md#main-pars_title_1995166862). L&#39;Editor di contenuto può selezionare i livelli dei titoli disponibili nella finestra di dialogo [di modifica](title-v1.md#main-pars_title). Per maggiore praticità, è disponibile anche una semplice modifica diretta del testo dell&#39;intestazione.

## Versione e Compatibilità {#version-and-compatibility}

Questo documento descrive v 1 del componente Titolo, originariamente introdotto con la release 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità della release v 1 del componente Titolo.

| Versione di AEM | Componente titolo v 1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la versione 1 del componente Titolo.
>
>Per informazioni dettagliate sulla versione corrente del componente Titolo, [vedere](title.md) il documento Titolo titolo.

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>L&#39;esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consultate le informazioni [di compatibilità per i componenti core v 1](versions.md#main-pars_title_236368006) .

## Finestra di dialogo di modifica {#edit-dialog}

La finestra di dialogo di modifica consente all&#39;autore del contenuto di definire il testo del titolo e di selezionare il livello di intestazione.

>[!NOTE]
>
>Un valore vuoto per il titolo causa la visualizzazione del titolo della pagina.

![](assets/chlimage_1-91.png)

L&#39;editor locale può essere usato anche per modificare il testo del componente Titolo.

![](assets/chlimage_1-37.png)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire il livello di intestazione predefinito che i componenti titolo avranno quando creati dagli autori dei contenuti.

![](assets/chlimage_1-92.png)

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente [Titolo è disponibile su github](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title).

L&#39;intero progetto componenti core può essere scaricato da github.

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).
