---
title: PropertyGroup-Element (MSBuild) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#PropertyGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <PropertyGroup> element [MSBuild]
- PropertyGroup element [MSBuild]
ms.assetid: ff1e6c68-b9a1-4263-a1ce-dc3b829a64d4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e8c532692b7faddd90a3a67ffdd52b512511d719
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2018
ms.locfileid: "39152187"
---
# <a name="propertygroup-element-msbuild"></a>PropertyGroup-Element (MSBuild)
Enthält eine Reihe von benutzerdefinierten [Eigenschaft](../msbuild/property-element-msbuild.md)-Elementen. Jedes `Property`-Element, das in einem [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]-Projekt verwendet wird, muss ein untergeordnetes Element eines `PropertyGroup`-Elements sein.  

 \<Project>  
 \<PropertyGroup>  

## <a name="syntax"></a>Syntax  

```xml  
<PropertyGroup Condition="'String A' == 'String B'">  
    <Property1>...</Property1>  
    <Property2>...</Property2>  
</PropertyGroup>  
```  

## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  

### <a name="attributes"></a>Attribute  

|Attribut|Beschreibung |  
|---------------|-----------------|  
|Bedingung|Optionales Attribut.<br /><br /> Die auszuwertende Bedingung. Weitere Informationen finden Sie unter [Conditions](../msbuild/msbuild-conditions.md) (MSBuild-Bedingungen).|  

### <a name="child-elements"></a>Untergeordnete Elemente  

|Element|Beschreibung |  
|-------------|-----------------|  
|[Eigenschaft](../msbuild/property-element-msbuild.md)|Optionales Element.<br /><br /> Ein benutzerdefinierter Eigenschaftenname, der den Wert der Eigenschaft enthält. Es kann kein oder mehrere *Eigenschafts*-Elemente in einem `PropertyGroup`-Element geben.|  

### <a name="parent-elements"></a>Übergeordnete Elemente  

|Element|Beschreibung |  
|-------------|-----------------|  
|[Projekt](../msbuild/project-element-msbuild.md)|Erforderliches Stammelement einer [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] -Projektdatei.|  

## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Einstellung von Eigenschaften auf der Grundlage einer Bedingung veranschaulicht. Wenn der Wert der `CompileConfig`-Eigenschaft in diesem Beispiel `DEBUG`, `Optimization`, `Obfuscate` ist und `OutputPath`-Eigenschaften im `PropertyGroup`-Element festgelegt sind.  

```xml  
<PropertyGroup Condition="'$(CompileConfig)' == 'DEBUG'" >  
    <Optimization>false</Optimization>  
    <Obfuscate>false</Obfuscate>  
    <OutputPath>$(OutputPath)\debug</OutputPath>  
</PropertyGroup>  
```  

## <a name="see-also"></a>Siehe auch  
 [Referenz zum Projektdateischema](../msbuild/msbuild-project-file-schema-reference.md)  
 [MSBuild-Eigenschaften](../msbuild/msbuild-properties.md)
