---
title: 'Idiasymbol:: Get_type | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_type method
ms.assetid: 1c6a4176-dd4e-4c22-8b8f-0e559fc078ba
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 414c66b000a7cd81783ec963d78105792d6b816b
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
ms.locfileid: "31469723"
---
# <a name="idiasymbolgettype"></a>IDiaSymbol::get_type
Ruft das Symbol, das den Typ dieses Symbol darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```C++  
HRESULT get_type (   
   IDiaSymbol** pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pRetVal`  
 [out] Gibt eine [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) -Objekt, das den Typ dieses Symbols darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `S_OK`ist, andernfalls gibt `S_FALSE` oder ein Fehlercode.  
  
> [!NOTE]
>  Ein Rückgabewert von `S_FALSE` bedeutet, dass die Eigenschaft ist nicht verfügbar für das Symbol.  
  
## <a name="remarks"></a>Hinweise  
 Um den Typ zu bestimmen, ein Symbol aufweist, müssen Sie diese Methode aufrufen, und überprüfen Sie das Ergebnis [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) Objekt. Beachten Sie, dass es möglich, dass ein Symbol zum keinen Typ aufweisen. Beispielsweise der Namen einer Struktur wurde kein Typ jedoch möglicherweise untergeordnete Elemente Symbole (verwenden Sie die [idiasymbol:: Findchildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md) Methode, um diesen untergeordneten Elementen zu untersuchen).  
  
## <a name="example"></a>Beispiel  
  
```C++  
IDiaSymbol*         pType;  
CComPtr<IDiaSymbol> pBaseType;  
if (SUCCEEDED(pType->get_type( &pBaseType ))) {  
    BasicType btBaseType;  
    if (SUCCEEDED(pBaseType->get_baseType((DWORD *)&btBaseType))) {  
        // Do something with basic type.  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [Idiasymbol:: Get_basetype](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)   
 [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)