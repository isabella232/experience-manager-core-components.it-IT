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

Il componente core Incorpora componente permette all’autore del contenuto di definire il contenuto esterno selezionato da incorporare all’interno di una pagina di contenuto AEM. Inoltre, è disponibile un’opzione per definire anche l’HTML a forma libera da incorporare.

* Le proprietà del componente possono essere definite nella finestra di dialogo di [configurazione](#configure-dialog).
* I valori predefiniti per il componente quando viene aggiunto a una pagina possono essere definiti nella finestra di dialogo di progettazione [a1/>.](#design-dialog)

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Incorpora è v1, introdotto con la release 2.7.0 dei componenti core a settembre 2019, ed è descritto in questo documento.

Nella tabella seguente sono elencate tutte le versioni supportate del componente, le versioni AEM con cui sono compatibili le versioni del componente e i collegamenti alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4   | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consultare il documento [Versioni dei componenti core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per provare il componente Incorpora e vedere esempi delle relative opzioni di configurazione, nonché l&#39;output HTML e JSON, visitare la [Libreria componenti](https://adobe.com/go/aem_cmp_library_embed).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Incorpora [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_embed_v1).

Ulteriori dettagli sullo sviluppo di componenti core sono disponibili nella [documentazione per lo sviluppo di componenti core](/help/developing/overview.md).

## Configura finestra di dialogo {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire la risorsa esterna da incorporare nella pagina. Scegliete innanzitutto il tipo di risorsa da incorporare:

* [URL](#url)
* [Contenuto incorporabile](#embeddable)
* [HTML](#html)

Per ciascun tipo di modulo da incorporare, è possibile definire ad **ID**. Questa opzione consente di controllare l&#39;identificatore univoco del componente nell&#39;HTML e nel [Livello dati](/help/developing/data-layer/overview.md).

* Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato esaminando la pagina risultante.
* Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
* La modifica dell’ID può avere un impatto su CSS, JS e tracciamento dei livelli di dati.

### URL {#url}

L’incorporamento più semplice è l’URL. È sufficiente incollare l&#39;URL della risorsa da incorporare nel campo **URL**. Il componente tenterà di accedere alla risorsa e, se può essere rappresentato da uno dei processori, visualizzerà un messaggio di conferma sotto il campo **URL**. In caso contrario, il campo verrà contrassegnato come errore.

Il componente Incorpora viene fornito con processori per i seguenti tipi di risorse:

* Risorse conformi allo standard [oEmbed](https://oembed.com/), inclusi post di Facebook, Instagram, SoundCloud, Twitter e YouTube
* Pinterest

Gli sviluppatori possono aggiungere altri processori URL [seguendo la documentazione sviluppatore del componente Incorpora.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![Finestra di dialogo di modifica del componente Incorpora per l’URL](/help/assets/embed-url.png)

### Contenuto incorporabile {#embeddable}

Le variabili da incorporare consentono una maggiore personalizzazione della risorsa incorporata, che può essere parametrizzata e che include informazioni aggiuntive. Un autore può scegliere tra file da incorporare affidabili preconfigurati e i componenti vengono forniti con un out-of-the-box integrabile su YouTube.

Il campo **Embedable** definisce il tipo di processore da utilizzare. Nel caso di YouTube embedable potete quindi definire:

* **ID**  video - ID video univoco da YouTube della risorsa da incorporare
* **Larghezza**  - La larghezza del video incorporato
* **Altezza**  - L&#39;altezza del video incorporato

Altri elementi da incorporare offrirebbero campi simili e possono essere definiti da uno sviluppatore da [seguendo la documentazione sviluppatore del componente Incorpora.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![Finestra di dialogo di modifica per i componenti da incorporare](/help/assets/embed-embeddable.png)

>[!NOTE]
>Per essere disponibili per l&#39;autore della pagina, è necessario abilitare le variabili da incorporare a livello di modello tramite la finestra di dialogo [Progettazione](#design-dialog).

### HTML {#html}

È possibile aggiungere alla pagina codice HTML a forma libera utilizzando il componente Incorpora.

![Finestra di dialogo di modifica del componente Incorpora per HTML](/help/assets/embed-html.png)

>[!NOTE]
>Eventuali tag non sicuri, come gli script, verranno filtrati dall&#39;HTML immesso e non verranno rappresentati nella pagina risultante.

#### Sicurezza {#security}

La marcatura HTML che l&#39;autore può immettere viene filtrata a scopo di sicurezza per evitare attacchi di script tra siti che potrebbero, ad esempio, consentire agli autori di ottenere diritti amministrativi.

*In generale,* tutti gli script e  `style` gli elementi, nonché tutti  `on*` e  `style` gli attributi, verranno rimossi dall&#39;output.

Tuttavia, le regole sono più complicate perché il componente Incorpora segue AEM&#39;insieme di regole di filtraggio del framework HTML antiSamy, che si trova in `/libs/cq/xssprotection/config.xml`. Se necessario, lo sviluppatore può sovrapporre la configurazione specifica per il progetto.

Ulteriori informazioni sulla sicurezza sono reperibili nella [AEM documentazione per gli sviluppatori per le installazioni aziendali interne](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/security.html) e in AEM [come installazioni Cloud Service.](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/security/home.html)

>[!NOTE]
>Sebbene le regole del framework di sanificazione anti-Samy possano essere configurate sovrapponendo `/libs/cq/xssprotection/config.xml`, queste modifiche influiscono su tutti i comportamenti HTL e JSP e non solo sul componente core di incorporamento.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire le opzioni disponibili per l&#39;autore del contenuto che utilizza il componente Incorpora e le impostazioni predefinite impostate al momento del posizionamento del componente Incorpora.

![Finestra di dialogo di progettazione di Incorpora componente](/help/assets/embed-design.png)

* **Disattiva URL**  - Disattiva l&#39;opzione  **** URL per l&#39;autore del contenuto quando è selezionata
* **Disabilita incorporabili**  - Disattiva l&#39;opzione  **** Incorpora per l&#39;autore del contenuto quando è selezionata, indipendentemente da quali processori incorporabili sono consentiti.
* **Disattiva HTML**  - Disattiva l&#39;opzione  **** HTML per l&#39;autore del contenuto quando è selezionata.
* **Embeddables**  consentiti - Multilegge che definisce quali processori incorporabili sono disponibili per l&#39;autore del contenuto, a condizione che l&#39;opzione  **** Embeddable sia attiva.
