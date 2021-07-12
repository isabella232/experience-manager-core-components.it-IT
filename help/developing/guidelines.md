---
title: Linee guida per i componenti
description: I componenti core seguono modelli di implementazione moderni che sono molto diversi dai componenti di base.
role: Architect, Developer, Admin
exl-id: e8c58fa5-c991-433c-8d38-575dacfc3433
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '1272'
ht-degree: 2%

---

# Linee guida per i componenti {#component-guidelines}

I [Componenti core](overview.md) seguono modelli di implementazione moderni che sono molto diversi dai componenti di base.

Questa pagina spiega questi pattern e quando utilizzarli per creare componenti di authoring personalizzati. La prima sezione [Pattern generali dei componenti](#general-component-patterns) si applica a qualsiasi tipo di componente, mentre la seconda sezione [Pattern di componenti riutilizzabili](#reusable-component-patterns) si applica ai componenti destinati a essere riutilizzati tra siti o progetti, ad esempio i componenti core.

## Pattern dei componenti generali {#general-component-patterns}

Le linee guida illustrate in questa sezione sono consigliate per qualsiasi tipo di componente, indipendentemente dal fatto che sia specifico per un singolo progetto o se il componente debba essere ampiamente riutilizzato su più siti o progetti.

### Componenti configurabili {#configurable-components}

I componenti possono avere finestre di dialogo con diverse opzioni. Questo dovrebbe essere sfruttato per rendere i componenti flessibili e configurabili ed evitare di implementare più componenti che sono per lo più varianti tra loro.

In genere, se un wireframe o un design contiene varianti di elementi simili, queste varianti non devono essere implementate come componenti diversi, ma come un componente con opzioni per scegliere tra le varianti.

Per fare un ulteriore passo, se i componenti vengono riutilizzati tra siti o progetti, consulta la sezione [Capacità preconfigurabili](#pre-configurable-capabilities) .

### Separazione delle preoccupazioni {#separation-of-concerns}

In genere è consigliabile mantenere separata la logica (o il modello) di un componente dal modello di markup (o dalla vista). Ci sono diversi modi per farlo, tuttavia quello consigliato è quello di utilizzare [Sling Models](https://sling.apache.org/documentation/bundles/models.html) per la logica e il [HTML Template Language](https://docs.adobe.com/content/help/it-IT/experience-manager-htl/using/overview.html) (HTL) per il markup, come fanno anche i componenti core.

I modelli Sling sono un set di annotazioni Java per accedere facilmente alle variabili necessarie dai POJO e offrono quindi un modo semplice, potente ed efficiente per implementare la logica Java per i componenti.

HTL è stato progettato per essere un linguaggio di modelli sicuro e semplice, personalizzato per AEM. Può chiamare molte forme di logica, che la rendono molto flessibile.

## Pattern di componenti riutilizzabili {#reusable-component-patterns}

Le linee guida incluse in questa sezione possono essere utilizzate anche per qualsiasi tipo di componente, ma hanno più senso per i componenti destinati a essere riutilizzati su siti o progetti, ad esempio i componenti core. Queste linee guida possono pertanto essere ignorate per i componenti utilizzati solo su un singolo sito o progetto.

### Funzionalità preconfigurabili {#pre-configurable-capabilities}

Oltre alla finestra di dialogo di modifica utilizzata dagli autori delle pagine, i componenti possono avere anche una finestra di dialogo di progettazione per consentire agli autori dei modelli di preconfigurarli. L&#39; [Editor modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) consente di impostare tutte queste preconfigurazioni, che sono denominate &quot;Criteri&quot;.

Per rendere i componenti il più possibile riutilizzabili, è necessario fornire loro opzioni significative per la preconfigurazione. Questo consente di abilitare o disabilitare le funzioni dei componenti in modo che soddisfino le esigenze specifiche dei diversi siti.

### Pattern componente proxy {#proxy-component-pattern}

Poiché ogni risorsa di contenuto ha una proprietà `sling:resourceType` che fa riferimento al componente per eseguirne il rendering, in genere è buona prassi che queste proprietà puntino a componenti specifici del sito, invece di puntare a componenti condivisi da più siti. Questo offre maggiore flessibilità ed evita il refactoring dei contenuti se un sito necessita di un comportamento diverso per un componente, perché questa personalizzazione può quindi essere ottenuta sul componente specifico per il sito e non influisce sugli altri siti.

Tuttavia, affinché i componenti specifici del progetto non duplichino alcun codice, ciascuno di essi deve fare riferimento al componente principale condiviso con la proprietà `sling:resourceSuperType` . Questi componenti specifici del progetto che si riferiscono principalmente solo ai componenti padre sono chiamati &quot;componenti proxy&quot;. I componenti proxy possono essere completamente vuoti se ereditano completamente la funzionalità o se possono ridefinire alcuni aspetti del componente.

>[!TIP]
>
>Per informazioni dettagliate su come creare componenti proxy, consulta [Uso dei componenti core](/help/get-started/using.md#create-proxy-components) .

### Controllo delle versioni dei componenti {#component-versioning}

I componenti devono essere mantenuti completamente compatibili nel tempo, ma talvolta sono necessarie modifiche che non possono essere mantenute compatibili. Una soluzione a queste esigenze opposte è quella di introdurre il controllo delle versioni dei componenti aggiungendo un numero nel loro percorso del tipo di risorsa e nei nomi delle classi Java complete delle loro implementazioni. Questo numero di versione rappresenta una versione principale come definito dalle [linee guida per il controllo delle versioni semantiche](https://semver.org/), che viene incrementata solo per le modifiche non compatibili con le versioni precedenti.

Le modifiche non compatibili ai seguenti aspetti dei componenti ne risulteranno in una nuova versione:

* Modelli Sling (seguendo le linee guida per il controllo delle versioni semantiche)
* Script e modelli HTL
* Selettori HTML e CSS
* Rappresentazione JSON
* Finestre di dialogo

Per ulteriori dettagli, consulta il documento [Criteri di controllo delle versioni](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies) in GitHub.

Il controllo delle versioni dei componenti crea una forma di contratto importante per gli aggiornamenti, in quanto chiarisce quando potrebbe essere necessario eseguire il refactoring di un elemento. Vedi anche la sezione [Compatibilità di aggiornamento di Personalizzazioni](customizing.md#upgrade-compatibility-of-customizations), che spiega quali considerazioni richiedono diverse forme di personalizzazione per un aggiornamento.

Per evitare migrazioni dolorose dei contenuti, è importante non puntare mai direttamente ai componenti con versioni dalle risorse dei contenuti. Di regola, un `sling:resourceType` del contenuto non deve mai avere un numero di versione, altrimenti per l’aggiornamento dei componenti sarà necessario eseguire il refactoring anche del contenuto. Il modo migliore per evitarlo è seguire il [Pattern del componente proxy](#proxy-component-pattern) descritto sopra.

### Interfacce modello {#model-interfaces}

Questo pattern riguarda l’istruzione di HTL `data-sly-use` di puntare a un’interfaccia Java, mentre l’implementazione del modello Sling si registra anche al tipo di risorsa del componente.

In combinazione con il [Pattern componente proxy](#proxy-component-pattern) descritto sopra, questo tipo di offerte a doppio binding segue buoni punti di estensione:

1. Un sito può ridefinire l&#39;implementazione di un modello Sling registrandolo al tipo di risorsa del componente proxy, senza tenere conto del file HTL, che può ancora puntare all&#39;interfaccia.
1. Un sito può ridefinire il markup HTL di un componente senza considerare a quale logica di implementazione deve puntare.

## Mettere tutto insieme {#putting-it-all-together}

Di seguito è riportata una panoramica dell’intera struttura di binding dei tipi di risorsa, ad esempio il componente di base Titolo . Illustra come un componente proxy specifico per il sito consente di risolvere il controllo delle versioni dei componenti, per evitare che la risorsa di contenuto contenga numeri di versione. Mostra quindi come il file `title.html` [HTL](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html) del componente utilizza l&#39;interfaccia del modello, mentre l&#39;implementazione si lega alla versione specifica del componente tramite le annotazioni [Sling Model](https://sling.apache.org/documentation/bundles/models.html) .

![Panoramica sul binding delle risorse](/help/assets/chlimage_1-32.png)

Di seguito è riportata un&#39;altra panoramica, che non mostra i dettagli del POJO di implementazione, ma rivela come si fa riferimento ai [modelli e ai criteri ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html) associati.

La proprietà `cq:allowedTemplates` indica quali modelli possono essere utilizzati per un sito e il `cq:template` indica per ogni pagina quale sia il modello associato. Ogni modello è costituito da tre parti seguenti:

* **struttura** : contiene le risorse che verranno forzate sulla presenza di ogni pagina e che l’autore della pagina non sarà in grado di eliminare, come ad esempio i componenti di intestazione e piè di pagina.
* **initial**  - Contiene il contenuto iniziale che verrà duplicato nella pagina quando viene creato.
* **policy**  - Contiene per ogni componente la mappatura a un criterio, ovvero la preconfigurazione del componente. Questa mappatura consente di riutilizzare i criteri tra i vari modelli e quindi di gestirli centralmente.

![Modelli e panoramica dei criteri](/help/assets/screen_shot_2018-12-07at093102.png)

## AEM Project Archetype {#aem-project-archetype}

[L’](/help/developing/archetype/overview.md) archivio dei progetti di AEM individua un progetto Adobe Experience Manager minimo come punto di partenza per i tuoi progetti, incluso un esempio di componenti HTL personalizzati con SlingModels per la logica e la corretta implementazione dei componenti core con il modello proxy consigliato.

**Articolo successivo:**

* [Utilizzo dei componenti core](/help/get-started/using.md) : scopri come utilizzare i componenti core nel tuo progetto.
* [Personalizzazione dei componenti core](customizing.md) : per scoprire come assegnare stile e personalizzare i componenti core.
