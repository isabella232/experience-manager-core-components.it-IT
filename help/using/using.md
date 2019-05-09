---
title: Utilizzo dei componenti core
seo-title: Utilizzo dei componenti core
description: 'null'
seo-description: '" Per rendere disponibili i componenti core nel tuo progetto, sono disponibili tre passaggi: scaricare e installare, creare componenti proxy, caricare gli stili di base e consentire i componenti nei modelli. "'
uuid: a 1 ef 2 acf -8226-4510-838 b-f 5 fae 196 f 9 f 1
contentOwner: Utente
content-type: riferimento
topic-tags: sviluppo
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: 1703 a 171-830 c -477 e-a 34 f -99 caba 841 ec 4
disttype: dist5
gnavtheme: chiaro
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# Utilizzo dei componenti core{#using-core-components}

Per essere in esecuzione con [Componenti core](developing.md) nel tuo progetto, sono disponibili quattro passaggi, descritti singolarmente nelle sezioni seguenti:

1. [Download e installazione](#download-and-install)
1. [Creare componenti proxy](#create-proxy-components)
1. [Carica stili di base](#load-the-core-styles)
1. [Abilitare i componenti](#allow-the-components)

>[!NOTE]
>
>In alternativa, per istruzioni più ampie su come iniziare da zero con la configurazione del progetto, i componenti core, i modelli modificabili, le librerie client e lo sviluppo dei componenti, la seguente esercitazione su più parti potrebbe interessare:\
>[Guida introduttiva ad AEM Sites - Esercitazione WKND](wknd-tutorial.md)

## Download e installazione {#download-and-install}

Una delle idee guidate dietro i componenti core è la flessibilità. Il rilascio di nuove versioni dei Componenti core consente più spesso ad Adobe di essere più flessibile nella distribuzione delle nuove funzioni. Gli sviluppatori possono, a loro volta, essere flessibili nei componenti che desiderano integrare nei loro progetti e con la frequenza con cui desiderano aggiornarli.

Per questo motivo, i componenti core non fanno parte del rapido avvio in modalità di produzione (senza contenuto di esempio). Pertanto, il primo passaggio consiste [nel scaricare l&#39;ultimo pacchetto di contenuto rilasciato da github](https://github.com/adobe/aem-core-wcm-components/releases/latest) e per installarlo nei tuoi ambienti AEM.

Esistono diversi modi per automatizzare il contenuto, ma il modo più semplice per installare rapidamente un pacchetto di contenuti su un&#39;istanza è utilizzare Gestione pacchetti; consultate [Installare pacchetti](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html). Inoltre, una volta eseguita l&#39;istanza di pubblicazione, sarà necessario replicare il pacchetto all&#39;editore; consultate [Replica dei pacchetti](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html).

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T16:42:59.142-0400

Should we be promoting embedding the core-component package as an artifact in a customer application, reasoning as follows: 1) a customer application is required to leverage core components (at a minimum, proxy components must be defined) 2) a customer application must be updated to leverage new versions of core components (since it requires adjusting the sling:resourceSuperType to point at the new version of the component) It seems the only time theres an advantage to installing a release directly is if a bug-fix (non version-changing) release of core-components is cut, and it doesnt coincide with an application deployment. WDYT? For example, recommend doing this for ACS Commons which has a similar use-case (https://adobe-consulting-services.github.io/acs-aem-commons/pages/maven.html) We can of course keep the instructions for manually deploying, since some will want to do this, or the bug-fix use-case will appear.

 -->

## Creare componenti proxy {#create-proxy-components}

Per motivi illustrati nella [sezione Pattern](guidelines.md#proxy-component-pattern) di componente proxy, i componenti core non devono essere indirizzati direttamente dal contenuto. Per evitare tale situazione, tutti appartengono a un gruppo di componenti nascosto ( `.core-wcm` o `.core-wcm-form`), che ne impedirà la visualizzazione direttamente nell&#39;editor.

Al contrario, devono essere creati componenti specifici per il sito, che definiscono il nome e il gruppo di componenti desiderati per visualizzare gli autori delle pagine e fare riferimento a un componente core come super type. Questi componenti specifici per il sito sono talvolta denominati &quot;componenti proxy&quot;, perché non devono contenere nulla e servono principalmente per definire la versione di un componente da utilizzare per il sito. Tuttavia, quando si personalizzano i componenti [core](customizing.md), questi componenti proxy riproducono un ruolo essenziale per la personalizzazione logica e logica.

Pertanto, per ogni componente core che è necessario utilizzare per un sito, devi:

1. Create un componente proxy corrispondente nella cartella dei componenti del sito.

   **Esempio**
in `/apps/my-site/components` Creazione di un nodo titolo di tipo `cq:Component`

1. Point to the corresponding Core Component version with the super-type.

   **Esempio**
Aggiungi seguente proprietà:\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. Definite il gruppo, il titolo e facoltativamente la descrizione del componente. Questi valori sono specifici del progetto e stabiliscono la modalità di esposizione del componente agli autori.

   **Esempio**
Aggiungi le seguenti proprietà:

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

Ad esempio, osservate il [componente Titolo del sito](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/blob/master/ui.apps/src/main/content/jcr_root/apps/weretail/components/content/title/.content.xml)di riferimento We. Retail, un esempio di componente proxy creato in questo modo.

## Carica stili di base {#load-the-core-styles}

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

1. Se non lo avete ancora fatto, create una [libreria](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html) client contenente tutti i file CSS e JS richiesti per il sito.
1. Nella libreria client del sito, aggiungi le dipendenze ai componenti core necessari. Questa operazione viene eseguita aggiungendo una `embed` proprietà.

   Ad esempio, per includere le librerie client di tutti i componenti core v 1, la proprietà da aggiungere sarà:

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

## Consenti ai componenti {#allow-the-components}

I passaggi seguenti vengono eseguiti in genere nell&#39;Editor [modelli](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html), per le configurazioni esistenti, che possono essere eseguite in modalità Progettazione:

1. In Editor modelli (o modalità Progettazione), selezionate il Contenitore di layout (o parsys) e aprite il relativo criterio (o la configurazione di progettazione).
1. Nell&#39;elenco dei componenti consentiti, selezionate i componenti proxy creati in precedenza, che dovrebbero essere visualizzati sotto il gruppo di componenti assegnato loro. Una volta apportate le modifiche, applicate le modifiche.
1. Facoltativamente, per i componenti con una finestra di dialogo di progettazione, possono essere preconfigurati.

Così facendo, nelle pagine create dal modello modificato, adesso dovreste essere in grado di utilizzare i componenti appena creati.

**Leggi avanti:**

* [Personalizzazione dei componenti](customizing.md) core - per apprendere come formattare e personalizzare i componenti core.
* [Linee guida sui componenti](guidelines.md) - per apprendere i pattern di implementazione dei componenti core.
