---
title: Introduzione ai componenti core di Forms adattivi AEM
description: Crea esperienze di iscrizione accattivanti (moduli) utilizzando la flessibilità dei componenti core Forms adattivi e forniscile con la potenza di Adobe Experience Manager.
role: Architect, Developer, Admin, User
source-git-commit: 86fa434d884b24b8d4b231c6108f5e6151a89813
workflow-type: tm+mt
source-wordcount: '1231'
ht-degree: 11%

---


# Introduzione ai componenti core adattabili di Forms {#adaptive-forms-core-components-introduction}

Utilizzando i componenti core Forms adattivi in Adobe Experience Manager, puoi creare esperienze di iscrizione accattivanti utilizzando le opzioni di flessibilità e personalizzazione disponibili.

## Componenti core   {#overview}

In Adobe Experience Manager (AEM), i componenti sono i blocchi predefiniti utilizzati per creare pagine e moduli. Offrono agli autori un modo semplice e potente per creare e gestire i contenuti, fornendo allo stesso tempo agli sviluppatori la flessibilità e l’estensibilità necessarie per creare componenti personalizzati. Questi sono progettati per velocizzare i tempi di sviluppo e ridurre i costi di manutenzione per siti web e moduli, essere flessibili e possono essere facilmente personalizzati in base alle esigenze specifiche di un sito web e di un modulo.

I componenti core sono inoltre progettati per essere reattivi e supportano un’ampia gamma di dispositivi, tra cui desktop, tablet e smartphone. Inoltre, rispettano gli standard web e le best practice più recenti, rendendoli una soluzione solida e affidabile per la creazione di contenuti web.

Nel complesso, i componenti core sono uno strumento essenziale per la creazione e la gestione dei contenuti web in AEM, fornendo una soluzione potente e flessibile che può contribuire a ridurre i tempi di sviluppo e i costi di manutenzione, fornendo al contempo ai visitatori del sito web una grande esperienza utente.

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
| Tabella a tema | I componenti implementano il [sistema di stili](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html?lang=it) e il markup segue le [convenzioni BEM CSS](https://getbem.com/). |
| Personalizzabili | Diversi modelli consentono una facile personalizzazione, dalla rettifica del codice HTML al riutilizzo avanzato delle funzionalità. |
| Controllo delle versioni | I [criteri di controllo delle versioni](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) garantiscono che i Componenti core non blocchino il tuo sito in fase di miglioramento di elementi che potrebbero influire su di te. |
| Open Source | Se qualcosa non è come dovrebbe, contribuire al tuo miglioramento. |

## Vantaggi {#benefits}

Le esperienze di acquisizione dei dati sono fondamentali per la generazione e la registrazione dei lead e i componenti core per Forms adattivi offrono una soluzione potente per la creazione di moduli ottimizzati per l’acquisizione dei dati. Alcuni dei motivi per utilizzare i componenti core per creare queste esperienze sui componenti di base sono:

* **Disponibilità su GitHub e documentazione completa**: I AEM componenti core per Forms adattivi sono open-source e disponibili su GitHub, insieme a una documentazione completa. In questo modo gli sviluppatori possono comprendere più facilmente i componenti e il loro funzionamento e contribuire al loro sviluppo. La [aemcomponents.dev](https://www.aemcomponents.dev/) Il sito web è anche una risorsa preziosa, in cui gli sviluppatori possono vedere i componenti in azione e accedere alla documentazione dettagliata.

* **Modello BEM per stile**: I componenti core seguono il modello BEM (Block Element Modifier) per lo stile, una metodologia consolidata e ampiamente utilizzata per l’organizzazione dei CSS. In questo modo gli sviluppatori possono comprendere più facilmente come sono organizzati gli stili e come modificarli in base alle proprie esigenze specifiche.

* **Nessuna dipendenza dalle librerie di terze parti**: Uno dei vantaggi dei componenti core è che non hanno dipendenza da librerie JavaScript di terze parti, inclusi JQuery e Underscore. Questo rende i componenti più veloci e leggeri, nonché più facili da integrare in un’implementazione AEM esistente.

* **Concentrati su prestazioni e accessibilità**: I componenti core sono progettati tenendo presente le prestazioni e l’accessibilità, che si riflettono nei loro punteggi Google Lighthouse e web vitals elevati. Questo rende più facile per gli sviluppatori creare pagine web accessibili e dalle prestazioni elevate, che è sempre più importante nell&#39;attuale panorama digitale.

* **Componenti modulo nel modello e nei temi di Sites 30**: I componenti core supportano i componenti modulo nel modello e nei temi di Sites 30, facilitando agli sviluppatori la creazione e la personalizzazione dei moduli all’interno di AEM.

* **Stile più semplice**: Lo stile dei componenti core è più semplice rispetto a quello dei componenti di base. Il processo di creazione del tema è simile a Sites, con la possibilità di ereditare lo stesso tema/CSS dalla pagina Sites principale. Inoltre, il modello BEM per lo stile facilita la comprensione e la modifica degli stili.

* **Accessibilità**: I componenti core Forms adattivi supportano gli standard e le linee guida di accessibilità, ad esempio  [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), per garantire che i moduli possano essere utilizzati da persone con disabilità, incluse quelle che utilizzano tecnologie per l’accessibilità quali gli assistenti vocali.

* **Allineamento con AEM Sites**: I componenti core sono progettati per essere più allineati con AEM Sites, facilitando l’adozione e l’utilizzo da parte degli utenti di Sites senza dover apprendere nulla di nuovo. I componenti utilizzano la stessa pipeline front-end di Sites, facilitandone lo stile e modificarne l’aspetto. Inoltre, i seguenti punti illustrano ulteriormente questo allineamento:

   * **Authoring di esperienze in linea con l’editor di pagine**: I componenti core dispongono di un’esperienza di authoring in linea con l’editor Sites, con finestre di dialogo ed altre esperienze simili all’editor pagina. Questo semplifica la creazione e la gestione dei moduli da parte degli utenti di Sites nel contesto familiare dell’editor Sites.

   * **Modifica in linea del modulo nell’editor di Sites**: I componenti core consentono la modifica in linea dei moduli all’interno dell’editor Sites, evitando la necessità di passare da un editor all’altro. Questo semplifica l’esperienza di authoring e facilita la creazione e la gestione dei moduli.

   * **Eredità delle funzioni di Sites in Forms**: Forms creato all’interno di una pagina Sites eredita le stesse funzioni di Sites. Questo offre un’esperienza diretta e integrata per la creazione e la gestione dei moduli nel contesto di AEM Sites

   <!--including Multi Site Manager, the ability to use Sites components within a form for static content, support for scheduled publish/unpublish, form translation aligned with Sites translation, versioning, and targeting -->



## Requisiti {#requirements}

I componenti core Forms adattivi hanno i seguenti requisiti.

| AEM | Componente aggiuntivo AEM Forms | Componenti core |
|---|---|---|
| AEM as a Cloud Service | Forms - Registrazione digitale | [Versione 2.20.8](/help/versions.md)+ |


## Componenti core adattabili di Forms {#components}

È possibile utilizzare [Editor Forms adattivo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html) per creare un Forms adattivo basato su componenti di base. La versione corrente dei componenti core di Forms adattivi include i componenti elencati di seguito.

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

