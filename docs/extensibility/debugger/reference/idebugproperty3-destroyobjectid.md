---
title: IDebugProperty3::DestroyObjectID | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProperty3::DestroyObjectID
helpviewer_keywords:
- IDebugProperty3::DestroyObjectID
ms.assetid: bd08f356-cc67-4717-98c9-c3d00cad2040
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0db5ef80a1734aedb819c109aa4c27c40224886e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
ms.locfileid: "31122937"
---
# <a name="idebugproperty3destroyobjectid"></a>IDebugProperty3::DestroyObjectID
Zerstört die eindeutige ID dieser Eigenschaft zugeordnet, der angibt, dass der Aufrufer wird nicht mehr, dass diese Eigenschaft aus allen anderen Eigenschaften eindeutig zu identifizieren.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DestroyObjectID(  
   void  
);  
```  
  
```csharp  
int DestroyObjectID();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `S_OK`ist, andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Debugging-Modul nicht eindeutige IDs für eine Eigenschaft unterstützen (da es bereits diese eindeutig intern verfolgt), und klicken Sie dann einfach zurückgegeben werden kann `E_NOTIMPL` für diese Methode.  
  
 Eindeutige IDs werden durch einen Aufruf erstellt die [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md) Methode, wenn der Aufrufer benötigt, um sicherzustellen, dass diese Eigenschaft für alle anderen Eigenschaften eindeutig identifiziert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)