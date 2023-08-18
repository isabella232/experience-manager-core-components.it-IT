---
title: Personalizzare i componenti core di Forms adattivi
description: Scopri come estendere o creare un componente core Forms adattivo per implementare funzionalità personalizzate per la tua organizzazione.
role: Architect, Developer, Admin
source-git-commit: 9a80b453d6a6cf7b347128654d3b5e673a063505
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 3%

---


# Personalizzare i componenti core di Forms adattivi

La personalizzazione dei componenti core adattivi di Forms consente di personalizzare le funzionalità predefinite in base alle esigenze specifiche. Questa guida illustra come personalizzare questi componenti per creare un’esperienza più personalizzata.

## Prerequisito

Prima di iniziare a personalizzare i componenti core Adaptive Forms,

* Scopri di più su [Architettura di un Componente core](customizing.md#customizing-the-markup-customizing-the-markup) e passa attraverso [documentazione ufficiale dei Componenti core di Adobe Experience Manager](customizing.md). Queste risorse complete fungono da guida durante l’intero processo di personalizzazione.
* Configurare l’ambiente di sviluppo In questo modo si garantisce un flusso di lavoro fluido per apportare modifiche ai componenti core. Durante la configurazione dell’ambiente di sviluppo, utilizza un progetto Archetipo AEM basato sul progetto Archetipo AEM più recente. In base all’ambiente, puoi:

   * [Configurare un ambiente di sviluppo locale per Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-local-development-environment.html).
   * [Configurare un ambiente di sviluppo locale per Forms AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html?lang=it)

## Personalizzare un componente core Forms adattivo

Segui i passaggi seguenti per modificare l’aspetto, il comportamento e la funzionalità di un componente core Forms adattivo.

1. **Identificare e duplicare il Componente core**

   Durante la configurazione dell’ambiente di sviluppo, hai creato un progetto basato su Archetipo. Nel progetto Archetipo AEM, identifica il componente core specifico che desideri personalizzare. Una volta identificato, crea un duplicato del componente all’interno del progetto basato su Archetipo AEM. Mantieni questa funzione in parallelo con altri componenti core di Adaptive Forms. Questo passaggio assicura che le attività di personalizzazione non influiscano sul componente originale, consentendoti di sperimentare liberamente.

1. **Personalizzare il componente copiato**

   Apri il componente duplicato e inizia ad apportare le modifiche necessarie in base alle tue esigenze:

   * **Personalizza struttura HTML**: personalizza la struttura dei HTML in base alle tue esigenze di progettazione, rispettando allo stesso tempo [BEM (Block Element Modifier)](https://github.com/adobe/aem-core-wcm-components/wiki/css-coding-conventions) procedure di stile per il codice gestibile e scalabile.
   * **Aggiorna etichetta**: aggiorna l’etichetta del componente per fornire un nome chiaro e descrittivo per la versione personalizzata. Fai riferimento al fornito [Modello di etichetta preconfigurata](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/label.html) per coerenza.
   * **Personalizza widget**: regola il widget utilizzato all’interno del componente (menu a discesa, caselle di controllo) per allinearlo al caso d’uso specifico. Consulta la sezione [esempio di implementazione di un widget](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/textinput.html) per riferimento.
   * **Testo della Guida e descrizioni**: personalizza il testo della guida o le descrizioni associate al componente per offrire agli utenti contesto e indicazioni. Utilizza il [Modello di testo guida preconfigurato](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/questionMark.html) come punto di partenza.
   * **Attributi dei dati**: incorpora tutti gli attributi di dati necessari all’interno degli elementi HTML del componente. Questi attributi sono fondamentali per il corretto funzionamento del componente in fase di esecuzione. Consulta la [documentazione](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput) per comprendere il ruolo degli attributi di dati nei componenti core di Adaptive Forms.

1. **Implementare la logica di back-end**

   Se la personalizzazione richiede una logica di back-end, puoi estendere i modelli sling esistenti. Fai riferimento al fornito [esempio](https://github.com/adobe/aem-core-forms-components/blob/master/bundles/af-core/src/main/java/com/adobe/cq/forms/core/components/internal/models/v1/form/TextInputImpl.java) per integrare perfettamente la funzionalità desiderata nel componente personalizzato.

1. **Configurare la finestra di dialogo del componente**

   Configura la finestra di dialogo associata al componente personalizzato. Utilizza l’esempio [finestra di dialogo del componente](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/_cq_dialog/.content.xml) fornite nella documentazione per garantire che le interazioni e le impostazioni dell’utente siano gestite in modo appropriato.

1. **Distribuire e testare il componente nell’ambiente di sviluppo locale**

   Utilizzare [Maven per generare e distribuire il componente](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html#building-and-installing) nell&#39;ambiente di sviluppo locale. Dopo la distribuzione del componente, crea un modulo adattivo per testare il componente personalizzato.

1. **Distribuire il componente personalizzato nell’ambiente di produzione**

   Dopo aver testato il componente nell’ambiente di sviluppo locale, implementalo negli ambienti di produzione.

