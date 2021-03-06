---
title: 'Gewusst wie: Festlegen von CLR-Attributen für ein Element'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.EditAttributesDialog
helpviewer_keywords:
- Domain-Specific Language, custom attrributes
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: ceca2556e269d554d40e025e5edcb91753149622
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
ms.locfileid: "31948911"
---
# <a name="how-to-set-clr-attributes-on-an-element"></a>Gewusst wie: Festlegen von CLR-Attributen für ein Element
Benutzerdefinierte Attribute sind spezielle Attribute, die Domänenelemente, Formen, Connectors und Diagramme hinzugefügt werden können. Sie können jedes Attribut, das von erbt Hinzufügen der `System.Attribute` Klasse.

### <a name="to-add-a-custom-attribute"></a>So fügen Sie ein benutzerdefiniertes Attribut hinzu

1.  In der **Explorer für DSL**, wählen Sie das Element, dem Sie ein benutzerdefiniertes Attribut hinzufügen möchten.

2.  In der **Eigenschaften** neben der **benutzerdefinierte Attribute** -Eigenschaft, klicken Sie auf die Schaltfläche zum Durchsuchen (**...** ) Symbol ".

     Die **Attribute bearbeiten** Dialogfeld wird geöffnet.

3.  In der **Namen** Spalte, klicken Sie auf  **\<attributhinzufügen >** und geben Sie den Namen des Attributs. Drücken Sie die EINGABETASTE.

4.  Die Linie unter dem Namen des Attributs zeigt Klammern. Geben Sie auf diese Zeile Parametertyp für das Attribut (z. B. `string`), und drücken Sie dann die EINGABETASTE.

5.  In der **Namenseigenschaft** Spalte Geben Sie einen passenden Namen, z. B. `MyString`.

6.  Klicken Sie auf **OK**.

     Die **benutzerdefinierte Attribute** Eigenschaft zeigt jetzt das Attribut im folgenden Format:

     `[` *AttributeName* `(` *ParameterName* `=` *Typ* `)]`

## <a name="see-also"></a>Siehe auch

- [Domänenspezifische Sprache Tools Glossar](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)