---
title: IDebugDocumentContext2::GetLanguageInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDocumentContext2::GetLanguageInfo
helpviewer_keywords:
- IDebugDocumentContext2::GetLanguageInfo
ms.assetid: 6a212ee5-414c-4eb5-ab11-19db1786943d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d86a31893a62391c0da1041402e3806c7a1e997e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107425"
---
# <a name="idebugdocumentcontext2getlanguageinfo"></a>IDebugDocumentContext2::GetLanguageInfo
Ruft die diesem Dokumentenkontext zugeordnete Sprache ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetLanguageInfo(   
   BSTR* pbstrLanguage,  
   GUID* pguidLanguage  
);  
```  
  
```csharp  
int GetLanguageInfo(   
   out string pbstrLanguage,  
   out Guid   pguidLanguage  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pbstrLanguage`  
 [out] Der Name der Sprache, die den Code in diesem Dokumentenkontext zurückgegeben.  
  
 `pguidLanguage`  
 [out] Gibt die GUID der Sprache, die den Code in diesem Dokumentenkontext zurück. Beispielsweise `guidVBScriptLang` oder `guidCPPLang`. Diese GUID ist nicht beschränkt auf die Sprachen, die vom [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `S_OK`ist, andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie diese Methode für eine einfache implementiert `CDebugContext` -Objekt, das macht die [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) Schnittstelle.  
  
```cpp  
HRESULT CDebugContext::GetLanguageInfo(BSTR* pbstrLanguage, GUID* pguidLanguage)    
{    
   HRESULT hr;    
  
   // Check for a valid language argument pointers.    
   if (pbstrLanguage && pguidLanguage)    
   {    
      *pguidLanguage = GUID_NULL;    
      *pbstrLanguage = SysAllocString(L"Batch File");    
      if (*pbstrLanguage)    
      {    
         *pguidLanguage = guidBatLang;    
         hr = S_OK;    
      }    
      else    
      {    
         hr = E_OUTOFMEMORY;    
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
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)