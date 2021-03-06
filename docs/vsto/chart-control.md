---
title: Chart-Steuerelement
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.ProjectItem.ExcelChart
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Chart control [Office development in Visual Studio], events
- Chart control [Office development in Visual Studio]
- Chart control [Office development in Visual Studio], data binding
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b1adf0d961489b09a9dc01775148636e6d2d231a
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34267729"
---
# <a name="chart-control"></a>Chart-Steuerelement
  Das <xref:Microsoft.Office.Tools.Excel.Chart>-Steuerelement ist ein Diagrammobjekt, das Ereignisse verfügbar macht. Beim Hinzufügen eines Diagramms zu einem Arbeitsblatt erstellt Visual Studio ein <xref:Microsoft.Office.Tools.Excel.Chart>-Objekt, für das Sie direkt programmieren können, ohne das Objektmodell von Microsoft Office Excel zu durchlaufen.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="create-the-control"></a>Erstellen des Steuerelements  
 Sie können hinzufügen <xref:Microsoft.Office.Tools.Excel.Chart> Steuerelementen zu einem Microsoft Office Excel-Arbeitsblatt zur Entwurfszeit oder zur Laufzeit in einem Projekt auf Dokumentebene.  
  
 Sie können hinzufügen <xref:Microsoft.Office.Tools.Excel.Chart> Steuerelementen zu einem Arbeitsblatt zur Laufzeit in einem VSTO-Add-in. Weitere Informationen finden Sie unter [wie: Hinzufügen von Chart-Steuerelementen an Arbeitsblätter](../vsto/how-to-add-chart-controls-to-worksheets.md).  
  
> [!NOTE]  
>  Dynamisch erstellte Diagrammobjekte werden nicht im Arbeitsblatt als Hoststeuerelemente dauerhaft gespeichert, wenn das Arbeitsblatt geschlossen wird. Weitere Informationen finden Sie unter [Hinzufügen von Steuerelementen zu Office-Dokumenten zur Laufzeit](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
## <a name="formatting"></a>Formatierung  
 Die gesamte Formatierung, die auf <xref:Microsoft.Office.Interop.Excel.Chart> angewendet werden kann, ist auch auf ein <xref:Microsoft.Office.Tools.Excel.Chart>-Steuerelement anwendbar. Dies umfasst Rahmen, Schriftarten, Diagrammtypen, Gitternetzlinien, Legenden und Datenbezeichnungen.  
  
## <a name="events"></a>Ereignisse  
 Die folgenden Ereignisse sind für das <xref:Microsoft.Office.Tools.Excel.Chart>-Steuerelement verfügbar:  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.ActivateEvent>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.Calculate>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.Deactivate>  
  
-   <xref:System.ComponentModel.Component.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.DragOver>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.DragPlot>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.MouseDown>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.MouseMove>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.MouseUp>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.Resize>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.SelectEvent>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.SeriesChange>  
  
## <a name="see-also"></a>Siehe auch  
 [Office-Entwicklungsbeispiele und exemplarische Vorgehensweisen](../vsto/office-development-samples-and-walkthroughs.md)   
 [Erweitern von Word-Dokumenten und Excel-Arbeitsmappen in VSTO-Add-ins zur Laufzeit](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Steuerelemente für Office-Dokumente](../vsto/controls-on-office-documents.md)   
 [Hinzufügen von Steuerelementen zu Office-Dokumenten zur Laufzeit](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Automatisieren von Excel mithilfe von erweiterten Objekten](../vsto/automating-excel-by-using-extended-objects.md)   
 [Vorgehensweise: Hinzufügen von Diagrammsteuerelementen zu Arbeitsblättern](../vsto/how-to-add-chart-controls-to-worksheets.md)   
 [Binden von Daten an Steuerelemente in Office-Projektmappen](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Programmgesteuerte Einschränkungen von Hostelementen und Hoststeuerelementen](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  