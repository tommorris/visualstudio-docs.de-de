---
title: Ausdrucksauswertungskontext | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- expression evaluation, context
ms.assetid: a2fd3758-09bd-45ae-8ecc-2d276c0036ba
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fc2c2ecc4f7867c2ad39ba72f9edcb72c0935ce5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47514039"
---
# <a name="expression-evaluation-context"></a>Ausdrucksauswertungskontext
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Ausdrucksauswertungskontext](https://docs.microsoft.com/visualstudio/extensibility/debugger/expression-evaluation-context).  
  
In [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Debuggen, ein **ausdrucksauswertungskontext**:  
  
-   Stellt einen Kontext für ausdrucksauswertung dar. Im Allgemeinen entspricht ein Evaluierungskontext den lexikalischen Gültigkeitsbereich in der Variablen, Parameter, Funktionen und Methoden zu bewerten. Beispielsweise wird ein ausdrucksauswertungskontext einen Stapelrahmen zugeordnet Kontext bereitstellen, für Ihre Evaluierung von lokalen Variablen, Methodenparameter und Klassenmember (falls zutreffend).  
  
-   Ist vorhanden, wenn ein Programm an einem Haltepunkt beendet wurde. Der Ausdruck selbst ist eine Datenstruktur, die einen analysierten Ausdruck, der bereit für die Bindung und Auswerten von innerhalb des angegebenen Kontexts darstellt.  
  
     Im Detail, werden Ausdrücke erstellt, mit der [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) Methode. Wenn ein Ausdruck ausgewertet wird, generiert er eine druckbare Zeichenfolge, die den Namen und Typ der Variablen "oder" Argument "und" den Wert enthält. Diese Zeichenfolge wird in das Überwachungsfenster oder im Fenster "lokal" der IDE angezeigt.  
  
     Erhält eine `BSTR` und [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) -Schnittstelle, die eine Debug-Engine (DE) erstellen kann eine [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) -Schnittstelle durch die Analyse eines Ausdrucks. Erhält ein `IDebugExpression2` -Schnittstelle, die DE kann durch synchrone oder asynchrone ausdrucksauswertung einen Wert abrufen. Dieser Wert zusammen mit dem Namen und Typ der Variablen oder des Arguments, wird für die Anzeige der IDE gesendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Schnittstellen für die Ausdrucksauswertung](../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [Debuggerkontexte](../../extensibility/debugger/debugger-contexts.md)

