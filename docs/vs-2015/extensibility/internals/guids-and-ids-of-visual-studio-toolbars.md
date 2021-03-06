---
title: GUIDs und IDs der Visual Studio-Symbolleisten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- visual studio groups
- toolbars
- visual studio toolbar
- id
- toolgar group
- tool window toolbar
- guid
ms.assetid: c9cacd57-9225-450f-a9ac-cbf3168ea844
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f24e406f0d7e4fe9782ccba56aa33dfbb4b658fe
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47513785"
---
# <a name="guids-and-ids-of-visual-studio-toolbars"></a>GUIDs und IDs der Visual Studio-Symbolleisten
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [GUIDs und IDs der Visual Studio-Symbolleisten](https://docs.microsoft.com/visualstudio/extensibility/internals/guids-and-ids-of-visual-studio-toolbars).  
  
Dieses Thema listet die GUID und ID-Werte, der in Symbolleisten, die in der integrierten Entwicklungsumgebung (IDE) von Visual Studio enthalten sind, und der Gruppen enthalten. Diese Werte werden in der VSCT-Dateien definiert, die als Teil der Visual Studio SDK installiert sind. Weitere Informationen finden Sie unter [IDE-Defined Befehle, Menüs und Gruppen](../../extensibility/internals/ide-defined-commands-menus-and-groups.md).  
  
> [!NOTE]
>  Viele der in Symbolleisten in Visual Studio zur Verfügung sind nicht definiert, von Visual Studio und ihrer GUID und ID-Werte sind nicht öffentlich. Dieses Thema enthält nur die Symbolleisten, die in Visual Studio SDK VSCT-Dateien definiert sind.  
  
 Weitere Informationen zum Arbeiten mit IDE-Objekten, die in der VSCT-Dateien definiert sind, finden Sie unter [Erweitern von Menüs und Befehlen](../../extensibility/extending-menus-and-commands.md).  
  
 Verwenden Sie die GUID die von Visual Studio-IDE bereitgestellten Standardsymbolleisten `guidSHLMainMenu`, sofern nicht anders angegeben, mit der GUID: ID-Syntax.  
  
## <a name="ide-toolbars"></a>IDE-Symbolleisten  
 Die folgenden Symbolleisten werden von Visual Studio-IDE bereitgestellt. Symbolleisten können angezeigt werden, indem Sie sie auf Auswählen der **Symbolleisten** Untermenü die **Tools** Menü. Symbolleisten in Toolfenstern sind nicht in diesem Abschnitt enthalten.  
  
 Nur Gruppen können direkt von Symbolleisten abgeleitet werden. Um eine Gruppe hinzuzufügen, legen Sie das übergeordnete Element auf die GUID und ID der Symbolleiste aus. Um eine Symbolleiste eine Schaltfläche hinzuzufügen, legen Sie das übergeordnete Element zu einer Gruppe auf der Symbolleiste.  
  
|Symbolleiste|Id|  
|-------------|--------|  
|Standard|IDM_VS_TOOL_STANDARD|  
|Build|IDM_VS_TOOL_BUILD|  
|Text-Editor|IDM_VS_TOOL_TEXTEDITOR|  
|Debug|guidVSDebugGroup:IDM_DEBUG_TOOLBAR|  
|Debugspeicherort|guidVSDebugGroup:IDM_DEBUG_CONTEXT_TOOLBAR|  
  
### <a name="special-toolbars"></a>Spezielle Symbolleisten  
 Diese Symbolleisten werden definiert, von der Visual Studio-IDE, aber sie spezielle Funktionen bereitstellen und hosten Sie Befehlsgruppen nicht.  
  
|Symbolleiste|Id|  
|-------------|--------|  
|Befehl hinzufügen|IDM_VS_TOOL_ADDCOMMAND|  
|Nicht definiert|IDM_VS_TOOL_UNDEFINED|  
|XML-Schema|IDM_VS_TOOL_SCHEMA|  
|XML-Daten|IDM_VS_TOOL_DATA|  
  
## <a name="groups-on-the-ide-toolbars"></a>Gruppen auf dem IDE-Symbolleisten  
 Um eine standard-Symbolleiste eine Schaltfläche hinzuzufügen, legen Sie eine der folgenden Gruppen als übergeordnete Klasse aus. Die Gruppen werden von der übergeordneten Symbolleiste sortiert.  
  
### <a name="standard-toolbar-groups"></a>Standardsymbolleiste Gruppen  
  
|name|Id|  
|----------|--------|  
|Speichern/Öffnen|IDG_VS_TOOLSB_SAVEOPEN|  
|Ausschneiden/Kopieren|IDG_VS_TOOLSB_CUTCOPY|  
|Rückgängig/Wiederholen|IDG_VS_TOOLSB_UNDOREDO|  
|Führen Sie/Build|IDG_VS_TOOLSB_RUNBUILD|  
|Suchen|IDG_VS_TOOLSB_SEARCH|  
|Windows|IDG_VS_TOOLSB_WINDOWS|  
|Neue Windows|IDG_VS_TOOLSB_NEWWINDOWS|  
|Laden/Speichern|IDG_VS_WINDOWUI_LOADSAVE|  
|Monitor "|IDG_VS_TOOLSB_GAUGE|  
  
### <a name="build-toolbar-groups"></a>Symbolleistengruppen erstellen  
  
|name|Id|  
|----------|--------|  
|Build-Leiste|IDG_VS_BUILDBAR|  
|Abbrechen|IDG_VS_BUILD_CANCEL|  
  
### <a name="text-editor-toolbar-groups"></a>Text-Editor-Symbolleiste Gruppen  
  
|name|Id|  
|----------|--------|  
|Abschluss|IDM_VS_TOOL_TEXTEDITOR|  
|Indent|IDG_VS_EDITTOOLBAR_INDENT|  
|Kommentar|IDG_VS_EDITTOOLBAR_COMMENT|  
|Lesezeichen|IDG_VS_EDITTOOLBAR_TEMPBOOKMARKS|  
  
### <a name="debug-toolbar-groups"></a>Debug-Symbolleistengruppen  
  
|name|Id|  
|----------|--------|  
|Ausführung|IDM_DEBUG_TOOLBAR|  
|Schrittweises Ausführen|IDG_DEBUG_TOOLBAR_STEPPING|  
|Überwachen|IDG_DEBUG_TOOLBAR_WATCH|  
|Windows|IDG_DEBUG_TOOLBAR_WINDOWS|  
  
### <a name="debug-location-toolbar-groups"></a>Debuggen von Gruppen für Standort-Symbolleiste  
  
|name|Id|  
|----------|--------|  
|Debugspeicherort|IDG_DEBUG_CONTEXT_TOOLBAR|  
  
## <a name="tool-window-toolbars"></a>Symbolleisten des Toolfensters  
 Symbolleisten können angezeigt werden direkt in der IDE oder in Toolfenstern wie z. B. **Projektmappen-Explorer**. Da das Toolfenster nicht in der VSCT-Dateien definiert sind, müssen die Symbolleisten des Toolfensters nicht definierte übergeordneten Elementen. Stattdessen werden diese im Code platziert. Die folgende Tabelle zeigt die Symbolleisten, die Toolfenster in der IDE angezeigt werden und die darin enthaltenen Befehlsgruppen.  
  
> [!NOTE]
>  Verwenden Sie die GUID, Symbolleisten und Gruppen `guidSHLMainMenu`, sofern nicht anders angegeben, mit der GUID: ID-Syntax. Eine GUID für eine Symbolleiste angegeben ist, gilt er auch den Gruppen, die von dieser Symbolleiste abgeleitet.  
  
|Toolfenster|Symbolleiste|Gruppen|  
|-----------------|-------------|------------|  
|Projektmappen-Explorer|IDM_VS_TOOL_PROJWIN|IDG_VS_PROJ_TOOLBAR1... 5|  
|Server-Explorer|guid_SE_MenuGroup:IDM_SE_TOOLBAR_SERVEREXPLORER|IDG_SE_TOOLBAR_REFRESH|  
|Eigenschaften|IDM_VS_TOOL_PROPERTIES|IDG_VS_PROPERTIES_SORT<br /><br /> IDG_VS_PROPERTIES_PAGES|  
|Klassenansicht|IDM_VS_TOOL_CLASSVIEW|IDG_VS_CLASSVIEW_FOLDERS<br /><br /> IDG_VS_CLASSVIEW_SEARCH<br /><br /> IDG_VS_CLASSVIEW_SETTINGS|  
|Klassenansicht|IDM_VS_TOOL_CLASSVIEW_GO|IDG_VS_CLASSVIEW_SEARCH2|  
|Objektkatalog|IDM_VS_TOOL_OBJBROWSER|IDG_VS_OBJBROWSER_SUBSETS<br /><br /> IDG_VS_OBJBROWSER_SEARCH<br /><br /> IDG_VS_OBJBROWSER_ADDREFERENCE<br /><br /> IDG_VS_OBJBROWSER_BROWSERSETTINGS|  
|Objektkatalog|IDM_VS_TOOL_OBJECT_BROWSER_GO|IDG_VS_OBJBROWSER_SEARCH2|  
|Output|IDM_VS_TOOL_OUTPUTWINDOW|IDG_VS_OUTPUTWINDOW_SELECT<br /><br /> IDG_VS_OUTPUTWINDOW_GOTO<br /><br /> IDG_VS_OUTPUTWINDOW_NEXTPREV<br /><br /> IDG_VS_OUTPUTWINDOW_CLEAR<br /><br /> IDG_VS_OUTPUTWINDOW_WORDWRAP|  
|Suchen und Ersetzen|IDM_VS_TOOL_UNIFIEDFIND|IDG_VS_FINDTAB<br /><br /> IDG_VS_REPLACETAB|  
|Suchergebnisse: 1|IDM_VS_TOOL_FINDRESULTS1|IDG_VS_FINDRESULTS1_GOTO<br /><br /> IDG_VS_FINDRESULTS1_NEXTPREV<br /><br /> IDG_VS_FINDRESULTS1_CLEAR<br /><br /> IDG_VS_FINDRESULTS1_STOPFIND|  
|Suchergebnisse: 2|IDM_VS_TOOL_FINDRESULTS2|IDG_VS_FINDRESULTS2_GOTO<br /><br /> IDG_VS_FINDRESULTS2_NEXTPREV<br /><br /> IDG_VS_FINDRESULTS2_CLEAR<br /><br /> IDG_VS_FINDRESULTS2_STOPFIND|  
|Codeausschnitt|IDM_VS_TOOL_SNIPPETMENUS|IDG_VS_SNIPPET_REPL<br /><br /> IDG_VS_SNIPPET_REF<br /><br /> IDG_VS_SNIPPET_PROP|  
|Lesezeichen|IDM_VS_TOOL_BOOKMARKWIND|IDG_VS_BWNEWFOLDER<br /><br /> IDG_VS_BWNEXTBM<br /><br /> IDG_VS_BWNEXTBMF<br /><br /> IDG_VS_BWENABLE<br /><br /> IDG_VS_BWDELETE|  
|Aufgabenliste|IDM_VS_TOOL_TASKLIST|IDG_VS_TASKLIST_PROVIDERLIST|  
|Benutzeraufgaben|IDM_VS_TOOL_USERTASKS|IDG_VS_TASKLIST_PROVIDERLIST<br /><br /> IDG_VS_USERTASKS_EDIT|  
|Fehlerliste|IDM_VS_TOOL_ERRORLIST|IDG_VS_ERRORLIST_ERRORGROUP<br /><br /> IDG_VS_ERRORLIST_WARNINGGROUP<br /><br /> IDG_VS_ERRORLIST_MESSAGEGROUP|  
|Aufrufbrowser|IDM_VS_TOOL_CALLBROWSER1... 16|IDG_VS_TOOLBAR_CALLBROWSER1_ACTIONS<br /><br /> IDG_VS_TOOLBAR_CALLBROWSER1_TYPE<br /><br /> IDG_VS_TOOLBAR_CALLBROWSER1_CBSETTINGS|  
|Haltepunkte|guidVSDebugGroup:IDM_BREAKPOINTS_WINDOW_TOOLBAR|IDG_BREAKPOINTS_WINDOW_NEW<br /><br /> IDG_BREAKPOINTS_WINDOW_DELETE<br /><br /> IDG_BREAKPOINTS_WINDOW_ALL<br /><br /> IDG_BREAKPOINTS_WINDOW_VIEW<br /><br /> IDG_BREAKPOINTS_WINDOW_EDIT<br /><br /> IDG_BREAKPOINTS_WINDOW_COLUMNS|  
|Disassemblierung|guidVSDebugGroup:IDM_DISASM_WINDOW_TOOLBAR|IDG_DISASM_WINDOW_TOOLBAR|  
|Arbeitsspeicher von 1 bis 4|GuidVSDebugGroup:IDM_MEMORY_WINDOW_TOOLBAR1... 4|IDG_MEMORY_EXPRESSION1... 4<br /><br /> IDG_MEMORY_COLUMNS1... 4|  
|Prozesse|guidVSDebugGroup:IDM_ATTACHED_PROCS_TOOLBAR|IDG_ATTACHED_PROCS_EXECCNTRL IDG_ATTACHED_PROCS_STEPPING<br /><br /> IDG_ATTACHED_PROCS_EXECCNTRL2<br /><br /> IDG_ATTACHED_PROCS_ATTACH<br /><br /> IDG_ATTACHED_PROCS_COLUMNS|  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen eines Menücontrollers zu einer Symbolleiste](../../extensibility/adding-a-menu-controller-to-a-toolbar.md)   
 [Hinzufügen einer Symbolleiste zu einem Toolfenster](../../extensibility/adding-a-toolbar-to-a-tool-window.md)   
 [GUIDs und IDs der Visual Studio-Menüs](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md)

