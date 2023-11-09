---
title: Come si ottengono temi e modelli di esempio per i componenti core di AEM Forms?
description: I componenti core di AEM Forms forniscono esempi di temi, modelli e modelli di dati per moduli adattivi.
solution: Experience Manager Forms
topic: Administration
role: Admin, User
level: Intermediate
exl-id: aef6e88b-dcae-4777-9893-9257d7702f43
source-git-commit: 1dd55fdd836dff89763887d88af2671ed1f9ce2b
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 69%

---

# Temi, modelli e modelli dati modulo di esempio {#sample-themes-templates-and-data-models}

I Componenti core di [!DNL AEM Forms] forniscono temi di esempio, modelli e modelli dati modulo pronti all’uso per creare rapidamente moduli adattivi versatili. Questi consentono inoltre agli autori dei moduli di apprendere l’estensibilità, l’adattabilità e la reattività di [Componenti core Forms adattivi](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=it) per creare moduli semplici in poco tempo e moduli complessi in modo semplice e senza interruzioni, collegandosi al database.

I temi, i modelli e i modelli dati modulo di esempio inclusi nel pacchetto di contenuti di riferimento sono:

| Modelli | Temi | Modelli dati modulo |
---------|----------|---------
| [Vuoto](#Blank) | [Area di lavoro](#Canvas) | Microsoft® Dynamics 365 |
| [Contattaci](#Contact-Us) | [WKND](#WKND) | Salesforce |
| [Aggiornamento dei dettagli di contatto](#Contact-Details-Update) | [Cavalletto](#Easel) |   |
| [Modulo di consenso](#Consent-Form) | [FSI](#FSI) |  |
| [Richiesta servizio di registro](#Log-Service-Request) | [Assistenza sanitaria](#Healthcare) |  |
| [Invia feedback](#Give-Feedback) |  |  |
| [Iscrizione alle prestazioni](#Benefits-Enrollment) |  |   |
| [Riepilogo prestazioni dei dipendenti](#Employee-Benefits-Summary) |   |   |
| [Richiesta di estratto conto](#Request-for-Account-Statement) |   |   |
| [Modulo del controllo di sicurezza](#Safety-Inspection) |   |   |
| [Ispezione del controllo di qualità](#Quality-Control-Inspection) |   |   |
| [Richiesta di acquisto](#Purchase-Request) |  |  |

## Temi di esempio {#Sample-Themes}

I temi di esempio di riferimento consentono agli autori di utilizzare, definire e personalizzare lo stile dei moduli, mentre gli autori con conoscenze di base di CSS possono personalizzarli in base alle esigenze.

**Come ottenere questi temi?**
Per ottenere questi temi, segui i passaggi indicati di seguito per **AEM as a Cloud Service** ambiente:

1. [Abilita componenti core modulo adattivo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html?lang=it)
1. [Distribuire un progetto Archetipo 45 AEM nell’ambiente](https://github.com/adobe/aem-project-archetype)


Quando si distribuisce un Archetipo AEM, è possibile utilizzare solo i temi inclusi nei moduli, Per personalizzare i temi in base alle proprie esigenze, [Utilizzare la pipeline front-end](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=it) per distribuire i temi.

>[!NOTE]
>
> * I temi non sono disponibili per **AEM 6.5** ambiente.

<!--

1. **AEM 6.5**

    1. [Enable Adaptive Form Core Components](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/enable-adaptive-forms-core-components.html)
    1. [Deploy an AEM Archetype 45 project to your environment](https://github.com/adobe/aem-project-archetype)


    When you deploy an AEM Archetype, you can only use the OOTB themes in your forms, To customize the themes as per your requirements, [Use the front-end pipeline](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html) to deploy the themes.

-->


<!--

### Deploying an AEM Archetype 45 project to your environment {#using-archetype-to-deploy-themes}

You can get these themes by deploying an [AEM Archetype 45](https://github.com/adobe/aem-project-archetype) to your **AEM Forms as a Cloud Service** or **AEM 6.5** Forms environment.

### Enable core components and use front-end pipeline to deploy themes {#use-front-end-pipeline-to-deploy-themes}

1. To get these themes on **Forms as a Cloud Service** environment, [enable Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html) and use the [front-end pipeline](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html) to deploy these themes.
    
1. To get these themes on **AEM 6.5 Forms** environment, [enable Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/enable-adaptive-forms-core-components.html) and use the [Package Manager](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html) to deploy these themes.

[Learn to use and customize themes in AEM Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html). 

[Learn to use and customize themes in AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html).

-->

I temi **pronti all’uso** dei [Componenti core dei moduli adattivi](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=it) sono:

![Temi pronti all’uso](/help/adaptive-forms/assets/archetype-45-themes-1.png)

### Area di lavoro {#Canvas}

Il tema Area di lavoro è il tema predefinito per le maschere ed evidenzia l&#39;utilizzo di colori di base, trasparenza e icone piatte. Nella schermata seguente, è possibile visualizzare l’aspetto del tema Area di lavoro.

![Tema Area di lavoro](/help/adaptive-forms/assets/Safety-Inspection-Theme-Canvas.png)

### WKND {#WKND}

Il tema WKND è caratterizzato da un design vivace, fantasioso e coinvolgente per dare un aspetto elegante ai moduli. Il tema è basato sull’aspetto e lo stile del [Sito WKND](https://wknd.site/us/en.html) che è un sito web di viaggi e avventura basato sui [Componenti core di Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=it).

![Tema WKND](/help/adaptive-forms/assets/Safety-Inspection-Form-Theme.png)


### Cavalletto {#Easel}

Il tema Cavalletto consente di creare un modulo dall’aspetto accattivante e facile da impostare, personalizzato per maggiore semplicità e facilità d’uso. Il tema del cavalletto è basato sul concetto in cui uno stand portatile è utilizzato dagli artisti per sostenere una tela mentre lavorano sui loro dipinti.

![Tema Cavalletto](/help/adaptive-forms/assets/Safety-Inspection-Theme-Easel.png)

### FSI (Servizi finanziari e assicurativi) {#FSI}

Il tema FSI pone l&#39;accento sul conferire al tuo modulo un aspetto pulito e pratico. Al modulo viene applicata la tonalità lieve blu quando si applica il tema FSI, come illustrato nell&#39;immagine.

![Tema FSI](/help/adaptive-forms/assets/fsi-theme-new1.png)


### Assistenza sanitaria {#Healthcare}

Il tema Healthcare utilizza toni ricchi e verdanti per accentuare elementi come schede, pannelli, caselle di testo e pulsanti all’interno del modulo.

![Tema Healthcare](/help/adaptive-forms/assets/healthcare-new-theme.png)


## Modelli di esempio {#Sample-templates}

I modelli definiscono la struttura iniziale del modulo, il contenuto e le azioni da replicare oppure utilizzano una struttura di modello simile al tuo modulo, ad esempio Modulo di consenso, Modulo di iscrizione alle prestazioni e molto altro ancora.

**Come si ottengono questi modelli?**
Per ottenere questi modelli, distribuisci un [Archetipo AEM 45](https://github.com/adobe/aem-project-archetype) al tuo **AEM Forms as a Cloud Service** ambiente o **AEM 6.5 Forms** ambiente.

<!--

>[!NOTE]
>
> * If you have [enabled core components and used front-end pipeline to deploy themes](#use-front-end-pipeline-to-deploy-themes), you need not to deploy an AEM Archetype.
> * You can find list of all OOTB templates when you create a form.

-->


I modelli **pronti all’uso** dei [Componenti core dei moduli adattivi](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=it) sono:

![Modelli di riferimento](/help/adaptive-forms/assets/reference-templates-core-components.png)

<!--

### Basic {#Basic}

A basic template helps you quickly create an enrollment experience form. You can also use it to preview the functionality of [Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html). It provides a wizard layout for section-by-section presentation of data.

![Basic Template](/help/adaptive-forms/assets/Basic-template-desktop-view.png)

-->

### Vuoto {#Blank}

Un modello di area di lavoro vuoto consente di creare da zero una struttura, un contenuto e le regole di un modulo adattivo. Nessun componente per modulo viene pre-incorporato nel modello vuoto.

![Modello vuoto](/help/adaptive-forms/assets/Blank-temp-desktop-view.png)

### Contattaci {#Contact-Us}

Il modello di modulo Contattaci viene utilizzato per creare un modulo per facilitare la comunicazione tra i visitatori del sito web e gli amministratori del modulo. Tramite questo modulo gli utenti possono inviare query, feedback o richieste di supporto.

![Modello Contattaci](/help/adaptive-forms/assets/Contact-us-desktop-view.png)

### Aggiornamento dei dettagli di contatto {#Contact-Details-Update}

Il modello di aggiornamento dei dettagli di contatto consente agli autori di creare un modulo per l’aggiornamento dell’indirizzo e dei dettagli di contatto della clientela. Il modulo aiuta inoltre la clientela ad aggiornare le informazioni personali relative alle iscrizioni o alle prestazioni per garantire una comunicazione fluida e un accesso ininterrotto ai servizi o ai vantaggi.

![Contact-details-update](/help/adaptive-forms/assets/Contact-details-update.png)

### Modulo di consenso {#Consent-Form}

Il modello di modulo di consenso viene utilizzato per creare un modulo per l’ottenimento di un documento legale da parte dei partecipanti che partecipano a un’attività specifica, a uno studio di ricerca, a una procedura medica o a qualsiasi situazione in cui possano essere coinvolti i loro dati o diritti personali. Il modulo garantisce la trasparenza, tutela i diritti dei partecipanti e fornisce una spiegazione chiara di ciò che l’individuo sta accettando.

![Modulo di consenso](/help/adaptive-forms/assets/Consent-form-desktop-view.png)

### Richiesta servizio di registro {#Log-Service-Request}

Il modello di richiesta del servizio di registro consente di creare un modulo che richiede a un fornitore di servizi servizi di registrazione specifici. Il modulo funge da richiesta formale per creare un ticket per eventi, attività o registri di dati per monitorare o tenere traccia dello stato.

![Modello di richiesta servizio di registro](/help/adaptive-forms/assets/Log-service-request-desktop-view.png)


### Invia feedback {#Give-Feedback}

Il modello del modulo di feedback consente di creare un modulo per fornire un feedback costruttivo a un’altra persona o a un team. Il modulo contribuisce a garantire che il feedback sia chiaro, specifico e actionable, promuovendo una comunicazione aperta e miglioramenti.

![Modello invia feedback](/help/adaptive-forms/assets/Give-feedback-desktop-view.png)


### Iscrizione alle prestazioni {#Benefits-Enrollment}

Il modello del modulo di iscrizione alle prestazioni viene utilizzato per creare un modulo per raccogliere informazioni essenziali dai dipendenti in merito alle prestazioni e alle opzioni di copertura preferiti. In genere è necessario nel periodo di iscrizione alle prestazioni annuali.

![Modello iscrizione alle prestazioni](/help/adaptive-forms/assets/Benefits-enrollment-form-template.png)


### Riepilogo prestazioni dei dipendenti {#Employee-Benefits-Summary}

Il modello del modulo Riepilogo prestazioni dei dipendenti consente di creare un modulo per raccogliere dettagli essenziali sulle prestazioni di un indivuduo. Consente di valutare la copertura in modo rapido e accurato, fornendo una panoramica completa per ottenere assistenza e supporto efficienti.
![Riepilogo prestazioni dei dipendenti](/help/adaptive-forms/assets/Employee-benefits-summary.png)


### Richiesta di estratto conto {#Request-for-Account-Statement}

Un modello di richiesta di rendiconto conto consente di creare un modulo che avvia il processo di ottenimento di un rendiconto dei clienti accurato e aggiornato. L’estratto fornisce una registrazione dettagliata di transazioni finanziarie, attività o altre informazioni rilevanti sulla clientela che utilizza questo modulo.

![Richiesta di estratto conto](/help/adaptive-forms/assets/Request-for-account-statment.png)

### Controllo di sicurezza {#Safety-Inspection}

Il modello del modulo per il controllo di sicurezza consente di creare un modulo in cui inserire dettagli per garantire un ambiente di lavoro sicuro. Effettuando controlli regolari tramite questo modulo, è possibile identificare potenziali rischi. Il modulo copre vari aspetti come le uscite di emergenza, la prevenzione di incendi, la sicurezza elettrica, i materiali pericolosi, i dispositivi di protezione personale, l’ergonomia delle postazioni di lavoro per la sicurezza e il benessere di dipendenti, visitatori e clienti.

![Modulo di controllo di sicurezza](/help/adaptive-forms/assets/Safety-inspection-form.png)

### Ispezione del controllo qualità {#Quality-Control-Inspection}

Il modello del modulo per l’ispezione del controllo qualità consente di creare un modulo per valutare e documentare l’aspetto visivo, le dimensioni, la funzionalità, la documentazione, i risultati dei test e la qualità complessiva di un prodotto o di un elemento. Consente di identificare i difetti, le non conformità e le azioni correttive necessarie per garantire il rispetto degli standard di qualità.

![Ispezione del controllo qualità](/help/adaptive-forms/assets/Quality-Control-Inspection.png)


### Richiesta di acquisto {#Purchase-Request}

Il modello del modulo per la richiesta di acquisto consente di creare un modulo per avviare il processo di approvvigionamento e consentire ai dipendenti di richiedere formalmente l’acquisto di beni o servizi necessari per il proprio lavoro. Il modulo acquisisce dettagli essenziali come la descrizione dell’articolo, la quantità, il fornitore preferito (se applicabile), l’allocazione del budget, la giustificazione per l’acquisto, le informazioni di consegna e le approvazioni richieste.

![Modulo richiesta di acquisto](/help/adaptive-forms/assets/Purchase-request-form.png)

## Modelli di dati modulo di riferimento {#reference-models}

Dopo aver creato un modulo adattivo basato su un [Componente core](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=it), è possibile connettere il modulo con i server di database Microsoft® Dynamics 365 e Salesforce, per abilitare i flussi di lavoro aziendali. Ad esempio:

* Scrivere i dati in Microsoft® Dynamics 365 e Salesforce all’invio del modulo adattivo.
* Scrivere i dati in Microsoft® Dynamics 365 e Salesforce tramite entità personalizzate definite nel Modello di dati modulo e viceversa.
* Effettuare query per i dati sui server Microsoft® Dynamics 365 e Salesforce e precompilare i moduli adattivi.
* Leggere i dati dal server Microsoft® Dynamics 365 e Salesforce.

È possibile ottenere i seguenti modelli dati del modulo installando il [Pacchetto contenuto di riferimento](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/it/details.html/content/dam/aemcloud/public/aem-forms-reference-content.ui.content-2.1.0.zip):

* Microsoft® Dynamics 365
* Salesforce

Per informazioni sull’utilizzo di questi modelli, consultare [Configurazione di Microsoft® Dynamics 365 e dei servizi cloud Salesforce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/configure-msdynamics-salesforce.html?lang=it#configure-dynamics-cloud-service)
