---
title: Filtern des AddItem-Dialogfelds für geschachtelte Projekte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- filtering, nested projects
- nested projects, AddItem dialog box filtering
ms.assetid: 5b3e352e-7f18-4f66-be16-b0ad55637ce5
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c007a2aa0895460f539acb50f49844f8ec158fa7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47520323"
---
# <a name="filtering-the-additem-dialog-box-for-nested-projects"></a>Filtern des AddItem-Dialogfelds für geschachtelte Projekte
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Filtern des AddItem-Dialogfelds für geschachtelte Projekte](https://docs.microsoft.com/visualstudio/extensibility/internals/filtering-the-additem-dialog-box-for-nested-projects).  
  
Beim Anzeigen einer **AddItem** eines geschachtelten Projekts, das übergeordnete Projekt im Dialogfeld kann steuern, welche Elemente im Dialogfeld angezeigt werden.  
  
 Die <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2> Schnittstelle können Sie die Knoten zu filtern, die in einer **AddItem** Dialogfeld. Wenn das untergeordnete Projekt angezeigt wird, die **AddItem** kann implementieren, klicken Sie im Dialogfeld das übergeordnete Element der `IVsFilterAddProjectItemDlg` -Schnittstelle und Filtern von Elementen, die andernfalls in des untergeordneten Standortes Projekt angezeigt werden.  
  
 Wenn Sie Projekte nach ihrer Funktion unter bestimmten übergeordneten Projekte gruppiert sind, können Sie implementieren `IVsFilterAddProjectItemDlg` Wenn der Benutzer auswählt **Projektelemente hinzufügen** im Kontextmenü in einem geschachtelten Projekt. Implementieren von `IvsFilterAddProjectItemDlg displays` nur Projekt Elemente oder speziell für diese Gruppe von Dateien. Projektelemente für andere Gruppen werden aus dem Dialogfeld gefiltert, auch wenn sie im gleichen Verzeichnis gespeichert werden.  
  
 Wenn ein Benutzer öffnet die **AddItem** im Dialogfeld für das untergeordnete Element des übergeordneten Projekts Implementierung der `IVsFilterAddProjectItemDlg` Schnittstelle aufgerufen wird.  
  
 Die `IVsFilterAddProjectItemDlg` Schnittstelle können Sie auch implementieren nach Kategorie filtern. Weitere Informationen finden Sie unter [Elemente hinzufügen, um das Hinzufügen neuer Dialogfelder](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md) und [Registrieren von Projekt- und Elementvorlagen](../../extensibility/internals/registering-project-and-item-templates.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [Hinzufügen von Elementen, das Hinzufügen neuer Elemente in Dialogfeldern](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [Registrieren von Projekt- und Elementvorlagen](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Schachteln von Projekten](../../extensibility/internals/nesting-projects.md)

