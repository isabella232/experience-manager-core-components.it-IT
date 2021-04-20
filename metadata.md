---
product: adobe experience manager
solution: Experience Manager Sites
type: Documentation
description: Documentazione per i componenti core di Adobe Experience Manager
git-repo: https://git.corp.adobe.com/AdobeDocs/experience-manager-core-components.it-IT
index: y
translation-type: tm+mt
source-git-commit: 290423c39b925ea8cf4077f31a76ecf01167f344
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 6%

---


# Metadati per uso interno

I metadati nel sistema di authoring GitHub sono gerarchici e vengono definiti i seguenti livelli crescenti di precedenti.

1. metadata.md
1. ToC
1. Articolo

I metadati definiti nel file metadata.md si applicano all&#39;intero repository, ma possono essere ignorati a livello di AC e di articolo. Qualsiasi override dei metadati deve essere eseguito al livello più basso possibile.

I metadati nell&#39;archivio experience-manager-core-components.en sono il minimo richiesto.

metadata.md

* `product`
* `git-repo`
* `index: y`
* `solution-title`
* `solution-hub-url`
* `getting-started-title`
* `getting-started-url`
* `tutorials-title`
* `tutorials-url`

ToCs

* `sub-product`
* `user-guide-title`

Articolo

* `title`
* `description`
* `index: n` (solo per le versioni precedenti dei componenti)

Ulteriori informazioni sui metadati sono disponibili nella [guida all&#39;authoring interno.](https://docs.adobe.com/help/en/collaborative-doc-instructions/collaboration-guide/markdown/metadata.html#solution-metadata)
