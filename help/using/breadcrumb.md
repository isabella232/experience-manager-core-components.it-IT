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
source-git-commit: c58826c133eb112b305fa4facbe2a81e577eb896

---


# Breadcrumb Component{#breadcrumb-component}

Il componente Breadcrumb di base è un componente di navigazione che genera un breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.

## Utilizzo {#usage}

Il componente Breadcrumb visualizza la posizione della pagina corrente nella gerarchia del sito, consentendo ai visitatori della pagina di navigare nella gerarchia delle pagine dalla posizione corrente. Spesso si integra in intestazioni di pagina o piè di pagina.

Available options, such as the default navigation level and the ability to show the current page or hidden pages, can be defined by the template author in the [design dialog](#design-dialog). The content editor can then choose if hidden pages should be shown or not and the actual navigation level for the component in the [edit dialog](#edit-dialog).

## Version and Compatibility {#version-and-compatibility}

La versione corrente del componente Breadcrumb è v 2, introdotta con la release 2.0.0 dei Componenti core a gennaio 2018, descritta in questo documento.

Nella tabella seguente sono riportate tutte le versioni supportate del componente, le versioni AEM con le quali le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](breadcrumb-v1.md) | Compatibile | Compatibile | Compatibile |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Breadcrumb Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/breadcrumb.html).

>[!NOTE]
>
>As of Core Components release 2.1.0, the Breadcrumb Component supports [schema.org microdata](https://schema.org/BreadcrumbList).

## Technical Details {#technical-details}

The latest technical documentation about the Breadcrumb Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all&#39;autore del contenuto di disattivare le pagine nascoste e attive nelle breadcrumb, oltre alla profondità nella gerarchia da visualizzare.

![](assets/screen_shot_2018-01-12at124250.png)

* **Livello** iniziale di navigazione: dove nella gerarchia il componente breadcrumb deve iniziare a spostarsi verso il basso fino alla pagina corrente. Ad esempio in We. Retail:

   * 0 starts at `/content`

   * 1 starts at `/content/we-retail`
   * 2 starts at `/content/we-retail/<country>`

* **Mostra elementi** di navigazione nascosti: mostra pagine contrassegnate come nascoste nella breadcrumb (per impostazione predefinita, non vengono visualizzate)
* **Nascondi pagina corrente**- Elimina la pagina corrente nel percorso di navigazione (per impostazione predefinita, verrà visualizzata)

## Design Dialog {#design-dialog}

La finestra di dialogo di progettazione consente all&#39;autore del modello di definire i valori predefiniti da utilizzare per rimuovere le pagine nascoste e attive nelle breadcrumb e la profondità nella gerarchia da visualizzare.

### Main Tab {#main-tab}

![](assets/screen_shot_2018-01-12at124437.png)

* **Livello** iniziale di navigazione: definisce il valore predefinito per cui nella gerarchia il componente breadcrumb deve iniziare a spostarsi verso la pagina corrente quando il componente breadcrumb viene aggiunto a una pagina.
* **Mostra elementi** di navigazione nascosti: definisce il valore predefinito dell&#39;opzione **Mostra elementi** di navigazione nascosti quando il componente breadcrumb viene aggiunto a una pagina.

   * Non consente o disabilita l&#39;opzione per l&#39;autore. Imposta solo il valore predefinito.

* **Nascondi pagina corrente**: definisce il valore predefinito dell&#39;opzione **Nascondi pagina** corrente quando il componente breadcrumb viene aggiunto a una pagina.

   * Non consente o disabilita l&#39;opzione per l&#39;autore. Imposta solo il valore predefinito.

### Styles Tab {#styles-tab}

The Breadcrumb Component supports the AEM [Style System](authoring.md#component-styling).