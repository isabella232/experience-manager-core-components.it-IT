---
title: Plug-in Maven di Build Analyzer nel SDK di AEM as a Cloud Service
description: Documentazione del plug-in Maven locale di Build Analyzer
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: de26b310-a294-42d6-a0db-91f6036a328c
source-git-commit: db33866f0a9e87e34eaaa061d308438c6f5bebb4
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 84%

---

# Plug-in Maven di Build Analyzer nel SDK di AEM as a Cloud Service {#maven-analyzer-plugin}

Il Plug-in Maven di Build Analyzer nel Software Development Kit (SDK) di AEM as a Cloud Service analizza la struttura dei vari progetti di pacchetti di contenuti.

Per informazioni su come includerlo in un progetto Maven, di AEM, vedi la [documentazione del Plug-in Maven](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md).

>[!NOTE]
>
>È consigliabile aggiornare il progetto Maven per fare riferimento all’ultima versione del Plug-in presente nell’archivio centrale Maven, nella posizione seguente: https://repo1.maven.org/maven2/com/adobe/aem/aemanalyser-maven-plugin/

Il Plug-in utilizza il SDK più recente disponibile, anziché quello configurato nel progetto.

La tabella che segue descrive gli analizzatori eseguiti come parte di questo passaggio. <!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| Modulo | Funzione, esempio e risoluzione dei problemi | SDK locale | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | Verifica se la dichiarazione Export-Package di altri bundle inclusi nel progetto Maven soddisfa le dichiarazione Import-Package di tutti i bundle OSGI. Un errore è simile al seguente: <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>Per risolvere i problemi, verifica se il bundle che fornisce il pacchetto è incluso nella distribuzione oppure, in alternativa, esamina il manifesto del bundle che ritieni debba effettuare l’esportare per stabilire se è stato utilizzato il nome o la versione errata. | Sì | Sì |
| `requirements-capabilities` | Verifica se le dichiarazioni delle funzionalità di altri bundle inclusi nel progetto Maven soddisfano tutte le dichiarazioni dei requisiti definite nei bundle OSGI. Un errore è simile al seguente: <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> Per risolvere i problemi, esamina il manifesto del bundle che ritieni debba dichiarare una funzionalità per stabilire il motivo della mancata dichiarazione oppure verifica nel manifesto del bundle richiedente se il requisito riportato è corretto. | Sì | Sì |
| `bundle-content` | Visualizza un avviso se un bundle include contenuto iniziale specificato con Sling-Initial-Content, che è problematico nell’ambiente a cluster di AEM as a Cloud Service. L’avviso si presenta così: <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>Per risolvere i problemi relativi alla conversione di contenuto iniziale in istruzioni Repoinit, vedi la documentazione di Repoinit. | Sì | Sì |
| `bundle-resources` | Visualizza un avviso se un bundle include contenuto iniziale specificato con l’intestazione Sling-Bundle-Resources, che è problematica nell’ambiente a cluster di AEM as a Cloud Service. L’avviso si presenta così:<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> Per risolvere i problemi relativi alla conversione delle risorse in istruzioni Repoinit, vedi la [documentazione di Repoinit](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=it#repo-init). | Sì | Sì |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | Questi analizzatori verificano alcuni dettagli del [pacchetto di contenuti per il processo di conversione del modello di funzione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=it#deploying) che crea artefatti conformi al modello di funzione Sling. Eventuali errori devono essere segnalati all’Assistenza clienti di Adobe. | Sì | Sì |
| `api-regions-crossfeature-dups` | Verifica che i bundle OSGI del cliente non abbiano dichiarazioni Export-Package l’API pubblica di AEM as a Cloud Service<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>Per risolvere il problema, evita di esportare un pacchetto che fa parte dell’API pubblica di AEM. | Sì | Sì |
| `repoinit` | Verifica la sintassi di tutte le sezioni Repoinit | Sì | Sì |
| `bundle-nativecode` | Verifica che i bundle OSGI non installino codice nativo. | Sì | Sì |
| `configuration-api` | Verifica importanti configurazioni OSGi. <p> </p> `Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Configuration is not allowed (com.mysite:mysite.all:1.0.0-SNAPSHOT\|com.mysite:mysite.ui.config:1.0.0-SNAPSHOT)` | Sì | Sì |
| `region-deprecated-api` | Verifica l’eventuale utilizzo di [API obsolete](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-apis.html?lang=it) <p> </p>`[WARNING] com.mysite:mysite.core:1.0.0-SNAPSHOT: Usage of deprecated package found : org.apache.sling.settings : Avoid these features at runtime: run modes, file system access (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | Sì | Sì |
| `artifact-rules` | Convalida le dipendenze come bundle e pacchetti di contenuto per evitare problemi noti negli artefatti.<p> </p>`[WARNING] [artifact-rules] com.adobe.acs:acs-aem-commons-bundle:5.0.4: Use at least version 5.0.10 (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | Sì | Sì |

## Problemi noti

Di seguito è riportato un elenco dei problemi noti durante l’utilizzo del plugin Maven di Build Analyzer.

### Impossibile eseguire il plug-in Maven di Build Analyzer nell&#39;SDK locale

Quando utilizzi l’SDK locale con una versione del plug-in Maven di Build Analyzer inferiore a `1.1.2`, l’esecuzione del plug-in potrebbe causare l’errore seguente. In questo caso, aggiorna il progetto alla versione più recente del plug-in.

```txt
[ERROR] Failed to execute goal com.adobe.aem:aemanalyser-maven-plugin:1.1.0:analyse (default-analyse) on project mysite.analyse: Execution default-analyse of goal com.adobe.aem:aemanalyser-maven-plugin:1.1.0:analyse failed: arraycopy: source index -1 out of bounds for char[65536] -> [Help 1]
```

Se hai utilizzato AEM Archetipo di progetto per configurare il progetto, assicurati di regolare la proprietà nella radice Maven `pom.xml` come indicato di seguito.

```xml
   ...
   <properties>
      ...
      <aemanalyser.version>1.1.2</aemanalyser.version> <!-- Make sure to use the latest release -->
      ...
   </properties>
```
