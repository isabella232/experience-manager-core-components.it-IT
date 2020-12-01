---
title: Linee guida per i componenti
description: I componenti core seguono modelli di implementazione moderni che sono molto diversi dai componenti di base.
translation-type: tm+mt
source-git-commit: 2926c51c2ab97b50b9ec4942cd5415c15a1411b6
workflow-type: tm+mt
source-wordcount: '1259'
ht-degree: 2%

---


# Linee guida per i componenti {#component-guidelines}

I [Componenti di base](overview.md) seguono modelli di implementazione moderni che sono molto diversi dai componenti di base.

In questa pagina sono illustrati questi pattern e quando utilizzarli per creare componenti modificabili personalizzati. La prima sezione [Pattern componenti generali](#general-component-patterns) si applica a qualsiasi tipo di componente, mentre la seconda sezione [Pattern componenti riutilizzabili](#reusable-component-patterns) si applica ai componenti destinati a essere riutilizzati tra siti o progetti, come ad esempio i Componenti di base.

## Pattern componenti generali {#general-component-patterns}

Le linee guida di questa sezione sono consigliate per qualsiasi tipo di componente, a prescindere dal fatto che il componente sia specifico per un singolo progetto o che sia destinato a essere ampiamente riutilizzato su più siti o progetti.

### Componenti configurabili {#configurable-components}

I componenti possono avere finestre di dialogo con diverse opzioni. Questo dovrebbe essere sfruttato per rendere i componenti flessibili e configurabili ed evitare di implementare più componenti che sono per lo più varianti l&#39;uno dell&#39;altro.

In genere, se un wireframe o un progetto contiene varianti di elementi simili, queste varianti non devono essere implementate come componenti diversi, ma come un componente unico con opzioni per scegliere tra le varianti.

Per fare un passo avanti, se i componenti vengono riutilizzati tra siti o progetti, consultare la sezione [Capacità preconfigurabili](#pre-configurable-capabilities).

### Separazione delle preoccupazioni {#separation-of-concerns}

In genere è consigliabile tenere separata la logica (o il modello) di un componente dal modello (o dalla vista) di marcatura. Esistono diversi modi per ottenere questo, tuttavia quello consigliato è utilizzare [Sling Models](https://sling.apache.org/documentation/bundles/models.html) per la logica e il [HTML Template Language](https://docs.adobe.com/content/help/it-IT/experience-manager-htl/using/overview.html) (HTL) per la marcatura, come anche i componenti core.

Sling Models è una serie di annotazioni Java per accedere facilmente alle variabili necessarie dai POJO, e quindi offre un modo semplice, potente ed efficiente per implementare la logica Java per i componenti.

HTL è stato progettato per essere un linguaggio di modello semplice e sicuro, adatto per AEM. Può chiamare molte forme di logica, che la rende molto flessibile.

## Pattern componenti riutilizzabili {#reusable-component-patterns}

Le linee guida di questa sezione possono essere utilizzate anche per qualsiasi tipo di componente, ma hanno più senso per i componenti che devono essere riutilizzati tra siti o progetti, come ad esempio i componenti core. Queste linee guida possono pertanto essere ignorate per i componenti utilizzati solo su un singolo sito o progetto.

### Capacità preconfigurabili {#pre-configurable-capabilities}

Oltre alla finestra di dialogo di modifica utilizzata dagli autori delle pagine, i componenti possono anche avere una finestra di dialogo di progettazione per consentire agli autori dei modelli di preconfigurarli. [Editor modelli](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) consente di impostare tutte queste preconfigurazioni, che sono denominate &quot;Criteri&quot;.

Per rendere i componenti il più possibile riutilizzabili, è necessario fornire loro opzioni significative per la preconfigurazione. Questo consente di abilitare o disabilitare le funzioni dei componenti per soddisfare le esigenze specifiche dei diversi siti.

### Pattern componente proxy {#proxy-component-pattern}

Poiché ogni risorsa di contenuto dispone di una proprietà `sling:resourceType` che fa riferimento al componente per eseguirne il rendering, in genere è buona norma che queste proprietà facciano riferimento a componenti specifici del sito, invece di puntare a componenti condivisi da più siti. Ciò offre maggiore flessibilità ed evita il refactoring dei contenuti se un sito necessita di un comportamento diverso per un componente, perché questa personalizzazione può essere ottenuta sul componente specifico del sito e non interesserà gli altri siti.

Tuttavia, affinché i componenti specifici del progetto non duplichino codice, devono fare riferimento ciascuno al componente principale condiviso con la proprietà `sling:resourceSuperType`. Questi componenti specifici del progetto che si riferiscono solo ai componenti padre sono denominati &quot;componenti proxy&quot;. I componenti proxy possono essere completamente vuoti se ereditano completamente la funzionalità o se possono ridefinire alcuni aspetti del componente.

### Versione componente {#component-versioning}

I componenti dovrebbero essere mantenuti completamente compatibili nel tempo, ma a volte sono necessarie modifiche che non possono essere mantenute compatibili. Una soluzione a queste esigenze opposte è introdurre il controllo delle versioni dei componenti aggiungendo un numero nel percorso del tipo di risorsa e nei nomi completi delle classi Java delle rispettive implementazioni. Questo numero di versione rappresenta una versione principale come definito dalle [linee guida relative alle versioni semantiche](https://semver.org/), che viene incrementata solo per le modifiche non compatibili con le versioni precedenti.

Le modifiche non compatibili ai seguenti aspetti dei componenti ne causeranno una nuova versione:

* Modelli Sling (seguendo le linee guida relative alle versioni semantiche)
* Script e modelli HTL
* Selettori HTML e CSS
* Rappresentazione JSON
* Finestre di dialogo

Per ulteriori dettagli, vedere il documento [Criteri di gestione delle versioni](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies) in GitHub.

Il controllo delle versioni dei componenti crea una forma di contratto che è importante per gli aggiornamenti, in quanto chiarisce quando potrebbe essere necessario reimpostare qualcosa. Vedere anche la sezione [Compatibilità di aggiornamento di Personalizzazioni](customizing.md#upgrade-compatibility-of-customizations), che spiega quali considerazioni richiedono diverse forme di personalizzazione per un aggiornamento.

Per evitare migrazioni di contenuti dolorose, è importante non puntare mai direttamente ai componenti con versione dalle risorse di contenuto. Di regola, un `sling:resourceType` contenuto non deve mai avere un numero di versione al suo interno, altrimenti per aggiornare i componenti sarà necessario modificare anche il contenuto. Il modo migliore per evitarlo è seguire il [Pattern componente proxy](#proxy-component-pattern) descritto sopra.

### Interfacce modello {#model-interfaces}

Questo pattern riguarda l&#39;istruzione HTL `data-sly-use` di puntare a un&#39;interfaccia Java, mentre l&#39;implementazione del modello Sling si sta registrando anche al tipo di risorsa del componente.

Se combinato con il modello di componente proxy [Proxy](#proxy-component-pattern) descritto sopra, questo tipo di doppia associazione offre i seguenti bei punti di estensione:

1. Un sito può ridefinire l&#39;implementazione di un modello Sling registrandolo nel tipo di risorsa del componente proxy, senza doversi occupare del file HTL, che può comunque puntare all&#39;interfaccia.
1. Un sito può ridefinire la marcatura HTL di un componente, senza considerare a quale logica di implementazione deve puntare.

## Mettere tutto insieme {#putting-it-all-together}

Di seguito è riportata una panoramica dell’intera struttura di binding dei tipi di risorsa, ad esempio il componente Titolo principale. Illustra come un componente proxy specifico per il sito possa risolvere il controllo delle versioni dei componenti, per evitare che la risorsa di contenuto contenga un numero di versione qualsiasi. Viene quindi mostrato come il file `title.html` [HTL](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html) del componente utilizza l&#39;interfaccia del modello, mentre l&#39;implementazione si collega alla versione specifica del componente tramite le annotazioni [Sling Model](https://sling.apache.org/documentation/bundles/models.html).

![Panoramica sul binding delle risorse](/help/assets/chlimage_1-32.png)

Di seguito è riportata un&#39;altra panoramica, che non mostra i dettagli dell&#39;implementazione di POJO, ma rivela come i [modelli e criteri ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html) associati sono citati.

La proprietà `cq:allowedTemplates` indica quali modelli possono essere utilizzati per un sito, mentre la proprietà `cq:template` indica per ciascuna pagina quale sia il modello associato. Ogni modello è costituito da tre parti seguenti:

* **struttura**  - Contiene le risorse che verranno forzate a essere presenti su ciascuna pagina e che l&#39;autore della pagina non potrà eliminare, come ad esempio i componenti dell&#39;intestazione e del piè di pagina.
* **initial**  - Contiene il contenuto iniziale che verrà duplicato nella pagina al momento della creazione.
* **criteri**  - Contiene per ciascun componente la mappatura a un criterio, ovvero la preconfigurazione del componente. Questa mappatura consente di riutilizzare i criteri tra i modelli, e quindi di essere gestiti a livello centrale.

![Modelli e panoramica dei criteri](/help/assets/screen_shot_2018-12-07at093102.png)

## AEM Project Archetype {#aem-project-archetype}

[AEM Project ](/help/developing/archetype/overview.md) Archetyspecifica un progetto Adobe Experience Manager minimo come punto di partenza per i vostri progetti, incluso un esempio di componenti HTL personalizzati con SlingModels per la logica e la corretta implementazione dei componenti core con il pattern proxy consigliato.

**Articolo successivo:**

* [Utilizzo dei componenti](/help/get-started/using.md)  di base: per iniziare a usare i componenti di base nel tuo progetto.
* [Personalizzazione dei componenti](customizing.md)  core - per imparare a personalizzare lo stile dei componenti core.
