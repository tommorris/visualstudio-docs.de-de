---
title: 'CA1505: Nicht wartbaren Code vermeiden'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidUnmaintainableCode
- CA1505
helpviewer_keywords:
- AvoidUnmaintainableCode
- CA1505
ms.assetid: 8292b268-5929-4221-b699-f9c414bcec5d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9aae34f6e999bcf74fdfbae4597b22529863e34f
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546914"
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505: Nicht wartbaren Code vermeiden

|||
|-|-|
|TypeName|AvoidUnmantainableCode|
|CheckId|CA1505|
|Kategorie|Microsoft.Maintainability|
|Unterbrechende Änderung|Nicht unterbrechend|

## <a name="cause"></a>Ursache
 Ein Typ oder eine Methode verfügt über einen niedrigen Wartbarkeitsindexwert.

## <a name="rule-description"></a>Regelbeschreibung
 Der Wartbarkeitsindex wird berechnet, indem Sie die folgenden Metriken: Zeilen Code, Programm-Volume und zyklomatische Komplexität. Programm-Volume ist ein Maß für die Schwierigkeit der Überblick über einen Typ oder Methode, die basierend auf der Anzahl von Operatoren und Operanden in den Code. Zyklomatische Komplexität ist ein Maß der strukturellen Komplexität des Typs oder -Methode. Weitere Informationen finden Sie Informationen zu codemetriken auf [Messen von Komplexität und verwaltbarkeit von verwaltetem Code](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md).

 Ein niedriger Wartbarkeitsindex zeigt an, dass ein Typ oder Methode wahrscheinlich schwer zu verwalten und wäre ein guter Kandidat, neu zu entwerfen.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um diese Verletzung zu beheben, gestalten Sie den Typ oder die Methode aus, und versuchen Sie es in kleinere und stärker fokussierte Typen oder Methoden unterteilt.

## <a name="when-to-suppress-warnings"></a>Wenn Sie Warnungen unterdrücken
 Schließen Sie diese Warnung aus, wenn Sie einen Typ oder Methode immer noch als verwaltbar angesehen wird trotz seiner Größe, oder wenn der Typ oder Methode unterteilt werden kann.

## <a name="see-also"></a>Siehe auch

- [Verwaltbarkeitswarnungen](../code-quality/maintainability-warnings.md)
- [Messen von Komplexität und Verwaltbarkeit verwalteten Codes](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)