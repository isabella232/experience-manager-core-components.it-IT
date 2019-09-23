---
title: Componente Breadcrumb
seo-title: Componente Breadcrumb
description: 'null'
seo-description: Il componente di base Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.
uuid: 13e858d5-24ad-4144-adc4-0fa1ffd257c1
contentOwner: Utente
content-type: riferimento
topic-tags: authoring
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: ecd237df-08b8-4deb-9881-66a1f0d65ef3
modalsize: 426x240
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Componente Breadcrumb{#breadcrumb-component}

Il componente di base Breadcrumb è un componente di navigazione che crea una breadcrumb di collegamenti in base alla posizione della pagina nella gerarchia dei contenuti.

## Utilizzo {#usage}

Il componente Breadcrumb visualizza la posizione della pagina corrente all’interno della gerarchia del sito, consentendo ai visitatori della pagina di spostarsi nella gerarchia di pagina dalla posizione corrente. Questa funzione è spesso integrata nelle intestazioni o nei piè di pagina della pagina.

Le opzioni disponibili, come il livello di navigazione predefinito e la possibilità di visualizzare la pagina corrente o le pagine nascoste, possono essere definite dall'autore del modello nella finestra di dialogo [](#design-dialog)della progettazione. L’editor dei contenuti può quindi scegliere se visualizzare o meno le pagine nascoste e il livello di navigazione effettivo per il componente nella finestra di dialogo [di](#edit-dialog)modifica.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Breadcrumb è v2, introdotta con la release 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](breadcrumb-v1.md) | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Breadcrumb e per visualizzare esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la libreria [](http://opensource.adobe.com/aem-core-wcm-components/library/breadcrumb/hidden/level-1/level-2/breadcrumb.html)dei componenti.

>[!NOTE]
>
>Nella release 2.1.0 dei componenti core, il componente Breadcrumb supporta i microdati [](https://schema.org/BreadcrumbList)schema.org.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Breadcrumb [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Edit Dialog {#edit-dialog}

La finestra di dialogo di modifica consente all’autore del contenuto di eliminare le pagine nascoste e attive nelle breadcrumb e la profondità nella gerarchia che dovrebbe visualizzare.

![](assets/screen_shot_2018-01-12at124250.png)

* **Livello** iniziale navigazione - Punto della gerarchia in cui il componente breadcrumb deve iniziare a camminare verso il basso fino alla pagina corrente. Ad esempio in We.Retail:

   * 0 inizia da `/content`

   * 1 inizia a `/content/we-retail`
   * 2 inizia a `/content/we-retail/<country>`

* **Mostra elementi** di navigazione nascosti - Mostra pagine contrassegnate come nascoste nel percorso di navigazione (per impostazione predefinita non vengono visualizzate)
* **Nascondi pagina** corrente - Elimina la pagina corrente nel percorso di navigazione (per impostazione predefinita verrà visualizzata)

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all'autore del modello di definire i valori predefiniti per le opzioni che consentono di eliminare le pagine nascoste e attive nelle breadcrumb, nonché la profondità nella gerarchia che dovrebbe visualizzare.

### Scheda Principale {#main-tab}

![](assets/screen_shot_2018-01-12at124437.png)

* **Livello** iniziale navigazione - Definisce il valore predefinito per la posizione nella gerarchia in cui il componente breadcrumb deve iniziare a camminare verso il basso fino alla pagina corrente quando il componente breadcrumb viene aggiunto a una pagina.
* **Mostra elementi** di navigazione nascosti - Definisce il valore predefinito dell'opzione **Mostra elementi** di navigazione nascosti quando il componente breadcrumb viene aggiunto a una pagina.

   * Non attiva o disattiva l’opzione per l’autore. Imposta solo il valore predefinito.

* **Nascondi pagina** corrente - Definisce il valore predefinito dell’opzione **Nascondi pagina** corrente quando il componente breadcrumb viene aggiunto a una pagina.

   * Non attiva o disattiva l’opzione per l’autore. Imposta solo il valore predefinito.

### Scheda Stili {#styles-tab}

Il componente Breadcrumb supporta AEM [Style System](authoring.md#component-styling).