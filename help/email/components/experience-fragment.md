---
title: Componente Frammento esperienza e-mail
description: Il componente Frammento esperienza e-mail consente all’autore del contenuto di inserire una variante del frammento esperienza nel contenuto e di supportare una struttura di contenuto localizzata.
role: Architect, Developer, Admin, User
exl-id: 861c1fd1-6d6d-426c-a338-a558326fe16e
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 27%

---


# Componente Frammento esperienza e-mail {#email-experience-fragment-component}

Il componente Frammento esperienza e-mail consente all’autore del contenuto di inserire una variante del frammento esperienza nel contenuto e di supportare una struttura di contenuto localizzata.

## Utilizzo {#usage}

Il componente Frammento esperienza e-mail consente all’autore del contenuto di selezionare tra le varianti esistenti di Frammento esperienza e inserirne una all’interno del contenuto. Un frammento esperienza è un gruppo di contenuti che include sia il contenuto che il layout ed è riutilizzabile tra i canali.

* Le proprietà del componente possono essere definite nella [finestra di dialogo per configurazione](#configure-dialog).
* I valori predefiniti per il componente quando lo si aggiunge al contenuto possono essere definiti nella [finestra di dialogo di progettazione](#design-dialog).

Il componente Frammento esperienza e-mail supporta una struttura del sito localizzata.

## Versione e compatibilità {#version-and-compatibility}

La versione corrente del componente Frammento esperienza e-mail è v1, introdotto con la versione X dei componenti core e-mail nell’ottobre 2022, ed è descritto in questo documento.

La tabella che segue descrive tutte le versioni supportate del componente, le versioni di AEM con cui le versioni del componente sono compatibili e i collegamenti alla documentazione delle versioni precedenti.

| Versione del componente | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Compatibile | Compatibile |

Per ulteriori informazioni sulle versioni e le versioni dei componenti core e-mail, consulta il documento [Versioni dei componenti core di e-mail.](/help/email/versions.md)

## Supporto della struttura localizzata del sito {#localized-site-structure}

Il componente Frammento esperienza e-mail si adatta alle strutture di contenuto localizzate ed esegue il rendering del frammento esperienza appropriato in base alla localizzazione del contenuto. A questo scopo, il frammento esperienza deve soddisfare le seguenti condizioni.

* Il componente Frammento esperienza e-mail viene aggiunto a un [modello di pagina.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/templates.html)
* Il modello viene utilizzato per creare una nuova pagina di contenuto che fa parte di una struttura localizzata sotto `/content/<site>`.
* Il frammento esperienza a cui si fa riferimento in una pagina di contenuto fa parte di una struttura di frammento esperienza localizzata qui sotto `/content/experience-fragments` che segue gli stessi pattern del sito sottostante `/content/<site>` anche utilizzando gli stessi nomi di componenti.

In questo caso, il frammento con la stessa localizzazione ([lingua, blueprint o Live Copy](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/reusing-content/msm-and-translation.html)) come viene eseguito il rendering della pagina corrente come parte del modello.

Questo comportamento è limitato ai componenti Frammento esperienza e-mail aggiunti ai modelli. I componenti Frammento esperienza aggiunti alle singole pagine di contenuto renderanno le rappresentazioni dei frammenti esperienza configurate all’interno del componente.

* Per un esempio del funzionamento delle funzioni di localizzazione del componente Frammento esperienza , consulta [la sezione seguente](#example).
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

In questo caso, se il componente Frammento esperienza e-mail `/content/experience-fragments/wknd/us/en/footerTextXf` viene posizionato in un modello, le pagine localizzate create in base a tale modello renderanno automaticamente il frammento esperienza localizzato che corrisponde alla pagina del contenuto localizzato.

Pertanto, se vai a una pagina di contenuto sotto `/content/wknd/ch/de` che utilizza lo stesso modello, viene eseguito il rendering di `/content/experience-fragments/wknd/ch/de/footerTextXf` invece di `/content/experience-fragments/wknd/us/en/footerTextXf`.

### Regresso {#fallback}

Il componente Frammento esperienza e-mail tenta di trovare un componente localizzato corrispondente nell’ordine seguente.

1. Prima tenta di trovare una directory principale della lingua.
1. Se non la trova, tenta di trovare un modello.
1. Se non lo trova, tenta di trovare una Live Copy.
1. Se non viene trovato, per impostazione predefinita viene visualizzato il frammento esperienza configurato nel componente .

## Esempio di output del componente {#sample-component-output}

Per scoprire il componente Frammento esperienza e-mail e visualizzare esempi delle relative opzioni di configurazione, nonché l’output di HTML e JSON, visita il [Libreria dei componenti.](https://adobe.com/go/aem_cmp_library_email_xf)

## Dettagli tecnici {#technical-details}

La documentazione tecnica più recente sul componente Frammento esperienza [è disponibile su GitHub.](https://adobe.com/go/aem_cmp_email_tech_xf_v1)

Ulteriori dettagli sullo sviluppo dei componenti core sono disponibili nella sezione [Documentazione per gli sviluppatori dei componenti core.](/help/developing/overview.md)

## Finestra di dialogo per la configurazione {#configure-dialog}

La finestra di dialogo di configurazione consente all’autore del contenuto di selezionare la variante del frammento esperienza da visualizzare nel contenuto.

![Finestra di dialogo di modifica del componente Frammento esperienza e-mail](/help/email/assets/email-experience-fragment-edit.png)

Utilizza la **Finestra di dialogo Apri selezione** per aprire il selettore dei componenti e scegliere la variante del componente Frammento esperienza da aggiungere alla pagina del contenuto.

Se aggiungi il componente Frammento esperienza e-mail a un modello, questo verrà localizzato automaticamente a condizione che i Frammenti esperienza siano localizzati, in modo che il rendering nella pagina possa variare dal componente selezionato in modo esplicito. Per ulteriori informazioni, [vedi l’esempio precedente](#example).

Puoi anche definire un **ID**. Questa opzione consente di controllare l’identificatore univoco del componente nell’HTM.

* Se lasciato vuoto, viene generato automaticamente un ID univoco che può essere trovato controllando il contenuto risultante.
* Se l’ID viene specificato, è responsabilità dell’autore accertarsi che sia univoco.
* La modifica dell’ID può avere un impatto sui CSS.

### Scheda Stili {#styles-tab-edit}

Il componente Frammento esperienza e-mail supporta il AEM [Sistema di stili.](/help/get-started/authoring.md#component-styling)

Utilizza il menu a discesa per selezionare gli stili da applicare al componente. Le selezioni effettuate nella finestra di dialogo di modifica hanno lo stesso effetto di quelle selezionate nella barra degli strumenti del componente.

Gli stili devono essere configurati per questo componente nel [finestra di dialogo di progettazione](#design-dialog) affinché la scheda sia disponibile.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo di progettazione consente all’autore del modello di definire le opzioni disponibili per l’autore del contenuto che utilizza il componente Frammento esperienza e-mail e le impostazioni predefinite per il posizionamento del componente Frammento esperienza e-mail .

### Scheda Stili {#styles-tab}

Il componente Frammento esperienza e-mail supporta il AEM [Sistema di stili.](/help/get-started/authoring.md#component-styling)
