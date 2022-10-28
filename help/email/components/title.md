---
title: Componente Titolo E-mail
description: Il componente Titolo e-mail è un componente dell’intestazione della sezione per le e-mail che presenta funzioni di modifica diretta.
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 51%

---


# Componente Titolo E-mail {#email-title-component}

Il componente Titolo e-mail è un componente dell’intestazione della sezione per le e-mail che presenta funzioni di modifica diretta.

## Utilizzo {#usage}

Il componente Titolo e-mail deve essere utilizzato come titolo o intestazione di una sezione di un’e-mail.

* I livelli di intestazione disponibili possono essere definiti dall’autore del modello nella [finestra di dialogo per progettazione.](#design-dialog)
* L’autore del contenuto può selezionare tra i livelli di intestazione disponibili nel [finestra di dialogo di modifica.](#edit-dialog)

Per maggiore comodità, è disponibile anche una semplice modifica diretta del testo dell’intestazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Titolo e-mail è v1, introdotto con la versione x dei componenti core e-mail nell’ottobre 2022, ed è descritto in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti e-mail core](/help/versions.md).

## Esempio di output del componente {#sample-component-output}

Per avere un’idea del componente Titolo e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti.](https://adobe.com/go/aem_cmp_library_email_title)

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Titolo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_email_title_v1).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per modifica {#edit-dialog}

La finestra di dialogo per modifica consente all’autore di contenuto di definire il testo del titolo e selezionare il livello dell’intestazione.

* **Titolo**: se questo campo viene lasciato vuoto, viene utilizzato il titolo della pagina
   * Fai clic sull’icona Campagna per aprire la [Seleziona variabile Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.
* **Tipo/Dimensione**: definisce il livello di intestazione del titolo
* **Collegamento**: definisce il contenuto a cui verrà collegato il titolo. Può essere un percorso che punta a una pagina di contenuto, un URL esterno o un ancoraggio di pagina.
   * Fai clic sull’icona Campagna per aprire la [Seleziona variabile Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.
* **ID** - Questa opzione consente di controllare l’identificatore univoco del componente in HTML.
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sui CSS.

![Finestra di dialogo di modifica del componente Titolo e-mail](/help/email/assets/email-title-edit.png)

L’editor locale può essere utilizzato anche per modificare il testo del componente Titolo.

![Modifica diretta del componente Titolo e-mail](/help/email/assets/email-title-edit-inline.png)

### Scheda Stili {#styles-tab-edit}

Il componente Titolo e-mail supporta l’AEM [Sistema di stili.](/help/get-started/authoring.md#component-styling)

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nel [finestra di dialogo di progettazione](#design-dialog) affinché il menu a discesa sia disponibile.

![Scheda Stili della finestra di dialogo di modifica del componente Titolo](/help/email/assets/email-title-edit-styles.png)

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire il livello di intestazione predefinito dei componenti Titolo che vengono creati dagli autori di contenuto.

### Scheda Dimensioni {#sizes-tab}

![Finestra di dialogo per progettazione del componente Titolo](/help/email/assets/email-title-design.png)

* **Tipi/dimensioni consentiti per gli autori** - Abilitare o disabilitare i tipi di intestazione che saranno disponibili per gli autori di contenuti quando utilizzano il componente Titolo e-mail .
* **Tipo/Dimensione predefinita** - Definisci il tipo di intestazione che verrà assegnato automaticamente quando un autore di contenuti aggiunge il componente Titolo e-mail a una pagina.
* **Disattiva collegamento** - Disabilita il supporto dei collegamenti nel componente Titolo e-mail per impedire agli autori di contenuti di effettuare collegamenti dai titoli.

### Scheda Stili {#styles-tab}

Il componente Titolo e-mail supporta l’AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).
