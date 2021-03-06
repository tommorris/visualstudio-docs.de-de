---
title: Bereitstellen von Projekttypen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4bed37260925d4961ed5b5b7d3e69d55169444ad
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2018
ms.locfileid: "39497900"
---
# <a name="deploy-project-types"></a>Bereitstellen von Projekttypen
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] installiert einen neuen Projekttyp Aggregator (*ProjectAggregator2.dll*) und auch ein Windows Installer-Paket für die weiterverteilung (*ProjectAggregator2.msi*). Sie müssen den neuen Aggregator für Projekttypen von verwaltetem Code verwenden. ProjectAggregator2 umgeht Einschränkungen in der [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Projekt Aggregator, der verhindert, dass Projekttypen von verwaltetem Code ordnungsgemäß funktioniert. Die folgenden Schritte beschreiben, wie Sie Ihr VSPackage für die Verwendung des neuen Aggregators zu ändern.  
  
1.  Entfernen Sie das Projekt NativeHierarchyWrapper aus der Projektmappe.  
  
2.  Entfernen Sie alle NativeHierarchyWrapper-Binärdateien aus dem Setup.  
  
3.  Hinzufügen *ProjectAggregator2.msi* auf Ihr Setup.