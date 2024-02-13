---
title: Progettazione reattiva dei Componenti core
description: Scopri la progettazione reattiva dei Componenti core e come può influenzare il progetto.
role: Architect, Developer, Admin, User
source-git-commit: d39fe0084522f67664203a026340b23d325c1883
workflow-type: ht
source-wordcount: '174'
ht-degree: 100%

---


# Progettazione reattiva dei Componenti core {#responsive-design}

Tutti i Componenti core sono progettati per essere completamente reattivi, garantendo un’esperienza fluida su tutti i dispositivi. È importante notare che alcuni componenti avanzati, come ad esempio i componenti [Carosello](/help/components/carousel.md), [Schede](/help/components/tabs.md) e [Pannello a soffietto,](/help/components/accordion.md) possono richiedere una considerazione specifica nel contesto del progetto di implementazione al fine di mantenere la reattività in tutte le condizioni.

Date le diverse modalità in cui questi componenti possono mostrare un comportamento reattivo, e nell’impegno di Adobe di mantenere i Componenti core leggeri e pronti all’uso, la responsabilità di implementare gli aspetti reattivi dettagliati è intenzionalmente lasciata al progetto.

Ad esempio, su schermi stretti il componente Schede può adattarsi suddividendo schede ampie in nuove righe, consentendo lo scorrimento verticale, trasformando schede in elenchi a discesa o adottando uno stile Pannello a soffietto. A causa del potenziale impatto sulle prestazioni che l’implementazione di tutti questi comportamenti potrebbe causare, le [clientlibs](/help/developing/including-clientlibs.md#provided) sono intese come punto di partenza per chi è addetto all’implementazione piuttosto che come soluzione esaustiva.
