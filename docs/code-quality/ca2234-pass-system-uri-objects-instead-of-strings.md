---
title: 'CA2234: Übergeben Sie System.Uri-Objekte anstelle von Zeichenfolgen'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PassSystemUriObjectsInsteadOfStrings
- CA2234
helpviewer_keywords:
- CA2234
- PassSystemUriObjectsInsteadOfStrings
ms.assetid: 14616b37-74c4-4286-b051-115d00aceb5f
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: fcc7994e67e268aff21af925632d2ee9cf102ff4
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45547161"
---
# <a name="ca2234-pass-systemuri-objects-instead-of-strings"></a>CA2234: Übergeben Sie System.Uri-Objekte anstelle von Zeichenfolgen

|||
|-|-|
|TypeName|PassSystemUriObjectsInsteadOfStrings|
|CheckId|CA2234|
|Kategorie|Microsoft.Usage|
|Unterbrechende Änderung|Nicht unterbrechende Änderung|

## <a name="cause"></a>Ursache
 Ein Aufruf wird einer Methode ausgelöst, die einen Zeichenfolgenparameter verfügt, deren Name "Uri", "Uri", "Urn", "Urn", "Url" oder "Url" enthält. und der deklarierende Typ der Methode enthält eine entsprechende methodenüberladung, die eine <xref:System.Uri?displayProperty=fullName> Parameter.

## <a name="rule-description"></a>Regelbeschreibung
 Ein Parametername in Token basierend auf der Kamel unterteilt, und anschließend wird jedes Token überprüft, um festzustellen, ob es sich um "Uri", "Uri", "Urn", "Urn", "Url" oder "Url" gleich. Wenn eine Übereinstimmung vorliegt, wird angenommen, dass der Parameter einen uniform Resource Identifier (URI) darstellen. Eine Zeichenfolgendarstellung eines URIs ist anfällig für Analyse- und Codierungsfehler und kann zu Sicherheitsmängeln führen. Die <xref:System.Uri> Klasse stellt diese Dienste auf sichere Weise. Wenn eine Auswahl zwischen zwei Überladungen, die unterscheiden sich nur bezüglich der Darstellung einer URI vorhanden ist, sollte der Benutzer auswählen die Überladung mit einem <xref:System.Uri> Argument.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, rufen Sie die Überladung, akzeptiert die <xref:System.Uri> Argument.

## <a name="when-to-suppress-warnings"></a>Wenn Sie Warnungen unterdrücken
 Es ist sicher eine Warnung dieser Regel zu unterdrücken, wenn der Zeichenfolgenparameter keinen URI darstellt.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt eine Methode, `ErrorProne`, die gegen die Regel und eine Methode, `SaferWay`, ordnungsgemäß Ruft die <xref:System.Uri> überladen.

 [!code-vb[FxCop.Usage.PassUri#1](../code-quality/codesnippet/VisualBasic/ca2234-pass-system-uri-objects-instead-of-strings_1.vb)]
 [!code-cpp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CPP/ca2234-pass-system-uri-objects-instead-of-strings_1.cpp)]
 [!code-csharp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CSharp/ca2234-pass-system-uri-objects-instead-of-strings_1.cs)]

## <a name="related-rules"></a>Verwandte Regeln
 [CA1057: URI-Überladungen vom Typ string rufen Überladungen vom Typ System.Uri auf](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)

 [CA1056: URI-Eigenschaften dürfen keine Zeichenfolgen sein](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

 [CA1054: URI-Parameter dürfen keine Zeichenfolgen sein](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

 [CA1055: URI-Rückgabewerte dürfen keine Zeichenfolgen sein](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)