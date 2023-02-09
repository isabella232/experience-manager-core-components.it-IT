---
title: Componente core Forms adattivo - Ingresso numero
description: Utilizzo o personalizzazione del componente core di input per numero di Forms adattivo.
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '1780'
ht-degree: 1%

---


# Ingresso numero {#number-input-adaptive-forms-core-component}

Un componente Input numero in un modulo adattivo è un tipo di campo modulo che consente agli utenti di immettere valori numerici. Il componente è in genere rappresentato da un campo di testo con una freccia su e giù per incrementare e diminuire il numero.

Può essere utilizzato anche con attributi come min, max, step, value e altro ancora. Questi attributi possono essere utilizzati per impostare i valori minimi e massimi consentiti nel campo, l’intervallo di passaggi per l’incremento o la riduzione del numero e il valore predefinito del campo.

Questo componente può essere utilizzato per raccogliere dati numerici come età, quantità e altro ancora. e può essere utilizzato anche per eseguire operazioni matematiche come addizione e sottrazione. Questo componente può essere utilizzato anche per convalidare i dati numerici immessi dall’utente.

Per l’accessibilità, è importante specificare l’etichetta che descrive lo scopo del campo di immissione del numero e il tipo di input previsto.

**Esempio**

![](/help/adaptive-forms/assets/numeric-stepper.png)

## Utilizzo {#reasons-to-use-number-input-numeric-stepper}

Esistono diversi motivi per cui è utile includere un componente di input numerico in un modulo adattivo, tra cui:

* **Operazioni matematiche**: I campi numerici possono essere utilizzati per eseguire operazioni matematiche quali addizione, sottrazione, moltiplicazione e divisione.

* **Intervallo dati**: I campi numerici possono essere utilizzati per impostare un intervallo di valori validi mediante gli attributi min, max e step.

* **Contenuto dinamico**: Il componente numerico può essere utilizzato per visualizzare i dati dinamici in base ai campi del modulo.


## Versione e compatibilità {#version-and-compatibility}

Il componente di base per l’input del numero di Forms adattivo è stato rilasciato nel febbraio 2023 come parte dei componenti di base 2.0.4. Questa tabella mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

|  |  |
|---|---|
| Versione del componente | AEM as a Cloud Service |
| --- | --- |
| v1 | Compatibile  con<br>[versione 2.0.4](/help/versions.md) e successivi | Compatibile | Compatibile |

Per informazioni sulle versioni e sulle versioni dei componenti core, consulta [Versioni dei componenti core](/help/versions.md) documento.


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Scarica le informazioni più recenti sul componente core di input per numero di Forms adattivo nella documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/numberinput/v1/numberinput). Per ulteriori informazioni sullo sviluppo dei componenti core, consulta la sezione [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza di immissione del numero per i visitatori tramite la finestra di dialogo Configura . È inoltre possibile definire con facilità le opzioni di immissione del numero per un’esperienza utente diretta.

### Scheda di base {#basic-tab}

![Scheda di base](/help/adaptive-forms/assets/numberinput_basictab.png)

* **Nome** - È possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo** - Con il relativo Titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungete un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo** - Seleziona l’opzione per nascondere il titolo del componente.

* **Testo segnaposto** - Il testo segnaposto in un componente modulo si riferisce a un’etichetta o a un prompt breve che viene visualizzato all’interno di un campo di input come suggerimento per l’utente sul tipo di informazioni che ci si aspetta venga immesso in quel campo. Il testo segnaposto scompare quando l’utente inizia a digitare nel campo e viene visualizzato nuovamente se il campo viene lasciato vuoto. Fornisce un segnale visivo all’utente, ma non agisce come etichetta o valore permanente per il campo.
* **Riferimento a un&#39;associazione** - Un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, fornendo un’esperienza utente semplice per la raccolta e la gestione dei dati.
* **Nascondi componente** - Selezionare l’opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente** - Seleziona l’opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.
* **Sola lettura** - Selezionare l&#39;opzione per rendere il componente non modificabile L&#39;utente può vedere il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’Editor regole.
* **Tipo di numero** - Questa opzione consente di selezionare il tipo di valori numerici &#x200B; consentiti nel campo modulo. È possibile selezionare i tipi Decimal o Integer dal menu a discesa.
* **Valore predefinito** - Questa opzione consente di aggiungere un valore predefinito in un campo modulo. Se **Componente disabilitato** o **Componente di sola lettura** è selezionato, il valore predefinito viene visualizzato sullo schermo. Se l’utente non immette alcun valore nel campo modulo, questo valore viene inviato al momento dell’invio del modulo

### Scheda Convalida {#validation-tab}

![Scheda Convalida](/help/adaptive-forms/assets/numberinput_validationtab.png)

* **Obbligatorio** - Selezionare questa opzione se si desidera visualizzare il componente in un modulo adattivo. Non è possibile selezionare la **Nascondi componente** o **Disattiva componente**  in **Base** quando questa opzione è selezionata.

* **Messaggio di errore** - Questa opzione consente di inserire un messaggio visualizzato se **Obbligatorio** è selezionata e il campo viene lasciato vuoto.

* **Messaggio di convalida script** - Questa opzione consente di inserire un messaggio da visualizzare in caso di errore di convalida dello script.

* **Numero più basso / Numero più piccolo** - Utilizzare questa opzione per selezionare il numero minimo consentito da immettere nel campo modulo. Se il valore è inferiore al numero specificato in **Numero più basso / Numero più piccolo** nel campo modulo viene immessa l’opzione , viene visualizzato un messaggio di errore.

* **Messaggio di errore minimo** - Questa opzione consente di inserire un messaggio di errore visualizzato quando l’utente immette un valore inferiore al valore specificato nel **Numero minimo/Numero minimo** opzione .

* **Escludi valore minimo** - Selezionare questa casella di controllo se non si desidera che il valore minimo specificato nel **Numero più basso / Numero più piccolo** da includere nell’intervallo di valori &#x200B; da immettere nel campo modulo.

* **Numero più alto / numero più grande** - Utilizzare questa opzione per selezionare il numero massimo consentito per l’immissione nel campo del modulo. Se il numero è maggiore del numero specificato in **Numero più alto / numero più grande** nel campo modulo viene immessa l’opzione , viene visualizzato un messaggio di errore.

* **Messaggio di errore massimo** - Questa opzione consente di inserire un messaggio di errore visualizzato quando l’utente immette un valore maggiore del valore specificato nel **Numero più alto / numero più grande** opzione .

* **Escludi valore massimo** - Selezionare questa casella di controllo se non si desidera il valore massimo specificato nel **Numero più alto / numero più grande** da includere nell’intervallo di valori da immettere nel campo modulo.

### Scheda Contenuto dell’Aiuto {#help-content}

![Scheda Contenuto della guida](/help/adaptive-forms/assets/numberinput_helptab.png)

* **Breve descrizione** - Una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita la **Mostra sempre una breve descrizione** per visualizzarlo sotto il componente.

* **Mostra sempre una breve descrizione** - Abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo della Guida** - Il testo della Guida si riferisce a informazioni o indicazioni aggiuntive fornite all&#39;utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’Aiuto (i) posta accanto al componente. Il testo della Guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility}

![Scheda Accessibilità](/help/adaptive-forms/assets/numberinput_accessibility.png)

* **Testo per assistenti vocali** - Il testo per gli assistenti vocali si riferisce al testo aggiuntivo destinato specificamente alla lettura da parte di tecnologie per l’accessibilità, come gli assistenti vocali, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome ed eventuali messaggi pertinenti del campo (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di tutti gli utenti, compresi quelli con problemi visivi, e di comprendere appieno il campo del modulo e i relativi requisiti.

### Scheda Formati {#formats-tab}

![Scheda Accessibilità](/help/adaptive-forms/assets/numberinput_formattab.png)


* **Formato di visualizzazione** - Questa opzione consente di selezionare l&#39;opzione tra diversi formati numerici interi da visualizzare. Quando l&#39;utente seleziona una qualsiasi opzione dal **Tipo** menu a discesa, **Formato** diventa visibile nel pannello . È possibile scegliere un formato specifico in cui i numeri vengono visualizzati all&#39;utente.

* **Numero di cifre prima del separatore decimale (1234.000)** - Utilizzare questa opzione per specificare il numero di cifre da visualizzare prima del punto decimale.

* **Numero di cifre dopo il separatore decimale (1234.000)** - Utilizzare questa opzione per specificare il numero di cifre da visualizzare dopo il separatore decimale.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo Progettazione viene utilizzata per definire e gestire gli stili CSS per il componente di input Numero .


### Scheda Stili {#styles-tab}

La finestra di dialogo Progettazione consente di definire e gestire gli stili CSS per un componente. Il componente di base per l’input del numero di Forms adattivo supporta il AEM [Sistema di stili](/help/get-started/authoring.md#component-styling).

**Classi CSS predefinite**: È possibile fornire una classe CSS predefinita per il componente core di input per numero di Forms adattivo.

**Stili consentiti**: È possibile definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato &quot;bold text&quot; e fornire la classe CSS &quot;font-weight: grassetto&quot;. Puoi utilizzare o applicare questi stili a un modulo adattivo nell’editor di Forms adattivo. Per applicare uno stile, nell’editor di Forms adattivo, seleziona il componente a cui applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dal **Stili** elenco a discesa. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo Progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

### Scheda Formati {#format-tab}

La scheda Formati consente di specificare i formati numerici predefiniti e personalizzati.
