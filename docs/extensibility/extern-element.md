---
title: Extern-Element | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- Extern
helpviewer_keywords:
- VSCT XML schema elements, Extern
- Extern element (VSCT XML schema)
ms.assetid: db6c3ddd-a1ba-450a-897a-bb568a5377fc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 353d7e59d7f9d0cbc6aa93d4118a4cb8ff6ee197
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2018
ms.locfileid: "39497705"
---
# <a name="extern-element"></a>Extern-element
Das Element "extern" verweist auf alle externen Header (*h*)-Dateien zum Zusammenführen mit der *VSCT* Datei zum Zeitpunkt der Kompilierung. Die Dateien, die zusammengeführt werden muss auf dem Include-Pfad, dem VSCT-Compiler zugewiesen oder mithilfe einer ["Include"-Element](../extensibility/include-element.md). Die Dateien sind möglicherweise andere *VSCT* Dateien oder C++-Headerdateien.  
  
 Definitionen in Headerdateien muss im Format "#define [Symbol] [Wert]" der Wert kann ein anderes Symbol sein, wenn sie zuvor definiert wird. Definitionen können in bedingten Anweisungen der Befehl-Elemente verwendet werden. Jedes Symbol nicht verwendet werden verworfen.  
  
 CommandTable-Element  
Extern-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<Extern href="stdidcmd.h" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|href|Erforderlich. Der Pfad zur Headerdatei:<br /><br /> href="stdidcmd.h"|  
|Bedingung|Dies ist optional. Finden Sie unter [bedingte Attribute](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
|language|Dies ist optional. Die Standardsprache für alle [ \<Zeichenfolgen >](../extensibility/strings-element.md) Elemente in der Befehlstabelle:<br /><br /> Language = "En-us"|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|Keine|Keine|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[CommandTable-element](../extensibility/commandtable-element.md)|Definiert alle Elemente, die Befehle darstellen, d. h. Menüelemente, Menüs, Symbolleisten und Kombinationsfeldern –, die eine VSPackage für die IDE bietet.|  
  
## <a name="example"></a>Beispiel  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-  
  18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <Extern href="C:\VSCore\vscommon\inc\vsshlids.h"/>  
    ...  
  <Commands package="guidMyPackage">  
</CommandTable>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Studio-Befehlstabellen (VSCT)-Befehlsdateien](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [Wie VSPackages Benutzeroberflächenelemente hinzufügen](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Befehle, Menüs und Symbolleisten](../extensibility/internals/commands-menus-and-toolbars.md)