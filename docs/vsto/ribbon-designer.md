---
title: Multifunktionsleisten-Designer
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- Designer_Microsoft.VisualStudio.Tools.Office.Ribbon.Design.RibbonDesigner
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, about Ribbon Designer
- controls [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], controls
- customizing the Ribbon, about Ribbon Designer
- Ribbon [Office development in Visual Studio], visual designer
- customizing the Ribbon
- custom Ribbon
- designers [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], customizing
- Ribbon [Office development in Visual Studio], common tasks
- Ribbon Designer [Office development in Visual Studio]
- read-only properties
- Ribbon [Office development in Visual Studio], shortcut keys
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8cb8df33c89ce044572508918ba48edae2a6d75e
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693343"
---
# <a name="ribbon-designer"></a>Multifunktionsleisten-Designer
  Der Menüband-Designer ist ein visueller Entwurfzeichnungsbereich. Verwenden Sie die Menüband-Designer, um benutzerdefinierte Registerkarten, Gruppen und Steuerelemente des Menübands einer Microsoft Office-Anwendung hinzufügen.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
 Fügen Sie zum Öffnen des Menüband-Designers eine **Menüband (visueller Designer)** Element aus, um das Projekt. Anschließend können die Entwurftools für die folgenden Aufgaben verwendet werden:  
  
-   [Entwerfen des Menübandlayouts](#DesigningRibbonLayout)  
  
-   [Verarbeiten von Ereignissen und Festlegen von Steuerelementeigenschaften](#HandleEventsSetProperties)  
  
-   [Hinzufügen von Steuerelementen zur Backstage-Ansicht](#CustomizingMicrosoftOfficeButton)  
  
> [!NOTE]  
>  Einige Aufgaben können mit dem Menüband-Designer nicht ausgeführt werden. Weitere Informationen zu diesen Aufgaben und wie Sie sie ausführen können, finden Sie unter [Übersicht über das Menüband](../vsto/ribbon-overview.md).  
  
 ![Link zu Video](../vsto/media/playvideo.gif "Link zu Video") eine entsprechende Videodemo finden Sie unter [How do I: mithilfe des Menüband-Designers zum Anpassen des Menübands in Outlook?](http://go.microsoft.com/fwlink/?LinkID=130312).  
  
## <a name="add-a-ribbon-visual-designer-item-to-a-project"></a>Fügen Sie ein Element "Menüband (visueller Designer)" zu einem Projekt  
 Um die Menüband-Designer zu verwenden, fügen Sie einen neuen **Menüband (visueller Designer)** Element aus, um das Projekt. Weitere Informationen finden Sie unter [wie: Erste Schritte beim Anpassen des Menübands](../vsto/how-to-get-started-customizing-the-ribbon.md).  
  
 Beim Hinzufügen einer neuen **Menüband (visueller Designer)** item, Visual Studio automatisch die folgenden Dateien Ihrem Projekt hinzugefügt:  
  
-   Eine Menüband-Codedatei. Diese Datei hat den Namen, den Sie, für angeben die **Menüband (visueller Designer)** Element in der **neues Element hinzufügen** (Dialogfeld). Fügen Sie dieser Datei zum Behandeln der Menübandereignisse Code hinzu.  
  
-   Eine Codedatei des Menüband-Designers. Diese Datei beinhaltet vom Menüband-Designer generierten Code und sollte nicht direkt bearbeitet werden.  
  
-   Eine Ressourcendatei. Diese Datei enthält die Eigenschaftswerte jedes Steuerelements auf dem Menüband.  
  
 Falls Sie noch eine **Menüband (visueller Designer)** Element aus einem anderen Projekt können Sie diesen wiederverwenden in Ihrem aktuellen Projekt mithilfe der **vorhandenes Element hinzufügen** (Dialogfeld).  
  
##  <a name="DesigningRibbonLayout"></a> Entwerfen eines Menübands  
 Zum Öffnen des Menüband-Designers stehen drei Möglichkeiten zur Verfügung:  
  
-   In **Projektmappen-Explorer**, doppelklicken Sie auf die Menüband-Codedatei.  
  
-   In **Projektmappen-Explorer**mit der rechten Maustaste auf die Menüband-Codedatei, und klicken Sie dann auf **Sicht-Designer**.  
  
-   In **Projektmappen-Explorer**, wählen Sie die Menüband-Codedatei, und klicken Sie dann auf **Designer** auf die **Ansicht** Menü.  
  
 Der Menüband-Designer beinhaltet eine Standardregisterkarte und -gruppe. Standardregisterkarte und -gruppe können aus dem Menüband-Designer entfernt werden. Zum Entfernen der Standardgruppe Maustaste **Group1**, und klicken Sie dann auf **löschen**. Klicken Sie zum Entfernen der Standardregisterkarte mit der rechten Maustaste in eines leeren Bereichs der Entwurfsoberfläche, und klicken Sie dann auf **Registerkarte für Menüband entfernen**.  
  
 Dem Menüband-Designer können auch benutzerdefinierte Registerkarten, Gruppen und Steuerelemente hinzugefügt werden. Diese Steuerelemente befinden sich in der **Toolbox**in der **Steuerelemente für Office-Menübänder** Gruppe. Es gibt drei Möglichkeiten zum Hinzufügen von Steuerelementen aus dem **Steuerelemente für Office-Menübänder** Gruppe auf dem Menüband-Designer:  
  
-   Ein Steuerelement in einen geeigneten Bereich im Menüband-Designer ziehen.  
  
-   Auf ein Steuerelement und anschließend in einen geeigneten Bereich im Menüband-Designer klicken.  
  
-   Wählen Sie einen geeigneten Bereich im Designer, und doppelklicken Sie dann auf ein Steuerelement in der **Toolbox**.  
  
### <a name="ribbon-design-workflow"></a>Menüband-entwurfworkflow  
 Führen Sie folgende grundlegende Schritte zum Entwerfen des Menübandlayouts aus:  
  
1.  [Hinzufügen eine benutzerdefinierte Registerkarte zum Menüband](#AddTabToRibbon).  
  
2.  [Hinzufügen von Gruppen zur Registerkarte ""](#AddGroupsToTab).  
  
3.  [Hinzufügen von Steuerelementen zu Gruppen](#AddControlsToGroups).  
  
 Steuerelemente können nur auf Gruppen abgelegt werden; Sie können kein Steuerelement ziehen, direkt zu einer Registerkarte oder das Menüband. Gruppen können nur auf Registerkarten abgelegt werden; das Ziehen einer Gruppe direkt auf ein Menüband ist nicht möglich.  
  
 Ordnen Sie Steuerelemente durch Ziehen zu den korrekten Positionen an. Sie können die Eigenschaften eines Steuerelements festlegen, mit der **Eigenschaften** Fenster.  
  
 Steuerelemente kann nicht auf dem Menüband nicht von einer Registerkarte zur anderen gezogen werden. Wenn ein Steuerelement zu einer anderen Registerkarte verschoben werden sollen, müssen Sie verwenden die **Ausschneiden** Befehl aus, um das Steuerelement von einer Registerkarte zu entfernen, und fügen das Steuerelement auf einer anderen Registerkarte. Wird das Steuerelement ausgeschnitten und eingefügt, wird der Ereignishandler angehalten. Können Sie die Verbindung wiederherstellen des Ereignishandler in der **Eigenschaften** Fenster. Weitere Informationen finden Sie unter [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).  
  
###  <a name="AddTabToRibbon"></a> Fügen Sie benutzerdefinierter Registerkarten zum Menüband hinzu  
 Es gibt drei Möglichkeiten zum Hinzufügen einer benutzerdefinierten Registerkarte zum Menüband:  
  
-   Hinzufügen einer Registerkarte aus der **Toolbox**.  
  
-   Mit der rechten Maustaste in der Menüband-Designer, und klicken Sie dann auf **Registerkarte für Menüband hinzufügen**.  
  
-   Öffnen der **Registerkartenauflistungs-Editor**, und klicken Sie dann auf **hinzufügen**.  
  
     Zu öffnen die **Registerkartenauflistungs-Editor**in der **Eigenschaften** wählen die **Registerkarten** -Eigenschaft, und klicken Sie dann auf die Schaltfläche mit den Auslassungspunkten ![ASP.NET Mobile Designer Ellipse](../sharepoint/media/mwellipsis.gif "ASP.NET Mobile-Designer Ellipse").  
  
 Nach dem Hinzufügen einer Registerkarte können Gruppen mit Steuerelementen hinzugefügt werden.  
  
#### <a name="remove-custom-tabs-from-the-ribbon"></a>Entfernen von benutzerdefinierten Registerkarten vom Menüband  
 Es gibt drei Möglichkeiten zum Entfernen einer benutzerdefinierten Registerkarte vom Menüband aus:  
  
-   Mit der rechten Maustaste in des Designers, und klicken Sie dann auf **Registerkarte für Menüband entfernen**.  
  
-   In der **Befehle** im Bereich der **Eigenschaften** Fenster, klicken Sie auf **Registerkarte für Menüband entfernen**.  
  
-   Öffnen der **Registerkartenauflistungs-Editor**, wählen Sie die Registerkarte, und klicken Sie dann auf **entfernen**.  
  
#### <a name="change-the-position-of-a-tab-on-the-ribbon"></a>Ändern der Position einer Registerkarte auf dem Menüband  
 Sie können die Reihenfolge von benutzerdefinierten Registerkarten auf einem Menüband ändern. Sie können auch benutzerdefinierte Registerkarten vor oder nach einer integrierten Registerkarte auf dem Menüband positionieren. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern der Position einer Registerkarte auf dem Menüband](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md).  
  
#### <a name="customize-built-in-tabs-on-the-ribbon"></a>Anpassen der integrierten Registerkarten auf dem Menüband  
 Eine integrierte Registerkarte ist eine Registerkarte, die bereits auf dem Menüband einer Microsoft Office-Anwendung befindet. Z. B. die **Daten** Registerkarte ist eine integrierte Registerkarte in Excel.  
  
 Einer integrierten Registerkarte können Gruppen und Steuerelemente hinzugefügt werden. Standardmäßig wird eine benutzerdefinierte Gruppe als letzte Gruppe auf einer integrierten Registerkarte angezeigt, obwohl sie vor oder hinter eine integrierte Gruppe auf der Registerkarte verschoben werden kann.  
  
 Integrierte Gruppen können nicht entfernt werden.  
  
 Ausführliche Informationen zum Anpassen einer integrierten Registerkarte finden Sie unter [wie: Anpassen einer integrierten Registerkarte](../vsto/how-to-customize-a-built-in-tab.md).  
  
###  <a name="AddGroupsToTab"></a> Hinzufügen von Gruppen zu einer Registerkarte  
 Steuerelemente auf dem Menüband werden mithilfe von Gruppen logisch organisiert. Fügen Sie Registerkarten Gruppen hinzu. Fügen Sie der Gruppe alle anderen Steuerelemente hinzu.  
  
###  <a name="AddControlsToGroups"></a> Hinzufügen von Steuerelementen zu Gruppen  
 Fügen Sie einer Gruppe mindestens ein Steuerelement hinzu. In der folgenden Tabelle wird jedes Steuerelement beschrieben.  
  
|Steuerelement|Beschreibung|  
|-------------|-----------------|  
|**Kontrollkästchen**|Ein Container, der Steuerelemente in einer Gruppe organisiert. Einem Feld kann mit Ausnahme von Trennzeichen, Gruppen oder Registerkarten jedes beliebige Steuerelement hinzugefügt werden. Ein Feld kann horizontal oder vertikal dargestellt werden.|  
|**Button** (Schaltfläche)|Eine Schaltfläche, durch die eine Aktion gestartet wird. Sie können einer Gruppe, einer Schaltflächengruppe, einer Dropdownliste, einem Katalog, einem Menü oder einer Trennschaltfläche eine Schaltfläche hinzufügen.|  
|**Schaltflächengruppe**|Eine Gruppe, die mindestens eine Schaltfläche, eine Umschaltfläche, ein Menü, eine Trennschaltfläche und einen Katalog beinhaltet. Einer Gruppe oder einem Menü kann eine Schaltflächengruppe oder eine Gruppe hinzugefügt werden.|  
|**CheckBox**|Ein Feld, das zum Aktivieren oder Deaktivieren einer Option aktiviert oder deaktiviert ist.|  
|**ComboBox**|Ein Bearbeitungsfeld mit einem angehängten Listenfeld. Benutzer können ihre Auswahl entweder eingeben oder auswählen. Im Feld wird die aktuelle Auswahl angezeigt. Verwenden der <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.Items%2A> Eigenschaft hinzufügen und Entfernen von Elementen zur Laufzeit vor oder nach dem Laden des Menübands in die Office-Anwendung.|  
|**Dropdownliste**|Eine Liste der Elemente, die von Benutzern ausgewählt werden können. In eine Dropdownliste kann kein neues Element eingegeben werden.<br /><br /> Fügen Sie der Liste mithilfe der <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.Items%2A>-Eigenschaft Elemente hinzu. Sie können hinzufügen und Entfernen von Elementen zur Laufzeit.<br /><br /> Fügen Sie der Liste mithilfe der <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.Buttons%2A>-Eigenschaft Schaltflächen hinzu. Sie können nicht jedoch hinzufügen und Entfernen von Schaltflächen zur Laufzeit nach dem Laden des Menübands in die Office-Anwendung.|  
|**Bearbeitungsfeld**|Ein Feld, in das der Benutzer Text eingeben kann.|  
|**Katalog**|Ein Menü mit einem visuellen Auswahlarray oder -raster, in dem Benutzer eine Auswahl treffen können. Das Layout der Auswahl im Menü kann gesteuert werden. Verwenden Sie die <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ColumnCount%2A>-Eigenschaft und die <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.RowCount%2A>-Eigenschaft, um die Anzahl der Zeilen und Spalten anzugeben, in denen die Elemente und Schaltflächen des Katalogs angezeigt werden.|  
|**Bezeichnung**|Text, die Sie verwenden können, um Steuerelemente auf dem Menüband zu identifizieren.|  
|**Menü**|Eine Dropdownliste, die sämtliche der folgenden Steuerelemente beinhalten kann:<br /><br /> -Schaltfläche<br />-Kontrollkästchen<br />-Katalog<br />-Menü<br />-Unterteilte Schaltfläche<br />-Ein/aus Schaltfläche<br />-Trennzeichen<br /><br /> Wenn Sie einem Menü im Menüband-Designer ein Steuerelement hinzufügen möchten, klicken Sie im Menü auf den Pfeil nach unten, um die Menüentwurfsoberfläche anzuzeigen. Sie können Menübandsteuerelemente von der **Toolbox** Menü gezogen. Ordnen Sie Steuerelemente durch Ziehen zu den gewünschten Positionen an.<br /><br /> Zum Hinzufügen von Steuerelementen an die <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu> nach dem Laden des Menübands in die Office-Anwendung ist, müssen Sie festlegen der <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu.Dynamic%2A> Eigenschaft, um **"true"** vor dem Laden des Menübands. Informationen hierzu finden Sie unter [Multifunktionsleisten-objektmodellübersicht](../vsto/ribbon-object-model-overview.md).|  
|**Trennzeichen**|Eine dünne Leiste zum Trennen von Elementen in einer Liste. Beim Hinzufügen zu einer Gruppe ist die Leiste vertikal. Beim Hinzufügen zu einem Menü ist die Leiste horizontal.|  
|**"SplitButton"**|Eine Schaltfläche mit einem angehängten Menü. Eine Trennschaltfläche kann jedes der folgenden Steuerelemente beinhalten:<br /><br /> -Schaltfläche<br />-Kontrollkästchen<br />-Katalog<br />-Menü<br />-Unterteilte Schaltfläche<br />-Ein/aus Schaltfläche<br />-Trennzeichen<br /><br /> Ebenso wie das Menü verfügt die Trennschaltfläche über eine eigene Entwurfsoberfläche. Allerdings können im Gegensatz zu einem Menü Sie nur aktualisieren die Elemente auf einer Trennschaltfläche vor dem Laden des Menübands in die Office-Anwendung. Informationen zum Aktualisieren der Elemente auf einer Trennschaltfläche finden Sie unter [Multifunktionsleisten-objektmodellübersicht](../vsto/ribbon-object-model-overview.md).|  
|**ToggleButton**|Eine Schaltfläche, die gedrückt oder nicht gedrückt angezeigt wird.|  
  
##  <a name="HandleEventsSetProperties"></a> Behandeln von Ereignissen und Festlegen von Eigenschaften  
 Menüband-Designer können Sie Steuerelementeigenschaften zur Entwurfszeit festlegen, indem die **Eigenschaften** Fenster. Darüber hinaus macht das Menüband ein stark typisiertes Objektmodell, das Sie zum Abrufen und Festlegen der Eigenschaften von Menübandsteuerelementen zur Laufzeit verwenden können.  
  
 Sie können auf jedes Steuerelement im Designer doppelklicken, um einen Ereignishandler für das Standardereignis des Steuerelements zu öffnen. Sie können Ereignishandler für alle anderen Steuerelementereignisse erstellen, mit der **Eigenschaften** Fenster.  
  
 Menübandereignisse befinden sich im <xref:Microsoft.Office.Tools.Ribbon>-Namespace. Die **Menüband (visueller Designer)** Element fügt automatisch einen Verweis auf diese Assembly im Projekt und fügt die entsprechende **mit** oder **Importe** -Anweisung am Anfang der Menüband-Codedatei.  
  
 Informationen zum Behandeln von Menübandereignissen und zum Festlegen der Eigenschaften von Menübandsteuerelementen zur Laufzeit finden Sie unter [Multifunktionsleisten-objektmodellübersicht](../vsto/ribbon-object-model-overview.md).  
  
##  <a name="CustomizingMicrosoftOfficeButton"></a> Anpassen der Backstage-Ansicht  
 Können Sie dem Menüband-Designer zum Hinzufügen von Steuerelementen zum Menü, das geöffnet wird, wenn Sie auf die **Datei** Registerkarte. Mit diesem Menü wird die Backstage-Ansicht aufgerufen.  
  
 Sie können mit dem Menüband-Designer keine Steuerelemente vor oder nach integrierten Steuerelementen positionieren. Ein integriertes Steuerelement ist ein Steuerelement, das bereits in der Backstage-Ansicht angezeigt wird. Wenn Sie Steuerelemente vor oder nach integrierten Steuerelementen positionieren möchten, müssen Sie ein Menüband-XML verwenden. Weitere Informationen zu **Menüband (XML)**, finden Sie unter [Menüband-XML-](../vsto/ribbon-xml.md). Weitere Informationen zum Anpassen der Backstage-Ansicht finden Sie unter [Einführung in die Office 2010-Backstage-Ansicht für Entwickler](http://go.microsoft.com/fwlink/?LinkId=182189) und [anpassen die Office 2010-Backstage-Ansicht für Entwickler](http://go.microsoft.com/fwlink/?LinkId=182188).  
  
 [!INCLUDE[appliesto_ribbon_2010](../vsto/includes/appliesto-ribbon-2010-md.md)]  
  
 Informationen zur Vorgehensweise beim Hinzufügen von Steuerelementen zur Backstage-Ansicht finden Sie unter [wie: Hinzufügen von Steuerelementen zur Backstage-Ansicht](../vsto/how-to-add-controls-to-the-backstage-view.md).  
  
##  <a name="Accessibility"></a> Barrierefreiheit im Menüband-Designer  
 Steuerelemente auf dem Menüband-Designer können mithilfe von Tastenkombinationen verschoben werden. Einige Tastenkombinationen gelten für alle Steuerelemente, wohingegen einige Tastenkombinationen nur für Steuerelemente mit Menüs verwendbar sind.  
  
 Die für alle Steuerelemente verwendbaren Tastenkombinationen werden in der folgenden Tabelle angezeigt.  
  
|Aktion|Tastenkombination|  
|------------|-----------------------|  
|Verschieben eines Steuerelements vor das vorherige Steuerelement in der Liste.|**STRG**+**einrichten**<br /><br /> **STRG**+**links**|  
|Verschieben eines Steuerelements hinter das nächste Steuerelement in der Liste.|**STRG**+**nach unten**<br /><br /> **STRG**+**rechts**|  
|Verschieben der Auswahl von einem Steuerelement zu einem anderen Steuerelement in derselben Gruppe. Wechseln Sie in einem Dropdownbereich zwischen dem übergeordneten Steuerelement und den Steuerelementen im Dropdownbereich.|**nach-oben**<br /><br /> **Nach-unten**|  
|Durchlaufen aller Steuerelemente (vorwärts).|**TAB**|  
|Durchlaufen aller Steuerelemente (rückwärts).|**UMSCHALT**+**Tab**|  
|Löschen des ausgewählten Steuerelements oder eines Satzes von Steuerelementen.|**Löschen**|  
|Kopieren der ausgewählten Steuerelemente.|**STRG**+**C**|  
|Ausschneiden der ausgewählten Steuerelemente.|**STRG**+**X**|  
|Einfügen von Steuerelementen aus der Zwischenablage.|**STRG**+**V**|  
|Wählen Sie die **Toolbox**.|**STRG**+**Alt**+**X**|  
|Auswählen der übergeordneten Komponente.|**ESC**|  
  
 Die Tastenkombinationen gelten nur für das Microsoft Office-Menü; <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu> und <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton> werden in der folgenden Tabelle angezeigt.  
  
|Aktion|Tastenkombination|  
|------------|-----------------------|  
|Auswählen des übergeordneten Steuerelements, falls der Dropdownbereich geöffnet ist und im Dropdownbereich ein Steuerelement ausgewählt ist.|**Links**|  
|Schließen des Dropdownbereichs, falls der Dropdownbereich geöffnet ist und das übergeordnete Steuerelement ausgewählt ist.|**Links**|  
|Öffnen des Dropdownbereichs.|**Rechts**|  
|Auswählen des ersten Steuerelements im Dropdownbereich, falls der Dropdownbereich geöffnet ist.|**Rechts**|  
|Schließen eines Dropdownbereichs.|**ESC**|  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das Menüband](../vsto/ribbon-overview.md)   
 [Menüband-XML](../vsto/ribbon-xml.md)   
 [Exemplarische Vorgehensweise: Erstellen einer benutzerdefinierten Registerkarte mit Menüband-Designer](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Vorgehensweise: Exportieren eines Menübands vom Menüband-Designer in Menüband-XML](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [Vorgehensweise: Erste Schritte beim Anpassen des Menübands](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [Zugriff auf die Multifunktionsleiste zur Laufzeit](../vsto/accessing-the-ribbon-at-run-time.md)  
  
  