---
title: Componente core Forms adattivo - Piè di pagina
description: Utilizzo o personalizzazione del componente core Footer di Forms adattivo.
role: Architect, Developer, Admin, User
source-git-commit: b378fbd5695f82b8fc9de3a2d53a8387099ae33b
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 19%

---


# Piè di pagina {#footer-adaptive-forms-core-component}

Un componente piè di pagina in un modulo adattivo è un’area che in genere viene visualizzata nella parte inferiore del modulo e contiene informazioni quali un avviso di copyright, collegamenti a risorse correlate o informazioni di contatto. Un piè di pagina può fornire informazioni aggiuntive, ad esempio la data dell’ultimo aggiornamento, che possono essere utili per gli utenti con esigenze di accessibilità.

**Esempio**

![](/help/adaptive-forms/assets/footer.png)

## Utilizzo {#reasons-to-use-footer}

È utile includere un componente piè di pagina in un modulo per diversi motivi, tra cui:

* **Requisiti legali**: Ad alcune forme può essere richiesto di includere una liberatoria, un avviso di copyright o altre informazioni legali. Un piè di pagina è un luogo conveniente per includere queste informazioni.

* **Navigazione**: Un piè di pagina può fornire collegamenti ad altre pagine importanti del sito web, come ad esempio una informativa sulla privacy, termini di servizio o pagina di contatto.

* **Branding**: Un piè di pagina può essere utilizzato per includere un logo o altri elementi di branding, contribuendo a rafforzare l’identità dell’organizzazione o del sito web.

* **Coerenza**: Un piè di pagina garantisce coerenza nella struttura e nel layout del modulo, facilitando la navigazione agli utenti.

* **Contesto aggiuntivo**: Un piè di pagina può fornire un contesto aggiuntivo al modulo, ad esempio un testo che descrive il modulo o un collegamento a risorse correlate, rendendo il modulo più informativo e semplice da usare.

## Versione e compatibilità {#version-and-compatibility}

Il componente core Footer di Forms adattivo è stato rilasciato a febbraio 2023 come parte dei componenti core 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Per informazioni aggiornate sul componente core Footer di Adattivo Forms, consulta la documentazione tecnica disponibile in [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/footer/v1/footer). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).


## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del piè di pagina per i visitatori tramite la finestra di dialogo Configura . È inoltre possibile definire le opzioni piè di pagina con facilità per un’esperienza utente fluida.

![Scheda Proprietà](/help/adaptive-forms/assets/footer_propertiestab.png)

* **Finestra di dialogo Modifica**
La finestra di dialogo di modifica fornisce strumenti di formattazione RTF standard che consentono all’utente di creare testo per il piè di pagina.

* **Grassetto** - Questa opzione applica la formattazione in grassetto al testo selezionato o al testo in formato grassetto immesso dopo il cursore. `Ctrl+B` è una scelta rapida da tastiera.

* **Corsivo** - Questa opzione applica la formattazione in corsivo al testo selezionato o al testo in corsivo immesso dopo il cursore. `Ctrl+I` è una scelta rapida da tastiera.

![Opzioni punto elenco](/help/adaptive-forms/assets/footer_bullet.png)


* **Punto elenco**

   * **Icona punto elenco** - Formatta il testo selezionato come elenco puntato o inizia l&#39;inserimento di un elenco puntato dopo il cursore. Per terminare un elenco puntato, tocca o fai clic nuovamente sul pulsante Punto elenco oppure immetti due ritorni a capo.

   * **Icona Elenco numerato** - Formatta il testo selezionato come elenco numerato o inizia l&#39;inserimento di un elenco numerato dopo il cursore. Per terminare un elenco numerato, tocca o fai clic nuovamente sul pulsante Numero oppure immetti due ritorni a capo.

   * **Icona Outright** - Diminuisce il livello di rientro del testo o del testo selezionato dopo il cursore. L’opzione è attiva solo se il testo selezionato o la posizione del cursore è già rientrata.

   * **Icona Rientro** - Aumenta il livello di rientro del testo o del testo selezionato dopo il cursore.

![Opzioni collegamento ipertestuale](/help/adaptive-forms/assets/footer_link.png)

* **Collegamento ipertestuale**

   * **Percorso** - Inserire il percorso
      1. La finestra di dialogo per selezione consente di scegliere un percorso in AEM.
      1. Se il collegamento non è in AEM, utilizza l’URL assoluto.
      1. I percorsi non assoluti vengono interpretati come relativi ad AEM.
   * **Testo alternativo** - Inserisci un testo descrittivo alternativo per il collegamento.

   * **Target** - Selezionare il comportamento del collegamento
      * Destinazione
      * Stessa scheda
      * Nuova scheda
      * Frame principale
      * Frame superiore
   * **Icona Scollega** - Questa opzione rimuove un collegamento già applicato al testo selezionato. Questa opzione è attiva solo se il collegamento è già selezionato.

   * **Icona del formato paragrafo** - Questa opzione consente di applicare la formattazione del paragrafo al testo selezionato. Consente inoltre di formattare il testo inserito dopo il cursore. Definisce il livello di intestazione del titolo.



* **ID**: Questa opzione consente di controllare l’identificatore univoco del componente in HTML e nel livello dati.

   * Se lasciato vuoto, viene generato automaticamente un ID univoco * ed è possibile trovarlo controllando la pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.


