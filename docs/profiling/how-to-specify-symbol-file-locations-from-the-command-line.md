---
title: 'Vorgehensweise: Angeben von Symboldateispeicherorten über die Befehlszeile | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 8aa067bb-e8bf-4081-aff0-cfbcf65934a0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d31479ec46c407ca875a1ad2a1d81e1438b7715
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845209"
---
# <a name="how-to-specify-symbol-file-locations-from-the-command-line"></a>Vorgehensweise: Angeben von Symboldateispeicherorten über die Befehlszeile
Zum Anzeigen von Symbolinformationen, wie z.B. Funktionsnamen und Zeilennummern benötigt das VSPerfReport-Befehlszeilentool Zugriff auf die Symboldateien (*PDB*) der profilierten Komponenten und die Windows-Systemdateien. Symboldateien werden erstellt, wenn eine Komponente kompiliert wird. Weitere Informationen finden Sie unter [VSPerfReport](../profiling/vsperfreport.md). VSPerfReport sucht automatisch in den folgenden Speicherorten nach Symboldateien:  
  
-   Angegeben Pfade in der **/SymbolPath**-Option oder in der **_NT_SYMBOL_PATH**-Umgebungsvariable.  
  
-   Der genaue lokale Pfad, in dem eine Komponente kompiliert wurde.  
  
-   Das Verzeichnis, das die Profilerstellungsdatendatei (*VSP* oder *VSPS*) enthält.  
  
 Microsoft stellt die *PDB-Dateien* für viele seiner Produkte online auf einem Symbolserver bereit. Wenn der Computer, den Sie für die Berichterstattung verwenden, mit dem Internet verbunden ist, verbindet sich VSPerfReport mit dem Online-Symbolserver, um automatisch nach Symbolinformationen zu suchen und die Dateien in einem lokalen Speicher zu speichern.  
  
 Sie können den Speicherort der Symboldateien und den Microsoft-Symbolserver folgendermaßen angeben:  
  
-   Legen Sie die **_NT_SYMBOL_PATH**-Umgebungsvariable fest.  
  
-   Fügen Sie die **/SymbolPath**-Option zur VSPerfReport-Befehlszeile hinzu.  
  
 Sie können auch beide Methoden verwenden.  
  
> [!NOTE]
>  Wenn [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] auf dem lokalen Computer installiert ist, wurde wahrscheinlich bereits ein Speicherort für die Windows-Symboldateien angegeben. Weitere Informationen finden Sie unter [Vorgehensweise: Verweisen auf Windows-Symbolinformationen](../profiling/how-to-reference-windows-symbol-information.md). Sie müssen VSPerfReport dennoch konfigurieren, um den Speicherort und den Server, wie weiter unten in diesem Thema beschrieben, zu verwenden.  
  
## <a name="specify-windows-symbol-files"></a>Angeben von Windows-Symboldateien  
  
#### <a name="to-configure-the-use-of-the-windows-symbol-server"></a>So konfigurieren Sie die Verwendung des Windows-Symbolservers  
  
1.  Falls erforderlich, erstellen Sie ein Verzeichnis, um die Symboldateien lokal zu speichern.  
  
2.  Verwenden Sie die folgende Syntax zum Festlegen der **_NT_SYMBOL_PATH**-Umgebungsvariable oder die VSPerfReport /SymbolPath-Option:  
  
     **srv\*** *LocalStore* **\*http://msdl.microsoft.com/downloads/symbols**  
  
     wobei *LocalStore* der Pfad des lokalen Verzeichnisses ist, das Sie erstellt haben.  
  
## <a name="specify-component-symbol-files"></a>Angeben von Komponentensymboldateien  
 Profilerstellungstools suchen nach den *PDB-Dateien* der Komponenten, die Sie in ihren ursprünglichen Speicherorten erstellen möchten, die in den Komponenten oder in den Ordnern mit der Profilerstellungsdatendatei gespeichert werden. Sie können andere Speicherorte zum Suchen angeben, indem Sie eine oder mehrere Pfade zu **_NT_SYMBOL_PATH** oder der **/SymbolPath**-Option hinzufügen. Separate Pfade mit Semikolons.  
  
## <a name="example"></a>Beispiel  
 Die folgende Befehlszeile legt die **_NT_SYMBOL_PATH**-Umgebungsvariable auf den Windows-Symbolserver und das lokale Verzeichnis auf **C:\Symbols**.  
  
 **set _NT_SYMBOL_PATH=srv\*C:\symbols\*http://msdl.microsoft.com/downloads/symbols**  
  
 Die folgende VSPerfReport-Befehlszeile fügt mithilfe der **/SymbolPath**-Option das Verzeichnis *C:\Projects\Symbols* zum Suchpfad hinzu.  
  
 **VSPerfReport**  *MyApp* **.exe /SymbolPath:C:\Projects\Symbols /summary:all**