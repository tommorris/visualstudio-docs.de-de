---
title: Erste Schritte mit dem Debugger-Erweiterbarkeit | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- getting started, Debugging SDK
- debugging [Debugging SDK], getting started
- Debugging SDK, getting started
ms.assetid: d6ce6f43-1409-4bf7-93cd-f3464ca23504
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e1a812575d14ef6595d58cc3ecc5d9f94b8f5635
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "39231283"
---
# <a name="get-started-with-debugger-extensibility"></a>Erste Schritte mit dem Debugger-Erweiterbarkeit
Die [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] enthält die Informationen, die Sie zum Erstellen und Anpassen von Debugger-Komponenten verwendet benötigen, um das Debuggen von Programmen innerhalb der [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Umgebung.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Debuggen von Verbesserungen, die die umfassende benutzerfreundlichkeit, die auf vorherigen durchgeführten Tests abgeleitet wurden [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Debugger. Sie können [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] debugging für Schritt durch eine Anwendung mehrsprachig, oder Sie können auf dynamische Bearbeitung von Variablen beim Debuggen von Anwendungen und Lösungen mit mehreren Sprachen implementieren.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Debuggen ist ausgeführten Out-of-Process mit dem Programm im Debugmodus befindlichen und daher weniger intrusiv im Prozessbereich der Anwendung. Daher ist es einfacher, Komponenten, die Interaktion mit dem Debugger zu schreiben, ohne Auswirkungen auf das Programm debuggen.  
  
 Die optimale Verwendung der [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], Sie sollten mit den folgenden Artikeln vertraut sein:  
  
-   Die [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrierte Entwicklungsumgebung (IDE)  
  
-   Die Programmiersprache C++  
  
-   ATL-COM  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Roadmap für die Erweiterung des Debuggers](../../extensibility/debugger/roadmap-for-extending-the-debugger.md)  
 Beschreibt den Prozess der Implementierung Debuggen in Ihrem Produkt, je nach dem Compiler und seine Ausgabe an.  
  
 [Debugger-Komponenten](../../extensibility/debugger/debugger-components.md)  
 Bietet eine Übersicht über die [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] debugging-Komponenten, die die Debug-Engine (DE), die ausdrucksauswertung (EE) und die Symbol-Handler (SH) enthalten.  
  
 [Debuggerkonzepte](../../extensibility/debugger/debugger-concepts.md)  
 Beschreibt die wichtigsten Konzepte für das Debuggen Architektur an.  
  
 [Debuggerkontexte](../../extensibility/debugger/debugger-contexts.md)  
 Erläutert, wie die Debug-Engine (DE) gleichzeitig in Code, Dokumentationen und Auswertung von ausdruckskontexten arbeitet. Beschreibt, für jede der drei Kontexten, Speicherort, Position oder Auswertung, die für sie relevant.  
  
 [Debuggingaufgaben](../../extensibility/debugger/debugging-tasks.md)  
 Enthält Links zu verschiedenen Debuggen Aufgaben wie das Starten eines Programms und Auswerten von Ausdrücken.