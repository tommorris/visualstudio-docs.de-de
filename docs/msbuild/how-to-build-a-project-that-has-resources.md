---
title: 'Vorgehensweise: Erstellen eines Projekts, das über Ressourcen verfügt | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- resource files, compiling with MSBuild
- resources [Visual Studio], compiling with MSBuild
- projects [.NET Framework], building
- MSBuild, building a project with resources
ms.assetid: d07ac73f-2c2d-4e9a-812a-6dcb632bafe2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e7724969a4677bc0d8480b794ae72b2dbee74a86
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2018
ms.locfileid: "39180346"
---
# <a name="how-to-build-a-project-that-has-resources"></a>Vorgehensweise: Erstellen eines Projekts, das über Ressourcen verfügt
Wenn Sie lokalisierte Versionen eines Projekts erstellen, müssen alle Benutzeroberflächenelemente in Ressourcendateien für die verschiedenen Sprachen eingeteilt werden. Wenn das Projekt nur Zeichenfolgen verwendet, können die Ressourcendateien Textdateien verwenden. Alternativ können Sie *RESX*-Dateien als Ressourcendateien verwenden.  
  
## <a name="compile-resources-with-msbuild"></a>Kompilieren von Ressourcen mit MSBuild  
 Die Bibliothek von allgemeinen Aufgaben, die mit [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] bereitgestellt wird, enthält eine `GenerateResource`-Aufgabe, die Sie zum Kompilieren von Ressourcen in *RESX*- oder Textdateien verwenden können. Diese Aufgabe umfasst den Parameter `Sources`, um anzugeben, welche Ressourcendateien zu kompilieren sind, und den Parameter `OutputResources`, um Namen für die Ausgabe der Ressourcendateien anzugeben. Weitere Informationen zu der `GenerateResource`-Aufgabe finden Sie unter [GenerateResource-Aufgabe](../msbuild/generateresource-task.md).  
  
#### <a name="to-compile-resources-with-msbuild"></a>So kompilieren Sie Ressourcen mit MSBuild  
  
1.  Identifizieren Sie die Ressourcendateien des Projekts und übergeben Sie sie entweder als Elementlisten oder als Dateinamen an die `GenerateResource`-Aufgabe.  
  
2.  Geben Sie den Parameter `OutputResources` der Aufgabe `GenerateResource` an, was Ihnen ermöglicht die Namen für die Ausgabenressourcendateien festzulegen.  
  
3.  Verwenden Sie zum Speichern des Werts des Parameters `OutputResources` in einem Element das Element `Output` der Aufgabe.  
  
4.  Verwenden Sie das Element, das aus dem Element `Output` erstellt wurde, als Ausgabe in eine andere Aufgabe.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird gezeigt, wie das Element `Output` angibt, dass das Attribut `OutputResources` der Aufgabe `GenerateResource` die kompilierten Ressourcendateien *alpha.resources* und *beta.resources* enthält und dass diese zwei Dateien in die Elementliste `Resources` gelegt werden. Indem Sie diese *RESOURCES*-Dateien als eine Sammlung von Elementen mit gleichem Namen identifizieren, können Sie sie einfach als Eingabe für eine andere Aufgabe wie die [Csc](../msbuild/csc-task.md)-Aufgabe verwenden.  
  
 Diese Aufgabe entspricht der Verwendung des **/compile**-Schalters für [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator):  
  
 `Resgen.exe /compile alpha.resx,alpha.resources /compile beta.txt,beta.resources`  
  
```xml  
<GenerateResource  
    Sources="alpha.resx; beta.txt"  
    OutputResources="alpha.resources; beta.resources">  
    <Output TaskParameter="OutputResources"  
        ItemName="Resources"/>  
</GenerateResource>  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispielprojekt enthält zwei Aufgaben: die Aufgabe `GenerateResource` zur Kompilierung von Ressourcen und die Aufgabe `Csc` zum Kompilieren von Quellcodedateien und kompilierten Ressourcendateien. Die von der Aufgabe `GenerateResource` kompilierten Ressourcendateien sind im Element `Resources` gespeichert und werde an die Aufgabe `Csc` geleitet.  
  
```xml  
<Project DefaultTargets = "Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <Target Name="Resources">  
        <GenerateResource  
            Sources="alpha.resx; beta.txt"  
            OutputResources="alpha.resources; beta.resources">  
            <Output TaskParameter="OutputResources"  
                ItemName="Resources"/>  
        </GenerateResource>  
    </Target>  
  
    <Target Name="Build" DependsOnTargets="Resources">  
        <Csc Sources="hello.cs"  
                Resources="@(Resources)"  
                OutputAssembly="hello.exe"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Siehe auch  
[MSBuild](../msbuild/msbuild.md)  
 [GenerateResource-Aufgabe](../msbuild/generateresource-task.md)   
 [Csc-Aufgabe](../msbuild/csc-task.md)   
 [Resgen.exe (Resource File Generator)](/dotnet/framework/tools/resgen-exe-resource-file-generator)