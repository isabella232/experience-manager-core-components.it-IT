---
title: Componente Testo Modulo
description: Il componente Testo modulo componente di base consente di inserire il testo del modulo da inviare.
role: Architect, Developer, Admin, User
exl-id: e8fa3881-51fb-4726-9654-8f93acfb7464
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 7%

---

# Componente Testo Modulo{#form-text-component}

Il componente Testo modulo componente di base consente di inserire il testo del modulo da inviare.

## Utilizzo {#usage}

Il componente Testo modulo consente l’invio di diversi tipi di testo e deve essere utilizzato insieme al componente [contenitore modulo](form-container.md). Il tipo di convalida di testo, etichette e messaggi della guida può essere definito dall&#39;editor di contenuti nella finestra di dialogo [configura](#configure-dialog).

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente di testo per modulo è v2, introdotta con la versione 2.0.0 dei componenti core nel gennaio 2018, ed è descritta in questo documento.

La tabella seguente descrive tutte le versioni supportate del componente, le versioni AEM con cui le versioni del componente sono compatibili e si collega alla documentazione delle versioni precedenti.

| Versione componente | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Compatibile | Compatibile | Compatibile |
| [v1](/help/components/v1/form-text-v1.md) | Compatibile | Compatibile | - |

Per ulteriori informazioni sulle versioni e sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/versions.md) .

## Output componente di esempio {#sample-component-output}

Per visualizzare esempi delle opzioni di configurazione del componente Testo modulo e dell’output HTML e JSON, visita la [Libreria dei componenti](https://adobe.com/go/aem_cmp_library_form_text) .

### Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Testo modulo [è disponibile su GitHub](https://adobe.com/go/aem_cmp_tech_form_text_v2).

Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la [documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md) .

## Finestra di dialogo Configura {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di definire il tipo di testo da inserire, nonché i valori e le etichette predefiniti.

### Scheda Proprietà {#properties-tab}

![Scheda Proprietà](/help/assets/form-text-edit-properties.png)

* **Vincolo** : il tipo di testo da inserire e su cui verrà convalidato.
   * **Testo**
   * **Area testo**
   * **E-mail**
   * **Tel.**
   * **Data**
   * **Numero**
   * **Password**
* **Righe**  di testo - Numero di righe da visualizzare nell’area di testo (solo se l’opzione  **** Limite è impostata su  **Area** di testo)
* **Etichetta** : l’etichetta che verrà visualizzata per il campo
* **Nascondere l’etichetta dalla visualizzazione**  - Necessario se l’etichetta è necessaria solo a scopo di accessibilità e non fornisce ulteriori informazioni visive sul campo
* **Nome elemento** : il nome del campo inviato con i dati del modulo
* **Valore** : valore predefinito precompilato nel campo
* **ID**  - Questa opzione consente di controllare l’identificatore univoco del componente nell’HTML e nel livello  [dati](/help/developing/data-layer/overview.md).
   * Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando la pagina risultante.
   * Se viene specificato un ID, è responsabilità dell’autore assicurarsi che sia univoco.
   * La modifica dell’ID può avere un impatto su CSS, JS e tracciamento livello dati.

### Scheda Informazioni {#about-tab}

![Scheda Informazioni](/help/assets/form-text-edit-about.png)

* **Messaggio della Guida** : un suggerimento per l’utente su cosa è possibile inserire nel campo
* **Visualizza il messaggio della guida come segnaposto** : per visualizzare il messaggio della guida all’interno del modulo di input quando è vuoto o non attivo

### Scheda Vincoli {#constraints-tab}

![Scheda Vincoli](/help/assets/form-text-edit-constraints.png)

* **Messaggio vincolo**
   * Messaggio visualizzato come descrizione comando quando si invia il modulo, se il valore non convalida il tipo scelto
   * Non visualizzato per i tipi di vincolo **Testo** e **Area di testo**
* **Obbligatorio** : se selezionato, l’utente deve compilare un valore prima di inviare il modulo
   * **Messaggio richiesto** : messaggio visualizzato come descrizione comando se il campo viene lasciato vuoto
* **Rendi sola**  lettura: se selezionata, l&#39;utente non può modificare il valore del campo

## Finestra di dialogo Progettazione {#design-dialog}

### Scheda Stili {#styles-tab}

Il componente Testo modulo supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).
