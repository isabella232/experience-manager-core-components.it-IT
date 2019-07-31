---
source-git-commit: 1273505a2b00913a89606b856d2e7c3811a3bd72
translation-type: tm+mt

---
# Linee guida per contribuire alla documentazione di AEM

## Filosofia documentazione AEM

Sappiamo che gli utenti di Adobe Experience Manager lavorano in ambienti altamente competitivi, cercando di creare esperienze digitali che li distingueranno dai loro concorrenza. È quindi essenziale che, quando Adobe offre nuovi strumenti avanzati in AEM, questi strumenti dispongano di documentazione precisa e chiara per consentire al cliente di sfruttare immediatamente il proprio investimento AEM e massimizzare il ROI.

L'obiettivo della documentazione di AEM è quello di mettere la documentazione nelle mani degli utenti di AEM il prima possibile. Per questo motivo, abbiamo priorità a una documentazione accurata e utilizzabile e stiamo cercando di aggiornarla costantemente e di migliorarla.

## Contributi alla documentazione AEM

Al fine di migliorare costantemente la documentazione di AEM, l'intera community di utenti AEM ha il benvenuto per contribuire alla documentazione. Grazie a richieste o problemi estesi, i miglioramenti alla documentazione possono essere correzioni, chiarimenti, espansioni e altri esempi.

## Standard documentazione

Mentre apprezziamo i contributi alla nostra documentazione, qualsiasi contributo alla documentazione AEM, sotto forma di richiesta di pull o di un problema, deve rispettare i nostri standard di contributo e documentazione.

I contributi che non soddisfano questi standard possono essere rifiutati.

### I casi d'uso standard sono i documenti.

La documentazione di AEM copre i casi d'uso standard. I casi d'uso oltre l'ambito dell'installazione e dell'utilizzo standard del prodotto non fanno parte della documentazione di AEM.

### Non si verificano bug né soluzioni alternative.

Poiché la documentazione di AEM copre casi di utilizzo standard, bug, tali effetti causati da bug e soluzioni alternative non sono documentati.

### I contributi della documentazione non sono per rispondere alle domande tecniche.

Qualsiasi idea che potrebbe essere necessaria per migliorare la documentazione di AEM è utile come contributo. However comments, issues, and pull requests are intended for *contributions* only. Non devono essere utilizzati per rispondere alle domande su come utilizzare AEM o risolvere problemi tecnici.

Any questions about the usage of AEM or technical errors you may have should be reported through the normal support process via the [Experience Manager Support Portal](https://daycare.day.com/home.html) or discussed in the [Experience Manager community](http://help-forums.adobe.com/content/adobeforums/en/experience-manager-forum/adobe-experience-manager.html).

***I contributi della documentazione AEM non sostituiscono il supporto Adobe*** e tutti questi contributi che richiedono risposte alle domande relative al supporto verranno rifiutati.

### I contributi devono fare riferimento chiaramente alle pagine della documentazione interessate.

Se si crea un problema per suggerire miglioramenti alla documentazione, è necessario includere i collegamenti alle pagine interessate. If you create an issue by using the **Edit this page** link on a documentation page, the issue will be created with a link to the page automatically.

Ciò non si applica alle richieste pull perché le richieste pull includono le pagine interessate per definizione.

## Linee guida sulla documentazione

Chiediamo che i contributi alla documentazione seguano determinate linee guida sugli stili.

Seguendo queste linee guida, la revisione del contributo risulta più semplice e, pertanto, l'integrazione nella documentazione è più rapida. Tuttavia, non conformità o conformità a tali linee guida non significa che il contributo verrà rifiutato.

### Lingua e stile

#### Lingua

* La documentazione di AEM viene creata e gestita in inglese americano.
* Semplificate al massimo le frasi.
* Mantenere la lingua chiara e concisa.

Ricorda che i lettori di documentazione AEM sono in tutto il mondo e non possono essere altoparlanti in inglese nativi o fluidi. Evitate le postazioni e mantenete la lingua il più semplice e semplice possibile.

#### Segui manuale Microsoft di stile

[Il manuale di stile Microsoft](https://docs.microsoft.com/en-us/style-guide/welcome/) è una guida di stile disponibile in maniera gratuita, incentrata sulla documentazione del software e la documentazione di AEM segue questa guida, dove possibile.

### Formattazione

| Elemento | Stile |
|---|---|
| Elemento interfaccia o opzione | **grassetto** |
| Nome file, percorso, input utente, valori dei parametri | `monospaced` |
| Codice, riga di comando | ```Code Block``` |

### Schermate

Le schermate devono essere utilizzate con cautela e solo quando una descrizione testuale è insufficiente.

Non devono essere utilizzati marcatori o altre annotazioni nelle schermate (come cornici rossi, frecce o testo). In questo modo è più facile riutilizzare o replicare le schermate nelle versioni localizzate della documentazione.

### Riferimenti specifici alla versione

Cercate di evitare eventuali riferimenti diretti a una versione specifica nel contenuto della documentazione, quando possibile. Ciò rende la documentazione più flessibile ed estensibile per le versioni future.

### Utilizzo del giorno, AEM, CQ, CRX

The product should always be referred to by its full name **Adobe Experience Manager** for the first time in an article and can thereafter be referred to as **AEM**.

Day, Day Software, CQ e CRX non devono essere utilizzati, ad eccezione dei casi in cui sono inevitabili, ad esempio nei nomi di classe o nella cronologia di AEM.