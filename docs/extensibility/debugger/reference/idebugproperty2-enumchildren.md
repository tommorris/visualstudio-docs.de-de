---
title: IDebugProperty2::EnumChildren | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProperty2::EnumChildren
helpviewer_keywords:
- IDebugProperty2::EnumChildren
ms.assetid: cf79f666-65d1-417c-af7c-9271bac9a267
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9631ee89dc9d241932b745db4ce094799a899bad
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
ms.locfileid: "31122209"
---
# <a name="idebugproperty2enumchildren"></a>IDebugProperty2::EnumChildren
Ruft eine Liste der untergeordneten Elemente der Eigenschaft ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumChildren (   
   DEBUGPROP_INFO_FLAGS      dwFields,  
   DWORD                     dwRadix,  
   REFGUID                   guidFilter,  
   DBG_ATTRIB_FLAGS          dwAttribFilter,  
   LPCOLESTR                 pszNameFilter,  
   DWORD                     dwTimeout,  
   IEnumDebugPropertyInfo2** ppEnum  
);  
```  
  
```csharp  
int EnumChildren (   
   enum_DEBUGPROP_INFO_FLAGS   dwFields,  
   uint                        dwRadix,  
   ref Guid                    guidFilter,  
   uint                        dwAttribFilter,  
   string                      pszNameFilter,  
   uint                        dwTimeout,  
   out IEnumDebugPropertyInfo2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwFields`  
 [in] Eine Kombination aus Flags aus der [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) Enumeration, der angibt, welche Felder in den aufgelisteten [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) Strukturen sind ausgefüllt werden.  
  
 `dwRadix`  
 [in] Gibt die Wurzel an eine beliebige numerische Formatierungsinformationen verwendet werden.  
  
 `guidFilter`  
 [in] GUID des Filters verwendet wird, mit der `dwAttribFilter` und `pszNameFilter` Parameter auswählen, welche `DEBUG_PROPERTY_INFO` untergeordneten Elemente sind, aufgelistet werden sollen. Beispielsweise `guidFilterLocals` Filter für lokale Variablen.  
  
 `dwAttribFilter`  
 [in] Eine Kombination aus Flags aus der [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) Enumeration, der angibt, welche Art von Objekten zum Aufzählen, z. B. `DBG_ATTRIB_METHOD` für alle Methoden, die untergeordneten Elemente dieser Eigenschaft möglicherweise. Verwendet in Kombination mit der `guidFilter` und `pszNameFilter` Parameter.  
  
 `pszNameFilter`  
 [in] Der Name des Filters verwendet wird, mit der `guidFilter` und `dwAttribFilter` Parameter auswählen, welche `DEBUG_PROPERTY_INFO` untergeordneten Elemente sind, aufgelistet werden sollen. Dieser Parameter z. B. festlegen "MyX" Filter, für alle untergeordneten Elemente mit dem Namen "MyX."  
  
 `dwTimeout`  
 [in] Gibt die maximale Zeit in Millisekunden, bis vor der Rückgabe dieser Methode. Verwendung `INFINITE` zum unendlichen Warten angibt.  
  
 `ppEnum`  
 [out] Gibt eine [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) Objekt, das eine Liste der untergeordneten Eigenschaften enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `S_OK`; andernfalls wird Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)   
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)