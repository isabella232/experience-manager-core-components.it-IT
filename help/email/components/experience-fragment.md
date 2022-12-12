---
title: Componente Frammento esperienza e-mail
description: Il componente Frammento esperienza e-mail consente all’autore del contenuto di inserire in esso una variante del Frammento esperienza e al contempo supporta una struttura per contenuti localizzati.
role: Architect, Developer, Admin, User
exl-id: 861c1fd1-6d6d-426c-a338-a558326fe16e
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: ht
source-wordcount: '927'
ht-degree: 100%

---


# Componente Frammento esperienza e-mail {#email-experience-fragment-component}

Il componente Frammento esperienza e-mail consente all’autore del contenuto di inserire in esso una variante del Frammento esperienza e al contempo supporta una struttura per contenuti localizzati.

## Utilizzo {#usage}

Il componente Frammento esperienza e-mail consente all’autore del contenuto di selezionare tra le varianti di Frammento esperienza esistenti e inserirne una nel contenuto. Un frammento di esperienza è un gruppo di contenuti che include sia il contenuto che il layout ed è riutilizzabile nei diversi canali.

* Le proprietà del componente possono essere definite nella [finestra di dialogo per la configurazione](#configure-dialog).
* Le impostazioni predefinite del componente, quando lo si aggiunge al contenuto, possono essere definite nella [finestra di dialogo per la progettazione](#design-dialog).

Il componente Frammento esperienza e-mail supporta anche una struttura per sito localizzato.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento esperienza e-mail è la versione 1, introdotta con la versione X dei componenti core E-mail a ottobre 2022, ed è quella descritta in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e sugli aggiornamenti dei Componenti core e-mail, vedi il documento [Versioni dei Componenti core e-mail.](/help/email/versions.md)

## Supporto della struttura per siti localizzati {#localized-site-structure}

Il componente Frammento esperienza e-mail si adatta alle strutture per contenuti localizzati in più lingue ed esegue il rendering del frammento di esperienza appropriato in base alla localizzazione del contenuto. A questo scopo, il frammento di esperienza deve soddisfare le seguenti condizioni.

* Il componente Frammento esperienza e-mail viene aggiunto a un [modello di pagina.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/templates.html?lang=it)
* Il modello viene utilizzato per creare una nuova pagina di contenuto che fa parte di una struttura per contenuti localizzati in `/content/<site>`.
* Il frammento di esperienza a cui si fa riferimento in una pagina di contenuto fa parte di una struttura di frammenti di esperienza localizzati in `/content/experience-fragments` che segue gli stessi modelli del sito in `/content/<site>`, incluso l’utilizzo degli stessi nomi di componenti.

In questo caso, come parte del modello, verrà eseguito il rendering del frammento con la stessa localizzazione ([lingua, blueprint o Live Copy](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/reusing-content/msm-and-translation.html?lang=it)) della pagina corrente.

Questo comportamento è limitato ai componenti Frammento esperienza e-mail aggiunti ai modelli. I componenti Frammento esperienza aggiunti alle singole pagine di contenuto eseguiranno il rendering delle rappresentazioni esatte dei frammenti di esperienza configurate nel componente.

* Per un esempio delle funzioni di localizzazione del componente Frammento esperienza, vedi la [sezione che segue](#example).
* Per un esempio dell’interazione delle funzioni di localizzazione dei Componenti core, visita la pagina [Funzioni di localizzazione dei Componenti core](/help/get-started/localization.md).

### Esempio {#example}

Supponiamo che il contenuto sia simile al seguente:

```
/content
+-- experience-fragments
   \-- wknd
      +-- language-masters
      +-- us
         +-- en
            +-- footerTextXf
            \-- headerTextXf
         \-- es
            +-- footerTextXf
            \-- headerTextXf
      \-- ch
         +-- de
            +-- footerTextXf
            \-- headerTextXf
         +-- fr
            +-- footerTextXf
            \-- headerTextXf
         \-- it
            +-- footerTextXf
            \-- headerTextXf
+-- wknd
   +-- language-masters
   +-- us
      +-- en
      \-- es
   +-- ch
      +-- de
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

Nota come la struttura sotto `/content/experience-fragments/wknd` rispecchi la struttura di `/content/wknd`.

In questo caso, se il componente Frammento esperienza e-mail `/content/experience-fragments/wknd/us/en/footerTextXf` è inserito in un modello, per le pagine localizzate create in base a quel modello verrà automaticamente eseguito il rendering del frammento di esperienza localizzato che corrisponde alla pagina del contenuto localizzato.

Pertanto, se vai a una pagina di contenuto sotto `/content/wknd/ch/de` che utilizza lo stesso modello, viene eseguito il rendering di `/content/experience-fragments/wknd/ch/de/footerTextXf` invece di `/content/experience-fragments/wknd/us/en/footerTextXf`.

### Regresso {#fallback}

Il componente Frammento esperienza e-mail tenta di trovare un componente localizzato corrispondente nell’ordine seguente.

1. Prima tenta di trovare una directory principale della lingua.
1. Se non la trova, tenta di trovare un modello.
1. Se non lo trova, tenta di trovare una Live Copy.
1. Se non lo trova, per impostazione predefinita viene visualizzato il frammento di esperienza configurato nel componente.

## Esempio di output del componente {#sample-component-output}

Per sperimentare il componente Frammento esperienza e-mail e vedere esempi delle opzioni di configurazione e dell’output HTML e JSON, visita la [libreria dei componenti.](https://adobe.com/go/aem_cmp_library_email_xf)

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Frammento esperienza [è disponibile su GitHub.](https://adobe.com/go/aem_cmp_email_tech_xf_v1)

Per ulteriori informazioni sullo sviluppo di Componenti core, vedi la [documentazione per gli sviluppatori di Componenti core.](/help/developing/overview.md)

## Finestra di dialogo per la configurazione {#configure-dialog}

La finestra di dialogo per configurazione consente all’autore di contenuti di selezionare la variante del frammento di esperienza di cui eseguire il rendering nel contenuto.

![Finestra di dialogo per modifica del componente Frammento esperienza e-mail](/help/email/assets/email-experience-fragment-edit.png)

Utilizza il pulsante **Apri finestra di dialogo per selezione** per aprire il selettore di componenti e scegliere la variante del componente Frammento esperienza da aggiungere alla pagina di contenuto.

Se aggiungi il componente Frammento esperienza e-mail a un modello, noterai che verrà automaticamente localizzato, a condizione che i frammenti esperienza siano localizzati, pertanto ciò che viene renderizzato sulla pagina può variare in base al componente esplicitamente selezionato. Per ulteriori informazioni, [vedi l’esempio precedente](#example).

Puoi anche definire un **ID**. Questa opzione consente di controllare l’identificatore univoco del componente nell’HTM.

* Se non specificato, viene generato automaticamente un ID univoco reperibile esaminando il contenuto risultante.
* Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
* La modifica dell’ID può avere un impatto sulle CSS.

### Scheda Stili {#styles-tab-edit}

Il componente Frammento esperienza e-mail supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nella [finestra di dialogo per la progettazione](#design-dialog) affinché la scheda sia disponibile.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore dei contenuti che utilizza il componente Frammento esperienza e-mail e le impostazioni predefinite scelte al momento del suo posizionamento.

### Scheda Stili {#styles-tab}

Il componente Frammento esperienza e-mail supporta il [sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.
