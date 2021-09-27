---
title: Modulo ui.content di Archetipo progetto AEM
description: Modulo ui.content di Archetipo progetto AEM
feature: Componenti core, Archetipo Progetto AEM
role: Architect, Developer, Admin
exl-id: af019cd8-c733-4b53-bb57-321dd9451178
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '223'
ht-degree: 100%

---

# Modulo ui.content di Archetipo progetto AEM {#uicontent-module}

Il modulo maven ui.content (`<src-directory>/<project>/ui.content`) include il contenuto e le configurazioni di base sotto `/content` e `/conf`. Il modulo ui.content viene compilato in un pacchetto AEM in modo molto simile a ui.apps. La differenza principale è che i nodi memorizzati in ui.content possono essere modificati direttamente sull’istanza di AEM. Sono inclusi pagine, risorse DAM e modelli modificabili. Il modulo ui.content può essere utilizzato per memorizzare esempi di contenuto per un’istanza pulita e/o per creare alcune configurazioni di base da gestire nel controllo del codice sorgente.

## File filter.xml {#filter}

Il file `filter.xml` del modulo ui.content si trova in `<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml` e contiene i percorsi che verranno inclusi e installati con il pacchetto ui.content. Al percorso viene aggiunto un attributo `mode="merge"`. In questo modo le configurazioni distribuite insieme a una distribuzione di codice non sovrascrivono automaticamente contenuto o configurazioni create direttamente sull’istanza di AEM.

## ui.content/pom.xml

Il modulo ui.content, come il modulo ui.apps, utilizza il plug-in FileVault Package. Tuttavia, il file POM ui.content (`<src>/<project>/ui.content/pom.xml`) include una proprietà di configurazione aggiuntiva denominata `acHandling`, impostata su `merge_preserve`. Questa proprietà è inclusa perché il modulo ui.content include a sua volta liste di controllo degli accessi (ACL, Access Control List) le cui autorizzazioni stabiliscono chi può modificare i modelli. Per importare queste ACL in AEM è necessaria la proprietà `acHandling`.
