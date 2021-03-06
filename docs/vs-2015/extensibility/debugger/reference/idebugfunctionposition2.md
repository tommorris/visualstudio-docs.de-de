---
title: IDebugFunctionPosition2 | Microsoft-Dokumentation
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
- IDebugFunctionPosition2
helpviewer_keywords:
- IDebugFunctionPosition2 interface
ms.assetid: a835f65b-91b0-48ad-8485-04534c814b1b
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 65726f1f2f05a459c07687e2a77f9db0dcb0b45a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47513403"
---
# <a name="idebugfunctionposition2"></a>IDebugFunctionPosition2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IDebugFunctionPosition2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfunctionposition2).  
  
Diese Schnittstelle stellt eine abstrakte Position einer Funktion in einem Quelldokument.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDebugFunctionPosition2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Die Debug-Engine (DE) implementiert diese Schnittstelle, um die Position einer Funktion in einem Quelldokument darstellen.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Diese Schnittstelle wird als Teil des angegeben ein [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) Union (insbesondere ein [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md) Struktur), die wiederum stammt von der [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) -Struktur, in das Erstellen eines ausstehenden Haltepunkts verwendet.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IDebugFunctionPosition2`.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetFunctionName](../../../extensibility/debugger/reference/idebugfunctionposition2-getfunctionname.md)|Ruft den Namen der Funktion, der diese Position relativ ist.|  
|[GetOffset](../../../extensibility/debugger/reference/idebugfunctionposition2-getoffset.md)|Ruft den Offset vom Anfang der Funktion ab.|  
  
## <a name="remarks"></a>Hinweise  
 Die Position, die von dieser Schnittstelle dargestellt ist textbasiert, insbesondere eine [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) Struktur.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Wichtige Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)   
 [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)

