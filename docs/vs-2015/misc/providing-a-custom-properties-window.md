---
title: Bereitstellen eines benutzerdefinierten Eigenschaftenfensters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- property browsers, providing
- Properties window, providing your own
ms.assetid: 408dcdef-8ef9-4644-97d2-f311cd35824f
caps.latest.revision: 12
manager: douge
ms.openlocfilehash: 88ba48a4cf04d0ad5efb59939c57f021926dfd2e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47510528"
---
# <a name="providing-a-custom-properties-window"></a>Bereitstellen eines benutzerdefinierten Eigenschaftenfensters
Es ist möglich, geben Sie Ihre eigenen **Eigenschaften** Fenster für eine bestimmte Projektsystem, anstatt zu erweitern die **Eigenschaften** Fenster durch die [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] integrierte Entwicklungsumgebung (IDE). Die häufigsten auftretenden Szenario ist selbst implementieren, dass das Objekt im Fensterrahmen positioniert.  
  
 Den Fall, dass Sie implementieren nicht das Objekt im Fensterrahmen positioniert, aber Sie müssen jedoch noch anderweitig Zugriff darauf, es gibt eine Reihe von Möglichkeiten, den Zugriff auf die <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> -Schnittstelle wie im letzten Verfahren auf dieser Seite aufgeführt.  
  
### <a name="to-provide-your-properties-window"></a>Bereitstellen Ihrer Fenster "Eigenschaften"  
  
1.  Definieren Sie eine GUID darstellt, die Ihre **Eigenschaften** Fenster-Implementierung.  
  
2.  In Ihrer <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> Implementierung verwenden die <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> aussprechen-Dienst Ihre **Eigenschaften** Fenster als Dienst in der Visual Studio-Umgebung.  
  
### <a name="to-call-your-properties-window"></a>Ihr Fenster "Eigenschaften" aufrufen  
  
1.  Rufen Sie die <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane.SetSite%2A>-Methode auf.  
  
2.  `QueryService` für <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx> aus der <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> übergeben die <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane.SetSite%2A> Methode.  
  
3.  Abrufen <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx> aus <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx> Service.  
  
4.  Rufen Sie <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx.OnElementValueChange%2A> mit dem ersten Parameter legen Sie auf `SEID_PropertyBrowserSID` (entnommen der <xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID> Enumeration), und der dritte Parameter `varValue`, eine Zeichenfolgendarstellung der GUID, die darstellt, das darstellt Ihre **Eigenschaften** Fenster. Stellen Sie diesen Aufruf nur einmal bei der ersten Erstellung Ihrer **Eigenschaften** Fenster Dokumentfenster. Nach dem Aufruf dieser **Eigenschaften** Fenster bezieht sich auf den Fensterrahmen.  
  
### <a name="to-obtain-the-window-frame-object-when-you-are-not-the-implementer"></a>Das Window Frame-Objekt abgerufen, wenn Sie nicht die Implementierung sind.  
  
-   Sie können `QueryService` für <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx> -Diensts von <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> mit dem Parameter `propid` festgelegt <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>.  
  
-   Sie erhalten das aktive Fenster durch Aufrufen von <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCurrentSelection%2A> über SVsMonitorSelection-Dienst. Legen Sie den Parameter `elementid` zu `SEID_WindowFrame`, die von der <xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID> Enumeration.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweitern von Eigenschaften](../extensibility/internals/extending-properties.md)   
 [Felder und Schnittstellen des Eigenschaftenfensters](../extensibility/internals/properties-window-fields-and-interfaces.md)