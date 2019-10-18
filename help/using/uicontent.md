---
title: modulo ui.content dell’archivio del progetto AEM
seo-title: modulo ui.content dell’archivio del progetto AEM
description: modulo ui.content dell’archivio del progetto AEM
seo-description: modulo ui.content dell’archivio del progetto AEM
contentOwner: bohnert
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: 3c37b57eb72d1d662cdbd41ca54cdc592919203c

---


# modulo ui.content dell’archivio del progetto AEM {#uicontent-module}

Il modulo ui.content maven (`<src-directory>/<project>/ui.content`) include il contenuto di base e le configurazioni sotto `/content` e `/conf`. ui.content viene compilato in un pacchetto AEM molto simile a ui.apps. La differenza principale sta nel fatto che i nodi memorizzati in ui.content possono essere modificati direttamente sull’istanza AEM. Sono incluse pagine, risorse DAM e modelli modificabili. Il modulo ui.content può essere utilizzato per memorizzare il contenuto campione per un'istanza pulita e/o per creare alcune configurazioni di base da gestire nel controllo del codice sorgente.

## filter.xml {#filter}

Il `filter.xml` file per il modulo ui.content si trova in `<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml` e contiene i percorsi che verranno inclusi e installati con il pacchetto ui.content. Un `mode="merge"` attributo viene aggiunto al percorso. Questo garantisce che le configurazioni distribuite con una distribuzione del codice non sovrascrivano automaticamente il contenuto o le configurazioni che sono state create direttamente nell’istanza di AEM.

## ui.content/pom.xml

Il modulo ui.content, come il modulo ui.apps, utilizza il plug-in Pacchetto FileVault. Tuttavia, l’URL di contenuto (`<src>/<project>/ui.content/pom.xml`) include una proprietà di configurazione aggiuntiva denominata `acHandling`, impostata su `merge_preserve`. Questo è incluso perché il modulo ui.content include gli elenchi di controllo degli accessi (ACL, Access Control List) che sono autorizzazioni e che determinano chi può modificare i modelli. Affinché tali ACL possano essere importati in AEM, è necessaria la `acHandling` proprietà.
