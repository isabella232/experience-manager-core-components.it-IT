---
title: Sviluppo front-end con l’archetipo progetto AEM
description: Scopri il meccanismo di sviluppo front-end opzionale e dedicato dell’archetipo progetto AEM basato su Webpack.
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 99132b49-bd06-4ac2-9348-12c0dfdfe8b2
source-git-commit: bd92a5d1884056ca7b44ea28e5817d8bde10a4d9
workflow-type: ht
source-wordcount: '654'
ht-degree: 100%

---


# Sviluppo front-end con l’archetipo progetto AEM {#front-end}

L’Archetipo progetto AEM include un meccanismo di sviluppo front-end opzionale e dedicato basato su Webpack. Il modulo ui.frontend diventa così la posizione centrale per tutte le risorse front-end del progetto, inclusi i file JavaScript e CSS. Per sfruttare appieno questa funzione utile e flessibile, è importante comprendere in che modo lo sviluppo front-end si inserisce in un progetto AEM.

Questo documento si concentra sui pattern di utilizzo generali del modulo di sviluppo front-end e su ciò che può fare. Per opzioni di build e istruzioni tecniche dettagliate, consulta la documentazione nell’archivio GitHub dell’archetipo.

>[!TIP]
>
>La versione più recente dell’Archetipo progetto AEM [è disponibile su GitHub.](https://github.com/adobe/aem-project-archetype)

## Sviluppo front-end e back-end AEM {#front-end-back-end}

In termini molto semplificati, i progetti AEM si possono considerare costituiti da due parti distinte, ma correlate:

* Lo sviluppo back-end che guida la logica di AEM e produce librerie Java, servizi OSGi, ecc.
* Lo sviluppo front-end che guida la visualizzazione e il comportamento del sito web risultante e la generazione di librerie JavaScript e CSS

Poiché questi due processi di sviluppo si concentrano su parti diverse del progetto, lo sviluppo back-end e front-end può avvenire in parallelo.

![Diagramma del flusso di lavoro front-end](/help/assets/front-end-flow.png)

Tuttavia, qualsiasi progetto risultante deve utilizzare l’output di entrambi i processi di sviluppo, sia back-end che front-end.

## Determinazione del markup {#determining-markup}

Qualunque sia il flusso di lavoro di sviluppo front-end che decidi di implementare per il progetto, gli sviluppatori back-end e gli sviluppatori front-end devono prima concordare il markup. In genere, è AEM che definisce il markup, fornito dai Componenti core. [Tuttavia, il markup può essere personalizzato, se necessario](/help/developing/customizing.md#customizing-the-markup).

## Flussi di lavoro possibili per lo sviluppo front-end {#possible-workflows}

Il modulo di sviluppo front-end è uno strumento utile e molto flessibile, ma non c’è un’opinione prevalente su come dovrebbe essere utilizzato. Di seguito sono riportati due esempi di *possibile* utilizzo, ma le esigenze dei singoli progetti potrebbero sicuramente imporre altri modelli di utilizzo.

### Utilizzo del server di sviluppo statico Webpack {#using-webpack}

Utilizzando Webpack puoi creare stili e sviluppare in base all’output statico di pagine web AEM all’interno del modulo ui.frontend.

1. Visualizza un’anteprima della pagina in AEM utilizzando la modalità di anteprima pagina oppure specificando `wcmmode=disabled` nell’URL
1. Visualizza la sorgente della pagina e salvala come HTML statico nel modulo ui.frontend
1. [Avvia Webpack](#webpack-dev-server) e inizia a creare gli stili e generare i file JavaScript e CSS necessari
1. Esegui `npm run dev` per generare le clientlibs

In questo flusso, uno sviluppatore AEM potrebbe eseguire i passaggi uno e due e passare l’HTML statico allo sviluppatore front-end che sviluppa in base all’output HTML di AEM.

>[!TIP]
>
>È inoltre possibile sfruttare la [libreria dei componenti](https://adobe.com/go/aem_cmp_library_it) per acquisire campioni di output del markup di ciascun componente per lavorare a livello di componente anziché a livello di pagina.

### Utilizzo di Storybook {#using-storybook}

Utilizzando [Storybook](https://storybook.js.org) puoi eseguire uno sviluppo front-end più atomico. Anche se Storybook non è incluso in Archetipo progetto AEM, puoi installarlo e memorizzare gli artefatti di Storybook nel modulo ui.frontend. Quando sono pronti per il test in AEM, possono essere distribuiti come clientlibs eseguendo il comando `npm run dev`.

>[!NOTE]
>
>[Storybook](https://storybook.js.org) non è incluso in Archetipo progetto AEM. Se scegli di utilizzarlo, devi installarlo separatamente.

## Panoramica delle clientlibs {#clientlibs}

Il modulo front-end è reso disponibile utilizzando una [AEM clientlib.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html?lang=it). Durante l’esecuzione dello script di sviluppo NPM, l’app viene sviluppata e il pacchetto `aem-clientlib-generator` prende il risultante output di sviluppo e lo trasforma in una clientlib.

Una clientlib è costituita dai file e dalle directory seguenti:

* `css/`: file CSS che possono essere richiesti nel codice HTML
* `css.txt`: indica ad AEM l’ordine e i nomi dei file in `css/`, in modo che possano essere uniti
* `js/`: file JavaScript che possono essere richiesti nel codice HTML
* `js.txt` indica ad AEM l’ordine e i nomi dei file in `js/`, modo che possano essere uniti
* `resources/`: Mappe sorgente, blocchi di codice non-entrypoint (derivanti dalla suddivisione del codice), risorse statiche (ad esempio icone), ecc.

>[!TIP]
>
>Ulteriori informazioni su come l’AEM gestisce le clientlibs nella [documentazione sullo sviluppo di AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html?lang=it) e come includerli nella [documentazione dei Componenti core.](/help/developing/including-clientlibs.md)
