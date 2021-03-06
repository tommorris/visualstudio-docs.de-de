---
title: IEnumCodePaths2 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IEnumCodePaths2
helpviewer_keywords:
- IEnumCodePaths2 interface
ms.assetid: 17ec9f9e-dc06-4532-b5db-da52efcc8630
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c8fb38da8a389b8331a04ce26eb6f6ee257cf700
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47514732"
---
# <a name="ienumcodepaths2"></a>IEnumCodePaths2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IEnumCodePaths2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumcodepaths2).  
  
Diese Schnittstelle stellt eine Liste der Codepfade.  
  
## <a name="syntax"></a>Syntax  
  
```  
IEnumCodePaths2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Die Debug-Engine (DE) implementiert diese Schnittstelle, um eine Liste von Codepfaden darstellen.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Rufen Sie [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md) dieser Schnittstelle abgerufen.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IEnumCodePaths2`.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Nächste](../../../extensibility/debugger/reference/ienumcodepaths2-next.md)|Ruft eine angegebene Anzahl von Codepfade in einer Enumerationsfolge ab.|  
|[Skip](../../../extensibility/debugger/reference/ienumcodepaths2-skip.md)|Überspringt eine angegebene Anzahl von Codepfade in einer Enumerationsfolge.|  
|[Reset](../../../extensibility/debugger/reference/ienumcodepaths2-reset.md)|Setzt eine Enumerationsfolge auf den Anfang zurück.|  
|[Clone](../../../extensibility/debugger/reference/ienumcodepaths2-clone.md)|Erstellt einen Enumerator, der den gleichen Enumerationszustand wie der aktuelle Enumerator enthält.|  
|[GetCount](../../../extensibility/debugger/reference/ienumcodepaths2-getcount.md)|Ruft die Anzahl der Codepfade in einen Enumerator ab.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Codepfad stellt eine Verzweigung Punkt oder einen Funktionsaufruf in einem Programm dar. Eine Liste der Codepfade stellt dar, den Pfad, über dem Ausführung des Codes stattgefunden hat.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Wichtige Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)

