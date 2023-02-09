---
title: Introduzione ai componenti core di Forms adattivi AEM
description: Crea esperienze di iscrizione accattivanti (moduli) utilizzando la flessibilità dei componenti core Forms adattivi e forniscile con la potenza di Adobe Experience Manager.
role: Architect, Developer, Admin, User
source-git-commit: 781cf351ef52cbb56ff33c2674c8af591c81a30e
workflow-type: tm+mt
source-wordcount: '1069'
ht-degree: 13%

---


# Introduzione ai componenti core adattabili di Forms {#adaptive-forms-core-components-introduction}

Utilizzando i componenti core Forms adattivi in Adobe Experience Manager, puoi creare esperienze di iscrizione accattivanti utilizzando le opzioni di flessibilità e personalizzazione disponibili.

## Componenti core   {#overview}

In Adobe Experience Manager (AEM), i componenti sono i blocchi predefiniti utilizzati per creare pagine e moduli. Offrono agli autori un modo semplice e potente per creare e gestire i contenuti, fornendo allo stesso tempo agli sviluppatori la flessibilità e l’estensibilità necessarie per creare componenti personalizzati.

I componenti core sono una serie di componenti WCM precompilati e standardizzati progettati per velocizzare i tempi di sviluppo e ridurre i costi di manutenzione per i siti web. Questi componenti includono campi di testo, immagini, video e altro ancora. Sono progettati per essere flessibili e possono essere facilmente personalizzati in base alle esigenze specifiche di un sito web.

I componenti core sono inoltre progettati per essere reattivi e supportano un’ampia gamma di dispositivi, tra cui desktop, tablet e smartphone. Inoltre, rispettano gli standard web e le best practice più recenti, rendendoli una soluzione solida e affidabile per la creazione di contenuti web.

Inoltre, i componenti core sono progettati per funzionare in modo semplice con altre parti del AEM, consentendo agli autori e agli sviluppatori di creare moduli più interattivi e coinvolgenti con meno impegno e meno tempo.

Nel complesso, i componenti core sono uno strumento essenziale per la creazione e la gestione dei contenuti web in AEM, fornendo una soluzione potente e flessibile che può contribuire a ridurre i tempi di sviluppo e i costi di manutenzione, fornendo al contempo ai visitatori del sito web una grande esperienza utente.

In Adobe Experience Manager, i componenti sono gli elementi strutturali che costituiscono il contenuto delle pagine e dei moduli creati. I componenti sono sempre stati un elemento fondamentale dell’esperienza AEM, rendendo la creazione di pagine e moduli semplice ma potente per l’autore e lo sviluppo di componenti flessibili ed estensibili per lo sviluppatore. I componenti core sono un set di componenti WCM (Web Content Management) standardizzati per velocizzare i tempi di sviluppo e ridurre i costi di manutenzione dei siti web.

## Componenti core adattabili di Forms

I componenti core Forms adattivi sono un set di 24 componenti open-source compatibili con BEM basati sulle basi dei componenti core WCM di Adobe Experience Manager. Sono progettati appositamente per la creazione di Forms adattivo, moduli che si adattano al dispositivo, al browser e alle dimensioni dello schermo dell&#39;utente.

Questi componenti possono essere utilizzati per creare esperienze eccezionali di acquisizione e registrazione dei dati fornendo un’ampia gamma di opzioni per i campi modulo, compresi campi di testo, caselle di controllo, menu a discesa e altro ancora. Includono anche funzioni quali convalida, logica condizionale e progettazione reattiva, che possono essere utilizzate per creare moduli facili da usare e intuitivi.

Inoltre, poiché questi componenti sono open-source, gli sviluppatori possono personalizzare ed estendere facilmente i componenti in base alle esigenze specifiche della propria organizzazione. Questi componenti sono inoltre basati sulla metodologia BEM, che garantisce la scalabilità e la manutenzione dei componenti.

![](assets/sample-adaptive-form.png)

## Funzioni {#features}

|  |  |
|---|---|
| Pronti per la produzione | I componenti core Forms adattivi sono 24 componenti WCM affidabili. |
| Pronti per il cloud | Disponibile per  [AEM Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/home.html). |
| Versatili | I componenti rappresentano concetti generici con i quali gli autori di Forms possono assemblare quasi tutti i layout. |
| Configurabili | A livello di modello [criteri dei contenuti](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html?lang=it#content-policies) definisci quali funzioni possono essere utilizzate o meno. |
| Accessibili | Rispettano [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), fornire etichette ARIA, supportare la navigazione da tastiera ([problemi noti](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)) e testo per tecnologie di assistenza come gli assistenti vocali. |
| Supportano i temi | I componenti implementano il [sistema di stili](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html?lang=it) e il markup segue le [convenzioni BEM CSS](http://getbem.com/). |
| Personalizzabili | Diversi modelli consentono una facile personalizzazione, dalla rettifica del codice HTML al riutilizzo avanzato delle funzionalità. |
| Controllo delle versioni | I [criteri di controllo delle versioni](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) garantiscono che i Componenti core non blocchino il tuo sito in fase di miglioramento di elementi che potrebbero influire su di te. |
| Open Source | Se qualcosa non è come dovrebbe, contribuire al tuo miglioramento. |

## Vantaggi {#benefits}

Le esperienze di acquisizione dei dati sono fondamentali per la generazione e la registrazione dei lead e i componenti core per Forms adattivi offrono una soluzione potente per la creazione di moduli ottimizzati per l’acquisizione dei dati. Alcuni dei motivi per utilizzare i componenti core per creare queste esperienze sono:

* **Personalizzazione**: I componenti core Forms adattivi consentono agli sviluppatori di personalizzare facilmente l’aspetto e il comportamento dei componenti modulo, ad esempio campi di testo, caselle di controllo e menu a discesa, in modo da soddisfare requisiti specifici.

* **Accessibilità**: I componenti core Forms adattivi supportano gli standard e le linee guida di accessibilità, ad esempio  [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), per garantire che i moduli possano essere utilizzati da persone con disabilità, incluse quelle che utilizzano tecnologie per l’accessibilità quali gli assistenti vocali.

* **Moduli coerenti**: Utilizzando i componenti core di Forms adattivi, gli sviluppatori possono creare moduli dall’aspetto e dal aspetto uniformi, facilitando agli utenti la comprensione e la compilazione dei moduli, aumentando il coinvolgimento e migliorando l’esperienza utente.

* **Editor WYSIWYG**: AEM Forms fornisce un’interfaccia intuitiva e un editor WYSIWYG semplice da utilizzare per creare un modulo adattivo. Consente agli autori dei moduli di creare e modificare i moduli senza che sia necessario sapere come eseguire il codice. Include inoltre un editor di regole visive per facilitare la creazione di azioni basate su regole e implementare logiche complesse per automatizzare il comportamento del modulo senza dover scrivere codice.

* **Logica condizionale**: I componenti core Forms adattivi supportano l’uso della logica condizionale, il che significa che l’aspetto o il comportamento dei componenti modulo può essere modificato in base ai valori immessi dall’utente. Ad esempio, alcuni campi possono essere nascosti o resi obbligatori in base alla selezione effettuata in altri campi.

* **Convalida dei dati**: I componenti core Forms adattivi forniscono funzionalità di convalida dei dati integrate che consentono agli sviluppatori di garantire che i dati immessi dall’utente soddisfino criteri specifici, ad esempio lunghezze minime e massime, valori richiesti e formati specifici.

## Requisiti {#requirements}

I componenti core Forms adattivi hanno i seguenti requisiti.

| AEM | Componente aggiuntivo AEM Forms | Componenti core |
|---|---|---|
| AEM as a Cloud Service | Forms - Registrazione digitale | [Versione 2.20.8](/help/versions.md)+ |


## Componenti core adattabili di Forms {#components}

La versione corrente dei componenti core di Forms adattivi include i seguenti componenti.

* Pannello a soffietto
* Pulsante
* Gruppo di caselle di controllo
* Selettore data
* Elenco a discesa
* Ingresso e-mail
* Contenitore modulo
* Allegato file
* Piè di pagina
* Intestazione
* Schede orizzontali
* Immagine
* Ingresso numero
* Contenitore pannelli
* Pulsante di scelta
* Pulsante Ripristina
* Pulsante Invia
* Ingresso telefonico
* Input testo
* Testo
* Titolo
* Wizard

