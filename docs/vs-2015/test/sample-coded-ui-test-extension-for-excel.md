---
title: Sample Coded UI Test Extension for Excel (Beispielerweiterungen für programmierte UI-Test für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- coded UI tests, extensions for Excel
ms.assetid: 451e4d14-7fac-42f9-af56-2bdc8414c6c7
caps.latest.revision: 15
ms.author: gewarren
manager: douge
ms.openlocfilehash: b4da574b77d8dd2b1b14ccb0b04e449799338620
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47524113"
---
# <a name="sample-coded-ui-test-extension-for-excel"></a>Beispielerweiterung für Tests der programmierten Benutzeroberfläche für Excel
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Beispiel Coded UI-Testerweiterung für Excel](https://docs.microsoft.com/visualstudio/test/sample-coded-ui-test-extension-for-excel).  
  
Die Erweiterungskomponente des Beispiels wird im [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]Visual Studio.programmierten UI-Testprozess durchgeführt und ist in einer hierarchischen Beziehung mit der `ExtensionPackage`-Klasse an der Basis. Die `TechnologyManager`-, `ActionFilter`- und `PropertyProvider`-Klassen sind auf der nächsten Ebene, mit den Steuerelementen auf der obersten Ebene.  
  
 ![Testerweiterungsarchitektur für Excel](../test/media/excel-extarch.png "Excel_ExtArch")  
Erweiterungsarchitektur für Excel  
  
## <a name="extension-points"></a>Erweiterungspunkte  
 Diese Klassen stellen die Erweiterungspunkte dar, die in der Stichprobe implementiert werden, um programmierte UI-Tests für [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] zu aktivieren.  
  
### <a name="extensionpackage"></a>ExtensionPackage  
 Von der <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>-Klasse geerbt. Dies ist der Einstiegspunkt für die Erweiterung für den Test der programmierten UI. Durch die Implementierung dieser abstrakten Klasse erhält das Framework für programmierte UI-Tests internen Zugriff auf Ihren benutzerdefinierten UI-Test-Technologie-Manager, UI-Test-Eigenschaftenanbieter und UI-Test-Aktionsfilter für das Testen der neuen UI. Weitere Informationen finden Sie unter [ExtensionPackage-Klasse](../test/sample-excel-extension-extensionpackage-class.md).  
  
### <a name="technologymanager"></a>TechnologyManager  
 Von der <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager>-Klasse geerbt. Diese Klasse stellt einen Technologie-Manager für die Testaufzeichnung und -wiedergabe bereit. Weitere Informationen finden Sie unter [TechnologyManager-Klasse](../test/sample-excel-extension-technologymanager-class.md).  
  
### <a name="actionfilter"></a>ActionFilter  
 Von der <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>-Klasse geerbt. Diese Klasse stellt eine Basisklasse für das Aggregieren ähnlicher Testaktionsergebnisse in ein einziges Testergebnis bereit. Weitere Informationen finden Sie unter [ActionFilter-Klasse](../test/sample-excel-extension-actionfilter-class.md).  
  
### <a name="technology-elements"></a>Technologieelemente  
 Eine von der <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>-Klasse geerbte Basisklasse stellt die Grundlage für die Technologieelemente Ihrer UI-Tests bereit, die aufgezeichnet und wiedergegeben werden können. Weitere Informationen finden Sie unter [Elementklassen](../test/sample-excel-extension-element-classes.md).  
  
### <a name="propertyprovider"></a>PropertyProvider  
 Von der <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>-Klasse geerbt. Diese Klasse stellt eine Basisklasse für die Unterstützung der Eigenschaften von UI-Elementen für die Aufzeichnung und Wiedergabe der Tests bereit. Weitere Informationen finden Sie unter [PropertyProvider-Klasse](../test/sample-excel-extension-propertyprovider-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>   
 [ExtensionPackage-Klasse](../test/sample-excel-extension-extensionpackage-class.md)   
 [TechnologyManager-Klasse](../test/sample-excel-extension-technologymanager-class.md)   
 [ActionFilter-Klasse](../test/sample-excel-extension-actionfilter-class.md)   
 [Elementklasse](../test/sample-excel-extension-element-classes.md)   
 [PropertyProvider-Klasse](../test/sample-excel-extension-propertyprovider-class.md)



