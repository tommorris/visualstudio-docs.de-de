---
title: IDebugProperty2::SetValueAsReference | Microsoft-Dokumentation
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
- IDebugProperty2::SetValueAsReference
helpviewer_keywords:
- IDebugProperty2::SetValueAsReference method
ms.assetid: 341b1b89-4ab8-4e1c-abe2-fb955df5c6b0
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aa128e570c0b55af71f87946d7c25d668b987fcd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47511136"
---
# <a name="idebugproperty2setvalueasreference"></a>IDebugProperty2::SetValueAsReference
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IDebugProperty2::SetValueAsReference](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugproperty2-setvalueasreference).  
  
Legt den Wert dieser Eigenschaft auf den Wert des angegebenen Verweises.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT SetValueAsReference(  
   IDebugReference2** rgpArgs,  
   DWORD              dwArgCount,  
   IDebugReference2*  pValue,  
   DWORD              dwTimeout  
);  
```  
  
```csharp  
int SetValueAsReference(  
   IDebugReference2[] rgpArgs,  
   uint               dwArgCount,  
   IDebugReference2   pValue,  
   uint               dwTimeout  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `rgpArgs`  
 [in] Ein Array von Argumenten, die an den Eigenschaftensetter für verwalteten Code übergeben werden sollen. Wenn Setter für die Eigenschaft über keine Argumente akzeptiert, oder wenn diese [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) Objekt verweist nicht auf solche einen Eigenschaften-Setter `rgpArgs` sollte ein null-Wert sein. Dieser Parameter ist in der Regel einen null-Wert.  
  
 `dwArgCount`  
 [in] Die Anzahl der Argumente in der `rgpArgs` Array.  
  
 `pValue`  
 [in] Ein Verweis in Form einer [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) Objekt, das den Wert, der zum Festlegen dieser Eigenschaft.  
  
 `dwTimeout`  
 [in] Wie lange ausführen, um den Wert in Millisekunden festgelegt. Ein typischer Wert `INFINITE`. Dies wirkt sich auf die Länge der Zeit, die alle möglichen Auswertung aus.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`; andernfalls ein Fehler code wird zurückgegeben, in der Regel eine der folgenden:  
  
|Fehler|Beschreibung|  
|-----------|-----------------|  
|`E_SETVALUEASREFERENCE_NOTSUPPORTED`|Festlegen des Werts aus einem Verweis wird nicht unterstützt.|  
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|Der Wert kann nicht festgelegt werden, wie diese Eigenschaft auf eine Methode verweist.|  
|`E_SETVALUE_VALUE_IS_READONLY`|Der Wert ist schreibgeschützt und kann nicht festgelegt werden.|  
|`E_NOTIMPL`|Die Methode ist nicht implementiert.|  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)

