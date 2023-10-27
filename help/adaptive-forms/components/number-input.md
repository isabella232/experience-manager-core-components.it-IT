---
title: Componente core moduli adattivi - Input numero
description: Utilizzo o personalizzazione del componente core di inserimento numero dei moduli adattivi.
role: Architect, Developer, Admin, User
exl-id: 75604ecf-1ec5-4e97-b934-d6ed49726147
source-git-commit: be630c4d0a10ebaa679b77419b901fac818addb1
workflow-type: ht
source-wordcount: '1834'
ht-degree: 100%

---

# Inserimento numero {#number-input-adaptive-forms-core-component}

Un componente di inserimento numero in un modulo adattivo è un tipo di campo modulo che consente agli utenti di immettere valori numerici. Il componente è in genere rappresentato da un campo di testo con una freccia su e giù per incrementare e diminuire il numero.

Può essere utilizzato anche con attributi come min, max, passaggio, valore e altro ancora. Questi attributi possono essere utilizzati per impostare i valori minimi e massimi consentiti nel campo, l’intervallo di passaggio per l’incremento o la riduzione del numero e il valore predefinito del campo.

Questo componente può essere utilizzato per raccogliere dati numerici come età, quantità e altro ancora, Può essere utilizzato anche per eseguire operazioni matematiche come addizione e sottrazione. Questo componente può essere utilizzato anche per convalidare i dati numerici immessi dall’utente.

Per l’accessibilità, è importante specificare l’etichetta che descrive lo scopo del campo di inserimento numero e il tipo di inserimento previsto.

**Esempio**

![](/help/adaptive-forms/assets/numeric-stepper.png)

## Utilizzo {#reasons-to-use-number-input-numeric-stepper}

Esistono diversi motivi per cui è utile includere un componente di inserimento numerico in un modulo adattivo, tra cui:

* **Operazioni matematiche**: i campi numerici possono essere utilizzati per eseguire operazioni matematiche quali addizione, sottrazione, moltiplicazione e divisione.

* **Intervallo dati**: i campi numerici possono essere utilizzati per impostare un intervallo di valori validi mediante gli attributi min, max e passaggio.

* **Contenuto dinamico**: il componente numerico può essere utilizzato per visualizzare i dati dinamici in base ai campi del modulo.


## Versione e compatibilità {#version-and-compatibility}

Il componente core Pannello a soffietto moduli adattativi è stato rilasciato a febbraio 2023 come parte dei Componenti core 2.0.4 per Cloud Service e i Componenti core 1.1.12 per AEM Forms 6.5.16.0 o versioni successive. Di seguito è riportata una tabella che mostra tutte le versioni supportate, la compatibilità AEM e i collegamenti alla documentazione corrispondente:

| Versione del componente | AEM as a Cloud Service | AEM Forms 6.5.16.0 o versioni successive |
|---|---|---|
| v1 | Compatibile con<br>[versione 2.0.4](/help/adaptive-forms/version.md) e successive | Compatibile con <br>[versione 1.1.12](/help/adaptive-forms/version.md) e successive, ma precedenti a 2.0.0. |

Per informazioni sulle versioni dei componenti core, consulta il documento [Versioni dei componenti core](/help/adaptive-forms/version.md).


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Dettagli tecnici {#technical-details}

Scarica le informazioni più recenti sul componente core per l’inserimento numerico dei moduli adattivi nella documentazione tecnica su [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/numberinput/v1/numberinput). Per ulteriori informazioni sullo sviluppo dei componenti core, dai un’occhiata alla [Documentazione per gli sviluppatori dei componenti core](/help/developing/overview.md).

## Finestra di dialogo per la configurazione {#configure-dialog}

Puoi personalizzare facilmente l’esperienza di inserimento numerico per i visitatori tramite la finestra di dialogo Configura. È inoltre possibile definire con facilità le opzioni di inserimento numerico per un’esperienza utente semplice.

### Scheda Base {#basic-tab}

![Scheda Base](/help/adaptive-forms/assets/numberinput_basictab.png)

* **Nome**: è possibile identificare facilmente un componente modulo con il suo nome univoco sia nel modulo che nell’editor di regole, ma il nome non deve contenere spazi o caratteri speciali.

* **Titolo**: con il relativo titolo è possibile identificare facilmente un componente in un modulo e, per impostazione predefinita, il titolo viene visualizzato sopra il componente. Se non aggiungi un titolo, al posto del testo del titolo viene visualizzato il nome del componente.

* **Nascondi titolo**: seleziona l’opzione per nascondere il titolo del componente.

* **Testo segnaposto**: il testo segnaposto in un componente modulo si riferisce a un’etichetta o a un prompt brevi che vengono visualizzati all’interno di un campo di inserimento come suggerimento per l’utente sul tipo di informazioni che ci si aspetta venga immesso in quel campo. Il testo segnaposto scompare quando l’utente inizia a digitare nel campo e viene visualizzato nuovamente se il campo viene lasciato vuoto. Fornisce un suggerimento visivo all’utente, ma non funge da etichetta o valore permanente per il campo.
* **Riferimento di binding**: un riferimento di binding è un riferimento a un elemento dati memorizzato in un’origine dati esterna e utilizzato in un modulo. Il riferimento di binding consente di eseguire un binding dinamico dei dati ai campi del modulo, in modo che il modulo possa visualizzare i dati più aggiornati dell’origine dati. Ad esempio, è possibile utilizzare un riferimento di binding per visualizzare il nome e l’indirizzo di un cliente in un modulo, in base all’ID cliente immesso nel modulo. È inoltre possibile utilizzare il riferimento di binding per aggiornare l’origine dati con i dati immessi nel modulo. In questo modo, AEM Forms consente di creare moduli che interagiscono con origini dati esterne, offrendo agli utenti un’esperienza utente semplice per la raccolta e la gestione dei dati.
* **Nascondi componente**: seleziona questa opzione per nascondere il componente dal modulo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole. Questa funzione è utile quando devi memorizzare informazioni che non devono essere viste o modificate direttamente dall’utente.
* **Disattiva componente**: seleziona questa opzione per disabilitare il componente. Il componente disabilitato non è attivo o modificabile dall’utente finale. L’utente può visualizzare il valore del campo, ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.
* **Sola lettura**: seleziona questa opzione per rendere il componente non modificabile. L’utente può vedere il valore del campo ma non può modificarlo. Il componente rimane accessibile per altri scopi, ad esempio per i calcoli nell’editor di regole.
* **Tipo di numero**: questa opzione consente di selezionare il tipo di valori numerici consentiti nel campo modulo. È possibile selezionare i tipi Decimale o Intero dal menu a discesa.
* **Valore predefinito** - questa opzione consente di aggiungere un valore predefinito in un campo modulo. Se **Componente disabilitato** o **Componente di sola lettura** è selezionato, il valore predefinito viene visualizzato sullo schermo. Se l’utente non immette alcun valore nel campo modulo, questo valore viene inviato al momento dell’invio del modulo.

### Scheda Convalida {#validation-tab}

![Scheda Convalida](/help/adaptive-forms/assets/numberinput_validationtab.png)

* **Obbligatorio**: seleziona questa opzione se desideri visualizzare il componente in un modulo adattivo. Non è possibile selezionare **Nascondi componente** o **Disattiva componente** nella scheda **Base** quando questa opzione è selezionata.

* **Messaggio di errore**: questa opzione consente di inserire un messaggio visualizzato se la casella di controllo **Obbligatorio** è selezionata e il campo viene lasciato vuoto.

* **Messaggio di convalida script**: questa opzione consente di inserire un messaggio da visualizzare in caso di errore di convalida dello script.

* **Numero più basso/più piccolo**: utilizza questa opzione per selezionare il numero minimo consentito da immettere nel campo modulo. Se un valore inferiore al numero specificato nell’opzione **Numero più basso/più piccolo** viene inserito nel campo modulo, viene visualizzato un messaggio di errore.

* **Messaggio di errore minimo**: questa opzione consente di inserire un messaggio di errore visualizzato quando l’utente immette un valore inferiore al valore specificato nell’opzione **Numero minimo/Numero minimo**.

* **Escludi valore minimo**: seleziona questa casella di controllo se non desideri che il valore minimo specificato nell’opzione **Numero più basso/più piccolo** sia incluso nell’intervallo di valori da inserire nel campo del modulo.

* **Numero più alto/più grande**: utilizza questa opzione per selezionare il numero massimo consentito per l’inserimento nel campo del modulo. Se un numero maggiore del numero specificato nell’opzione **Numero più alto/più grande** viene inserito nel campo modulo, viene visualizzato il messaggio di errore.

* **Messaggio di errore massimo**: questa opzione consente di inserire un messaggio di errore visualizzato quando l’utente immette un valore maggiore del valore specificato nell’opzione **Numero più alto/più grande**.

* **Escludi valore massimo**: seleziona questa casella di controllo se non desideri che il valore massimo specificato nell’opzione **Numero più alto/più grande** sia incluso nell’intervallo di valori da immettere nel campo del modulo.

### Scheda Contenuto Guida {#help-content}

![Scheda Contenuto Guida](/help/adaptive-forms/assets/numberinput_helptab.png)

* **Breve descrizione**: una breve descrizione è una breve spiegazione testuale che fornisce informazioni aggiuntive o chiarimenti sullo scopo di un campo modulo specifico. Aiuta l’utente a capire quale tipo di dati deve essere immesso nel campo e può fornire linee guida o esempi per garantire che le informazioni immesse siano valide e soddisfino i criteri desiderati. Per impostazione predefinita, le descrizioni brevi rimangono nascoste. Abilita l’opzione **Mostra sempre una breve descrizione** per visualizzarla sotto il componente.

* **Mostra sempre una breve descrizione**: abilita l’opzione per visualizzare la descrizione breve sotto il componente.

* **Testo guida**: il testo guida si riferisce a informazioni o indicazioni aggiuntive fornite all’utente per aiutarlo a compilare correttamente un campo del modulo. Viene visualizzato quando l’utente fa clic sull’icona dell’aiuto (i) posta vicino al componente. Il testo guida fornisce informazioni più dettagliate rispetto all’etichetta o al testo segnaposto di un campo del modulo ed è progettato per consentire all’utente di comprendere i requisiti o i vincoli del campo. Può inoltre offrire suggerimenti o esempi per rendere più semplice e precisa la compilazione del modulo.

### Scheda Accessibilità {#accessibility}

![Scheda Accessibilità](/help/adaptive-forms/assets/numberinput_accessibility.png)

**Testo per utilità per la lettura dello schermo**: il testo per le utilità per la lettura dello schermo indica il testo aggiuntivo destinato alla lettura da parte di tecnologie per l’accessibilità, come le utilità per la lettura dello schermo, utilizzate da persone ipovedenti. Questo testo fornisce una descrizione audio dello scopo del campo modulo e può includere informazioni sul titolo, la descrizione, il nome del campo ed eventuali messaggi rilevanti (testo personalizzato). Il testo dell’assistente vocale consente di garantire l’accesso al modulo da parte di qualsiasi utente, comprese le persone ipovedenti, consentendo di comprendere appieno il campo del modulo e i relativi requisiti.

### Scheda Formati {#formats-tab}

![Scheda Accessibilità](/help/adaptive-forms/assets/numberinput_formattab.png)

* **Formato visualizzato**: questa opzione consente di selezionare un’opzione tra diversi formati numerici interi da visualizzare. Quando l’utente seleziona una qualsiasi opzione dal menu a discesa **Tipo**, l’opzione **Formato** diventa visibile nel pannello. È possibile scegliere un formato specifico in cui i numeri vengono mostrati all’utente.

* **Numero di cifre prima del separatore decimale (1234,000)**: utilizza questa opzione per specificare il numero di cifre da visualizzare prima del separatore decimale.

* **Numero di cifre dopo il separatore decimale (1234,000)**: utilizza questa opzione per specificare il numero di cifre da visualizzare dopo il separatore decimale.

## Finestra di dialogo per la progettazione {#design-dialog}

La finestra di dialogo per la progettazione viene utilizzata per definire e gestire gli stili CSS per il componente di inserimento numero.

### Scheda Stili {#styles-tab}

La scheda è utilizzata per definire e gestire gli stili CSS per un componente. Il componente core per l’inserimento del numero dei moduli adattivi supporta il [Sistema di stili](/help/get-started/authoring.md#component-styling) di AEM.

![Scheda Stile](/help/adaptive-forms/assets/datepicker_styletab.png)

**Classi CSS predefinite**: è possibile fornire una classe CSS predefinita per il componente core di inserimento del numero dei moduli adattivi.

**Stili consentiti**: puoi definire gli stili fornendo un nome e la classe CSS che rappresenta lo stile. Ad esempio, puoi creare uno stile denominato “testo in grassetto” e fornire la classe CSS “spessore carattere: grassetto”. Puoi utilizzare o applicare questi stili a un modulo adattivo in Moduli adattivi. Per applicare uno stile, nell’editor di moduli adattivi, seleziona il componente a cui desideri applicare lo stile, passa alla finestra di dialogo delle proprietà e seleziona lo stile desiderato dall’elenco a discesa **Stili**. Per aggiornare o modificare gli stili, è sufficiente tornare alla finestra di dialogo per la progettazione, aggiornare gli stili nella scheda Stili e salvare le modifiche.

### Scheda Formati {#format-tab}

La scheda dei formati consente di specificare i formati numerici predefiniti e personalizzati.
![Scheda Progettazione](/help/adaptive-forms/assets/emailinput_designformattab.png)

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->


>[!MORELIKETHIS]
>
>* [Pannello a soffietto](/help/adaptive-forms/components/accordion.md)
>* [Pulsante](/help/adaptive-forms/components/button.md)
>* [Gruppo di caselle di selezione](/help/adaptive-forms/components/checkbox-group.md)
>* [Selettore data](/help/adaptive-forms/components/date-picker.md)
>* [Elenco a discesa](/help/adaptive-forms/components/drop-down.md)
>* [Inserimento e-mail](/help/adaptive-forms/components/email-input.md)
>* [Contenitore modulo](/help/adaptive-forms/components/form-container.md)
>* [Allegato file](/help/adaptive-forms/components/file-attachment.md)
>* [Piè di pagina](/help/adaptive-forms/components/footer.md)
>* [Intestazione](/help/adaptive-forms/components/header.md)
>* [Schede orizzontali](/help/adaptive-forms/components/horizontal-tabs.md)
>* [Immagine](/help/adaptive-forms/components/image.md)
>* [Contenitore pannelli](/help/adaptive-forms/components/panel-container.md)
>* [Pulsante di scelta](/help/adaptive-forms/components/radio-button.md)
>* [Pulsante Ripristina](/help/adaptive-forms/components/reset-button.md)
>* [Pulsante Invia](/help/adaptive-forms/components/submit-button.md)
>* [Inserimento telefono](/help/adaptive-forms/components/telephone-input.md)
>* [Inserimento testo](/help/adaptive-forms/components/text-input.md)
>* [Testo](/help/adaptive-forms/components/text.md)
>* [Titolo](/help/adaptive-forms/components/title.md)
>* [Procedura guidata](/help/adaptive-forms/components/wizard.md)


## Consulta anche {#see-also}

{{see-also}}