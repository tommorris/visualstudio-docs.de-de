---
title: TemplateGroupID-Element (Visual Studio-Vorlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#TemplateGroupID
helpviewer_keywords:
- TemplateGroupID element [Visual Studio Templates]
- <TemplateGroupID> element [Visual Studio Templates]
ms.assetid: bce7b49a-90bc-4691-aff3-a87e209f6d83
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c7b86716e5aa68eddab8a0cf2df9fb77ea366f58
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47509861"
---
# <a name="templategroupid-element-visual-studio-templates"></a>TemplateGroupID-Element (Visual Studio-Vorlagen)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [TemplateGroupID-Element (Visual Studio-Vorlagen)](https://docs.microsoft.com/visualstudio/extensibility/templategroupid-element-visual-studio-templates).  
  
Gibt an, in welcher Art von Projekt eine Elementvorlage angezeigt wird. Dieses Element ist erheblich, wenn [ShowByDefault (Visual Studio-Vorlagen)](../extensibility/showbydefault-visual-studio-templates.md) nastaven NA hodnotu `false`. Wenn [ShowByDefault (Visual Studio-Vorlagen)](../extensibility/showbydefault-visual-studio-templates.md) nastaven NA hodnotu `true`, und klicken Sie dann eine Elementvorlage in allen Projekttypen verfügbar ist.  
  
 \<VSTemplate>  
 \<TemplateData>  
 \<TemplateGroupID >  
  
## <a name="syntax"></a>Syntax  
  
```  
<TemplateGroupID> ... </TemplateGroupID>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Kategorisiert die Vorlage und definiert, wie diese in den Dialogfeldern **Neues Projekt** oder **Neues Element hinzufügen** angezeigt wird.|  
  
## <a name="text-value"></a>Textwert  
 Ein Textwert ist erforderlich.  
  
 Der Text gibt einen Bezeichner für eine Kategorie von Elementvorlagen an.  
  
## <a name="remarks"></a>Hinweise  
 `TemplateGroupID` ist ein Element.  
  
 Der Wert des der `TemplateGroupID` Element dient zusammen mit der projektsystemregistrierung (HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\*\<Versionsnummer >* \Projects\\) Filterung von Vorlagen, die in angezeigt werden. die **neues Element hinzufügen** Dialogfeld.  
  
|Visual C++-Wert|Bedeutung|  
|------------------------|-------------|  
|VC-systemeigen|Für systemeigene Projekte verwendet. Auch die Standardeinstellung, wenn ein Projekttyp nicht bestimmt werden kann.|  
|VC-verwaltet|Für verwaltete Projekte (/clr) verwendet.|  
|VC-Windows|Für alle Projekte verwendet, die auf die Windows-Plattform abzielen (systemeigen/verwaltet/Speicher).|  
|WinRT-systemeigen-UAP|Für Windows 10-Store-Projekte verwendet.|  
|CodeSharing-systemeigen|Für freigegebene Elementprojekte verwendet.|  
|WinRT-systemeigen-6.3|Für Windows 8.1-Store-Projekte verwendet.|  
|WinRT-systemeigen-Phone-6.3|Für Windows Phone 8.1-Projekte verwendet.|  
|WinRT-systemeigen|Für Windows 8.0-Store-Projekte verwendet.|  
|VC-Android|Für Android-Projekte verwendet.|  
  
## <a name="see-also"></a>Siehe auch  
 [Schemareferenz zu Visual Studio-Vorlagen](../extensibility/visual-studio-template-schema-reference.md)   
 [Erstellen von Projekt- und Elementvorlagen](../ide/creating-project-and-item-templates.md)

