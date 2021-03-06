---
title: Auswerten von Ausdrücken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- expressions [Debugging SDK], evaluating
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: 5ccfcc80-dea5-48a1-8bae-6a26f8d3bc56
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bfd6248b06b69fa89d1888467a70718cf98b2a9a
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "39232467"
---
# <a name="evaluate-expressions"></a>Auswerten von Ausdrücken
Ausdrücke werden von Zeichenfolgen, die vom übergebenen erstellt die **"Auto"**, **Watch**, **Schnellüberwachung**, oder **direkt** Windows. Wenn ein Ausdruck ausgewertet wird, generiert er eine druckbare Zeichenfolge, die den Namen und Typ der Variablen "oder" Argument "und" den Wert enthält. Diese Zeichenfolge wird in den zugehörigen IDE-Fenster angezeigt.  
  
## <a name="implementation"></a>Implementierung  
 Ausdrücke werden ausgewertet, wenn ein Programm an einem Haltepunkt beendet wurde. Der Ausdruck selbst wird durch dargestellt eine [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) -Schnittstelle, die einen analysierten Ausdruck darstellt, die für die Bindung und der Auswertung innerhalb des Kontexts des angegebenen Ausdrucks Auswertung bereit ist. Bestimmt Kontexts für die ausdrucksauswertung, die die Debug-Engine (DE) durch die Implementierung bereitstellt, der Stapelrahmen der [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) Schnittstelle.  
  
 Erhalten eine Benutzerzeichenfolge und ein [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) -Schnittstelle, eine Debug-Engine (DE) erhalten eine [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) Schnittstelle, übergeben Sie die Benutzerzeichenfolge, die die [ IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) Methode. Die IDebugExpression2-Schnittstelle, die zurückgegeben wird, enthält den analysierten Ausdruck bereit, für die Evaluierung.  
  
 Mit der `IDebugExpression2` -Schnittstelle, die DE erhalten den Wert des Ausdrucks durch synchrone oder asynchrone ausdrucksauswertung mit [IDebugExpression2::EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) oder [IDebugExpression2:: EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md). Dieser Wert zusammen mit dem Namen und Typ der Variablen oder des Arguments, wird für die Anzeige der IDE gesendet. Der Wert, Name und Typ werden durch dargestellt eine [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) Schnittstelle.  
  
 Um die Auswertung des Ausdrucks zu aktivieren, muss eine bereitgestellten Kompatibilitätsrichtlinie implementieren die [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) und [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) Schnittstellen. Synchrone und asynchrone Auswertung erfordern die Implementierung der [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Stapelrahmen](../../extensibility/debugger/stack-frames.md)   
 [Ausdrucksauswertungskontext](../../extensibility/debugger/expression-evaluation-context.md)   
 [Tasks zum Debuggen](../../extensibility/debugger/debugging-tasks.md)