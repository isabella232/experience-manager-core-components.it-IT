---
title: Linee guida sui componenti
seo-title: Linee guida sui componenti
description: I componenti core seguono pattern di implementazione moderni molto diversi dai componenti di base.
seo-description: I componenti core seguono pattern di implementazione moderni molto diversi dai componenti di base.
uuid: b 1 daea 89-da 3 c -454 f -8 ab 5-d 75 a 19412954
contentOwner: Utente
content-type: riferimento
topic-tags: sviluppo
products: SG_ EXPERIENCEMANAGER/CORECOMPONENTS-NEW
discoiquuid: 170 dba 8 f-a 2 ed -442 e-a 56 e -1126 b 338 c 36 e
translation-type: tm+mt
source-git-commit: 62643e5bd49ab006230f65004bb9374822dcc017

---


# Linee guida sui componenti {#component-guidelines}

I [componenti core](developing.md) seguono pattern di implementazione moderni molto diversi dai componenti di base.

Questa pagina spiega questi pattern e quando utilizzarli per creare componenti personalizzabili. La prima sezione [Pattern componenti generali](guidelines.md) si applica a qualsiasi tipo di componente, mentre la seconda sezione [Pattern](guidelines.md) componenti riutilizzabili si applica ai componenti destinati alla riuso tra siti o progetti, come i componenti core.

## Pattern generali componente {#general-component-patterns}

Le linee guida riportate in questa sezione sono consigliate per qualsiasi tipo di componente, indipendentemente dal fatto che il componente sia specifico di un singolo progetto o che il componente debba essere ampiamente riutilizzato in tutti i siti o progetti.

### Componenti configurabili {#configurable-components}

I componenti possono disporre di finestre di dialogo con diverse opzioni. Questa funzione dovrebbe essere sfruttata per rendere i componenti flessibili e configurabili ed evitare di implementare più componenti che sono prevalentemente varianti l&#39;uno dall&#39;altro.

Generalmente, se un reticolo o una progettazione contiene varianti di elementi simili, queste varianti non devono essere implementate come componenti diversi, ma come un componente con opzioni per scegliere tra le varianti.

Per eseguire un passo avanti, se i componenti vengono riutilizzati su siti o progetti, consulta la [sezione Capacità](#pre-configurable-capabilities) preconfigurabili.

### Separazione delle preoccupazioni {#separation-of-concerns}

Mantenere la logica (o modello) di un componente separato dal modello (o dalla vista) di un componente è in genere una buona prassi. Esistono diversi modi per farlo, tuttavia quella consigliata è utilizzare i modelli [Sling](https://sling.apache.org/documentation/bundles/models.html) per la logica e il [codice HTL (HTML Template Language)](https://helpx.adobe.com/experience-manager/htl/using/overview.html) per la marcatura, come accade anche per i componenti core.

I modelli Sling sono un insieme di annotazioni Java che consentono di accedere facilmente alle variabili necessarie da pojos e offrono quindi un modo semplice, potente e performanti per implementare la logica Java per i componenti.

HTL è stato progettato come linguaggio di modelli sicuro e semplice per AEM. Può richiamare molte forme di logica, il che rende molto flessibile.

## Pattern di componente riutilizzabili {#reusable-component-patterns}

Le linee guida riportate in questa sezione possono essere utilizzate anche per qualsiasi tipo di componente, ma hanno maggior senso per i componenti destinati alla riuso tra siti o progetti, come i componenti core. Queste linee guida possono essere ignorate per i componenti utilizzati solo su un singolo sito o progetto.

### Funzionalità preconfigurabili {#pre-configurable-capabilities}

Oltre alla finestra di dialogo di modifica utilizzata dagli autori delle pagine, i componenti possono anche avere una finestra di dialogo per la progettazione dei modelli per preconfigurarli. L&#39;Editor [modelli](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) consente di configurare tutte queste preconfigurazioni, denominate &quot;Criteri&quot;.

Per rendere i componenti più riutilizzabili possibile, devono essere forniti con opzioni significative per preconfigurarli. Ciò consente di abilitare o disabilitare le funzioni dei componenti in modo che corrispondano alle esigenze specifiche di siti diversi.

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T17:49:04.584-0400

Unclear how I can add my own capability toggle (for example, if i extend a component and want to toggle that extended functionality ... )

 -->

### Pattern componente proxy {#proxy-component-pattern}

Poiché ogni risorsa contenuto dispone di `sling:resourceType` una proprietà che fa riferimento al componente per eseguirne il rendering, in genere è buona norma che queste proprietà puntino a componenti specifici per il sito, invece di puntare a componenti condivisi da più siti. Questo offrirà maggiore flessibilità ed eviterà il refactoring dei contenuti se un sito richiede un comportamento diverso per un componente, in quanto questa personalizzazione può essere ottenuta sul componente specifico del sito e non avrà effetti sugli altri siti.

Tuttavia, affinché i componenti specifici del progetto non duplichino alcun codice, devono fare riferimento al componente principale condiviso con la `sling:resourceSuperType` proprietà. Questi componenti specifici per i progetti che si riferiscono principalmente ai componenti padre sono denominati &quot;componenti proxy&quot;. I componenti proxy possono essere completamente vuoti se ereditano completamente le funzionalità, oppure possono ridefinire alcuni aspetti del componente.

### Gestione versioni dei componenti {#component-versioning}

I componenti devono essere mantenuti completamente compatibili nel tempo, ma talvolta le modifiche che non possono essere mantenute sono necessarie. Una soluzione alle esigenze opposte consiste nell&#39;introdurre la gestione delle versioni dei componenti aggiungendo un numero nel relativo percorso di tipo risorsa e nei nomi di classe Java completi delle rispettive implementazioni. Questo numero di versione rappresenta una versione principale come definito dalle [linee guida](https://semver.org/)semantici, che vengono incrementate solo per le modifiche non compatibili con l&#39;indietro.

Le modifiche non compatibili apportate ai seguenti aspetti dei componenti ne determineranno una nuova versione:

* Modelli Sling (linee guida semantici per le versioni)
* Script e modelli HTL
* Selettori HTML e selettori CSS
* Rappresentazione JSON
* Finestre di dialogo

Per ulteriori dettagli, consultate [il documento sulla](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies) gestione delle versioni in github.

La gestione delle versioni dei componenti crea una forma di contratto importante per gli aggiornamenti, in quanto spiega quando può essere necessario rifacerla. Vedere anche la sezione [relativa alla sezione Compatibilità degli aggiornamenti delle personalizzazioni](customizing.md#upgrade-compatibility-of-customizations), che descrive le considerazioni richieste da diverse tipologie di personalizzazioni per un aggiornamento.

Per evitare la migrazione dolorosa dei contenuti, è importante non puntare mai direttamente ai componenti su versione dalle risorse di contenuto. Come regola di pollb, una `sling:resourceType` parte del contenuto non deve avere mai un numero di versione, o se si aggiornano componenti richiederà anche il controllo del contenuto. Il modo migliore per evitare questo problema è seguire il pattern di componente [proxy](#proxy-component-pattern) descritto in precedenza.

### Interfacce modello {#model-interfaces}

Questo pattern riguarda `data-sly-use` l&#39;istruzioni HTL per puntare a un&#39;interfaccia Java, mentre l&#39;implementazione del modello Sling si registra anche al tipo di risorsa del componente.

Se combinato con il pattern di componente [proxy](#proxy-component-pattern) descritto sopra, questa forma di due offerte è rappresentata da un doppio punto di estensione:

1. Un sito può ridefinire l&#39;implementazione di un modello Sling eseguendo la registrazione al tipo di risorsa del componente proxy, senza doverlo considerare sul file HTL, che può ancora puntare all&#39;interfaccia.
1. Un sito può ridefinire la marcatura HTL di un componente, senza dover considerare la logica di implementazione a cui punta.

## Tutto insieme {#putting-it-all-together}

Di seguito è riportata una panoramica dell&#39;intera struttura di binding del tipo di risorsa, con l&#39;esempio del componente Core Titolo. Viene illustrato come un componente proxy specifico per il sito consente di risolvere le versioni dei componenti, per evitare che la risorsa contenuto contenga un numero di versione. Viene quindi mostrato il modo in cui il file `title.html`[HTL](https://helpx.adobe.com/experience-manager/htl/using/overview.html) del componente utilizza l&#39;interfaccia del modello, mentre l&#39;implementazione si collega alla versione specifica del componente attraverso [le annotazioni di Sling Model](https://sling.apache.org/documentation/bundles/models.html) .

![Panoramica rilegatura risorse](assets/chlimage_1-32.png)

Di seguito viene fornita un&#39;altra panoramica, che non mostra i dettagli del POJO implementazione, ma mostra come si fanno riferimento ai [modelli e ai criteri](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/page-templates-editable.html) associati.

La `cq:allowedTemplates` proprietà indica quali modelli possono essere utilizzati per un sito e quali `cq:template` sono i modelli che si riferiscono a ogni pagina. Ogni modello è costituito da tre parti:

* **struttura**
Contiene le risorse che verranno forzate per ogni pagina e che l&#39;autore della pagina non può eliminare, come ad esempio i componenti dell&#39;intestazione della pagina e piè di pagina.
* **initial**
Contiene il contenuto iniziale che verrà duplicato alla pagina quando viene creato.
* **policy**
Contiene per ciascun componente la mappatura a un criterio, che è la pre-configurazione del componente. Questa mappatura consente di riutilizzare i criteri tra i modelli e di essere gestiti a livello centrale.

![Modelli e panoramica dei criteri](assets/screen_shot_2018-12-07at093102.png)

**Leggi avanti:**

* [Utilizzo dei componenti](using.md) core: diventa disponibile con componenti core nel tuo progetto.
* [Personalizzazione dei componenti](customizing.md) core - per apprendere come formattare e personalizzare i componenti core.
