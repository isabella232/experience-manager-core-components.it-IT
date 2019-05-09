---
title: Componente Breadcrumb
seo-title: Componente Breadcrumb
description: 'null'
seo-description: Il componente Breadcrumb di base è un componente di navigazione che genera un breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.
uuid: 13 e 858 d 5-24 ad -4144-adc 4-0 fa 1 ffd 257 c 1
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: ecd 237 df -08 b 8-4 deb -9881-66 a 1 f 0 d 65 ef 3
modalsize: 426x240
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# Componente Breadcrumb{#breadcrumb-component}

Il componente Breadcrumb di base è un componente di navigazione che genera un breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.

## Utilizzo {#usage}

Il componente Breadcrumb visualizza la posizione della pagina corrente nella gerarchia del sito, consentendo ai visitatori della pagina di navigare nella gerarchia delle pagine dalla posizione corrente. Spesso si integra in intestazioni di pagina o piè di pagina.

Le opzioni disponibili, ad esempio il livello di navigazione predefinito e la capacità di visualizzare la pagina o pagine nascoste, possono essere definite dall&#39;autore del modello nella finestra di dialogo [di progettazione](#design-dialog). L&#39;Editor di contenuto può quindi scegliere se mostrare o meno pagine nascoste e il livello di navigazione effettivo per il componente nella finestra di dialogo [di modifica](#edit-dialog).

## Versione e Compatibilità {#version-and-compatibility}

La versione corrente del componente Breadcrumb è v 2, introdotta con la release 2.0.0 dei Componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](breadcrumb-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, vedi Versioni componenti [core del documento](versions.md).

## Output componente campione {#sample-component-output}

Esempio di esempio prelevato da [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html).

### Schermata {#screenshot}

![](assets/chlimage_1.png)

### HTML {#html}

```
<nav class="cmp-breadcrumb">
    <ol class="cmp-breadcrumb__list">
        <li class="cmp-breadcrumb__item">
            <a href="/content/we-retail/us.html" class="cmp-breadcrumb__item-link">
                United States
            </a>
        </li>
    
        <li class="cmp-breadcrumb__item">
            <a href="/content/we-retail/us/en.html" class="cmp-breadcrumb__item-link">
                English
            </a>
        </li>
    
        <li class="cmp-breadcrumb__item cmp-breadcrumb__item--active">
            
                Experience
            
        </li>
    </ol>
</nav>
```

### JSON {#json}

```
"breadcrumb":{  
                     "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                     "items":[  
                        {  
                           "page":{  
                              "path":"/content/we-retail/us",
                              "pageTitle":null,
                              "name":"us",
                              "description":null,
                              "title":"United States"
                           },
                           "active":false
                        },
                        {  
                           "page":{  
                              "path":"/content/we-retail/us/en",
                              "pageTitle":null,
                              "name":"en",
                              "description":null,
                              "title":"English"
                           },
                           "active":false
                        },
                        {  
                           "page":{  
                              "path":"/content/we-retail/us/en/experience",
                              "pageTitle":null,
                              "name":"experience",
                              "description":null,
                              "title":"Experience"
                           },
                           "active":true
                        }
                     ],
                     ":type":"weretail/components/content/breadcrumb"
                  }
```

>[!NOTE]
>
>Dalla release dei componenti core 2.1.0, il componente Breadcrumb supporta [schema.org microdati](https://schema.org/BreadcrumbList).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente relativa al componente [Breadcrumb è disponibile su github](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb).

Ulteriori dettagli sullo sviluppo di componenti core si trovano nella documentazione per sviluppatori [di componenti core](developing.md).

## Finestra di dialogo di modifica {#edit-dialog}

La finestra di dialogo di modifica consente all&#39;autore del contenuto di disattivare le pagine nascoste e attive nelle breadcrumb, oltre alla profondità nella gerarchia da visualizzare.

![](assets/screen_shot_2018-01-12at124250.png)

* **Livello** iniziale di navigazione: dove nella gerarchia il componente breadcrumb deve iniziare a spostarsi verso il basso fino alla pagina corrente. Ad esempio in We. Retail:

   * 0 inizia da `/content`

   * 1 inizia da `/content/we-retail`
   * 2 inizia da `/content/we-retail/<country>`

* **Mostra elementi** di navigazione nascosti: mostra pagine contrassegnate come nascoste nella breadcrumb (per impostazione predefinita, non vengono visualizzate)
* **Nascondi pagina corrente**- Elimina la pagina corrente nel percorso di navigazione (per impostazione predefinita, verrà visualizzata)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire i valori predefiniti da utilizzare per rimuovere le pagine nascoste e attive nelle breadcrumb e la profondità nella gerarchia da visualizzare.

### Scheda Principale {#main-tab}

![](assets/screen_shot_2018-01-12at124437.png)

* **Livello** iniziale di navigazione: definisce il valore predefinito per cui nella gerarchia il componente breadcrumb deve iniziare a spostarsi verso la pagina corrente quando il componente breadcrumb viene aggiunto a una pagina.
* **Mostra elementi** di navigazione nascosti: definisce il valore predefinito dell&#39;opzione **Mostra elementi** di navigazione nascosti quando il componente breadcrumb viene aggiunto a una pagina.

   * Non consente o disabilita l&#39;opzione per l&#39;autore. Imposta solo il valore predefinito.

* **Nascondi pagina corrente**: definisce il valore predefinito dell&#39;opzione **Nascondi pagina** corrente quando il componente breadcrumb viene aggiunto a una pagina.

   * Non consente o disabilita l&#39;opzione per l&#39;autore. Imposta solo il valore predefinito.

### Scheda Stili {#styles-tab}

Il componente Breadcrumb supporta il sistema [di stile AEM](authoring.md#component-styling).