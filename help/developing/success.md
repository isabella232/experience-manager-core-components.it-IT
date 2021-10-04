---
title: Come utilizzare in modo efficace i Componenti core
description: Come eseguire correttamente l’implementazione del progetto con i Componenti core
role: Architect, Developer, Admin, User
exl-id: 1ea8cd1c-8435-4ded-82dc-5a7896c53e0c
source-git-commit: 888719359f9a1d1c9dccff97fb639b332f2be54c
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 97%

---

# Come utilizzare in modo efficace i Componenti core {#paths-to-success}

I Componenti core sono efficienti, flessibili e facili da usare e personalizzare. L’aderenza ad alcune linee guida chiave, presentate in questo documento, garantirà il successo del tuo progetto con i Componenti core.

## Due percorsi per un utilizzo efficace {#two-paths}

Esistono fondamentalmente due approcci per un’implementazione efficace dei Componenti core, ma entrambi presuppongono di effettuare delle scelte che vanno ponderate in base al singolo progetto.

1. Struttura i tuoi progetti sulla base dei Componenti core e utilizza il codice HTML che ti forniscono. Oppure
1. Se devi rispettare standard HTML già definiti, dovrai faticare di più e avrai meno vantaggi dai Componenti core.

## Insidie comuni nell’implementazione dei componenti {#common-pitfalls}

Due problemi comuni che impediscono la riuscita di progetti con i Componenti core:

* **Progetti finalizzati**: questi progetti potrebbero anche essere approvati ad alto e assegnati al team di sviluppo per essere implementati alla perfezione, senza però preoccuparsi della tecnologia che ne è alla base.
* **Linee guida per HTML a livello aziendale**: troppo spesso queste linee guida devono essere seguite dogmaticamente dai componenti con applicazione degli stili decisa dall’alto.

In entrambi i casi, i requisiti impostati per i componenti sono così rigidi e specifici che è difficile per i Componenti core o qualsiasi altro componente preconfigurato adattarvisi appieno, con conseguente sviluppo massiccio di componenti personalizzati.

## Inizia presto {#start-early}

Invece di considerare l’utilizzo dei Componenti core durante l’implementazione del progetto, parti già con i Componenti core durante la fase di design e creazione del wireframe.

### Utilizza la libreria dei componenti {#component-library}

Considera l’utilizzo della [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_it) già nella fase di design. I Componenti core sono efficienti e flessibili e possono accompagnarti lontano te sin da subito. Aggiungi componenti personalizzati solo in presenza di un’effettiva esigenza aziendale che non può essere ragionevolmente soddisfatta con un Componente core.

### Utilizza il kit di interfaccia utente per Adobe XD {#ui-kit}

Non appena si determina la comprovata necessità di un componente personalizzato, utilizza il [kit di interfaccia utente per Adobe XD](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd), in modo che i designer possano iniziare a creare wireframe e design con i Componenti core come elementi costitutivi.

## Non trascurare le funzioni più efficaci {#powerful-features}

Le funzioni di AEM e dei Componenti core possono essere molto efficienti, ma anche molto sfuggenti e determinate funzionalità potrebbero non risultare immediatamente evidenti a un designer.

### Frammenti di contenuto {#content-fragments}

I [Frammenti di contenuto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html) consentono di creare contenuto versatile utilizzabile in qualsiasi canale, con possibili varianti per canali specifici. Puoi quindi utilizzare questi frammenti, con le relative varianti, durante l’authoring di pagine di contenuto.

Insieme alla funzione di esportazione JSON aggiornata, i frammenti di contenuto strutturati possono anche essere utilizzati per distribuire contenuti AEM, tramite Content Services a canali diversi dalle pagine AEM.

### Modelli di Frammento esperienza {#experience-fragment-templates}

Se un autore desidera riutilizzare parti (un frammento di un’esperienza) di una pagina. Senza [Frammenti esperienza](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html), l’autore dovrebbe copiare e incollare ogni frammento. Creare e gestire queste esperienze di copia/incolla richiede tempo e può essere fonte di errori da parte dell’utente. Grazie a Frammenti esperienza non è più necessario eseguire operazioni di copia/incolla.

### Componente Incorpora {#embed-component}

[Il componente Incorpora](/help/components/embed.md) non solo consente di includere facilmente risorse esterne, come i video di YouTube, ma è anche estensibile per consentirgli di includere contenuto in base alle esigenze di un progetto.
