---
title: SccDirQueryInfo-Funktion | Microsoft-Dokumentation
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
- SccDirQueryInfo
helpviewer_keywords:
- SccDirQueryInfo function
ms.assetid: 459e2d99-573d-47c4-b834-6d82c5e14162
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d737f45a337f2b43243641ce898cc2ef1d3a82de
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47515638"
---
# <a name="sccdirqueryinfo-function"></a>SccDirQueryInfo-Funktion
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [SccDirQueryInfo-Funktion](https://docs.microsoft.com/visualstudio/extensibility/sccdirqueryinfo-function).  
  
Diese Funktion untersucht eine Liste der vollqualifizierten Verzeichnisse für ihren aktuellen Status.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
SCCRTN SccDirQueryInfo(  
LPVOID  pContext,  
LONG    nDirs,  
LPCSTR* lpDirNames,  
LPLONG  lpStatus  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 "pContext"  
 [in] Datenquellen-Steuerelement-Plug-in Context-Struktur.  
  
 nDirs  
 [in] Die Anzahl der Verzeichnisse, die abgefragt werden sollen.  
  
 lpDirNames  
 [in] Ein Array von vollqualifizierten Pfade der Verzeichnisse, die abgefragt werden.  
  
 lpStatus  
 [in, out] Eine Arraystruktur für das Quellcodeverwaltungs-Plug-in, um die Statusflags zurückzugeben (finden Sie unter [Directory Statuscode](../extensibility/directory-status-code-enumerator.md) Einzelheiten).  
  
## <a name="return-value"></a>Rückgabewert  
 Die Source-Steuerelement-Plug-in-Implementierung dieser Funktion muss einen der folgenden Werte zurückgeben:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|SCC_OK|Die Abfrage war erfolgreich.|  
|SCC_E_OPNOTSUPPORTED|Das Quellcodeverwaltungssystem wird dieser Vorgang nicht unterstützt.|  
|SCC_E_ACCESSFAILURE|Es wurde ein Problem, das Zugriff auf das Quellcodeverwaltungssystem, möglicherweise aufgrund eines Netzwerk-oder-Konflikte bestehen. Eine Wiederholung wird empfohlen.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Nicht spezifischen Fehler.|  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion füllt das return-Array mit einer Bitmaske von Bits aus der `SCC_DIRSTATUS` Familie (finden Sie unter [Directory Statuscode](../extensibility/directory-status-code-enumerator.md)), einen Eintrag für jedes Verzeichnis erhält. Das Statusarray, die vom Aufrufer zugeordnet ist.  
  
 Die IDE verwendet diese Funktion auf, bevor Sie ein Verzeichnis umbenannt wird, um zu überprüfen, ob das Verzeichnis befindet sich unter quellcodeverwaltung durch Abfragen, ob es sich um eine entsprechende Projekt verfügt. Wenn das Verzeichnis nicht in der quellcodeverwaltung enthalten ist, kann die IDE die richtige Warnung für dem Benutzer bereitstellen.  
  
> [!NOTE]
>  Wenn ein Quellcodeverwaltungs-Plug-in entscheidet, die nicht mindestens einer der Statuswerte implementiert, sollte nicht implementierte Bits auf 0 (null) festgelegt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Quellcodeverwaltungsfunktionen-Plug-in-API](../extensibility/source-control-plug-in-api-functions.md)   
 [Verzeichnisstatuscode](../extensibility/directory-status-code-enumerator.md)

