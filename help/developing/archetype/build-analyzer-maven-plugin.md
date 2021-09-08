---
title: Plug-in Maven di AEM as a Cloud Service SDK Build Analyzer
description: Documentazione per il plug-in locale Maven build analyzer
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: de26b310-a294-42d6-a0db-91f6036a328c
source-git-commit: db33866f0a9e87e34eaaa061d308438c6f5bebb4
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 4%

---

# Plug-in Maven di AEM as a Cloud Service SDK Build Analyzer {#maven-analyzer-plugin}

Il plug-in Maven AEM as a Cloud Service SDK Build Analyzer analizza la struttura dei vari progetti di pacchetti di contenuto.

Per informazioni su come includerlo in un progetto Maven, consulta la [documentazione del plug-in Maven](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md) .

>[!NOTE]
>
>È consigliabile aggiornare il progetto Maven per fare riferimento all’ultima versione del plug-in presente nell’archivio centrale Maven, nella posizione seguente: https://repo1.maven.org/maven2/com/adobe/aem/aemanalyser-maven-plugin/

Il plug-in utilizza l’SDK più recente disponibile anziché quello configurato nel progetto.

Di seguito è riportata una tabella che descrive gli analizzatori eseguiti come parte di questo passaggio. <!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| Modulo | Funzione, esempio e risoluzione dei problemi | SDK locale | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | Controlla se tutte le dichiarazioni Import-Package di tutti i bundle OSGI sono soddisfatte dalla dichiarazione Export-Package di altri bundle inclusi nel progetto Maven. Un errore è simile al seguente: <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>Per risolvere i problemi, controlla se il bundle che fornisce il pacchetto è incluso nella distribuzione oppure in alternativa osserva il manifesto del bundle che ti aspetteresti di esportare per determinare se è stato utilizzato il nome o la versione errata. | Sì | Sì |
| `requirements-capabilities` | Controlla se tutte le dichiarazioni dei requisiti rese nei bundle OSGI sono soddisfatte dalle dichiarazioni delle capacità di altri bundle inclusi nel progetto Maven. Un errore è simile al seguente: <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> Per risolvere i problemi, osserva il manifesto del bundle che ti aspetteresti di dichiarare una funzionalità per determinare il motivo della sua mancanza, o controlla nel manifesto del bundle che richiede per vedere che il requisito in esso è corretto. | Sì | Sì |
| `bundle-content` | Visualizza un avviso se un bundle contiene il contenuto iniziale specificato con Sling-Initial-Content, che è problematico nell’ambiente cluster di AEM come Cloud Service. L&#39;avviso si presenta così: <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>Per risolvere i problemi relativi alla conversione del contenuto iniziale in istruzioni di reindirizzamento, consulta la documentazione di reindirizzamento . | Sì | Sì |
| `bundle-resources` | Visualizza un avviso se un bundle contiene risorse specificate con l&#39;intestazione Sling-Bundle-Resources , che è problematica nell&#39;ambiente cluster AEM come Cloud Service. L&#39;avviso si presenta così:<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> Per risolvere i problemi relativi alla conversione delle risorse in istruzioni di reindirizzamento, consulta [Repoinit Documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=en#repo-init). | Sì | Sì |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | Questi analizzatori controllano alcuni dettagli relativi al [pacchetto di contenuti al processo di conversione del modello di feature](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=en#deploying) che crea artefatti conformi al modello di feature Sling. Eventuali errori devono essere segnalati all’Assistenza clienti di Adobe. | Sì | Sì |
| `api-regions-crossfeature-dups` | Convalida che i bundle OSGI del cliente non abbiano dichiarazioni di pacchetto di esportazione che sovrascrivono AEM come API pubblica del Cloud Service<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>Per risolvere il problema, interrompi l&#39;esportazione di un pacchetto che fa parte dell&#39;API pubblica AEM. | Sì | Sì |
| `repoinit` | Controlla la sintassi di tutte le sezioni di reindirizzamento | Sì | Sì |
| `bundle-nativecode` | Convalida che i bundle OSGI non installino il codice nativo. | Sì | Sì |
| `configuration-api` | Convalida importanti configurazioni OSGi. <p> </p> `Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Configuration is not allowed (com.mysite:mysite.all:1.0.0-SNAPSHOT\|com.mysite:mysite.ui.config:1.0.0-SNAPSHOT)` | Sì | Sì |
| `region-deprecated-api` | Controlla se viene utilizzato [api obsolete](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-apis.html) <p> </p>`[WARNING] com.mysite:mysite.core:1.0.0-SNAPSHOT: Usage of deprecated package found : org.apache.sling.settings : Avoid these features at runtime: run modes, file system access (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | Sì | Sì |
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
