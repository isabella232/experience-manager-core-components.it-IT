---
title: Versioni dei componenti core di AEM Forms
description: I componenti core AEM vengono pubblicati come versioni che possono contenere più di una versione degli stessi componenti core. Questo documento spiega cosa s’intende per versioni e come comprendere la compatibilità con i Componenti core e AEM.
role: Architect, Developer, Admin, User
exl-id: 8146a5b1-acf6-4b54-ad6b-6e1747a137f6
source-git-commit: a567b5ad937d426abe16c34e039e19cd0b1af5b0
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 58%

---

# Versioni dei Componenti core {#core-components-versions}

La versione corrente dei Componenti core 2.0.10 è compatibile con [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=it) e la versione 1.1.12 dei Componenti core è compatibile con le installazioni di [AEM 6.5 Form on-premise e AMS](https://experienceleague.adobe.com/docs/experience-manager-65/user-guide/home.html?lang=it).

## Cronologia delle versioni di AEM as Cloud Service {#aem-as-cs-version-history}

La tabella seguente presenta un elenco delle versioni dei Componenti core compatibili con AEM as a Cloud Service disponibili in [GitHub con dettagli completi relativi alle loro versioni](https://github.com/adobe/aem-core-forms-components/releases).

| Versione | Descrizione | AEM as a Cloud Service | Java™ | Data di pubblicazione |
|---|---|---|---|---|
| [2.0.74](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.74) | Con questa versione, l’errore di invio viene aggiornato per l’azione Invia in AEM Forms. | Continua | 8, 11 | 15 novembre 2023 |
| [2.0.70](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.70) | In questa versione è stato aggiunto il supporto per la gestione della lingua della pagina dei siti nel contenitore di moduli. | Continua | 8, 11 | 10 novembre 2023 |
| [2.0.64](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.64) | Supporto di testo RTF per le etichette dei componenti Radio/Casella di controllo. Questa versione include anche correzioni per il componente Termini e condizioni. | Continua | 8, 11 | 6 novembre 2023 |
| [2.0.62](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.62) | Con questa versione, è stato aggiunto il supporto per il componente Termini e condizioni. È stato aggiunto anche il supporto per il nome qualificato nei componenti core. | Continua | 8, 11 | 16 ottobre 2023 |
| [2.0.60](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.60) | Questa versione include correzioni relative alla funzione delle proprietà personalizzate, alla procedura guidata e al componente Selezione data. | Continua | 8, 11 | 12 settembre 2023 |
| [2.0.56](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.56) | Con questa versione è stato aggiunto il supporto per le proprietà personalizzate di tutti i Componenti core. | Continua | 8, 11 | 12 settembre 2023 |
| [2.0.54](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.54) | Questa versione ha risolto il problema relativo alla localizzazione con il componente Selezione data. | Continua | 8, 11 | 30 agosto 2023 |
| [2.0.52](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.52) | Supporto per l’utilizzo del componente Casella di controllo in un modulo adattivo. | Continua | 8, 11 | 25 agosto 2023 |
| [2.0.50](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.50) | Con questa versione è stato aggiunto il supporto per frammenti di modulo in un modulo adattivo. | Continua | 8, 11 | 4 agosto 2023 |
| [2.0.48](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.48) | I principali miglioramenti apportati in questa versione sono relativi alle prestazioni di Lighthouse. | Continua | 8, 11 | 25 luglio 2023 |
| [2.0.42](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.42) | La versione include miglioramenti alla fine della programmazione. | Continua | 8, 11 | 18 luglio 2023 |
| [2.0.38](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.38) | Con questa versione la funzione di accessibilità viene migliorata. | Continua | 8, 11 | 17 luglio 2023 |
| [2.0.36](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.36) | Con questa versione, puoi utilizzare il gestore degli errori personalizzato utilizzando il servizio Invoke dell’editor di regole. | Continua | 8, 11 | 3 luglio 2023 |
| [2.0.34](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.34) | È stato aggiunto il supporto della localizzazione per i messaggi di errore predefiniti insieme al pulsante Aggiungi/Rimuovi per il componente Ripetibile. | Continua | 8, 11 | 28 giugno 2023 |
| [2.0.32](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.32) | Con questa versione è stato aggiunto il supporto per Captcha per Adaptive Forms. | Continua | 8, 11 | 15 giugno 2023 |
| [2.0.26](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.26) | Supporto per l’aggiunta di moduli adattivi su AEM Sites. | Continua | 8, 11 | 7 giugno 2023 |
| [2.0.18](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.18) | Con questa versione, è stato aggiunto il supporto per la ripetibilità del componente Pannello a soffietto. È stato aggiunto anche un nuovo componente come schede verticali. | Continua | 8, 11 | 5 giugno 2023 |
| [2.0.10](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.10) | Con questa versione, nell’editor di Sites, viene introdotto il supporto per un componente contenitore di moduli adattivi. | Continua | 8, 11 | 17 marzo 2023 |
| [2.0.8](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.8) | In questa versione è stata introdotta la funzione di ripetibilità per il componente della procedura guidata. | Continua | 8, 11 | 3 marzo 2023 |
| [2.0.6](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.6) | In questa versione vengono introdotti più formati per il componente core dell’inserimento numerico. | Continua | 8, 11 | 08 febbraio 2023 |
| [2.0.4](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.6) | In questa versione viene introdotto il supporto per i componenti core per AEM as a Cloud Service. | Continua | 8, 11 | 30 gennaio 2023 |

## Cronologia delle versioni di AEM 6.5 Forms {#aem-as-form-version-history}

La tabella seguente presenta un elenco delle versioni dei Componenti core compatibili con AEM 6.5 Form on-premise e AMS disponibili in [GitHub con dettagli completi relativi alle loro versioni](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.12).

| Versione | Descrizione | AEM 6.4 | AEM 6.5 | Java™ | Data di pubblicazione |
|---|---|---|---|---|---|
| [1.1.32](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.32) | Questa versione ha aggiornato le informazioni sul pacchetto di AEM Service Pack 6.5.18.0. | - | 6.5.16.0+ | 8, 11 | 15 ottobre 2023 |
| [1.1.28](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.28) | Supporto di testo RTF per le etichette dei componenti Radio/Casella di controllo. Questa versione include anche il supporto per il componente Termini e condizioni. | - | 6.5.16.0+ | 8, 11 | 15 ottobre 2023 |
| [1.1.26](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.26) | Con questa versione è stato aggiunto il supporto per il componente Casella di controllo per Modulo adattivo. Include inoltre miglioramenti nelle prestazioni di Lighthouse. In questa versione è incluso anche il gestore degli errori personalizzato che utilizza il servizio Invoke dell’editor di regole. | - | 6.5.16.0+ | 8, 11 | 15 ottobre 2023 |
| [1.1.24](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.24) | È stato aggiunto il supporto della localizzazione per i messaggi di errore predefiniti insieme al pulsante Aggiungi/Rimuovi per il componente Ripetibile. È stato aggiunto anche il supporto per recaptcha in Adaptive Forms. | - | 6.5.16.0+ | 8, 11 | 29 giugno 2023 |
| [1.1.22](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.22) | Supporto per l’aggiunta di moduli adattivi su AEM Sites. È stata aggiunta la scheda Elementi nella finestra di dialogo per modifica della procedura guidata e del componente Schede verticali. | - | 6.5.16.0+ | 8, 11 | 07 giugno 2023 |
| [1.1.12](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.12) | In questa versione viene introdotto il supporto dei componenti core per AEM Forms on-premise e AMS. | - | 6.5.16.0+ | 8, 11 | 08 febbraio 2023 |

## Consulta anche {#see-also}

{{see-also}}