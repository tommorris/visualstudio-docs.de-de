---
title: 'Exemplarische Vorgehensweise: Zugreifen auf das DTE-Objekt aus einer Editor-Erweiterung | Microsoft-Dokumentation'
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
- editors [Visual Studio SDK], new - getting the DTE object
ms.assetid: c1f40bab-c6ec-45b0-8333-ea5ceb02a39d
caps.latest.revision: 23
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 91d1683b6c2743df2f04d6462ae0a57ec7b0aff4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47515491"
---
# <a name="walkthrough-accessing-the-dte-object-from-an-editor-extension"></a>Exemplarische Vorgehensweise: Zugreifen auf das DTE-Objekt über eine Editor-Erweiterung
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das DTE-Objekt aus einer Editor-Erweiterung](https://docs.microsoft.com/visualstudio/extensibility/walkthrough-accessing-the-dte-object-from-an-editor-extension).  
  
In VSPackages, erhalten Sie das DTE-Objekt durch Aufrufen der <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> Methode mit dem Typ des DTE-Objekt. In Erweiterungen des Managed Extensibility Framework (MEF), können Sie importieren <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> und rufen Sie dann die <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A> Methode mit dem Typ <xref:EnvDTE.DTE>.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Um diese exemplarische Vorgehensweise befolgen zu können, müssen Sie das Visual Studio SDK installieren. Weitere Informationen finden Sie unter [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="getting-the-dte-object"></a>Abrufen des DTE-Objekts  
  
#### <a name="to-get-the-dte-object-from-the-serviceprovider"></a>Um das DTE-Objekt über den ServiceProvider zu erhalten.  
  
1.  Erstellen Sie ein C#-VSIX-Projekt mit dem Namen `DTETest`. Hinzufügen einer Elementvorlage-Editor-Klassifizierung aus, und nennen Sie sie `DTETest`. Weitere Informationen finden Sie unter [Erstellen einer Erweiterung mit einer Editor-Elementvorlage](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
2.  Fügen Sie dem Projekt die folgenden Assemblyverweise hinzu:  
  
    -   EnvDTE  
  
    -   EnvDTE80  
  
    -   Microsoft.VisualStudio.Shell.Immutable.10.0  
  
3.  Wechseln Sie zur DTETest.cs, und fügen Sie die folgenden `using` Anweisungen:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    using Microsoft.VisualStudio.Shell;  
  
    ```  
  
4.  In der `GetDTEProvider` Klasse, importieren Sie eine <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider>.  
  
    ```csharp  
    [Import]  
    internal SVsServiceProvider ServiceProvider = null;  
  
    ```  
  
5.  Fügen Sie folgenden Code in die `GetClassifier()`-Methode ein.  
  
    ```csharp  
    DTE dte = (DTE)ServiceProvider.GetService(typeof(DTE));  
  
    ```  
  
6.  Wenn Sie verwenden die <xref:EnvDTE80.DTE2> -Schnittstelle können Sie das DTE-Objekt, umgewandelt.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterungspunkte für den Sprachdienst und den Editor](../extensibility/language-service-and-editor-extension-points.md)

