---
title: XmlMappedRange-Steuerelement
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLMappedRange control, data binding
- XMLMappedRange control
- XMLMappedRange control, events
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9cf21ceda64fe79996e05426a3379972c3c4be33
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "35673049"
---
# <a name="xmlmappedrange-control"></a>XmlMappedRange-Steuerelement
  Die <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> -Steuerelement ist ein Bereich, der erstellt wird, nur, wenn ein nicht wiederholendes Schemaelement einer Zelle in Microsoft Office Excel zugeordnet ist. Z. B., wenn die `maxOccurs` Attribut eines Schemaelements gleich 1. Nachdem Visual Studio den zugeordneten XML-Bereich erstellt wurde, können Sie dafür programmieren, direkt ohne das Objektmodell von Excel zu durchlaufen. Sie können nur löschen, eine <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> Steuerelement innerhalb von Excel aus, wenn die elementzuordnung entfernt wird.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 ![Link zum Video](../vsto/media/playvideo.gif "Link zum Video") eine entsprechende Videodemo finden Sie unter [wie I: Verwenden Sie XML-Zuordnung in Excel vornehmen?](http://go.microsoft.com/fwlink/?LinkID=130288).  
  
## <a name="bind-data-to-the-control"></a>Binden von Daten an das Steuerelement  
 Ein <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> Steuerelement unterstützt die Bindung an ein einzelnes Datenfeld (einfache Datenbindung). Die <xref:Microsoft.Office.Tools.Excel.ListObject> Steuerelement kann komplexe Datenbindung unterstützt und wird automatisch erstellt werden, wenn ein sich wiederholendes Schemaelement einer Zelle zugeordnet ist. Weitere Informationen finden Sie unter [ListObject-Steuerelement](../vsto/listobject-control.md).  
  
 Die <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> -Steuerelement gebunden ist, einer Datenquelle mithilfe der <xref:System.Windows.Forms.Control.DataBindings%2A> Eigenschaft. Wenn ein <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> wird auf eine Zelle eines Arbeitsblatts, Visual Studio generiert automatisch ein Dataset aus den Daten in den zugeordneten Zellen und bindet das Steuerelement an das Dataset hinzugefügt. Die Standard-Datenbindungseigenschaft von der <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> ist <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Value2%2A>.  
  
 Wenn die Daten im gebundenen Dataset auf beliebige Weise aktualisiert werden die <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> -Steuerelement die Änderungen wider.  
  
## <a name="formatting"></a>Formatierung  
 Sie können die Formatierung auf Anwenden eine <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> -Steuerelement, das Sie zuweisen können eine <xref:Microsoft.Office.Interop.Excel.Range>. Dies umfasst, Rahmen, Schriftarten, Zahlenformate und Stile.  
  
## <a name="events"></a>Ereignisse  
 Die Ereignisse, die für die <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> sind:  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Change>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Selected>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Deselected>  
  
-   <xref:System.ComponentModel.Component.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.SelectionChange>  
  
## <a name="see-also"></a>Siehe auch  
 [Automatisieren von Excel mithilfe von erweiterten Objekten](../vsto/automating-excel-by-using-extended-objects.md)   
 [Gewusst wie: Hinzufügen von XMLMappedRange-Steuerelementen zu Arbeitsblättern](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)   
 [Binden von Daten an Steuerelemente in Office-Projektmappen](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Gewusst wie: Zuordnen von Schemas zu Arbeitsblättern in Visual Studio](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)   
 [Einschränkungen für programmgesteuerte Aufgaben von Hostelementen und Hoststeuerelementen](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  