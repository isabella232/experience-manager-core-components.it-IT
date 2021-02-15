---
title: Incorpora componente
description: Il componente Incorpora consente di incorporare contenuto esterno in una pagina di contenuto AEM.
translation-type: tm+mt
source-git-commit: 601bee9df2a82255c92fcf30b8dacde70b0583dc
workflow-type: tm+mt
source-wordcount: '1341'
ht-degree: 2%

---


# Incorpora componente{#embed-component}

Il componente Incorpora componenti core consente di incorporare contenuto esterno in una pagina di contenuto AEM.

## Utilizzo {#usage}

Il componente core Incorpora componente permette all’autore del contenuto di definire il contenuto esterno selezionato da incorporare in una pagina di contenuto AEM. È inoltre disponibile un’opzione per definire anche l’HTML a forma libera da incorporare.

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

Le variabili da incorporare consentono una maggiore personalizzazione della risorsa incorporata, che può essere parametrizzata e che include informazioni aggiuntive. Un autore può selezionare tra file incorporati attendibili preconfigurati e i componenti vengono forniti con un componente YouTube incorporato out-of-the-box.

Il campo **Embedable** definisce il tipo di processore da utilizzare. Nel caso di YouTube embedable potete quindi definire:

* **ID**  video - ID video univoco da YouTube della risorsa da incorporare
* **Larghezza**  - La larghezza del video incorporato
* **Altezza**  - L&#39;altezza del video incorporato
* **Abilita disattivazione audio** : questo parametro specifica se il video verrà riprodotto in modo disattivato per impostazione predefinita. Attivando questa opzione si aumenta la possibilità che Autoplay funzioni nei browser più recenti.
* **Abilita riproduzione**  automatica: questo parametro specifica se il video iniziale verrà avviato automaticamente al caricamento del lettore. Questa opzione è valida solo per l’istanza di pubblicazione o per l’opzione **Visualizza come pubblicato** nell’istanza di creazione.
* **Abilita loop**  - Nel caso di un singolo video, questo parametro specifica se il lettore deve riprodurre ripetutamente il video iniziale. Nel caso di una playlist, il lettore riproduce l&#39;intera playlist e riparte dal primo video.
* **Abilita riproduzione in linea (iOS)**  - Questo parametro controlla se i video vengono riprodotti in linea (on) o a schermo intero (off) in un lettore HTML5 su iOS.
* **Video**  correlati senza restrizioni - Se questa opzione è disattivata, i relativi video proverranno dallo stesso canale del video appena riprodotto, altrimenti proverranno da qualsiasi canale.

Tenere presente che le opzioni &quot;enable&quot; devono essere attivate tramite la finestra di dialogo [Progettazione](#design-dialog) e possono essere impostate come valori predefiniti.

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

Tuttavia, le regole sono più complicate perché il componente Incorpora segue AEM set di regole di filtraggio del framework HTML AntiSamy, che si trova in `/libs/cq/xssprotection/config.xml`. Se necessario, lo sviluppatore può sovrapporre la configurazione specifica per il progetto.

Ulteriori informazioni sulla sicurezza sono reperibili nella [AEM documentazione per gli sviluppatori per le installazioni aziendali interne](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/security.html) e in AEM [come installazioni Cloud Service.](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/security/home.html)

>[!NOTE]
>Sebbene le regole del framework di sanificazione anti-Samy possano essere configurate sovrapponendo `/libs/cq/xssprotection/config.xml`, queste modifiche influiscono su tutti i comportamenti HTL e JSP e non solo sul componente core di incorporamento.

## Finestra di dialogo Progettazione {#design-dialog}

La finestra di dialogo Progettazione consente all&#39;autore del modello di definire le opzioni disponibili per l&#39;autore del contenuto che utilizza il componente Incorpora e le impostazioni predefinite impostate al momento del posizionamento del componente Incorpora.

### Scheda Tipi incorporabili {#embeddable-types-tab}

![Finestra di dialogo di progettazione di Incorpora componente](/help/assets/embed-design.png)

* **Disattiva URL**  - Disattiva l&#39;opzione  **** URL per l&#39;autore del contenuto quando è selezionata
* **Disabilita incorporabili**  - Disattiva l&#39;opzione  **** Incorpora per l&#39;autore del contenuto quando è selezionata, indipendentemente da quali processori incorporabili sono consentiti.
* **Disattiva HTML**  - Disattiva l&#39;opzione  **** HTML per l&#39;autore del contenuto quando è selezionata.
* **Embeddables**  consentiti: selezione multipla che definisce quali processori incorporabili sono disponibili per l&#39;autore del contenuto, a condizione che sia attiva l&#39;opzione  **** Embeddable.

### Scheda YouTube {#youtube-tab}

![Scheda YouTube della finestra di dialogo di progettazione del componente Incorpora](/help/assets/embed-design-youtube.png)

* **Consenti configurazione del comportamento**  disattivazione audio: consente all&#39;autore del contenuto di configurare l&#39;opzione  **Abilita** muteoption nel componente quando è selezionato il tipo di incorporamento di YouTube
   * **Valore predefinito di disattivazione audio** : imposta automaticamente  **Abilita** muteoption quando è selezionato il tipo di incorporamento di YouTube
* **Consenti configurazione del comportamento**  di riproduzione automatica: consente all&#39;autore del contenuto di configurare l&#39;opzione  **Abilita riproduzione** automatica nel componente quando il tipo di incorporamento di YouTube è selezionato
   * **Valore predefinito di esecuzione**  automatica: imposta automaticamente l&#39;opzione  **Abilita** riproduzione automatica quando è selezionato il tipo di incorporamento di YouTube
* **Consenti configurazione del comportamento**  del ciclo continuo: consente all&#39;autore del contenuto di configurare l&#39;opzione  **Abilita** posizione nel componente quando è selezionato il tipo di incorporamento di YouTube
   * **Valore predefinito del ciclo** : imposta automaticamente  **Abilita** posizione quando è selezionato il tipo di incorporamento di YouTube
* **Consenti configurazione della riproduzione in linea (iOS)**  - Consente all&#39;autore del contenuto di configurare l&#39; **opzione** Abilita riproduzione in linea (iOS) nel componente quando il tipo di incorporamento YouTube è selezionato
   * **Valore predefinito di riproduzione in linea (iOS)**  - Imposta automaticamente  **l&#39;** opzione Abilita riproduzione in linea (iOS) quando è selezionato il tipo di incorporamento di YouTube
* **Consenti configurazione di video**  in linea - Consente all&#39;autore del contenuto di configurare la  **Video correlati senza restrizioni nel** componente quando è selezionato il tipo di incorporamento di YouTube
   * **Valore predefinito di video**  correlati senza restrizioni - Imposta automaticamente  **** Video correlati senza restrizioni quando si seleziona il tipo di incorporamento di YouTube
