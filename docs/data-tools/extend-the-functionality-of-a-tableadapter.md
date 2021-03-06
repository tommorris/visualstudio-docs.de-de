---
title: Erweitern der Funktionalität eines TableAdapter
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- data [Visual Studio], extending TableAdapters
- TableAdapters, adding functionality
ms.assetid: 418249c8-c7f3-47ef-a94c-744cb6fe6aaf
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 9b5884ff140097010c90fbf2208fecd95980f2fe
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
ms.locfileid: "31924448"
---
# <a name="extend-the-functionality-of-a-tableadapter"></a>Erweitern der Funktionalität eines TableAdapter
Sie können die Funktionalität eines TableAdapter erweitern, indem partiellen Klassendatei des TableAdapter Code hinzugefügt.

 Der Code, der einen TableAdapter definiert erneut generiert, wenn alle Änderungen an den TableAdapter im vorgenommen werden die **Dataset-Designer**, oder wenn ein Assistent ändert die Konfiguration eines TableAdapter. Um zu verhindern, dass Ihr Code während der erneuten Generierung eines TableAdapter gelöscht wird, fügen Sie Code TableAdapters partiellen Klassendatei ein.

 Partielle Klassen können Sie Code für eine bestimmte Klasse auf mehrere physische Dateien unterteilt werden. Weitere Informationen finden Sie unter [partielle](/dotnet/visual-basic/language-reference/modifiers/partial) oder [Partial (Typ)](/dotnet/csharp/language-reference/keywords/partial-type).

## <a name="locate-tableadapters-in-code"></a>TableAdapters im Code suchen
 Während TableAdapters mit vorgesehen sind die **Dataset-Designer**, die TableAdapter-Klassen, die generiert werden, sind nicht geschachtelten Klassen von <xref:System.Data.DataSet>. TableAdapters befinden sich in einem Namespace, die basierend auf den Namen des dem TableAdapter zugeordneten Datasets. Wenn Ihre Anwendung ein Dataset Namens enthält z. B. `HRDataSet`, befindet sich die TableAdapters in die `HRDataSetTableAdapters` Namespace. (Die Benennungskonvention folgt diesem Muster: *DatasetName* + `TableAdapters`).

 Im folgende Beispiel wird davon ausgegangen, einen TableAdapter namens `CustomersTableAdapter`befindet sich in einem Projekt mit `NorthwindDataSet`.

#### <a name="to-create-a-partial-class-for-a-tableadapter"></a>So erstellen eine partielle Klasse für einen TableAdapter

1.  Fügen Sie eine neue Klasse zu Ihrem Projekt durch das Aufrufen der **Projekt** Menü- und Auswählen von **Klasse hinzufügen**.

2.  Nennen Sie die Klasse `CustomersTableAdapterExtended`.

3.  Wählen Sie **hinzufügen**.

4.  Ersetzen Sie den Code mit den richtigen Namespace und den Namen der partiellen Klasse für das Projekt wie folgt:

     [!code-csharp[VbRaddataTableAdapters#2](../data-tools/codesnippet/CSharp/extend-the-functionality-of-a-tableadapter_1.cs)]
     [!code-vb[VbRaddataTableAdapters#2](../data-tools/codesnippet/VisualBasic/extend-the-functionality-of-a-tableadapter_1.vb)]

## <a name="see-also"></a>Siehe auch

- [Füllen von Datasets mit TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md)