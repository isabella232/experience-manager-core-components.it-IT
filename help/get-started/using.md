---
title: Utilizzo dei componenti core
description: '"Per iniziare a usare i componenti core nel tuo progetto, devi seguire tre passaggi: scaricate e installate, create componenti proxy, caricate gli stili di base e consentite i componenti nei modelli."'
translation-type: tm+mt
source-git-commit: 78202dc777b90f795f66873921c55e21ef8a239c
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 4%

---


# Utilizzo dei componenti core{#using-core-components}

Per iniziare a utilizzare i componenti core nel tuo progetto, sono disponibili quattro passaggi, descritti singolarmente nelle sezioni seguenti:

1. [Download e installazione](#download-and-install)
1. [Creare componenti proxy](#create-proxy-components)
1. [Caricare gli stili di base](#load-the-core-styles)
1. [Abilitare i componenti](#allow-the-components)

>[!NOTE]
>
>In alternativa, per istruzioni più ampie su come iniziare da zero con la configurazione del progetto, i componenti core, i modelli modificabili, le librerie client e lo sviluppo di componenti, potrebbe essere interessante la seguente esercitazione multiparte:\
>[Guida introduttiva ad AEM Sites: tutorial WKND](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

## Download e installazione di {#download-and-install}

Una delle idee che stanno dietro ai componenti core è la flessibilità. Rilasciando nuove versioni dei componenti core più spesso,  Adobe è più flessibile nel fornire nuove funzioni. Gli sviluppatori possono a loro volta essere flessibili in base ai componenti che scelgono di integrare nei loro progetti e alla frequenza con cui desiderano aggiornarli.

Per questo motivo, i componenti core non fanno parte del lancio rapido quando si avvia in modalità di produzione (senza contenuti di esempio). Pertanto, il primo passaggio consiste nel [scaricare l&#39;ultimo pacchetto di contenuti rilasciato da GitHub](https://github.com/adobe/aem-core-wcm-components/releases/latest) e installarlo negli ambienti AEM.

Esistono diversi modi per automatizzare questo processo, ma il modo più semplice per installare rapidamente un pacchetto di contenuti in un&#39;istanza è utilizzare Gestione pacchetti; vedere [Installare i pacchetti](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages). Inoltre, una volta eseguita un&#39;istanza di pubblicazione, dovrete replicare il pacchetto all&#39;editore; vedere [Replica di pacchetti](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages).

## Crea componenti proxy {#create-proxy-components}

Per motivi illustrati nella sezione [Proxy Component Pattern](/help/developing/guidelines.md#proxy-component-pattern), i componenti core non devono essere direttamente citati dal contenuto. Per evitare che ciò accada, appartengono tutti a un gruppo di componenti nascosto ( `.core-wcm` o `.core-wcm-form`), il che impedirà loro di essere visualizzati direttamente nell&#39;editor.

Occorre invece creare componenti specifici per il sito, che definiscano il nome e il gruppo del componente desiderato da visualizzare agli autori della pagina, e che facciano riferimento a ciascun componente di base come super-tipo. Questi componenti specifici del sito sono talvolta denominati &quot;componenti proxy&quot;, perché non devono contenere nulla e servono principalmente a definire la versione di un componente da utilizzare per il sito. Tuttavia, quando si personalizzano i [componenti core](/help/developing/customizing.md), questi componenti proxy svolgono un ruolo essenziale per la marcatura e la personalizzazione logica.

Pertanto, per ogni componente di base che si desidera utilizzare per un sito, è necessario:

1. Create un componente proxy corrispondente nella cartella Components del sito.

   ****
EsempioIn  `/apps/my-site/components` creare un nodo titolo di tipo  `cq:Component`

1. Puntare alla versione del componente core corrispondente con il super-tipo.

   **EsempioAggiungi la proprietà**
seguente:\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. Definire il gruppo, il titolo e, facoltativamente, la descrizione del componente. Questi valori sono specifici del progetto e determinano in che modo il componente viene esposto agli autori.

   **EsempioAggiungi le proprietà seguenti:**


   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

Ad esempio, guardate il componente [title del sito WKND](https://github.com/adobe/aem-guides-wknd/blob/master/ui.apps/src/main/content/jcr_root/apps/wknd/components/title/.content.xml), che è un buon esempio di un componente proxy costruito in quel modo.

## Caricare gli stili di base {#load-the-core-styles}

1. Se non ancora, create una [libreria client](https://docs.adobe.com/content/help/it-IT/experience-manager-65/developing/introduction/clientlibs.html) che contenga tutti i file CSS e JS necessari per il sito.
1. Nella libreria client del sito, aggiungere le dipendenze ai componenti core eventualmente necessari. Questa operazione viene eseguita aggiungendo una proprietà `embed`.

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

Accertatevi che i componenti proxy e le librerie client siano stati distribuiti nell&#39;ambiente AEM prima di passare alla sezione successiva.

## Consenti componenti {#allow-the-components}

I passaggi seguenti vengono eseguiti nell&#39; [Editor modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

1. Nell&#39;Editor modelli, selezionare il Contenitore di layout e aprire il relativo criterio.
1. Nell’elenco Componenti consentiti, selezionare i componenti proxy creati in precedenza, che devono essere visualizzati sotto il gruppo di componenti assegnato. Al termine, applicate le modifiche.
1. Facoltativamente, per i componenti che dispongono di una finestra di dialogo di progettazione, possono essere preconfigurati.

È tutto! Nelle pagine create dal modello modificato, è ora possibile utilizzare i componenti appena creati.

**Articolo successivo:**

* [Personalizzazione dei componenti](/help/developing/customizing.md)  core - per imparare a personalizzare lo stile dei componenti core.
* [Linee guida](/help/developing/guidelines.md)  per i componenti - per apprendere i pattern di implementazione dei componenti core.
