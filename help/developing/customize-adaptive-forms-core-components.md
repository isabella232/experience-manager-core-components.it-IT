---
title: Personalizzare i componenti core dei moduli adattivi
description: Scopri come estendere o creare un componente core dei moduli adattivi per implementare funzionalità personalizzate per la tua organizzazione.
role: Architect, Developer, Admin
source-git-commit: 9a80b453d6a6cf7b347128654d3b5e673a063505
workflow-type: ht
source-wordcount: '707'
ht-degree: 100%

---


# Personalizzare i componenti core dei moduli adattivi

La personalizzazione dei componenti core dei moduli adattivi consente di personalizzare le funzionalità predefinite in base alle proprie esigenze specifiche. Questa guida illustra come personalizzare tali componenti, per creare un’esperienza più personale.

## Prerequisito

Prima di iniziare a personalizzare i componenti core dei moduli adattivi,

* scopri di più sull’[architettura di un componente core](customizing.md#customizing-the-markup-customizing-the-markup) ed esamina la [documentazione ufficiale dei componenti core di Adobe Experience Manager](customizing.md). Queste risorse complete fungono da guida durante l’intero processo di personalizzazione.
* Configura l’ambiente di sviluppo per garantire un flusso di lavoro semplificato e apportare modifiche ai componenti core. Durante la configurazione dell’ambiente di sviluppo, utilizza un Archetipo progetto AEM basato su quello più recente. In base all’ambiente, puoi:

   * [Configurare un ambiente di sviluppo locale per Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-local-development-environment.html?lang=it).
   * [Configurare un ambiente di sviluppo locale per AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html?lang=it)

## Personalizzare un componente core per moduli adattivi

Segui i passaggi seguenti per modificare l’aspetto, il comportamento e la funzionalità di un componente core per moduli adattivi.

1. **Identificare e duplicare il componente core**

   Durante la configurazione dell’ambiente di sviluppo, hai creato un progetto basato su Archetipo. Nell’Archetipo progetto AEM, identifica il componente core specifico che desideri personalizzare. Una volta identificato, crea un duplicato del componente all’interno del progetto basato su Archetipo AEM. Mantienilo in parallelo agli altri componenti core per moduli adattivi. Questo passaggio assicura che le attività di personalizzazione non influiscano sul componente originale, consentendoti di sperimentare liberamente.

1. **Personalizzare il componente copiato**

   Apri il componente duplicato e inizia ad apportare le modifiche necessarie in base alle tue esigenze:

   * **Personalizza struttura HTML**: personalizza la struttura HTML in base alle tue esigenze di progettazione, rispettando allo stesso tempo le procedure di stile [BEM (Block Element Modifier)](https://github.com/adobe/aem-core-wcm-components/wiki/css-coding-conventions) per il codice gestibile e scalabile.
   * **Aggiorna etichetta**: aggiorna l’etichetta del componente per fornire un nome chiaro e descrittivo per la versione personalizzata. Consulta il [Modello di etichetta OOTB (preconfigurata)](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/label.html) fornito per coerenza.
   * **Personalizza widget**: regola il widget utilizzato all’interno del componente (menu a discesa, caselle di controllo) per allinearlo al caso d’uso specifico. Consulta la sezione [esempio di implementazione di un widget](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/textinput.html) di riferimento.
   * **Testo guida e descrizioni comandi**: personalizza il testo della guida o le descrizioni comandi associate al componente per offrire agli utenti contesto e indicazioni. Utilizza il [modello di testo guida OOTB (preconfigurata)](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/questionMark.html) come punto di partenza.
   * **Attributi dei dati**: incorpora tutti gli attributi di dati necessari all’interno degli elementi HTML del componente. Questi attributi sono fondamentali per il corretto funzionamento del componente in fase di esecuzione. Per comprendere il ruolo degli attributi di dati nei componenti core per moduli adattivi, consulta la [documentazione](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput).

1. **Implementare la logica di back-end**

   Se la personalizzazione richiede una logica di back-end, puoi estendere i modelli sling esistenti. Per integrare perfettamente la funzionalità desiderata nel componente personalizzato, fai riferimento all’[esempio](https://github.com/adobe/aem-core-forms-components/blob/master/bundles/af-core/src/main/java/com/adobe/cq/forms/core/components/internal/models/v1/form/TextInputImpl.java) fornito.

1. **Configurare la finestra di dialogo del componente**

   Configura la finestra di dialogo associata al componente personalizzato. Utilizza l’esempio [finestra di dialogo del componente](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/_cq_dialog/.content.xml) fornito nella documentazione per garantire che le interazioni e le impostazioni dell’utente siano gestite in modo appropriato.

1. **Distribuire e testare il componente nell’ambiente di sviluppo locale**

   Utilizzare [Maven per generare e distribuire il componente](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html?lang=it#building-and-installing) nell’ambiente di sviluppo locale. Dopo la distribuzione del componente, crea un modulo adattivo per testare il componente personalizzato.

1. **Distribuire il componente personalizzato nell’ambiente di produzione**

   Dopo aver testato il componente nell’ambiente di sviluppo locale, distribuiscilo negli ambienti di produzione.

