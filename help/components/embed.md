---
title: Componente di incorporamento
description: Il componente Incorpora consente di incorporare contenuto esterno in una pagina di contenuto AEM.
role: Architect, Developer, Admin, User
exl-id: 985fa304-70a3-4329-957e-76d1832a06f1
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '1341'
ht-degree: 2%

---

# Componente di incorporamento{#embed-component}

Il componente Incorpora componenti core consente di incorporare contenuto esterno in una pagina di contenuto AEM.

## Utilizzo {#usage}

Il componente di base Incorpora componente consente all’autore del contenuto di definire il contenuto esterno selezionato da incorporare all’interno di una pagina di contenuto AEM. Inoltre, è disponibile un’opzione per definire anche l’HTML in formato libero da incorporare.

* Le proprietà del componente possono essere definite nella finestra di dialogo [configura](#configure-dialog).
* I valori predefiniti per il componente quando lo si aggiunge a una pagina possono essere definiti nella finestra di dialogo [progettazione](#design-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente da incorporare è la v1, introdotta con la versione 2.7.0 dei componenti core a settembre 2019, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Compatibile | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione e dell’output HTML e JSON del componente da incorporare, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_embed).

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente da incorporare [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_embed_v1).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Configura {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire la risorsa esterna da incorporare nella pagina. Scegli innanzitutto il tipo di risorsa da incorporare:

* [URL](#url)
* [Contenuto incorporabile](#embeddable)
* [HTML](#html)

Per ogni tipo di incorporabile, puoi definire l&#39;annuncio **ID**. Questa opzione consente di controllare l&#39;identificatore univoco del componente nell&#39;HTML e nel [Livello dati](/help/developing/data-layer/overview.md).

* Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
* Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
* La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

### URL {#url}

L’incorporamento più semplice è l’URL. È sufficiente incollare l’URL della risorsa da incorporare nel campo **URL** . Il componente tenterà di accedere alla risorsa e, se può essere riprodotto da uno dei processori, visualizzerà un messaggio di conferma sotto il campo **URL** . In caso contrario, il campo verrà contrassegnato per errore.

Il componente Incorpora viene fornito con processori per i seguenti tipi di risorse:

* Risorse conformi allo [standard di incorporamento](https://oembed.com/), inclusi Facebook Post, Instagram, SoundCloud, Twitter e YouTube
* Pinterest

Gli sviluppatori possono aggiungere processori URL aggiuntivi [seguendo la documentazione per gli sviluppatori del componente di incorporamento.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![Finestra di dialogo di modifica del componente da incorporare per l’URL](/help/assets/embed-url.png)

### Contenuto incorporabile {#embeddable}

Le tabelle da incorporare consentono una maggiore personalizzazione della risorsa incorporata, che può essere parametrizzata e includere informazioni aggiuntive. Un autore può scegliere tra file da incorporare affidabili preconfigurati e il componente viene fornito con un YouTube incorporato pronto all’uso.

Il campo **Incorporabile** definisce il tipo di processore che si desidera utilizzare. Nel caso di YouTube embeddable puoi quindi definire:

* **ID video** : l’ID video univoco di YouTube della risorsa da incorporare
* **Larghezza**  - Larghezza del video incorporato
* **Altezza**  - Altezza del video incorporato
* **Abilita muto** : questo parametro specifica se il video verrà riprodotto in modo disattivato per impostazione predefinita. L’abilitazione di questa opzione aumenta le possibilità che Autoplay funzioni nei browser moderni.
* **Abilita riproduzione automatica** : questo parametro specifica se il video iniziale verrà avviato automaticamente al caricamento del lettore. Questa opzione è valida solo per l&#39;istanza di pubblicazione o quando si utilizza l&#39;opzione **Visualizza come pubblicato** sull&#39;istanza di authoring.
* **Abilita loop** : nel caso di un singolo video, questo parametro specifica se il lettore deve riprodurre ripetutamente il video iniziale. Nel caso di una playlist, il lettore riproduce l&#39;intera playlist e quindi riparte dal primo video.
* **Abilita riproduzione in linea (iOS)** : questo parametro controlla se i video vengono riprodotti in linea (on) o a schermo intero (off) in un lettore HTML5 su iOS.
* **Video correlati illimitati**  - Se questa opzione è disattivata, i video correlati verranno dallo stesso canale del video appena riprodotto, altrimenti verranno da qualsiasi canale.

Le opzioni &quot;enable&quot; devono essere attivate tramite la finestra di dialogo [Progettazione](#design-dialog) e possono essere impostate come valori predefiniti.

Altri elementi incorporati offrirebbero campi simili e possono essere definiti da uno sviluppatore da [seguendo la documentazione per gli sviluppatori del componente di incorporamento.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![Finestra di dialogo di modifica del componente da incorporare](/help/assets/embed-embeddable.png)

>[!NOTE]
>Per poter essere disponibili per l’autore della pagina, le tabelle da incorporare devono essere abilitate a livello di modello tramite la [finestra di dialogo di progettazione](#design-dialog) .

### HTML {#html}

Puoi aggiungere alla pagina codice HTML in formato libero utilizzando il componente Incorpora .

![Finestra di dialogo di modifica del componente da incorporare per HTML](/help/assets/embed-html.png)

>[!NOTE]
>Eventuali tag non sicuri, come gli script, verranno filtrati dall’HTML inserito e non verranno riprodotti nella pagina risultante.

#### Sicurezza {#security}

Il markup HTML che l’autore può immettere viene filtrato a scopo di sicurezza per evitare attacchi di script tra siti che potrebbero, ad esempio, consentire agli autori di ottenere diritti amministrativi.

*In generale,* tutti gli script e  `style` gli elementi nonché tutti gli attributi  `on*` e  `style` verranno rimossi dall’output.

Tuttavia, le regole sono più complicate perché il componente Incorpora segue AEM set di regole di filtro del framework HTML AntiSamy di pulizia globale, che si trovano in `/libs/cq/xssprotection/config.xml`. Se necessario, uno sviluppatore può sovrapporre questa impostazione per la configurazione specifica del progetto.

Ulteriori informazioni sulla sicurezza sono disponibili nella [documentazione per gli sviluppatori di AEM per le installazioni on-premise](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/security.html) e [AEM come installazioni di Cloud Service.](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/security/home.html)

>[!NOTE]
>Anche se le regole del framework di sanificazione anti-Samy possono essere configurate sovrapponendo `/libs/cq/xssprotection/config.xml`, queste modifiche influiscono su tutti i comportamenti HTL e JSP e non solo sul componente core di incorporamento.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore del contenuto che utilizza il componente da incorporare e le impostazioni predefinite al momento del posizionamento del componente da incorporare.

### Scheda Tipi da incorporare {#embeddable-types-tab}

![Finestra di dialogo di progettazione del componente da incorporare](/help/assets/embed-design.png)

* **Disattiva URL** : disabilita l’opzione  **** URL per l’autore del contenuto quando è selezionato
* **Disabilita elementi da incorporare** : disabilita l’opzione  **** Embedable per l’autore del contenuto quando selezionato, indipendentemente dai processori da incorporare consentiti.
* **Disabilita HTML**  - Disattiva l’opzione  **** HTML per l’autore del contenuto quando è selezionato.
* **Embeddables consentiti** : selezione multipla che definisce quali processori incorporabili sono disponibili per l’autore dei contenuti, a condizione che l’opzione  **** Embeddableoption sia attiva.

### Scheda YouTube {#youtube-tab}

![Scheda YouTube della finestra di dialogo di progettazione del componente da incorporare](/help/assets/embed-design-youtube.png)

* **Consenti configurazione del comportamento muto** : consente all’autore del contenuto di configurare l’opzione  **Abilita** muteopzione nel componente quando è selezionato il tipo di incorporamento di YouTube
   * **Valore predefinito muto** : imposta automaticamente  **Enable** Muteoption quando è selezionato il tipo di incorporamento YouTube
* **Consenti configurazione del comportamento di riproduzione automatica** : consente all’autore del contenuto di configurare l’opzione  **Abilita riproduzione** automatica nel componente quando è selezionato il tipo di incorporamento YouTube
   * **Valore predefinito dell&#39;esecuzione automatica** : imposta automaticamente l&#39;opzione  **Abilita** riproduzione automatica quando è selezionato il tipo di incorporamento YouTube
* **Consenti configurazione del comportamento del ciclo** : consente all’autore del contenuto di configurare l’opzione  **Abilita** percorso nel componente quando è selezionato il tipo di incorporamento YouTube
   * **Valore predefinito del ciclo** : imposta automaticamente  **Abilita** percorso quando è selezionato il tipo di incorporamento YouTube
* **Consenti configurazione della riproduzione in linea (iOS)** : consente all’autore del contenuto di configurare l’opzione  **Abilita riproduzione in linea (iOS)**  nel componente quando è selezionato il tipo di incorporamento YouTube
   * **Valore predefinito di riproduzione in linea (iOS)** : imposta automaticamente l&#39;opzione  **Abilita riproduzione in linea (iOS)**  quando è selezionato il tipo di incorporamento YouTube
* **Consenti configurazione di video in linea**  - Consente all’autore del contenuto di configurare la  **visualizzazione correlata senza restrizioni nel** componente quando è selezionato il tipo di incorporamento YouTube
   * **Valore predefinito dei video correlati senza restrizioni**  - Imposta automaticamente  **la** visualizzazione correlata senza restrizioni quando è selezionato il tipo di incorporamento YouTube
