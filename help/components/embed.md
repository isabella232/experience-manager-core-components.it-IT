---
title: Incorpora componente
description: Il componente Incorpora consente di incorporare contenuto esterno in una pagina di contenuto AEM.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 2%

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

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento Versioni [dei componenti](/help/versions.md)core.

## Output componente di esempio {#sample-component-output}

Per provare il componente Incorpora e per vedere esempi delle relative opzioni di configurazione, nonché l’output HTML e JSON, visita la Libreria [](https://adobe.com/go/aem_cmp_library_embed)componenti.

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Embed [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_embed_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la documentazione [per lo sviluppatore di componenti](/help/developing/overview.md)core.

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire la risorsa esterna da incorporare nella pagina. Scegliete innanzitutto il tipo di risorsa da incorporare:

* [URL](#url)
* [Contenuto incorporabile](#embeddable)
* [HTML](#html)

Per ogni tipo di modulo da incorporare, puoi definire un **ID** annuncio. Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello [](/help/developing/data-layer/overview.md)dati.

* Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
* Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
* La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

### URL {#url}

L’incorporamento più semplice è l’URL. È sufficiente incollare l’URL della risorsa da incorporare nel campo **URL** . Il componente tenterà di accedere alla risorsa e, se può essere rappresentato da uno dei processori, visualizzerà un messaggio di conferma sotto il campo **URL** . In caso contrario, il campo verrà contrassegnato come errore.

Il componente Incorpora viene fornito con processori per i seguenti tipi di risorse:

* Risorse conformi allo standard [](https://oembed.com/) oEmbed, inclusi Facebook Post, Instagram, SoundCloud, Twitter e YouTube
* Pinterest

Gli sviluppatori possono aggiungere altri processori URL [seguendo la documentazione per gli sviluppatori del componente Incorpora.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![Finestra di dialogo di modifica del componente Incorpora per l’URL](/help/assets/embed-url.png)

### Contenuto incorporabile {#embeddable}

Le variabili da incorporare consentono una maggiore personalizzazione della risorsa incorporata, che può essere parametrizzata e che include informazioni aggiuntive. Un autore può scegliere tra file da incorporare affidabili preconfigurati e i componenti vengono forniti con un out-of-the-box integrabile su YouTube.

Il campo **Incorporabile** definisce il tipo di processore da utilizzare. Nel caso di YouTube embedable potete quindi definire:

* **ID** video - ID video univoco da YouTube della risorsa da incorporare
* **Larghezza** - La larghezza del video incorporato
* **Altezza** - L&#39;altezza del video incorporato

Altri elementi da incorporare offrirebbero campi simili e possono essere definiti da uno sviluppatore [seguendo la documentazione sviluppatore del componente Incorpora.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![Finestra di dialogo di modifica per i componenti da incorporare](/help/assets/embed-embeddable.png)

>[!NOTE]
>Per essere disponibili per l&#39;autore della pagina, le [schede di incorporamento devono essere abilitate a livello di modello tramite la finestra di dialogo](#design-dialog) Progettazione.

### HTML {#html}

È possibile aggiungere alla pagina codice HTML a forma libera utilizzando il componente Incorpora.

![Finestra di dialogo di modifica del componente Incorpora per HTML](/help/assets/embed-html.png)

>[!NOTE]
>Eventuali tag non sicuri, come gli script, verranno filtrati dall&#39;HTML immesso e non verranno rappresentati nella pagina risultante.

#### Sicurezza {#security}

La marcatura HTML che l&#39;autore può immettere viene filtrata a scopo di sicurezza per evitare attacchi di script tra siti che potrebbero, ad esempio, consentire agli autori di ottenere diritti amministrativi.

*In generale,* tutti gli elementi e `style` gli script, nonché tutti `on*` e `style` gli attributi, verranno rimossi dall&#39;output.

Tuttavia, le regole sono più complicate perché il componente Incorpora segue l’insieme di regole di filtraggio del framework HTML antiSamy di AEM, che è possibile trovare in `/libs/cq/xssprotection/config.xml`. Se necessario, lo sviluppatore può sovrapporre la configurazione specifica per il progetto.

Ulteriori informazioni sulla sicurezza sono disponibili nella documentazione per gli sviluppatori di [AEM per le installazioni](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/security.html) locali e per le installazioni di [AEM come servizio cloud.](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/security/home.html)

>[!NOTE]
>Anche se le regole del framework di sanificazione anti-Samy possono essere configurate tramite sovrapposizione `/libs/cq/xssprotection/config.xml`, queste modifiche influiscono su tutti i comportamenti HTL e JSP e non solo sul componente core di incorporamento.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire le opzioni disponibili per l&#39;autore del contenuto che utilizza il componente Incorpora e le impostazioni predefinite impostate al momento del posizionamento del componente Incorpora.

![Finestra di dialogo di progettazione di Incorpora componente](/help/assets/embed-design.png)

* **Disattiva URL** - Disattiva l&#39;opzione **URL** per l&#39;autore del contenuto selezionato
* **Disattiva incorporabili** - Disattiva l&#39;opzione **Incorporabile** per l&#39;autore del contenuto selezionato, indipendentemente dai processori incorporabili consentiti.
* **Disattiva HTML** - Disattiva l&#39;opzione **HTML** per l&#39;autore del contenuto selezionato.
* **Embeddables** consentiti - Multilegge che definisce quali processori incorporabili sono disponibili per l&#39;autore del contenuto, a condizione che l&#39;opzione **Embedable** sia attiva.
