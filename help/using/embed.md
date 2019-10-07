---
title: Incorpora componente
seo-title: Incorpora componente
description: Il componente Incorpora consente di incorporare contenuto esterno in una pagina di contenuto AEM.
seo-description: Il componente Incorpora consente di incorporare contenuto esterno in una pagina di contenuto AEM.
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: 648a54d3ab76ec9a9dee10dc97a3f91e6b7509df

---


# Incorpora componente{#embed-component}

Il componente Incorpora componenti core consente di incorporare contenuto esterno in una pagina di contenuto AEM.

## Utilizzo {#usage}

Il componente core Incorpora componente permette all’autore del contenuto di definire il contenuto esterno selezionato da incorporare in una pagina di contenuto AEM. È inoltre disponibile un’opzione per definire anche l’HTML a forma libera da incorporare.

* Le proprietà del componente possono essere definite nella finestra di dialogo [di](#configure-dialog)configurazione.
* I valori predefiniti per il componente quando lo si aggiunge a una pagina possono essere definiti nella finestra di dialogo [](#design-dialog)della progettazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Incorpora è v1, introdotto con la release 2.7.0 dei componenti core a settembre 2019, ed è descritto in questo documento.

La tabella seguente elenca tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Incorpora e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](http://opensource.adobe.com/aem-core-wcm-components/library/embed.html)componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Embed [è disponibile su GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](developing.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire la risorsa esterna da incorporare nella pagina. Scegliete innanzitutto il tipo di risorsa da incorporare:

* [URL](#url)
* [Contenuto incorporabile](#embeddable)
* [HTML](#html)

### URL {#url}

L’incorporamento più semplice è l’URL. È sufficiente incollare l’URL della risorsa da incorporare nel campo **URL** . Il componente tenterà di accedere alla risorsa e, se può essere rappresentato da uno dei processori, visualizzerà un messaggio di conferma sotto il campo **URL** . In caso contrario, il campo verrà contrassegnato come errore.

Il componente Incorpora viene fornito con processori per i seguenti tipi di risorse:

* Risorse conformi allo standard [](https://oembed.com/) oEmbed, inclusi Facebook Post, Instagram, SoundCloud, Twitter e YouTube
* Pinterest

Gli sviluppatori possono aggiungere altri processori URL [seguendo la documentazione per gli sviluppatori del componente Incorpora.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![](assets/screen-shot-2019-09-25-10.08.29.png)

### Contenuto incorporabile {#embeddable}

Le variabili da incorporare consentono una maggiore personalizzazione della risorsa incorporata, che può essere parametrizzata e includere informazioni aggiuntive. Un autore può scegliere tra file da incorporare affidabili preconfigurati e i componenti vengono forniti con un out-of-the-box YouTube incorporato.

Il campo **Incorporabile** definisce il tipo di processore da utilizzare. Nel caso di YouTube embedable potete quindi definire:

* **ID** video - ID video univoco da YouTube della risorsa da incorporare
* **Larghezza** - La larghezza del video incorporato
* **Altezza** - L'altezza del video incorporato

Altri elementi da incorporare offrirebbero campi simili e possono essere definiti da uno sviluppatore [seguendo la documentazione sviluppatore del componente Incorpora.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![](assets/screen-shot-2019-09-25-10.15.00.png)

>[!NOTE]
>Per essere disponibili per l'autore della pagina, le [schede di incorporamento devono essere abilitate a livello di modello tramite la finestra di dialogo](#design-dialog) Progettazione.

### HTML {#html}

È possibile aggiungere alla pagina codice HTML a forma libera utilizzando il componente Incorpora.

![](assets/screen-shot-2019-09-25-10.20.00.png)

>[!NOTE]
>Eventuali tag non sicuri, come gli script, verranno filtrati dall'HTML immesso e non verranno rappresentati nella pagina risultante.

#### Protezione {#security}

La marcatura HTML che l'autore può immettere viene filtrata a scopo di sicurezza per evitare attacchi di script tra siti che potrebbero, ad esempio, consentire agli autori di ottenere diritti amministrativi.

*In generale,* tutti gli elementi e `style` gli script, nonché tutti `on*` e `style` gli attributi, verranno rimossi dall'output.

Tuttavia, le regole sono più complicate perché il componente Incorpora segue l’insieme di regole di filtraggio del framework HTML antiSamy di AEM, che è possibile trovare in `/libs/cq/xssprotection/config.xml`. Se necessario, questo può essere sovrapposto a una configurazione specifica per il progetto da parte di uno sviluppatore.

Ulteriori informazioni sulla sicurezza sono disponibili nella documentazione per gli sviluppatori di [AEM.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/security.html)

>[!NOTE]
>Anche se le regole del framework di sanificazione anti-Samy possono essere configurate tramite sovrapposizione `/libs/cq/xssprotection/config.xml`, queste modifiche influiscono su tutti i comportamenti HTL e JSP e non solo sul componente core di incorporamento.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all'autore del modello di definire le opzioni disponibili per l'autore del contenuto che utilizza il componente Incorpora e le impostazioni predefinite impostate al momento del posizionamento del componente Incorpora.

![](assets/screen-shot-2019-09-25-10.25.28.png)

* **Disattiva URL** - Disattiva l'opzione **URL** per l'autore del contenuto selezionato
* **Disattiva incorporabili** - Disattiva l'opzione **Incorporabile** per l'autore del contenuto selezionato, indipendentemente dai processori incorporabili consentiti.
* **Disattiva HTML** - Disattiva l'opzione **HTML** per l'autore del contenuto selezionato.
* **Embeddables** consentiti - Multilegge che definisce quali processori incorporabili sono disponibili per l'autore del contenuto, a condizione che l'opzione **Embedable** sia attiva.
