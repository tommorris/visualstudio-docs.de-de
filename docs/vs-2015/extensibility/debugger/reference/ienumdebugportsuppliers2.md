---
title: IEnumDebugPortSuppliers2 | Microsoft-Dokumentation
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
- IEnumDebugPortSuppliers2
helpviewer_keywords:
- IEnumDebugPortSuppliers2
ms.assetid: cd0a73dc-dd25-46fd-8c4f-5b011501afeb
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c85119dc705ee171979467c453b771e3cea65237
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47523773"
---
# <a name="ienumdebugportsuppliers2"></a>IEnumDebugPortSuppliers2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IEnumDebugPortSuppliers2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugportsuppliers2).  
  
Diese Schnittstelle listet Portanbieter.  
  
## <a name="syntax"></a>Syntax  
  
```  
IEnumDebugPortSuppliers2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Visual Studio implementiert diese Schnittstelle, um eine Liste der Portanbieter darstellen.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Rufen Sie [EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md) zum Abrufen einer Liste von Portanbieter.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IEnumDebugPortSuppliers2`.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Nächste](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-next.md)|Ruft eine angegebene Anzahl von Portanbieter in einer Enumerationsfolge ab.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-skip.md)|Überspringt eine angegebene Anzahl von Portanbieter in einer Enumerationsfolge.|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-reset.md)|Setzt eine Enumerationsfolge auf den Anfang zurück.|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-clone.md)|Erstellt einen Enumerator, der den gleichen Enumerationszustand wie der aktuelle Enumerator enthält.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-getcount.md)|Ruft die Anzahl der Portanbieter in einen Enumerator ab.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Debug-Engine muss zum Abrufen dieser Schnittstelle in der Regel nicht.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Wichtige Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md)

