---
title: Diese verknüpfte Methode ist die Sicherungsmethode für die folgenden standardmäßigen Methoden zum Einfügen, Aktualisieren oder Löschen.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 62afa6da-97cf-48b9-8de3-33e4d72a0377
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 30e08cb10b6e1912fe5962620faf34a1c6250cf3
ms.sourcegitcommit: f37affbc1b885dfe246d4b2c295a6538b383a0ca
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37174156"
---
# <a name="this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods"></a>Diese verknüpfte Methode ist die Sicherungsmethode für die folgenden standardmäßigen Methoden zum Einfügen, Aktualisieren oder Löschen.

Diese verknüpfte Methode ist die dahinter liegende Methode für die folgenden Standardgruppen `Insert`, `Update`, oder `Delete` Methoden. Wenn sie gelöscht wird, werden die entsprechenden Methoden ebenfalls gelöscht. Möchten Sie den Vorgang fortsetzen?

Die ausgewählte `DataContext` Methode dient als eines der derzeit die `Insert`, `Update`, oder `Delete` Methoden für eine der Entitätsklassen der **O/R Designer**. Löschen die Ursachen für die ausgewählte Methode die Entitätsklasse, die diese Methode verwendet wurde, wieder in den das Standardverhalten für die Laufzeit für die Aktionen einfügen, aktualisieren oder Löschen während einer Aktualisierung.

## <a name="to-delete-the-selected-method-causing-the-entity-class-to-use-runtime-updates"></a>So löschen Sie die ausgewählte Methode und bewirken, dass die Entitätsklasse Laufzeitupdates verwendet

- Klicken Sie auf **Ja**.

    Die ausgewählte Methode wird gelöscht und alle Klassen, die diese Methode zum Überschreiben des Updateverhaltens verwendet hatten, greifen wieder auf das standardmäßige LINQ to SQL-Laufzeitverhalten zurück.

## <a name="to-close-the-message-box-leaving-the-selected-method-unchanged"></a>So schließen Sie das Meldungsfeld, ohne die ausgewählte Methode zu ändern

- Klicken Sie auf **keine**.

    Das Meldungsfeld wird geschlossen, und es werden keine Änderungen vorgenommen.

## <a name="see-also"></a>Siehe auch

- [O/R-Designer-Meldungen](../data-tools/o-r-designer-messages.md)
- [LINQ to SQL-Tools in Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)