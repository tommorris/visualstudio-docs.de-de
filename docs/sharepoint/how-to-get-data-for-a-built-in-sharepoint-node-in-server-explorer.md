---
title: 'Vorgehensweise: Abrufen von Daten für einen integrierten SharePoint-Knoten im Server-Explorer | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint Connections [SharePoint development in Visual Studio], extending a node
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 06965449cd07fb39480eb1974fc1c90e2d126c73
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37119188"
---
# <a name="how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer"></a>Gewusst wie: Abrufen von Daten für einen integrierten SharePoint-Knoten im Server-Explorer
  Für jeden integrierten SharePoint-Knoten im **Server-Explorer**, Sie können Daten abrufen, für die zugrunde liegende SharePoint-Komponente, die vom Knoten dargestellt. Weitere Informationen finden Sie unter [Erweitern des SharePoint-Verbindungsknotens im Server-Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Abrufen von Daten für die zugrunde liegende SharePoint-Liste, die in ein Listenknoten darstellt **Server-Explorer**. Standardmäßig die Liste mit den Knoten haben eine **in Browser anzeigen** Kontextmenüelement, die Sie klicken können, um die Listen in einem Webbrowser zu öffnen. Dieses Beispiel erweitert eine Liste mit den Knoten durch das Hinzufügen einer **in Visual Studio anzeigen** Kontextmenüelement, die die Listen direkt in Visual Studio geöffnet wird. Der Code greift auf die Listendaten für den Knoten aus, um die URL der Liste, die in Visual Studio öffnen abzurufen.  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#10](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorerextensionnodeinfo.vb#10)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#10](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorerextensionnodeinfo.cs#10)]  
  
 Dieses Beispiel verwendet die SharePoint-Projektdiensts zum Abrufen der <xref:EnvDTE.DTE> -Objekt, das verwendet wird, öffnen Sie in Visual Studio aufgeführt. Weitere Informationen zu SharePoint-Projektdiensts, finden Sie unter [verwenden SharePoint-Projektdiensts](../sharepoint/using-the-sharepoint-project-service.md).  
  
 Weitere Informationen zu den grundlegenden Aufgaben zum Erstellen einer Erweiterung für eine SharePoint-Knoten, finden Sie unter [Vorgehensweise: Erweitern eines SharePoint-Knotens im Server-Explorer](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md).  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Verweise auf die folgenden Assemblys:  
  
-   EnvDTE  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   Microsoft.VisualStudio.SharePoint.Explorer.Extensions  
  
-   System.ComponentModel.Composition  
  
## <a name="deploy-the-extension"></a>Bereitstellen der Erweiterung  
 Zum Bereitstellen der **Server-Explorer** -Erweiterung erstellen Sie eine [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] -Erweiterung (VSIX) Verpacken, für die Assembly und alle anderen Dateien, die Sie mit der Erweiterung verteilen möchten. Weitere Informationen finden Sie unter [Bereitstellen von Erweiterungen für SharePoint-Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Siehe auch
 [Erweitern des SharePoint-Verbindungsknotens im Server-Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [Gewusst wie: Erweitern eines SharePoint-Knotens im Server-Explorer](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)   
 [Verwenden Sie die SharePoint-Projektdiensts](../sharepoint/using-the-sharepoint-project-service.md)   
 [Bereitstellen von Erweiterungen für SharePoint-Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
