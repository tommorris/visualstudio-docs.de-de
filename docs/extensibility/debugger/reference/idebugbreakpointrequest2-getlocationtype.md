---
title: IDebugBreakpointRequest2::GetLocationType | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugBreakpointRequest2::GetLocationType
helpviewer_keywords:
- IDebugBreakpointRequest2::GetLocationType
ms.assetid: b6d14c59-d3aa-48ff-8278-f6b5bba9c2f3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: faa536c269e8c0ebd2772617ab9bd0e3412f35b2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
ms.locfileid: "31106177"
---
# <a name="idebugbreakpointrequest2getlocationtype"></a>IDebugBreakpointRequest2::GetLocationType
Ruft den Haltepunkt adressenart dieser Haltepunkt-Anforderung ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetLocationType(   
   BP_LOCATION_TYPE* pBPLocationType  
);  
```  
  
```csharp  
int GetLocationType(   
   out enum_BP_LOCATION_TYPE pBPLocationType  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pBPLocationType`  
 [out] Gibt einen Wert aus der [BP_LOCATION_TYPE](../../../extensibility/debugger/reference/bp-location-type.md) -Enumeration, der den Speicherort dieser Anforderung Breakpoint beschreibt.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `S_OK`ist, andernfalls wird ein Fehlercode zurückgegeben. Gibt `E_FAIL` Wenn die `bpLocation` im zugeordneten Feld [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) Struktur ist nicht gültig.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie diese Methode für eine einfache implementiert `CDebugBreakpointRequest` -Objekt, das macht die[IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md) Schnittstelle.  
  
```  
HRESULT CDebugBreakpointRequest::GetLocationType(BP_LOCATION_TYPE* pBPLocationType)    
{    
   HRESULT hr;    
  
   if (pBPLocationType)    
   {    
      // Set default BP_LOCATION_TYPE.    
      *pBPLocationType = BPLT_NONE;    
  
      // Check if the BPREQI_BPLOCATION flag is set in BPREQI_FIELDS.    
      if (IsFlagSet(m_bpRequestInfo.dwFields, BPREQI_BPLOCATION))    
      {    
         // Get the new BP_LOCATION_TYPE.    
         *pBPLocationType = m_bpRequestInfo.bpLocation.bpLocationType;    
         hr = S_OK;    
      }    
      else    
      {    
         hr = E_FAIL;    
      }    
   }    
   else    
   {    
      hr = E_INVALIDARG;    
   }    
  
   return hr;    
}    
```  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)   
 [BP_LOCATION_TYPE](../../../extensibility/debugger/reference/bp-location-type.md)   
 [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)