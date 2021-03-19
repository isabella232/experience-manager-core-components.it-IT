---
title: modulo ui.content dell'Archetipo di progetto AEM
description: modulo ui.content dell'Archetipo di progetto AEM
feature: Componenti core, AEM Project Archetype
role: Architetto, Sviluppatore, Amministratore
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---


# modulo ui.content dell&#39;Archetipo di progetto AEM {#uicontent-module}

Il modulo maven ui.content (`<src-directory>/<project>/ui.content`) include il contenuto e le configurazioni della linea di base sotto `/content` e `/conf`. ui.content viene compilato in un pacchetto AEM molto simile a ui.apps. La differenza principale è che i nodi memorizzati in ui.content possono essere modificati direttamente sull&#39;istanza AEM. Sono inclusi pagine, risorse DAM e modelli modificabili. Il modulo ui.content può essere utilizzato per memorizzare il contenuto di esempio per un&#39;istanza pulita e/o per creare alcune configurazioni della linea di base da gestire nel controllo del codice sorgente.

## filter.xml {#filter}

Il file `filter.xml` per il modulo ui.content si trova in `<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml` e contiene i percorsi che verranno inclusi e installati con il pacchetto ui.content. Al percorso viene aggiunto un attributo `mode="merge"` . In questo modo le configurazioni distribuite con una distribuzione di codice non sovrascrivono automaticamente i contenuti o le configurazioni create direttamente sull’istanza AEM.

## ui.content/pom.xml

Il modulo ui.content, come il modulo ui.apps, utilizza il plug-in FileVault Package. Tuttavia il file pom ui.content (`<src>/<project>/ui.content/pom.xml`) include una proprietà di configurazione aggiuntiva denominata `acHandling`, impostata su `merge_preserve`. Questo è incluso perché il modulo ui.content include gli elenchi di controllo di accesso (ACL, Access Control List) che sono autorizzazioni, che determinano chi può modificare i modelli. Affinché queste ACL siano importate in AEM la proprietà `acHandling` è necessaria.
