---
title: Componente Breadcrumb (v 1)
seo-title: Componente Breadcrumb (v 1)
description: Il componente Breadcrumb di base è un componente di navigazione che genera un breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.
seo-description: Il componente Breadcrumb di AEM Core è un componente di navigazione che genera un breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.
uuid: c 1 f 20 a 82-b 6 ff -4 a 3 c -920 a -6710084 a 69 f 2
content-type: riferimento
topic-tags: componenti core
discoiquuid: 0 b 3 a 7 d 8 f-d 110-424 f-b 531-ff 88 c 9 a 09128
disttype: dist5
gnavtheme: chiaro
groupsectionnavitems: 'no'
hidemerchandisingbar: eredita
hidepromocomponent: eredita
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# Componente Breadcrumb (v 1){#breadcrumb-component-v}

Il componente Breadcrumb di base è un componente di navigazione che genera un breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.

## Utilizzo {#usage}

Il componente Breadcrumb visualizza la posizione della pagina corrente nella gerarchia del sito, consentendo ai visitatori della pagina di navigare nella gerarchia delle pagine dalla posizione corrente. Spesso si integra in intestazioni di pagina o piè di pagina.

Le opzioni disponibili, ad esempio il livello di navigazione predefinito e la capacità di mostrare la pagina o pagine nascoste, possono essere definite dall&#39;autore del modello nella finestra di dialogo [di progettazione](breadcrumb-v1.md#main-pars_title_1995166862). L&#39;Editor di contenuto può quindi scegliere se mostrare o meno pagine nascoste e il livello di navigazione effettivo per il componente nella finestra di dialogo [di modifica](breadcrumb-v1.md#main-pars_title).

## Versione e Compatibilità {#version-and-compatibility}

Questo documento descrive v 1 del componente Breadcrumb, introdotto originariamente con la release 1.0.0 dei componenti core con AEM 6.3.

Nella tabella seguente è riportata la compatibilità della release v 1 del componente Breadcrumb.

| Versione di AEM | Componente Breadcrumb v 1 |
|--- |--- |
| 6.3 | Compatibile |
| 6.4 | Compatibile |

>[!CAUTION]
>
>Questo documento descrive la v 1 del componente Breadcrumb.
>Per informazioni dettagliate sulla versione corrente del componente Breadcrumb, consulta [il documento del componente](breadcrumb.md) Breadcrumb.

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/chlimage_1-33.png)

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
>L&#39;esportazione JSON dai componenti core richiede la release 1.1.0 dei componenti core. Per ulteriori informazioni, consultate le informazioni [di compatibilità per i componenti core v 1](versions.md#main-pars_title_236368006) .

## Finestra di dialogo di modifica {#edit-dialog}

La finestra di dialogo di modifica consente all&#39;autore del contenuto di disattivare le pagine nascoste e attive nelle breadcrumb, oltre alla profondità nella gerarchia da visualizzare.

![](assets/chlimage_1-34.png)

* **Livello di navigazione:** da dove inizia il componente breadcrumb per passare alla pagina corrente. Ad esempio in We. Retail:

   * 1 inizia da `/content/we-retail`
   * 2 inizia da `/content/we-retail/<country>`

* **Mostra nascosto** : mostra pagine contrassegnate come nascoste nella traccia breadcrumb (per impostazione predefinita non vengono visualizzate)
* **Nascondi corrente**: elimina la pagina corrente nel percorso di navigazione (per impostazione predefinita, verrà visualizzata)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire i valori predefiniti da utilizzare per rimuovere le pagine nascoste e attive nelle breadcrumb e la profondità nella gerarchia da visualizzare.

![](assets/chlimage_1-35.png)

* **Livello di navigazione da avviare** : definisce il valore predefinito per cui nella gerarchia il componente breadcrumb deve iniziare a spostarsi verso la pagina corrente quando il componente breadcrumb viene aggiunto a una pagina.
* **Mostra nascosto** : definisce il valore predefinito dell&#39;opzione **Mostra nascosto** quando il componente breadcrumb viene aggiunto a una pagina.

   * Non consente o disabilita l&#39;opzione per l&#39;autore. Imposta solo il valore predefinito.

* **Nascondi corrente** : definisce il valore predefinito dell&#39;opzione **Nascondi corrente** quando il componente breadcrumb viene aggiunto a una pagina.

   * Non consente o disabilita l&#39;opzione per l&#39;autore. Imposta solo il valore predefinito.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente relativa al componente [Breadcrumb è disponibile su github](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb).

L&#39;intero progetto componenti core può essere scaricato da github.

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).
