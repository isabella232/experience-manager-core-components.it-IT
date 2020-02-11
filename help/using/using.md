---
title: Utilizzo dei componenti core
description: '"Per iniziare a utilizzare i componenti core nel tuo progetto, devi seguire tre passaggi: scaricate e installate, create componenti proxy, caricate gli stili di base e consentite i componenti nei modelli."'
translation-type: tm+mt
source-git-commit: 945381996db443c227aa31f0aacb963071165681

---


# Utilizzo dei componenti core{#using-core-components}

Per iniziare a utilizzare i componenti [](developing.md) core nel progetto, sono disponibili quattro passaggi, descritti singolarmente nelle sezioni seguenti:

1. [Download e installazione](#download-and-install)
1. [Creare componenti proxy](#create-proxy-components)
1. [Caricare gli stili di base](#load-the-core-styles)
1. [Attivare i componenti](#allow-the-components)

>[!NOTE]
>
>In alternativa, per istruzioni più ampie su come iniziare da zero con la configurazione del progetto, i componenti core, i modelli modificabili, le librerie client e lo sviluppo di componenti, potrebbe essere interessante la seguente esercitazione multiparte:\
>[Guida introduttiva ad AEM Sites - Esercitazione WKND](wknd-tutorial.md)

## Download e installazione {#download-and-install}

Una delle idee che stanno dietro ai componenti core è la flessibilità. Rilasciando nuove versioni dei componenti core più spesso, Adobe è più flessibile nel fornire nuove funzioni. Gli sviluppatori possono a loro volta essere flessibili in base ai componenti che scelgono di integrare nei loro progetti e alla frequenza con cui desiderano aggiornarli.

Per questo motivo, i componenti core non fanno parte del lancio rapido quando si avvia in modalità di produzione (senza contenuti di esempio). Pertanto, il primo passaggio consiste nel [scaricare l’ultimo pacchetto di contenuti rilasciato da GitHub](https://github.com/adobe/aem-core-wcm-components/releases/latest) e installarlo nei vostri ambienti AEM.

Esistono diversi modi per automatizzare questo processo, ma il modo più semplice per installare rapidamente un pacchetto di contenuti in un&#39;istanza è utilizzare Gestione pacchetti; consultate [Installare i pacchetti](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages). Inoltre, una volta eseguita un&#39;istanza di pubblicazione, dovrete replicare il pacchetto all&#39;editore; consultate [Replica dei pacchetti](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages).

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T16:42:59.142-0400

Should we be promoting embedding the core-component package as an artifact in a customer application, reasoning as follows: 1) a customer application is required to leverage core components (at a minimum, proxy components must be defined) 2) a customer application must be updated to leverage new versions of core components (since it requires adjusting the sling:resourceSuperType to point at the new version of the component) It seems the only time theres an advantage to installing a release directly is if a bug-fix (non version-changing) release of core-components is cut, and it doesnt coincide with an application deployment. WDYT? For example, recommend doing this for ACS Commons which has a similar use-case (https://adobe-consulting-services.github.io/acs-aem-commons/pages/maven.html) We can of course keep the instructions for manually deploying, since some will want to do this, or the bug-fix use-case will appear.

 -->

## Creare componenti proxy {#create-proxy-components}

Per motivi illustrati nella sezione Pattern [componente](guidelines.md#proxy-component-pattern) proxy, i componenti core non devono essere direttamente citati dal contenuto. Per evitare che ciò accada, appartengono tutti a un gruppo di componenti nascosto ( `.core-wcm` o `.core-wcm-form`), il che ne impedisce la visualizzazione diretta nell’editor.

Occorre invece creare componenti specifici per il sito, che definiscano il nome e il gruppo del componente desiderato da visualizzare agli autori della pagina, e che facciano riferimento a ciascun componente core come super-tipo. Questi componenti specifici del sito sono talvolta denominati &quot;componenti proxy&quot;, perché non devono contenere nulla e servono principalmente a definire la versione di un componente da utilizzare per il sito. Tuttavia, quando si personalizzano i componenti [](customizing.md)core, questi componenti proxy svolgono un ruolo essenziale per la marcatura e la personalizzazione logica.

Pertanto, per ogni componente core che si desidera utilizzare per un sito, è necessario:

1. Create un componente proxy corrispondente nella cartella Components del sito.

   **Esempio** In `/apps/my-site/components` creare un nodo titolo di tipo `cq:Component`

1. Puntare alla versione del componente core corrispondente con il super-tipo.

   **Esempio** Aggiungi la seguente proprietà:\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. Definire il gruppo, il titolo e, facoltativamente, la descrizione del componente. Questi valori sono specifici del progetto e determinano in che modo il componente viene esposto agli autori.

   **Esempio**: aggiungere le seguenti proprietà:

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

Ad esempio, guardate il componente [titolo del sito](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/blob/master/ui.apps/src/main/content/jcr_root/apps/weretail/components/content/title/.content.xml)di riferimento We.Retail, che è un buon esempio di un componente proxy creato in quel modo.

## Caricare gli stili di base {#load-the-core-styles}

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T16:57:16.414-0400

Styles is odd in that most Core Components do not have CSS; very few even have structural CSS (breadcrumbs, list) It may be more apt to title this section: Load the Core JavaScript and CSS or Load the Core Client Libraries ?

 -->

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T17:41:37.115-0400

This section seems to cover the "sites" clientlibs for core components; Do we need a section for ensuring the editor clientlibs are loaded in the Page Editor? Pending: https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/issues/15

 -->

<!-- 

Comment Type: annotation
Last Modified By: cotescu
Last Modified Date: 2018-03-09T10:45:52.812-0500

Load the Core Client Libraries sounds way better

 -->

1. Se non ancora, create una libreria [](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/clientlibs.html) client che contenga tutti i file CSS e JS necessari per il sito.
1. Nella libreria client del sito, aggiungere le dipendenze ai componenti core eventualmente necessari. Questa operazione viene eseguita aggiungendo una `embed` proprietà.

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

Prima di passare alla sezione successiva, accertati che i componenti proxy e le librerie client siano stati distribuiti nell’ambiente AEM.

## Consenti componenti {#allow-the-components}

La procedura seguente viene eseguita nell&#39;Editor [](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)modelli.

1. Nell&#39;Editor modelli, selezionare il Contenitore di layout e aprire il relativo criterio.
1. Nell’elenco Componenti consentiti, selezionare i componenti proxy creati in precedenza, che devono essere visualizzati sotto il gruppo di componenti assegnato. Al termine, applicate le modifiche.
1. Facoltativamente, per i componenti che dispongono di una finestra di dialogo di progettazione possono essere preconfigurati.

È tutto! Nelle pagine create dal modello modificato, è ora possibile utilizzare i componenti appena creati.

**Articolo successivo:**

* [Personalizzazione dei componenti](customizing.md) di base: per informazioni su come definire lo stile e personalizzare i componenti di base.
* [Linee guida](guidelines.md) per i componenti - per apprendere i pattern di implementazione dei componenti core.
