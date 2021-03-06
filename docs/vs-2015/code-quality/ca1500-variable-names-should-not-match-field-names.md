---
title: 'CA1500: Variablennamen sollten nicht Feldnamen übereinstimmen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
helpviewer_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
ms.assetid: fa0e5029-79e9-4a33-8576-787ac3c26c39
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: fc900de76f0ae31cb3dc770fec681c1b7bed8213
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47509379"
---
# <a name="ca1500-variable-names-should-not-match-field-names"></a>CA1500: Variablennamen sollten nicht mit Feldnamen übereinstimmen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Dokumentation für Visual Studio 2017 finden Sie unter [CA1500: Variablennamen sollten nicht mit Feldnamen übereinstimmen](https://docs.microsoft.com/visualstudio/code-quality/ca1500-variable-names-should-not-match-field-names) auf docs.microsoft.com.  
  
|||  
|-|-|  
|TypeName|VariableNamesShouldNotMatchFieldNames|  
|CheckId|CA1500|  
|Kategorie|Microsoft.Maintainability|  
|Unterbrechende Änderung|Wenn für einen Parameter ausgelöst, die den gleichen Namen wie ein Feld hat folgende Aufgaben ausführen:<br /><br /> Nicht-unterbrechend – Wenn das Feld und die Methode, die den Parameter deklariert außerhalb der Assembly, unabhängig von der Änderung nicht sichtbar ist, die Sie vornehmen.<br />Unterbrechend – Wenn Sie den Namen des Felds ändern und außerhalb der Assembly angezeigt werden können.<br />-Unterbrechend – Wenn Sie den Namen des Parameters ändern und die Methode, die es deklariert außerhalb der Assembly angezeigt werden kann.<br /><br /> Wenn für eine lokale Variable ausgelöst, die den gleichen Namen wie ein Feld hat folgende Aufgaben ausführen:<br /><br /> Nicht-unterbrechend – Wenn das Feld kann nicht außerhalb der Assembly, unabhängig von der Änderung angezeigt werden, die Sie vornehmen.<br />Geringfügiger – Wenn Sie den Namen der lokalen Variablen ändern, und ändern Sie den Namen des Felds nicht.<br />-Unterbrechend – Wenn Sie den Namen des Felds ändern und ihn außerhalb der Assembly angezeigt werden kann.|  
  
## <a name="cause"></a>Ursache  
 Eine Instanzmethode deklariert einen Parameter oder eine lokale Variable, deren Name eines Instanzenfelds des deklarierenden Typs übereinstimmt. Zum Abfangen von lokaler Variablen, die die Regel verletzen, muss der getestete Assembly mit Debuginformationen erstellt werden, und die zugehörigen Programmdatenbankdatei (.pdb) muss verfügbar sein.  
  
## <a name="rule-description"></a>Regelbeschreibung  
 Wenn der Name eines Instanzenfelds einen Parameter oder einer lokalen Variablen übereinstimmt, erfolgt mithilfe des Instanzfelds der `this` (`Me` in [!INCLUDE[vbprvb](../includes/vbprvb-md.md)])-Schlüsselwort innerhalb des Methodentexts. Wenn Code zu verwalten, ist es einfach vergessen dieser Differenz. dabei wird vorausgesetzt, dass der Parameter/lokale Variablen auf das Instanzenfeld bezieht, was zu Fehlern führt. Dies gilt insbesondere bei langen Text.  
  
## <a name="how-to-fix-violations"></a>Behandeln von Verstößen  
 Um einen Verstoß gegen diese Regel zu beheben, benennen Sie entweder die Parametervariable oder das Feld ein.  
  
## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?  
 Unterdrücken Sie keine Warnung dieser Regel.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt zwei Verstöße gegen die Regel an.  
  
 [!code-csharp[FxCop.Maintainability.VarMatchesField#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Maintainability.VarMatchesField/cs/FxCop.Maintainability.VarMatchesField.cs#1)]
 [!code-vb[FxCop.Maintainability.VarMatchesField#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Maintainability.VarMatchesField/vb/FxCop.Maintainability.VarMatchesField.vb#1)]

