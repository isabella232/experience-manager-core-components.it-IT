---
title: Utilizzo dei Componenti core
description: '“Per iniziare a utilizzare i Componenti core nel tuo progetto, segui questi quattro passaggi: scarica e installa, crea componenti proxy, carica gli stili core e consenti i componenti sui tuoi modelli.”'
role: Architect, Developer, Admin, User
exl-id: ee2d25e4-e2b8-4ecc-a62c-f0066de2bf2d
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '977'
ht-degree: 100%

---

# Utilizzo dei Componenti core{#using-core-components}

Per iniziare a utilizzare i Componenti core nel tuo progetto, segui i quattro passaggi descritti singolarmente nelle sezioni che seguono:

1. [Scaricamento e installazione](#download-and-install)
1. [Creazione di componenti proxy](#create-proxy-components)
1. [Caricamento degli stili core](#load-the-core-styles)
1. [Abilitazione dei componenti](#allow-the-components)

>[!TIP]
>
>Per istruzioni più ampie su come iniziare da zero con la configurazione del progetto, i Componenti core, i modelli modificabili, le librerie client e lo sviluppo dei componenti, potrebbe essere interessante la seguente esercitazione in più parti:\
>[Guida introduttiva ai AEM Sites: esercitazione WKND](https://docs.adobe.com/content/help/it-IT/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!TIP]
>
>Se utilizzi [Archetipo progetto AEM,](/help/developing/archetype/overview.md) i Componenti core vengono inclusi automaticamente nel progetto in base alle raccomandazioni sulle best practice di Adobe.

## Scaricamento e installazione {#download-and-install}

Una delle idee alla base dei Componenti core è la flessibilità. Rilasciare più spesso nuove versioni dei Componenti core consente ad Adobe di essere più flessibile nella distribuzione di nuove funzioni. Gli sviluppatori possono a loro volta essere flessibili nella scelta dei componenti che intendono integrare nei loro progetti e nella frequenza con cui desiderano aggiornarli. Ciò determina un processo di rilascio separato per AEM e i Componenti core.

Pertanto, la procedura di installazione dipende dalla scelta di AEM as a Cloud Service oppure on-premise.

### AEM as a Cloud Service {#aemaacs}

Non c’è nessun passaggio uno! AEM as a Cloud Service viene fornito automaticamente con la versione più recente dei Componenti core. Proprio come AEMaaCS offre le funzioni più recenti di AEM, AEMaaCS ti tiene automaticamente aggiornato con l’ultima versione dei Componenti core.

Alcuni punti da tenere presenti quando utilizzi i Componenti core su AEMaaCS:

* I Componenti core sono inclusi in `/libs`.
* La pipeline di creazione del progetto genera avvisi nel registro, se include nuovamente i Componenti core come parte di `/apps`, e ignora la versione incorporata nel progetto.
   * In una prossima versione, includere nuovamente i Componenti core non permetterà di generare la pipeline.
* Se il progetto già includeva i Componenti core in `/apps`, [potrebbe essere necessario adeguare il progetto.](/help/developing/overview.md#via-aemaacs)
* Anche se i Componenti core sono ora inclusi in `/libs`, si sconsiglia di creare sovrapposizioni dello stesso percorso in `/apps`. Va invece utilizzato [il modello di componente proxy](/help/developing/guidelines.md#proxy-component-pattern), se è necessario personalizzare un qualunque aspetto dei componenti.

### AEM 6.5 e versioni precedenti {#aem-65}

I Componenti core non fanno parte dell’avvio rapido, quando si inizia in modalità di produzione (senza esempi di contenuto). Pertanto, il primo passaggio è quello di [scaricare l’ultimo pacchetto dei contenuti rilasciato da GitHub](https://github.com/adobe/aem-core-wcm-components/releases/latest) e installarlo nei tuoi ambienti AEM.

Esistono diversi modi per automatizzare questo processo, ma il modo più semplice per installare rapidamente un pacchetto dei contenuti su un’istanza è quello di utilizzare Gestione pacchetti; vedi [Installazione di pacchetti](https://docs.adobe.com/content/help/it-IT/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages). Inoltre, una volta che avrai in esecuzione anche un’istanza Publish, dovrai replicare quel pacchetto nell’editore; vedi [Replica di pacchetti](https://docs.adobe.com/content/help/it-IT/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages).

## Creazione di componenti proxy {#create-proxy-components}

Per i motivi illustrati nella sezione [Modello di componente proxy](/help/developing/guidelines.md#proxy-component-pattern), i Componenti core non devono avere un riferimento diretto dal contenuto. Per evitare questo problema, essi appartengono tutti a un gruppo di componenti nascosti (`.core-wcm` o `.core-wcm-form`), che ne impedisce la visualizzazione diretta nell’editor.

È invece necessario creare componenti specifici del sito, che definiscono il nome e il gruppo dei componenti da rendere visibili agli autori di pagine e che fanno riferimento a ciascun Componente core come loro super-tipo. Questi componenti specifici del sito vengono talvolta chiamati &quot;componenti proxy&quot;, perché non devono contenere nulla e servono principalmente a definire la versione di un componente da utilizzare per il sito. Tuttavia, quando si personalizzano i [Componenti core](/help/developing/customizing.md), questi componenti proxy svolgono un ruolo essenziale per il markup e la personalizzazione della logica.

Pertanto, per ciascun Componente core che vuoi utilizzare per un sito, devi:

1. Creare un componente proxy corrispondente nella cartella dei componenti del sito.

   **Esempio**
Sotto `/apps/my-site/components` crea un nodo titolo di tipo `cq:Component`

1. Puntare alla versione corrispondente del Componente core con il super-tipo.

   **Esempio**
Aggiungi la seguente proprietà:\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. Definire il gruppo, il titolo e, facoltativamente, la descrizione del componente. Questi valori sono specifici per il progetto e determinano il modo in cui il componente viene visualizzato agli autori.

   **Esempio**
Aggiungi le seguenti proprietà:

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

Guarda il [componente Titolo del sito WKND](https://github.com/adobe/aem-guides-wknd/blob/master/ui.apps/src/main/content/jcr_root/apps/wknd/components/title/.content.xml), che è un buon esempio di un componente proxy creato in questo modo.

## Caricamento degli stili core {#load-the-core-styles}

1. Se non l’hai ancora fatto, crea una [libreria client](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html?lang=it) che contiene tutti i file CSS e JS necessari per il sito.
1. Nella libreria client del sito, aggiungi le dipendenze ai Componenti core eventualmente necessari. A questo scopo, aggiungi una proprietà `embed`.

   Ad esempio, per includere le librerie client di tutti i Componenti core v1, la proprietà da aggiungere è:

   ```shell
   embed="[  
   core.wcm.components.image.v1,  
   core.wcm.components.list.v1,  
   core.wcm.components.breadcrumb.v1,  
   core.wcm.components.form.container.v1,  
   core.wcm.components.form.text.v1  
   ]"
   ```

Accertati che i componenti proxy e le librerie client siano stati distribuiti nell’ambiente AEM, prima di passare alla sezione successiva.

## Consenti i componenti {#allow-the-components}

I seguenti passaggi vengono eseguiti nell’[Editor di modelli](https://docs.adobe.com/content/help/it-IT/experience-manager-cloud-service/sites/authoring/features/templates.html).

1. Nell’editor di modelli, seleziona il Contenitore di layout e apri il relativo criterio.
1. Nell’elenco Componenti consentiti, seleziona i componenti proxy creati in precedenza, che devono essere visualizzati sotto il gruppo di componenti ad essi assegnato. Al termine, applica le modifiche.
1. Facoltativamente, per i componenti che hanno una finestra di dialogo per progettazione, essi possono essere preconfigurati.

Tutto qui! Nelle pagine create dal modello modificato, ora dovresti poter utilizzare i componenti appena creati.

**Articolo successivo:**

* [Personalizzazione dei Componenti core](/help/developing/customizing.md): per scoprire come assegnare stili e personalizzare i Componenti core.
* [Linee guida per i componenti](/help/developing/guidelines.md): per scoprire i modelli di implementazione dei Componenti core.
