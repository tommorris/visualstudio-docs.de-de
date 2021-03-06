---
title: RequiredPlatformVersion-Element (Visual Studio-Vorlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f0e4986-3157-4bba-aed3-c28413ebe976
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5fb35bfefeb7722c3ec488a1f9caf63cd49202dd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47515582"
---
# <a name="requiredplatformversion-element-visual-studio-templates"></a>RequiredPlatformVersion-Element (Visual Studio-Vorlagen)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [RequiredPlatformVersion-Element (Visual Studio-Vorlagen)](https://docs.microsoft.com/visualstudio/extensibility/requiredplatformversion-element-visual-studio-templates).  
  
Gibt die Mindestversion des Betriebssystems an, die vorliegen muss, damit die Projektvorlage ordnungsgemäß funktioniert. Dieses Element wird für Projektvorlagen verwendet, die [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)]-Apps erstellen.  
  
 Der Wert `RequiredPlatformVersion` wird unmittelbar mit der Version des Betriebssystems verglichen. Wenn die `RequiredPlatformVersion` ist höher als die Version des Betriebssystems, die Vorlage wird nicht angezeigt, der **neues Projekt** Dialogfeld. Um eine Vorlage für [!INCLUDE[win8](../includes/win8-md.md)] oder höher anzugeben, legen Sie `RequiredPlatformVersion` auf 6.2.0 fest. Um eine Vorlage für [!INCLUDE[win81](../includes/win81-md.md)] oder höher anzugeben, legen Sie "RequiredPlatformVersion" auf 6.3.0 fest.  
  
 Vorlagen, die `RequiredPlatformVersion`=8 angeben, sind mit früheren [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)]-Kundenvorlagen kompatibel.  
  
 VSTemplate  
TemplateData  
... TargetPlatformName  
RequiredPlatformVersion  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<RequiredPlatformVersion> OperatingSystem </RequiredPlatformVersion>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 Keine  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[TemplatePlatformName](../extensibility/templatedata-element-visual-studio-templates.md)|Gibt die Plattform an, auf die die Projektvorlage abzielt.|  
  
## <a name="text-value"></a>Textwert  
 Ein Textwert ist erforderlich.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Text gibt die Mindestversion des Betriebssystems an, die für die Vorlage erforderlich ist.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird angegeben, dass die Projektvorlage auf [!INCLUDE[win8](../includes/win8-md.md)] oder höher abzielt.  
  
```xml  
<VSTemplate Type="Project" Version="3.0.0"    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <TargetPlatformName>Windows</TargetPlatformName>  
            <RequiredPlatformVersion>6.3.0</RequiredPlatformVersion>  
  
    </TemplateData>  
    <TemplateContent>  
  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [TargetPlatformName-Element (Visual Studio-Vorlagen)](../extensibility/targetplatformname-element-visual-studio-templates.md)   
 [Erstellen von Projekt- und Elementvorlagen](../ide/creating-project-and-item-templates.md)   
 [Schemareferenz zu Visual Studio-Vorlagen](../extensibility/visual-studio-template-schema-reference.md)

