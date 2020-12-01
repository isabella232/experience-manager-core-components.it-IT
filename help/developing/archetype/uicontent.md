---
title: ui.content Modulo dell'archivio AEM progetto
description: ui.content Modulo dell'archivio AEM progetto
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---


# ui.content Modulo dell&#39;archivio AEM progetto {#uicontent-module}

Il modulo ui.content maven (`<src-directory>/<project>/ui.content`) include il contenuto e le configurazioni di base sotto `/content` e `/conf`. ui.content viene compilato in un pacchetto AEM come ui.apps. La differenza principale sta nel fatto che i nodi memorizzati in ui.content possono essere modificati direttamente sull&#39;istanza AEM. Sono incluse pagine, risorse DAM e modelli modificabili. Il modulo ui.content può essere utilizzato per memorizzare il contenuto campione per un&#39;istanza pulita e/o per creare alcune configurazioni di base da gestire nel controllo del codice sorgente.

## filter.xml {#filter}

Il file `filter.xml` per il modulo ui.content si trova in `<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml` e contiene i percorsi che verranno inclusi e installati con il pacchetto ui.content. Al percorso viene aggiunto un attributo `mode="merge"`. In questo modo le configurazioni distribuite con una distribuzione del codice non ignorano automaticamente il contenuto o le configurazioni che sono state create direttamente nell&#39;istanza AEM.

## ui.content/pom.xml

Il modulo ui.content, come il modulo ui.apps, utilizza il plug-in Pacchetto FileVault. Tuttavia il percorso ui.content (`<src>/<project>/ui.content/pom.xml`) include una proprietà di configurazione aggiuntiva denominata `acHandling`, impostata su `merge_preserve`. Questo è incluso perché il modulo ui.content include gli elenchi di controllo degli accessi (ACL, Access Control List) che sono autorizzazioni e che determinano chi può modificare i modelli. Affinché questi ACL possano essere importati in AEM è necessaria la proprietà `acHandling`.
