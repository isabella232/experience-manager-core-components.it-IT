---
title: Componente Titolo e-mail
description: Il componente Titolo e-mail è un componente di intestazione sezione per le e-mail che presenta funzioni di modifica diretta.
role: Architect, Developer, Admin, User
exl-id: f65b6973-bb36-406f-bbea-f85a23f5340b
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: ht
source-wordcount: '599'
ht-degree: 100%

---


# Componente Titolo e-mail {#email-title-component}

Il componente Titolo e-mail è un componente di intestazione sezione per le e-mail che presenta funzioni di modifica diretta.

## Utilizzo {#usage}

Il componente Titolo e-mail deve essere utilizzato come titolo o intestazione di una sezione di un messaggio e-mail.

* I livelli di intestazione disponibili possono essere definiti dall’autore del modello nella [finestra di dialogo per la progettazione.](#design-dialog)
* L’autore del contenuto può selezionare tra i livelli di intestazione disponibili nella [finestra di dialogo di modifica.](#edit-dialog)

Per maggiore comodità, è disponibile anche una semplice modifica diretta del testo dell’intestazione.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Titolo e-mail è la v1, introdotta con la versione x dei componenti core E-mail a ottobre 2022, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile  | - |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core, consulta il documento [Versioni dei componenti core E-mail](/help/versions.md).

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Titolo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_email_title_v1).

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core](/help/developing/overview.md).

## Finestra di dialogo per modifica {#edit-dialog}

La finestra di dialogo per modifica consente all’autore di contenuto di definire il testo del titolo e selezionare il livello dell’intestazione.

* **Titolo**: se questo campo viene lasciato vuoto, viene utilizzato il titolo della pagina
   * Fai clic sull’icona Campaign per aprire la finestra di dialogo [Seleziona variabile Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.
* **Tipo/Dimensione**: definisce il livello di intestazione del titolo
* **Collegamento**: definisce il contenuto a cui verrà collegato il titolo. Può essere un percorso che punta a una pagina di contenuto, un URL esterno o un ancoraggio di pagina.
   * Fai clic sull’icona Campagna per aprire la finestra di dialogo [Seleziona variabile di Adobe Campaign](/help/email/campaign-variables.md) per inserire contenuto dinamico da Adobe Campaign.
* **ID**: questa opzione consente di controllare l’identificatore univoco del componente nell’HTML.
   * Se non specificato, viene generato automaticamente un ID univoco reperibile sulla pagina risultante.
   * Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
   * La modifica dell’ID può avere un impatto sulle CSS.

![Finestra di dialogo di modifica del componente Titolo e-mail](/help/email/assets/email-title-edit.png)

L’editor locale può essere utilizzato anche per modificare il testo del componente Titolo.

![Modifica diretta del componente Titolo e-mail](/help/email/assets/email-title-edit-inline.png)

### Scheda Stili {#styles-tab-edit}

Il componente Titolo e-mail supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Affinché il menu a discesa sia disponibile, gli stili devono essere configurati per questo componente nella [finestra di dialogo per la progettazione](#design-dialog).

![Scheda Stili della finestra di dialogo di modifica del componente Titolo](/help/email/assets/email-title-edit-styles.png)

## Finestra di dialogo per progettazione {#design-dialog}

La finestra di dialogo per progettazione consente all’autore del modello di definire il livello di intestazione predefinito dei componenti Titolo che vengono creati dagli autori di contenuto.

### Scheda Dimensioni {#sizes-tab}

![Finestra di dialogo per progettazione del componente Titolo](/help/email/assets/email-title-design.png)

* **Tipi/dimensioni consentiti per autori**: abilita o disabilita i tipi di intestazione che saranno disponibili per gli autori di contenuto quando utilizzano il componente Titolo e-mail.
* **Tipo/dimensione predefinito**: definisce il tipo di intestazione che verrà assegnato automaticamente quando un autore di contenuti aggiunge il componente Titolo e-mail a una pagina.
* **Disabilita collegamento**: disabilita il supporto dei collegamenti nel componente Titolo e-mail per impedire agli autori di contenuti di collegare i titoli.

### Scheda Stili {#styles-tab}

Il componente Titolo e-mail supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
