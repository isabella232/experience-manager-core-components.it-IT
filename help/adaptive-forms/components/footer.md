---
title: Componente core moduli adattivi - Piè di pagina
description: Utilizzo o personalizzazione del componente core piè di pagina dei moduli adattivi.
role: Architect, Developer, Admin, User
exl-id: c8e7d3fe-4b82-4a80-8da2-19f6cff1e3e9
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '770'
ht-degree: 93%

---

# Piè di pagina {#footer-adaptive-forms-core-component}

Un componente piè di pagina in un modulo adattivo è un’area che in genere viene visualizzata nella parte inferiore del modulo e contiene informazioni quali un avviso di copyright, collegamenti a risorse correlate o informazioni di contatto. Un piè di pagina può fornire informazioni aggiuntive, come la data dell’ultimo aggiornamento, che possono essere utili per gli utenti con esigenze di accessibilità.

**Esempio**

![](/help/adaptive-forms/assets/footer.png)

## Utilizzo {#reasons-to-use-footer}

Includere un componente piè di pagina in un modulo è utile per vari motivi, tra cui:

* **Requisiti legali**: alcuni moduli potrebbero richiedere l’inclusione di una liberatoria, un avviso di copyright o altre informazioni legali. Un piè di pagina è una posizione comoda per includere queste informazioni.

* **Navigazione**: un piè di pagina può fornire collegamenti ad altre pagine importanti del sito web, come ad esempio una informativa sulla privacy, termini di servizio o pagina di contatto.

* **Branding**: un piè di pagina può essere utilizzato per includere un logo o altri elementi di branding, contribuendo a rafforzare l’identità dell’organizzazione o del sito web.

* **Coerenza**: un piè di pagina garantisce coerenza nella struttura e nel layout del modulo, rendendolo più intuitivo e semplice da navigare.

* **Contesto aggiuntivo**: un piè di pagina può fornire un contesto aggiuntivo al modulo, ad esempio un testo che lo descrive o un collegamento a risorse correlate, rendendolo più informativo e semplice da usare.

## Versione e compatibilità {#version-and-compatibility}

Il componente core per pannello a soffietto adattivo di Forms è stato rilasciato a febbraio 2023 come parte dei componenti core 2.0.4 per Cloud Service e i componenti core 1.1.12 per Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM 6.5.16.0 Forms o versione successiva |
|---|---|---|
| v1 | Compatibile  con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successive | Compatibile con<br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive ma inferiori a 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Ottieni informazioni aggiornate sul componente core piè di pagina dei moduli adattivi nella documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/footer/v1/footer). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).


## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza del piè di pagina per i visitatori tramite la finestra di dialogo Configura. Puoi anche definire le opzioni piè di pagina con facilità per un’esperienza utente semplice.

![Scheda Proprietà](/help/adaptive-forms/assets/footer_propertiestab.png)

* **Finestra di dialogo Modifica**
La finestra di dialogo Modifica fornisce strumenti di formattazione rich text standard che consentono all’utente di creare un testo per il piè di pagina.

* **Grassetto**: consente di applicare il grassetto al testo selezionato o al testo inserito dopo il cursore. `Ctrl+B` è una scelta rapida della tastiera.

* **Corsivo**: questa opzione applica la formattazione in corsivo al testo selezionato o al testo in corsivo inserito dopo il cursore. `Ctrl+I` è una scelta rapida della tastiera.

![Opzioni punto elenco](/help/adaptive-forms/assets/footer_bullet.png)


* **Punto elenco**

   * **Icona elenchi puntati**: formatta il testo selezionato come elenco puntato o di iniziare l’inserimento di un elenco puntato dopo il cursore. Per terminare un elenco puntato, tocca o fai clic nuovamente sul pulsante Punto elenco oppure immetti due ritorni a capo.

   * **Icona elenco numerato**: formatta il testo selezionato come elenco numerato o per iniziare l’inserimento di un elenco numerato dopo il cursore. Per terminare un elenco numerato, tocca o fai clic nuovamente sul pulsante Numero oppure immetti due ritorni a capo.

   * **Icona elimina rientro**: diminuisce il livello di rientro del testo selezionato o inserito dopo il cursore. L’opzione è attiva solo se il testo selezionato o la posizione del cursore è già rientrata.

   * **Icona Rientro**: aumenta il livello di rientro del testo selezionato o inserito dopo il cursore.

![Opzioni collegamento ipertestuale](/help/adaptive-forms/assets/footer_link.png)

* **Collegamento ipertestuale**

   * **Percorso**: inserisci il percorso
      1. La finestra di dialogo per selezione consente di scegliere un percorso in AEM.
      1. Se il collegamento non è in AEM, utilizza l’URL assoluto.
      1. I percorsi non assoluti vengono interpretati come relativi ad AEM.
   * **Testo alternativo**: inserisci un testo descrittivo alternativo per il collegamento.

   * **Target**: scegli il comportamento del collegamento
      * Destinazione
      * Stessa scheda
      * Nuova scheda
      * Frame principale
      * Frame superiore
   * **Icona Scollega**: questa opzione rimuove un collegamento già applicato al testo selezionato. Questa opzione è attiva solo se è già selezionato il collegamento.

   * **Icona del formato paragrafo**: questa opzione consente di applicare la formattazione del paragrafo al testo selezionato. Consente inoltre di formattare il testo inserito dopo il cursore. Definisce il livello di intestazione del titolo.



* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nel codice HTML e nel livello dati.

   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sul tracciamento di CSS, JS e Data Layer.

