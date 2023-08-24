---
title: Come ottenere temi e modelli di esempio per AEM Forms?
description: I componenti core di AEM Forms forniscono esempi di temi, modelli e modelli dati modulo per moduli adattivi
solution: Experience Manager Forms
topic: Administration
role: Admin, User
hide: true
hidefromtoc: true
level: Intermediate
source-git-commit: ebbe3471164341076fe085bbef9c93fcb1fe382a
workflow-type: ht
source-wordcount: '1259'
ht-degree: 100%

---


# Temi, modelli e modelli dati modulo di esempio {#sample-themes-templates-and-data-models}

I Componenti core di [!DNL AEM Forms] forniscono temi di esempio, modelli e modelli dati modulo pronti all’uso per creare rapidamente moduli adattivi versatili. Questi consentono inoltre agli autori dei moduli di apprendere l’estensibilità, l’adattabilità e la reattività dei [Componenti core di AEM Forms](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=it) per creare moduli semplici in poco tempo e moduli complessi in modo semplice collegandosi direttamente al database.

I temi, i modelli e i modelli dati modulo di esempio inclusi nel pacchetto di contenuti di riferimento sono:

| Modelli | Temi | Modelli dati modulo |
---------|----------|---------
| [Base](#Basic) | [Area di lavoro](#Canvas) | Microsoft® Dynamics 365 |
| [Vuoto](#Blank) | [WKND](#WKND) | Salesforce |
| [Contattaci](#Contact-Us) | [Cavalletto](#Easel) |  |
| [Aggiornamento dei dettagli di contatto](#Contact-Details-Update) |   |   |
| [Modulo di consenso](#Consent-Form) | |  |
| [Richiesta servizio di registro](#Log-Service-Request) |  |  |
| [Invia feedback](#Give-Feedback) |  |  |
| [Iscrizione alle prestazioni](#Benefits-Enrollment) |  |   |
| [Riepilogo prestazioni dei dipendenti](#Employee-Benefits-Summary) |   |   |
| [Richiesta di estratto conto](#Request-for-Account-Statement) |   |   |
| [Modulo del controllo di sicurezza](#Safety-Inspection) |   |   |
| [Ispezione del controllo di qualità](#Quality-Control-Inspection) |   |   |
| [Richiesta di acquisto](#Purchase-Request) |  |  |

## Temi di esempio {#Sample-Themes}

I temi di esempio di riferimento aiutano gli autori a definire e personalizzare lo stile dei moduli; gli autori con conoscenze di base di CSS possono personalizzare il tema secondo le esigenze.

**Come ottenere questi temi?**
* Per attivare questi temi nell’ambiente **Forms as a Cloud Service**, [abilita i Componenti core dei moduli adattivi](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html?lang=it) e utilizza una [pipeline front-end](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=it) per distribuirli.
* Per inserire questi temi in un ambiente **AEM 6.5 Forms**, [abilita i Componenti core dei moduli adattivi](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/enable-adaptive-forms-core-components.html?lang=it) e utilizza [Gestione pacchetti](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.?lang=it) per distribuirli.

I temi **pronti all’uso** dei [Componenti core dei moduli adattivi](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=it) sono:

![Temi pronti all’uso](/help/adaptive-forms/assets/OOTB-themes.png)

### Area di lavoro {#Canvas}

Il tema Area di lavoro è il tema predefinito per i moduli e sottolinea l’utilizzo di colori di base, trasparenza e icone semplici. Nella schermata seguente, è possibile visualizzare l’aspetto del tema Area di lavoro.

![Tema Area di lavoro](/help/adaptive-forms/assets/Safety-Inspection-Theme-Canvas.png)

### WKND {#WKND}

Il tema WKND è caratterizzato da un design vivace, fantasioso e coinvolgente per dare un aspetto elegante ai moduli. Il tema è basato sull’aspetto e lo stile del [Sito WKND](https://wknd.site/us/en.html) che è un sito web di viaggi e avventura basato sui [Componenti core di Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=it).

![Tema WKND](/help/adaptive-forms/assets/Safety-Inspection-Form-Theme.png)


### Cavalletto {#Easel}

Il tema Cavalletto consente di creare un modulo dall’aspetto accattivante e facile da impostare, personalizzato per maggiore semplicità e facilità d’uso. Il tema Cavalletto è basato sull’idea del supporto portatile utilizzato dagli artisti per sostenere una tela mentre lavorano ai loro dipinti.

![Tema Cavalletto](/help/adaptive-forms/assets/Safety-Inspection-Theme-Easel.png)

## Modelli di esempio {#Sample-templates}

I modelli definiscono la struttura iniziale del modulo, il contenuto e le azioni da replicare oppure utilizzano una struttura di modello simile al tuo modulo, ad esempio Modulo di consenso, Modulo di iscrizione alle prestazioni e molto altro ancora.

**Come si ottengono questi modelli?**
È possibile ottenere i modelli implementando un [progetto basato sull’Archetipo AEM 43 o versione successiva](https://github.com/adobe/aem-project-archetype) nel tuo ambiente **AEM Forms as a Cloud Service** o **AEM 6.5**.

I modelli **pronti all’uso** dei [Componenti core dei moduli adattivi](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=it) sono:

![Modelli di riferimento](/help/adaptive-forms/assets/reference-templates-core-components.png)

### Base {#Basic}

Il modello di base consente di creare rapidamente un modulo per l’esperienza di iscrizione. È possibile utilizzarlo anche per visualizzare in anteprima la funzionalità dei [Componenti core dei moduli adattivi](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=it). Fornisce un layout con una procedura guidata per la presentazione dei dati sezione per sezione.

![Modello di base](/help/adaptive-forms/assets/Basic-template-desktop-view.png)

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

Il modello del modulo di consenso viene utilizzato per creare un modulo per l’acquisizione di un documento legale da parte di partecipanti a un’attività specifica, a uno studio di ricerca, a una procedura medica o a qualsiasi situazione in cui possano essere coinvolti dati o diritti personali. Il modulo garantisce la trasparenza, tutela i diritti dei partecipanti e fornisce una spiegazione chiara di ciò che l’individuo sta accettando.

![Modulo di consenso](/help/adaptive-forms/assets/Consent-form-desktop-view.png)

### Richiesta servizio di registro {#Log-Service-Request}

Il modello di richiesta del servizio di registro consente di creare un modulo che richiede a un fornitore di servizi servizi di registrazione specifici. Il modulo funge da richiesta formale per creare un ticket per eventi, attività o dati registrati per il monitoraggio o il tracciamento dello stato.

![Modello di richiesta servizio di registro](/help/adaptive-forms/assets/Log-service-request-desktop-view.png)


### Invia feedback {#Give-Feedback}

Il modello del modulo di feedback consente di creare un modulo per fornire un feedback costruttivo a un’altra persona o a un team. Il modulo contribuisce a garantire un feedback chiaro, specifico e utilizzabile, promuovendo una comunicazione aperta e miglioramenti.

![Modello invia feedback](/help/adaptive-forms/assets/Give-feedback-desktop-view.png)


### Iscrizione alle prestazioni {#Benefits-Enrollment}

Il modello del modulo di iscrizione alle prestazioni viene utilizzato per creare un modulo per raccogliere informazioni essenziali dai dipendenti in merito alle prestazioni e alle opzioni di copertura preferiti. In genere è necessario nel periodo di iscrizione alle prestazioni annuali.

![Modello iscrizione alle prestazioni](/help/adaptive-forms/assets/Benefits-enrollment-form-template.png)


### Riepilogo prestazioni dei dipendenti {#Employee-Benefits-Summary}

Il modello del modulo Riepilogo prestazioni dei dipendenti consente di creare un modulo per raccogliere dettagli essenziali sulle prestazioni di un indivuduo. Consente di valutare la copertura in modo rapido e accurato, fornendo una panoramica completa per ottenere assistenza e supporto efficienti.
![Riepilogo prestazioni dei dipendenti](/help/adaptive-forms/assets/Employee-benefits-summary.png)


### Richiesta di estratto conto {#Request-for-Account-Statement}

Il modello Richiesta di estratto conto consente di creare un modulo che avvia il processo di ottenimento di un estratto accurato e aggiornato della clientela. L’estratto fornisce una registrazione dettagliata di transazioni finanziarie, attività o altre informazioni rilevanti sulla clientela che utilizza questo modulo.

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
