---
title: Componente Pulsante E-mail
description: Il componente Pulsante e-mail consente di configurare e visualizzare un pulsante nel contenuto.
role: Architect, Developer, Admin, User
exl-id: b144e8d1-1097-475d-b2eb-3353c176afb9
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 43%

---


# Componente Pulsante E-mail {#email-button-component}

Il componente Pulsante e-mail consente di configurare e visualizzare un pulsante nel contenuto.

## Utilizzo {#usage}

Il componente Pulsante e-mail consente di includere nel contenuto un pulsante, selezionabile dall’assistente contenuto, che si collega a risorse aggiuntive.

* Le proprietà del Pulsante possono essere selezionate nella [finestra di dialogo per configurazione.](#configure-dialog)
* Gli stili per il componente Pulsante e-mail possono essere definiti nella sezione [finestra di dialogo di progettazione.](#design-dialog)

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Pulsante e-mail è v1, introdotto con la versione x dei componenti core e-mail nell’ottobre 2022, ed è descritto in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core di e-mail.](/help/email/versions.md)

## Esempio di output del componente {#sample-component-output}

Per scoprire il componente Pulsante e-mail e visualizzare esempi delle relative opzioni di configurazione, nonché l’output di HTML e JSON, visita il [Libreria dei componenti.](https://adobe.com/go/aem_cmp_library_email_button)

## Dettagli tecnici {#technical-details}

Documentazione tecnica più recente sul componente Pulsante e-mail [si trova su GitHub.](https://adobe.com/go/aem_cmp_tech_email_button_v1)

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core.](/help/developing/overview.md)

## Finestra di dialogo per la configurazione {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il pulsante e il comportamento e la visualizzazione del pulsante per un lettore del contenuto.

### Scheda Proprietà {#properties-tab}

![Scheda Proprietà della finestra di dialogo per modifica del componente Pulsante](/help/email/assets/email-button-edit-properties.png)

* **Testo**: il testo da visualizzare sul pulsante
   * Fai clic sull’icona Campagna per aprire la [Seleziona variabile Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.
* **Collegamento**: il collegamento a una pagina di contenuto in AEM, una risorsa esterna o un ancoraggio
   * Utilizza la **finestra di dialogo per selezione** per scegliere un percorso all’interno di AEM.
   * Fai clic sull’icona Campagna per aprire la [Seleziona variabile Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.
* **Icona**: identificatore per la visualizzazione di un’icona nel pulsante
* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente in HTML.
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando il contenuto risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sui CSS.
* **Apri collegamento in una nuova scheda** - Se questa opzione è selezionata, il collegamento verrà aperto in una nuova scheda del browser.

### Scheda Accessibilità {#accessibility-tab}

![Scheda Accessibilità della finestra di dialogo per modifica del componente Pulsante](/help/email/assets/email-button-edit-accessibility.png)

Nella scheda **Accessibilità** è possibile impostare i valori per le etichette di [accessibilità ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) del componente.

* **Etichetta**: il valore di un attributo dell’etichetta ARIA del componente

### Scheda Stili {#styles-tab-edit}

Il componente Pulsante e-mail supporta l’AEM [Sistema di stili.](/help/get-started/authoring.md#component-styling).

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nel [finestra di dialogo di progettazione](#design-dialog) affinché la scheda sia disponibile.

## Finestra di dialogo per progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Pulsante e-mail supporta l’AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).
