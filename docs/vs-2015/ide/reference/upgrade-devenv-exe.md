---
title: -Upgrade (devenv.exe) | Microsoft-Dokumentation
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
- /upgrade Devenv switch
- Devenv, /upgrade switch
- upgrade Devenv switch
ms.assetid: 3468045c-5cc9-4157-9a9d-622452145d27
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4dc3a9000056babd5a05577dfa95af42a824f538
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47509248"
---
# <a name="upgrade-devenvexe"></a>/Upgrade (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [-Upgrade (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/upgrade-devenv-exe).  
  
  
Aktualisiert die Projektmappendatei und alle zugehörigen Projektdateien bzw. die angegebene Projektdatei mit den aktuellen , für diese Dateien gültigen [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]-Formaten.  
  
## <a name="syntax"></a>Syntax  
  
```  
devenv SolutionFile | ProjectFile /upgrade  
```  
  
## <a name="arguments"></a>Argumente  
 `SolutionFile`  
 Dies ist erforderlich, sofern Sie eine vollständige Projektmappe und deren Projekte aktualisieren. Der Pfad und Name einer Projektmappendatei. Es reicht aus, nur den Namen der Projektmappendatei oder einen vollständigen Pfad und den Namen der Projektmappendatei einzugeben. Wenn der angegebene Ordner bzw. die Datei noch nicht vorhanden ist, wird der Ordner oder die Datei erstellt.  
  
 `ProjectFile`  
 Dies ist erforderlich, sofern Sie ein einzelnes Projekt aktualisieren. Der Pfad und der Name einer Projektdatei innerhalb der Projektmappe. Es reicht aus, nur den Namen der Projektdatei oder einen vollständigen Pfad und den Namen der Projektdatei einzugeben. Wenn der angegebene Ordner bzw. die Datei noch nicht vorhanden ist, wird der Ordner oder die Datei erstellt.  
  
## <a name="remarks"></a>Hinweise  
 Es werden automatisch Sicherungen und in ein Verzeichnis mit der Bezeichnung "Backup" kopiert, das im aktuellen Verzeichnis erstellt wurde.  
  
 Der Quellcodeverwaltung unterliegende Projektmappen oder Projekte müssen ausgecheckt werden, bevor sie aktualisiert werden können.  
  
 Bei Verwendung des Schalters `/upgrade` wird [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] nicht gestartet. Die Ergebnisse des Upgrades sind im Upgradebericht für die Entwicklungssprache der Projektmappe oder des Projekts aufgeführt. Informationen zu Fehlern oder zur Verwendung werden nicht zurückgegeben. Weitere Informationen zum Upgraden von Projekten in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], finden Sie unter [wie: Problembehandlung bei nicht erfolgreichen Visual Studio-Projektupgrades](../../porting/how-to-troubleshoot-unsuccessful-visual-studio-project-upgrades.md).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird eine Projektmappendatei mit dem Namen "MyProject.sln" im Standardordner für [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]-Projektmappen aktualisiert.  
  
```  
devenv "MyProject.sln" /upgrade  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Problembehandlung bei nicht erfolgreichen Visual Studio-Projektupgrades](../../porting/how-to-troubleshoot-unsuccessful-visual-studio-project-upgrades.md)   
 [Devenv-Befehlszeilenschalter](../../ide/reference/devenv-command-line-switches.md)



