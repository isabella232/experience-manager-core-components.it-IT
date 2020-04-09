---
title: Percorsi per il successo con i componenti core
description: Come ottenere successo durante l’implementazione del progetto con i componenti core
translation-type: tm+mt
source-git-commit: c338428a681f652d17bb972fb6a2abf216a338c3

---


# Percorsi per il successo con i componenti core {#paths-to-success}

I componenti core sono potenti, flessibili e facili da usare e personalizzare. Seguendo alcune linee guida chiave come indicato in questo documento, il progetto con i componenti core avrà esito positivo.

## Due percorsi per il successo {#two-paths}

Esistono due approcci di base per l&#39;implementazione dei componenti core, che possono portare al successo, ma che devono essere considerati progetti per progetto.

1. Mappate i vostri progetti sui componenti core e ottenete il codice HTML fornito. Oppure
1. Se devi rispettare gli standard HTML già definiti, avrai bisogno di maggiore impegno e non potrai sfruttare tutti i vantaggi offerti dai componenti core.

## Pitfall comuni nell&#39;implementazione dei componenti {#common-pitfalls}

Due problemi comuni che portano al fallimento dei progetti con i componenti core sono:

* **Progetti** finiti - Questi possono anche essere approvati a livello C e vengono consegnati al team di sviluppo per essere implementati in modo perfetto in pixel, senza preoccuparsi della tecnologia sottostante.
* **Guida** allo stile HTML a livello di società: troppo spesso tali guide devono essere seguite dogmaticamente dai componenti che applicano gli stili in una prospettiva dall&#39;alto verso il basso.

In entrambi i casi, i requisiti applicati ai componenti sono talmente rigidi e specifici da rendere difficile la conformità dei componenti core o di qualsiasi componente out-of-the-box, con conseguente sviluppo massiccio di componenti personalizzati.

## Inizia presto {#start-early}

Invece di considerare solo i componenti core nella fase di implementazione del progetto, iniziate già con i componenti core durante la fase di wireframe e progettazione.

### Uso della libreria dei componenti {#component-library}

Fare riferimento alla Libreria [](https://adobe.com/go/aem_cmp_library) componenti già in fase di progettazione. I componenti core sono potenti e flessibili e possono portarvi a un punto di partenza. Aggiungi componenti personalizzati solo se esiste una necessità aziendale reale che non può essere ragionevolmente raggiunta con un componente core.

### Usare il kit dell&#39;interfaccia utente per Adobe XD {#ui-kit}

Non appena si verifica la necessità di un componente personalizzato, utilizzate il kit di [interfaccia utente per Adobe XD](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_Wireframe.xd) in modo che i designer possano iniziare a creare i wireframe e i design con i componenti core come elementi di base.

## Non ignorare le potenti funzioni {#powerful-features}

Le funzioni di AEM e dei componenti core possono essere molto potenti, ma anche molto sottili e le possibilità per determinate funzionalità potrebbero non essere immediatamente evidenti a un designer.

### Frammenti di contenuto {#content-fragments}

[I frammenti](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html) di contenuto consentono di creare contenuti versatili per canali e varianti (eventualmente specifiche per i canali). Puoi quindi utilizzare questi frammenti, con le relative varianti, durante l’authoring di pagine di contenuto.

Insieme alla funzione di esportazione JSON aggiornata, i frammenti di contenuto strutturati possono anche essere utilizzati per distribuire contenuti AEM, tramite Content Services a canali diversi dalle pagine AEM.

### Modelli di frammento esperienza {#experience-fragment-templates}

Se un autore desidera riutilizzare parti (un frammento di un’esperienza) di una pagina. Without [Experience Fragments,](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html) the author would need to copy and paste that fragment. Creare e gestire queste esperienze di copia/incolla richiede tempo e può essere fonte di errori da parte dell’utente. Grazie a Frammenti esperienza non è più necessario eseguire operazioni di copia/incolla.

### Il componente Incorpora {#embed-component}

[Il componente](/help/components/embed.md) Incorpora non solo consente di includere semplicemente risorse esterne come i contenuti video di YouTube, ma è anche estensibile per consentirgli di soddisfare le esigenze specifiche di un progetto.