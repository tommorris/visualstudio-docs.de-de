---
title: 'Gewusst wie: Einrichten von Konfigurationsinformationen für eine Office-Projektmappe'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], configuration files
- configuration files [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 87f50856439158d6d931b519fb35e98970ef7d58
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "35671913"
---
# <a name="how-to-set-up-configuration-information-for-an-office-solution"></a>Gewusst wie: Einrichten von Konfigurationsinformationen für eine Office-Projektmappe
  Sie können Konfigurationsdateien verwenden, um Einstellungen zu konfigurieren, die spezifisch für Ihre Office-Projektmappen sind. Sie können Einstellungen wie z. B. assemblybindungsrichtlinien, Remotingobjekte, Debug und Trace-Einstellungen angeben.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-configuration-file-to-your-office-project"></a>Um eine Konfigurationsdatei auf dem Office-Projekt hinzufügen  
  
1.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
2.  In der **Kategorien** Bereich, klicken Sie auf **allgemeine**.  
  
3.  In der **Vorlagen** wählen Sie im Bereich **Anwendungskonfigurationsdatei**.  
  
4.  In der **Namen** geben den gleichen Namen der Assembly mit der Erweiterung *config*. Beispielsweise eine Konfigurationsdatei für eine Assembly der Excel-Projekt namens *ExcelWorkbook1.dll* hieße *ExcelWorkbook1.dll.config*.  
  
5.  Klicken Sie auf **Hinzufügen**.  
  
6.  Erstellen Sie die Konfigurationsdatei entsprechend der Anwendung Konfigurationsdateischema. Weitere Informationen finden Sie unter [Konfigurationsdateischema für .NET Framework](/dotnet/framework/configure-apps/file-schema/index).  
  
 Es gibt keine besonderen Überlegungen für die Verwendung von Konfigurationsdateien mit Office-Projekten.  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurationsdateischema für .NET Framework](/dotnet/framework/configure-apps/file-schema/index)   
 [Entwerfen und Erstellen von Office-Projektmappen](../vsto/designing-and-creating-office-solutions.md)   
 [Bereitstellen einer Office-Projektmappe](../vsto/deploying-an-office-solution.md)  
  
  