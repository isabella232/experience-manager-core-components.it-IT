---
title: Linee guida per i componenti
description: I componenti core seguono modelli di implementazione moderni che sono molto diversi dai componenti di base.
translation-type: tm+mt
source-git-commit: 5439f90faef28c72367419bb7429a3a880b65229

---


# Linee guida per i componenti {#component-guidelines}

I componenti [](developing.md) core seguono modelli di implementazione moderni che sono molto diversi dai componenti di base.

In questa pagina sono illustrati questi pattern e quando utilizzarli per creare componenti modificabili personalizzati. La prima sezione Pattern [componenti](guidelines.md) generali si applica a qualsiasi tipo di componente, mentre la seconda sezione Modelli [componenti](guidelines.md) riutilizzabili si applica ai componenti destinati a essere riutilizzati tra siti o progetti, come ad esempio i Componenti principali.

## Pattern di componenti generali {#general-component-patterns}

Le linee guida di questa sezione sono consigliate per qualsiasi tipo di componente, a prescindere dal fatto che il componente sia specifico per un singolo progetto o che sia destinato a essere ampiamente riutilizzato su più siti o progetti.

### Componenti configurabili {#configurable-components}

I componenti possono avere finestre di dialogo con diverse opzioni. Questo dovrebbe essere sfruttato per rendere i componenti flessibili e configurabili ed evitare di implementare più componenti che sono per lo più varianti l&#39;uno dell&#39;altro.

In genere, se un wireframe o un progetto contiene varianti di elementi simili, queste varianti non devono essere implementate come componenti diversi, ma come un componente con opzioni per scegliere tra le varianti.

Per fare un passo avanti, se i componenti vengono riutilizzati tra siti o progetti, consulta la sezione [Capacità](#pre-configurable-capabilities) preconfigurabili.

### Separazione delle preoccupazioni {#separation-of-concerns}

In genere è consigliabile tenere separata la logica (o il modello) di un componente dal modello (o dalla vista) di marcatura. Esistono diversi modi per ottenere questo risultato, tuttavia quello consigliato è quello di utilizzare i modelli [](https://sling.apache.org/documentation/bundles/models.html) Sling per la logica e il linguaggio [HTL (](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html) HTML Template Language) per la marcatura, come fanno anche i componenti core.

Sling Models è una serie di annotazioni Java per accedere facilmente alle variabili necessarie dai POJO, e quindi offre un modo semplice, potente ed efficiente per implementare la logica Java per i componenti.

HTL è stato progettato per essere un linguaggio di modello semplice e sicuro, personalizzato per AEM. Può chiamare molte forme di logica, che la rende molto flessibile.

## Pattern di componenti riutilizzabili {#reusable-component-patterns}

Le linee guida di questa sezione possono essere utilizzate anche per qualsiasi tipo di componente, ma hanno più senso per i componenti che devono essere riutilizzati tra siti o progetti, come ad esempio i componenti core. Queste linee guida possono pertanto essere ignorate per i componenti utilizzati solo su un singolo sito o progetto.

### Capacità preconfigurabili {#pre-configurable-capabilities}

Oltre alla finestra di dialogo di modifica utilizzata dagli autori delle pagine, i componenti possono anche avere una finestra di dialogo di progettazione per consentire agli autori dei modelli di preconfigurarli. L&#39;Editor [](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) modelli consente di impostare tutte queste preconfigurazioni, che sono denominate &quot;Criteri&quot;.

Per rendere i componenti il più possibile riutilizzabili, è necessario fornire loro opzioni significative per la preconfigurazione. Questo consente di abilitare o disabilitare le funzioni dei componenti per soddisfare le esigenze specifiche dei diversi siti.

### Pattern componente proxy {#proxy-component-pattern}

Poiché ogni risorsa di contenuto ha una `sling:resourceType` proprietà che fa riferimento al componente per eseguirne il rendering, in genere è buona norma che queste proprietà facciano riferimento a componenti specifici del sito, invece di puntare a componenti condivisi da più siti. Ciò offre maggiore flessibilità ed evita il refactoring dei contenuti se un sito necessita di un comportamento diverso per un componente, perché questa personalizzazione può essere ottenuta sul componente specifico del sito e non interesserà gli altri siti.

Tuttavia, affinché i componenti specifici del progetto non duplichino codice, devono fare riferimento ciascuno al componente principale condiviso con la `sling:resourceSuperType` proprietà. Questi componenti specifici del progetto che si riferiscono solo ai componenti padre sono denominati &quot;componenti proxy&quot;. I componenti proxy possono essere completamente vuoti se ereditano completamente la funzionalità o se possono ridefinire alcuni aspetti del componente.

### Versione componente {#component-versioning}

I componenti dovrebbero essere mantenuti completamente compatibili nel tempo, ma a volte sono necessarie modifiche che non possono essere mantenute compatibili. Una soluzione a queste esigenze opposte è introdurre il controllo delle versioni dei componenti aggiungendo un numero nel percorso del tipo di risorsa e nei nomi completi delle classi Java delle rispettive implementazioni. Questo numero di versione rappresenta una versione principale come definita dalle linee guida [per il controllo delle versioni](https://semver.org/)semantiche, che viene incrementata solo per le modifiche non compatibili con le versioni precedenti.

Le modifiche non compatibili ai seguenti aspetti dei componenti ne causeranno una nuova versione:

* Modelli Sling (seguendo le linee guida relative alle versioni semantiche)
* Script e modelli HTL
* Selettori HTML e CSS
* Rappresentazione JSON
* Finestre di dialogo

Per ulteriori dettagli, consulta il documento Criteri [di](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies) controllo delle versioni in GitHub.

Il controllo delle versioni dei componenti crea una forma di contratto che è importante per gli aggiornamenti, in quanto chiarisce quando potrebbe essere necessario reimpostare qualcosa. Vedi anche la sezione Compatibilità [di aggiornamento delle personalizzazioni](customizing.md#upgrade-compatibility-of-customizations), che spiega quali considerazioni richiedono diverse forme di personalizzazione per un aggiornamento.

Per evitare migrazioni di contenuti dolorose, è importante non puntare mai direttamente ai componenti con versione dalle risorse di contenuto. Di regola, `sling:resourceType` il contenuto non deve mai avere un numero di versione al suo interno; in caso contrario, l’aggiornamento dei componenti richiederà anche il refactoring del contenuto. Il modo migliore per evitarlo è seguire il pattern [del componente](#proxy-component-pattern) proxy descritto in precedenza.

### Interfacce modello {#model-interfaces}

Questo pattern riguarda l&#39; `data-sly-use` istruzione HTL di puntare a un&#39;interfaccia Java, mentre l&#39;implementazione del modello Sling si sta registrando anche al tipo di risorsa del componente.

Se combinato con il modello [del componente](#proxy-component-pattern) proxy descritto sopra, questo tipo di binding doppia offre i seguenti punti di estensione:

1. Un sito può ridefinire l&#39;implementazione di un modello Sling registrandolo nel tipo di risorsa del componente proxy, senza doversi preoccupare del file HTL, che può comunque puntare all&#39;interfaccia.
1. Un sito può ridefinire la marcatura HTL di un componente, senza considerare a quale logica di implementazione deve puntare.

## Mettere tutto insieme {#putting-it-all-together}

Di seguito è riportata una panoramica dell’intera struttura di binding dei tipi di risorsa, ad esempio il componente Titolo principale. Illustra come un componente proxy specifico per il sito possa risolvere il controllo delle versioni dei componenti, per evitare che la risorsa di contenuto contenga un numero di versione qualsiasi. Viene quindi mostrato come il file `title.html` HTL [del componente utilizza l’interfaccia del modello, mentre l’implementazione si collega alla versione specifica del componente tramite le annotazioni](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html) Modello [](https://sling.apache.org/documentation/bundles/models.html) Sling.

![Panoramica sul binding delle risorse](assets/chlimage_1-32.png)

Di seguito è riportata un&#39;altra panoramica, che non mostra i dettagli dell&#39;implementazione del POJO, ma mostra come vengono utilizzati i [modelli e i criteri](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/page-templates-editable.html) associati.

La `cq:allowedTemplates` proprietà indica quali modelli possono essere utilizzati per un sito e `cq:template` indica per ciascuna pagina quale sia il modello associato. Ogni modello è costituito da tre parti:

* **struttura** - Contiene le risorse che verranno forzate a essere presenti su ciascuna pagina e che l&#39;autore della pagina non potrà eliminare, come ad esempio i componenti dell&#39;intestazione e del piè di pagina.
* **initial** - Contiene il contenuto iniziale che verrà duplicato nella pagina al momento della creazione.
* **criteri** - Contiene per ciascun componente la mappatura a un criterio, ovvero la preconfigurazione del componente. Questa mappatura consente di riutilizzare i criteri tra i modelli, e quindi di essere gestiti a livello centrale.

![Modelli e panoramica dei criteri](assets/screen_shot_2018-12-07at093102.png)

## AEM Project Archetype {#aem-project-archetype}

[AEM Project Archetype](overview.md) crea un progetto Adobe Experience Manager minimo come punto di partenza per i tuoi progetti, incluso un esempio di componenti HTL personalizzati con SlingModels per la logica e la corretta implementazione dei componenti core con il pattern proxy consigliato.

**Articolo successivo:**

* [Utilizzo dei componenti](using.md) di base: per iniziare a usare i componenti di base nel tuo progetto.
* [Personalizzazione dei componenti](customizing.md) di base: per informazioni su come definire lo stile e personalizzare i componenti di base.
