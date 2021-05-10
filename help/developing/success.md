---
title: Percorsi per il successo con i componenti core
description: Come eseguire correttamente l’implementazione del progetto con i componenti core
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 1ea8cd1c-8435-4ded-82dc-5a7896c53e0c
translation-type: tm+mt
source-git-commit: 056c5bc15ac9e669c3bf6d5da7f060d6eef02608
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 14%

---

# Percorsi per il successo con i componenti core {#paths-to-success}

I componenti core sono potenti, flessibili e facili da usare e personalizzare. Seguendo alcune linee guida chiave descritte in questo documento, il progetto con i componenti core avrà successo.

## Due percorsi per il successo {#two-paths}

Esistono due approcci di base per l’implementazione dei componenti di base, che possono portare al successo, ma hanno le proprie scelte che devono essere considerate per progetto.

1. Mappa le progettazioni sui componenti core e prendi il codice HTML che forniscono. Oppure
1. Se devi rispettare gli standard HTML già definiti, dovrai fare più sforzo e non ottenere tutti i vantaggi dei componenti core.

## Problemi comuni nell’implementazione dei componenti {#common-pitfalls}

Due problemi comuni che portano a progetti che non hanno successo con i componenti core sono:

* **Progetti**  finalizzati - Questi potrebbero anche essere approvati a livello C e vengono consegnati al team di sviluppo per essere implementati in modo perfetto per i pixel senza preoccuparsi della tecnologia sottostante.
* **Guida**  allo stile HTML a livello aziendale: troppo spesso tali guide devono essere seguite dogmaticamente dai componenti che applicano gli stili da una prospettiva dall’alto verso il basso.

In entrambi i casi, i requisiti impostati per i componenti sono così rigidi e specifici che è difficile conformarli a tali requisiti per i componenti core o qualsiasi componente preconfigurato, il che porta allo sviluppo massiccio di componenti personalizzati.

## Inizia presto {#start-early}

Invece di considerare solo i componenti core nella fase di implementazione del progetto, inizia già con i componenti core durante la fase di wireframe e progettazione.

### Utilizzare la libreria dei componenti {#component-library}

Fai riferimento alla [Libreria dei componenti](https://adobe.com/go/aem_cmp_library) già nella fase di progettazione. I componenti core sono potenti e flessibili e possono portarti fino a un punto di partenza. Aggiungi componenti personalizzati solo quando esiste una necessità aziendale reale che non può essere ragionevolmente raggiunta con un componente core.

### Utilizza il kit dell&#39;interfaccia utente per Adobe XD {#ui-kit}

Non appena si verifica una comprovata necessità di un componente personalizzato, utilizza il [kit di interfaccia utente per Adobe XD](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd) in modo che i designer possano iniziare a creare i wireframe e le progettazioni con i componenti core come blocchi predefiniti.

## Non trascurare le funzioni potenti {#powerful-features}

Le funzioni di AEM e i componenti core possono essere molto potenti, ma anche molto sottili e le possibilità di determinate funzionalità potrebbero non essere immediatamente evidenti a un progettista.

### Frammenti di contenuto {#content-fragments}

[I ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html) frammenti di contenuto ti consentono di creare contenuti neutri per il canale, insieme a varianti (eventualmente specifiche per il canale). Puoi quindi utilizzare questi frammenti, con le relative varianti, durante l’authoring di pagine di contenuto.

Insieme alla funzione di esportazione JSON aggiornata, i frammenti di contenuto strutturati possono anche essere utilizzati per distribuire contenuti AEM, tramite Content Services a canali diversi dalle pagine AEM.

### Modelli di frammento esperienza {#experience-fragment-templates}

Se un autore desidera riutilizzare parti (un frammento di un’esperienza) di una pagina. Senza [Frammenti esperienza,](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html) l’autore dovrebbe copiare e incollare tale frammento. Creare e gestire queste esperienze di copia/incolla richiede tempo e può essere fonte di errori da parte dell’utente. Grazie a Frammenti esperienza non è più necessario eseguire operazioni di copia/incolla.

### Componente di incorporamento {#embed-component}

[Il ](/help/components/embed.md) componente Incorpora non solo consente di includere facilmente risorse esterne come i contenuti video di YouTube, ma è anche estensibile per consentirgli di adattare i contenuti in base alle esigenze di un progetto.
