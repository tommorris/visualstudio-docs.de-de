---
title: -Deploy („devenv.exe“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Devenv, /deploy switch
- deploy Devenv switch
- deploying applications [Visual Studio], after build
- /deploy Devenv switch
ms.assetid: e47c8723-df08-4645-aa2d-0c956e7ccca2
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e4bed834524c159d42b2193857c805fab7628fe0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47510151"
---
# <a name="deploy-devenvexe"></a>/Deploy (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [-Bereitstellung (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/deploy-devenv-exe).  
  
  
Stellt eine Projektmappe nach einer Erstellung oder Neuerstellung bereit. Gilt nur für Projekte mit verwaltetem Code.  
  
## <a name="syntax"></a>Syntax  
  
```  
devenv SolutionName /deploy SolnConfigName [/project ProjName] [/projectconfig ProjConfigName] [/out LogFileName]  
```  
  
## <a name="arguments"></a>Argumente  
 `SolnConfigName`  
 Erforderlich. Der Name der Projektmappenkonfiguration, die für das Erstellen der Projektmappe verwendet wird, die in `SolutionName` benannt wurde  
  
 `SolutionName`  
 Erforderlich. Der vollständige Pfad und Name der Projektmappendatei  
  
 /project `ProjName`  
 Dies ist optional. Der Pfad und der Name einer Projektdatei innerhalb der Projektmappe. Sie können einen relativen Pfad vom `SolutionName`-Ordner zur Projektdatei, dem Anzeigenamen des Projekts oder dem vollständigen Pfad und Namen der Projektdatei eingeben.  
  
 /projectconfig `ProjConfigName`  
 Dies ist optional. Der Name der Projektbuildkonfiguration für die Erstellung des benannten `/project`.  
  
## <a name="remarks"></a>Hinweise  
 Das angegebene Projekt muss ein Bereitstellungsprojekt sein. Wenn das angegebene Projekt kein Bereitstellungsprojekt ist und das erstellte Projekt zur Bereitstellung übergeben wird, schlägt der Vorgang mit einer Fehlermeldung fehl.  
  
 Schließen Sie Zeichenfolgen, die Leerzeichen enthalten, in doppelten Anführungszeichen ein.  
  
 Zusammenfassende Informationen für Builds, inklusive Fehlermeldungen, können im Fenster **Befehl** oder in einer Protokolldatei, die durch den Schalter `/out` angegeben wird, angezeigt werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel stellt das Projekt `CSharpConsoleApp` mithilfe der Projektbuildkonfiguration `Release` in der Projektmappenkonfiguration `Release` von `MySolution` bereit.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /deploy Release /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Release   
```  
  
## <a name="see-also"></a>Siehe auch  
 [Devenv-Befehlszeilenschalter](../../ide/reference/devenv-command-line-switches.md)   
 [/Project („devenv.exe“)](../../ide/reference/project-devenv-exe.md)   
 [/Build („devenv.exe“)](../../ide/reference/build-devenv-exe.md)   
 [/Clean („devenv.exe“)](../../ide/reference/clean-devenv-exe.md)   
 [/Rebuild („devenv.exe“)](../../ide/reference/rebuild-devenv-exe.md)   
 [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)



