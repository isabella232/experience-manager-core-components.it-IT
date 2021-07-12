---
title: Utilizzo dei componenti core
description: '"Per iniziare a utilizzare i componenti core nel tuo progetto, segui tre passaggi: scarica e installa, crea componenti proxy, carica gli stili di base e consenti i componenti sui tuoi modelli."'
role: Architect, Developer, Admin, User
exl-id: ee2d25e4-e2b8-4ecc-a62c-f0066de2bf2d
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 2%

---

# Utilizzo dei componenti core{#using-core-components}

Per iniziare a utilizzare i componenti core nel tuo progetto, sono disponibili quattro passaggi, descritti singolarmente nelle sezioni seguenti:

1. [Scarica e installa](#download-and-install)
1. [Creare componenti proxy](#create-proxy-components)
1. [Caricare gli stili core](#load-the-core-styles)
1. [Attivare i componenti](#allow-the-components)

>[!TIP]
>
>Per istruzioni più generali su come iniziare da zero con la configurazione del progetto, i componenti core, i modelli modificabili, le librerie client e lo sviluppo dei componenti, potrebbe essere interessante la seguente esercitazione in più parti:\
>[Guida introduttiva ad AEM Sites: tutorial WKND](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!TIP]
>
>Se utilizzi [AEM Project Archetype,](/help/developing/archetype/overview.md) i componenti core vengono inclusi automaticamente nel progetto in base ai consigli sulle best practice di Adobe.

## Scarica e installa {#download-and-install}

Una delle idee alla base dei componenti principali è la flessibilità. Rilasciare più spesso nuove versioni dei componenti core consente ad Adobe di essere più flessibile nel distribuire nuove funzioni. Gli sviluppatori possono a loro volta essere flessibili in merito ai componenti che scelgono di integrare nei loro progetti e alla frequenza con cui desiderano aggiornarli. Questo determina un processo di rilascio separato per i componenti AEM e core.

Pertanto, la procedura di installazione dipende dal fatto che tu esegua AEM as a Cloud Service o on-premise.

### AEM as a Cloud Service {#aemaacs}

Non c&#39;è passo uno! AEM come Cloud Service viene fornito automaticamente con la versione più recente dei componenti core. Proprio come AEMaaCS offre le funzioni più recenti di AEM, AEMaaCS ti tiene automaticamente aggiornato con l’ultima versione dei componenti core.

Alcuni punti da tenere a mente quando utilizzi i componenti core su AEMaaCS:

* I componenti core sono inclusi in `/libs`.
* La pipeline di generazione del progetto genera avvisi nel registro se include nuovamente i componenti core come parte di `/apps` e ignora la versione incorporata come parte del progetto.
   * In una versione futura, includere nuovamente i componenti core non sarà in grado di generare la pipeline.
* Se il progetto includeva in precedenza i componenti core in `/apps`, [potrebbe essere necessario regolare il progetto.](/help/developing/overview.md#via-aemaacs)
* Anche se i componenti core sono ora in `/libs`, si sconsiglia di creare sovrapposizioni dello stesso percorso in `/apps`. [Il ](/help/developing/guidelines.md#proxy-component-pattern) pattern del componente proxy deve essere utilizzato invece se è necessario personalizzare qualsiasi aspetto dei componenti.

### AEM 6.5 e versioni precedenti {#aem-65}

I componenti core non fanno parte dell’avvio rapido quando si inizia in modalità di produzione (senza contenuti di esempio). Pertanto, il primo passaggio è quello di [scaricare l&#39;ultimo pacchetto di contenuti rilasciato da GitHub](https://github.com/adobe/aem-core-wcm-components/releases/latest) e installarlo nei tuoi ambienti AEM.

Esistono diversi modi per automatizzare questo processo, ma il modo più semplice per installare rapidamente un pacchetto di contenuti in un’istanza è quello di utilizzare Gestione pacchetti; consulta [Installare pacchetti](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages). Inoltre, una volta che avrai eseguito anche un&#39;istanza di pubblicazione, dovrai replicare quel pacchetto all&#39;editore; vedere [Replica dei pacchetti](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages).

## Creare componenti proxy {#create-proxy-components}

Per motivi illustrati nella sezione [Pattern componente proxy](/help/developing/guidelines.md#proxy-component-pattern) , i componenti core non devono essere direttamente citati dal contenuto. Per evitare questo problema, appartengono tutti a un gruppo di componenti nascosti ( `.core-wcm` o `.core-wcm-form`), il che ne impedisce la visualizzazione diretta nell’editor.

È invece necessario creare componenti specifici per il sito, che definiscono il nome e il gruppo di componenti desiderati da visualizzare agli autori di pagine, e fanno riferimento a ciascun componente core come super-tipo. Questi componenti specifici del sito vengono talvolta chiamati &quot;componenti proxy&quot;, perché non devono contenere nulla e servono principalmente a definire la versione di un componente da utilizzare per il sito. Tuttavia, quando si personalizzano i [Componenti core](/help/developing/customizing.md), questi componenti proxy svolgono un ruolo essenziale per il markup e la personalizzazione della logica.

Pertanto, per ogni componente core che desideri utilizzare per un sito, devi:

1. Crea un componente proxy corrispondente nella cartella dei componenti del sito.

   ****
EsempioIn  `/apps/my-site/components` crea un nodo titolo di tipo  `cq:Component`

1. Puntare alla versione corrispondente del componente core con il super-tipo.

   ****
EsempioAggiungi la seguente proprietà:\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. Definisci il gruppo, il titolo e, facoltativamente, la descrizione del componente. Questi valori sono specifici per il progetto e determinano in che modo il componente viene esposto agli autori.

   ****
EsempioAggiungi le seguenti proprietà:

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

Ad esempio, guarda il [componente titolo del sito WKND](https://github.com/adobe/aem-guides-wknd/blob/master/ui.apps/src/main/content/jcr_root/apps/wknd/components/title/.content.xml), che è un buon esempio di un componente proxy creato in questo modo.

## Caricare gli stili core {#load-the-core-styles}

1. Se non ancora eseguito, crea una [Libreria client](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html) che contiene tutti i file CSS e JS necessari per il sito.
1. Nella libreria client del sito, aggiungi le dipendenze ai componenti core eventualmente necessari. A questo scopo, aggiungi una proprietà `embed` .

   Ad esempio, per includere le librerie client di tutti i componenti core v1, la proprietà da aggiungere sarà:

   ```shell
   embed="[  
   core.wcm.components.image.v1,  
   core.wcm.components.list.v1,  
   core.wcm.components.breadcrumb.v1,  
   core.wcm.components.form.container.v1,  
   core.wcm.components.form.text.v1  
   ]"
   ```

Assicurati che i componenti proxy e le librerie client siano stati distribuiti nell’ambiente AEM prima di passare alla sezione successiva.

## Consenti componenti {#allow-the-components}

I seguenti passaggi vengono eseguiti in [Editor modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

1. Nell’Editor modelli, selezionare il Contenitore di layout e aprire il relativo criterio.
1. Nell’elenco Componenti consentiti , seleziona i componenti proxy creati in precedenza, che devono essere visualizzati sotto il gruppo di componenti assegnato. Al termine, applica le modifiche.
1. Facoltativamente, per i componenti che hanno una finestra di dialogo di progettazione, possono essere preconfigurati.

Tutto qui! Nelle pagine create dal modello modificato, ora dovresti essere in grado di utilizzare i componenti appena creati.

**Articolo successivo:**

* [Personalizzazione dei componenti core](/help/developing/customizing.md) : per scoprire come assegnare stile e personalizzare i componenti core.
* [Linee guida per i componenti](/help/developing/guidelines.md) : per scoprire i pattern di implementazione dei componenti core.
