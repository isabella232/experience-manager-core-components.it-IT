---
title: Linee guida per i componenti
description: I Componenti core seguono modelli di implementazione moderni che sono molto diversi da quelli dei componenti di base.
role: Architect, Developer, Admin
exl-id: e8c58fa5-c991-433c-8d38-575dacfc3433
source-git-commit: ee18626280f74a51a799f16d6bf3f5b0be9cd6b9
workflow-type: tm+mt
source-wordcount: '1267'
ht-degree: 99%

---

# Linee guida per i componenti {#component-guidelines}

I [Componenti core](overview.md) seguono modelli di implementazione moderni che sono molto diversi da quelli dei componenti di base.

Questa pagina spiega i modelli e indica quando utilizzarli per creare componenti personalizzati. La prima sezione [Modelli generici dei componenti](#general-component-patterns) vale per qualsiasi tipo di componente, mentre la seconda sezione [Modelli di componenti riutilizzabili](#reusable-component-patterns) vale per i componenti destinati a essere riutilizzati per vari siti o progetti, come, ad esempio, i Componenti core.

## Modelli generici dei componenti {#general-component-patterns}

Le linee guida illustrate in questa sezione sono consigliate per qualsiasi tipo di componente, indipendentemente dal fatto che sia specifico per un singolo progetto o debba essere ampiamente riutilizzato per più siti o progetti.

### Componenti configurabili {#configurable-components}

I componenti possono avere finestre di dialogo con diverse opzioni. Questa caratteristica dovrebbe essere utilizzata al meglio per rendere i componenti flessibili e configurabili ed evitare di implementare tanti componenti che spesso non sono che varianti l’uno dell’altro.

In genere, se un wireframe o un design contiene varianti di elementi simili, queste varianti non devono essere implementate come componenti diversi, ma come un unico componente con opzioni per la scelta delle varianti.

Per fare un ulteriore passo in avanti, se i componenti vengono riutilizzati per più siti o progetti, vedi la sezione [Funzionalità preconfigurabili](#pre-configurable-capabilities).

### Separazione tra logica e markup {#separation-of-concerns}

In genere, è consigliabile tenere separata la logica (o modello) di un componente dal modello di markup (o vista). Ci sono diversi modi per farlo, tuttavia quello consigliato è utilizzare i [modelli Sling](https://sling.apache.org/documentation/bundles/models.html) per la logica e l’[HTML Template Language](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=it) (HTL) per il markup, come fanno anche i Componenti core.

I modelli Sling sono un set di annotazioni Java per accedere facilmente alle variabili necessarie dai POJO (Plain Old Java Object) e offrono quindi un modo semplice, efficace ed efficiente di implementare la logica Java per i componenti.

L’HTL è stato concepito appositamente come linguaggio di modelli sicuro e semplice per AEM. Può richiamare molte forme di logica e ciò lo rende molto flessibile.

## Modelli di componenti riutilizzabili {#reusable-component-patterns}

Anche le linee guida incluse in questa sezione possono essere utilizzate per qualsiasi tipo di componente, tuttavia hanno più senso per i componenti destinati a essere riutilizzati per più siti o progetti, come, ad esempio, i Componenti core. Pertanto, queste linee guida possono essere ignorate per i componenti utilizzati solo su un singolo sito o progetto.

### Funzionalità preconfigurabili {#pre-configurable-capabilities}

Oltre alla finestra di dialogo per modifica utilizzata dagli autori di pagine, i componenti possono avere anche una finestra di dialogo per progettazione per consentire agli autori di modelli di preconfigurarli. L’[Editor di modelli](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=it) consente di impostare tutte queste preconfigurazioni, che sono chiamate “Criteri”.

Per rendere i componenti il più possibile riutilizzabili, è necessario fornire loro opzioni significative per la preconfigurazione. Ciò consente di abilitare o disabilitare funzioni dei componenti, in modo che soddisfino le esigenze specifiche dei vari siti.

### Modello di componente proxy {#proxy-component-pattern}

Poiché ogni risorsa di contenuto ha una proprietà `sling:resourceType` che fa riferimento al componente per eseguirne il rendering, in genere è buona prassi che queste proprietà puntino ai componenti specifici del sito, invece di puntare ai componenti condivisi da più siti. Ciò offre maggiore flessibilità ed evita il refactoring del contenuto, nel caso un sito necessiti di un comportamento diverso di un componente, perché questa personalizzazione può quindi essere applicata al componente specifico per il sito e non influisce sugli altri siti.

Tuttavia, affinché i componenti specifici del progetto non debbano duplicare il codice, ciascuno di essi deve fare riferimento al componente principale condiviso con la proprietà `sling:resourceSuperType`. Questi componenti specifici del progetto, che sono principalmente solo componenti padre, vengono detti “componenti proxy”. I componenti proxy possono essere completamente vuoti, se ereditano interamente la funzionalità, oppure se ne possono ridefinire alcuni aspetti.

>[!TIP]
>
>Per informazioni dettagliate su come creare componenti proxy, vedi [Utilizzo dei componenti proxy](/help/get-started/using.md#create-proxy-components).

### Controllo delle versioni dei componenti {#component-versioning}

I componenti devono restare completamente compatibili nel tempo, ma talvolta sono necessarie modifiche che non possono essere mantenute compatibili. Una soluzione che soddisfa queste opposte esigenze consiste nell’introdurre il controllo delle versioni dei componenti, aggiungendo un numero nel loro percorso del tipo di risorsa e nei nomi qualificati delle classi Java per le loro implementazioni. Questo numero rappresenta una versione principale, secondo quanto definito dalle [linee guida per il controllo delle versioni semantiche](https://semver.org/), e viene incrementato solo per modifiche che non sono compatibili con le versioni precedenti.

Le modifiche non compatibili apportate ai seguenti aspetti dei componenti daranno origine a una nuova versione:

* Modelli Sling (seguendo le linee guida per il controllo delle versioni semantiche)
* Script e modelli HTL
* Markup HTML e selettori CSS
* Rappresentazione JSON
* Finestre di dialogo

Per ulteriori dettagli, vedi il documento [Criteri di controllo delle versioni](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies) in GitHub.

Il controllo delle versioni dei componenti crea una forma di contratto importante per gli aggiornamenti, in quanto chiarisce quando potrebbe essere necessario il refactoring di un elemento. Vedi anche la sezione [Compatibilità delle personalizzazioni in un aggiornamento](customizing.md#upgrade-compatibility-of-customizations), che spiega quali considerazioni richiedono le diverse forme di personalizzazione per un aggiornamento.

Per evitare complicate migrazioni di contenuto, è importante non puntare mai direttamente ai componenti con versioni dalle risorse di contenuto. Come regola empirica, una proprietà `sling:resourceType` del contenuto non deve mai avere un numero di versione, altrimenti l’aggiornamento dei componenti richiederà il refactoring del contenuto. Il modo migliore per evitarlo è seguire il [modello di componente proxy](#proxy-component-pattern) descritto sopra.

### Interfacce di modello {#model-interfaces}

Questo modello prevede che l’istruzione HTL `data-sly-use` punti a un’interfaccia Java, mentre anche l’implementazione del modello Sling si registra per il tipo di risorsa del componente.

In combinazione con il [modello di componente proxy](#proxy-component-pattern) descritto sopra, questa forma di doppia associazione offre i seguenti validi punti di estensione:

1. Un sito può ridefinire l’implementazione di un modello Sling registrandolo per il tipo di risorsa del componente proxy, senza dover tenere conto del file HTL, che può ancora puntare all’interfaccia.
1. Un sito può ridefinire il markup HTL di un componente senza dover considerare a quale logica di implementazione deve puntare.

## Tutti gli elementi insieme {#putting-it-all-together}

Di seguito è riportata una panoramica dell’intera struttura di associazione dei tipi di risorsa, come, ad esempio, il componente core Titolo. La panoramica illustra come un componente proxy specifico del sito consenta di risolvere il controllo delle versioni dei componenti per evitare che la risorsa di contenuto contenga un numero di versione. Mostra altresì come il file [HTL](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html) `title.html` del componente utilizzi l’interfaccia di modello, mentre l’implementazione si associa alla versione specifica del componente tramite le annotazioni del [modello Sling](https://sling.apache.org/documentation/bundles/models.html).

![Panoramica sull’associazione delle risorse](/help/assets/chlimage_1-32.png)

Di seguito è riportata un’altra panoramica che non mostra i dettagli del POJO (Plain Old Java Object) di implementazione, ma rivela come viene fatto riferimento ai [modelli e criteri](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html) associati.

La proprietà `cq:allowedTemplates` indica quali modelli possono essere utilizzati per un sito e la proprietà `cq:template` indica qual è il modello associato a ciascuna pagina. Ogni modello consta di tre parti:

* **struttura**: contiene le risorse che verranno forzate su ciascuna pagina e che l’autore della pagina non potrà eliminare, come, ad esempio, intestazioni e piè di pagina.
* **iniziale**: include il contenuto iniziale che verrà duplicato nella pagina, quando viene creata.
* **criterio**: contiene il mapping a un criterio per ciascun componente, che rappresenta la preconfigurazione di quel componente. Il mapping consente di riutilizzare i criteri in vari modelli, che quindi possono essere gestiti in modo centralizzato.

![Panoramica di modelli e criteri](/help/assets/screen_shot_2018-12-07at093102.png)

## Archetipo progetto AEM {#aem-project-archetype}

[L’Archetipo progetto AEM](/help/developing/archetype/overview.md) crea un progetto Adobe Experience Manager minimo come punto di partenza per i tuoi progetti, incluso un esempio di componenti HTL personalizzati con i modelli Sling per la logica e la corretta implementazione dei Componenti core con il modello proxy consigliato.

**Articolo successivo:**

* [Utilizzo dei componenti core](/help/get-started/using.md): scopri come utilizzare i Componenti core nel tuo progetto.
* [Personalizzazione dei Componenti core](customizing.md): per scoprire come assegnare stili e personalizzare i Componenti core.
