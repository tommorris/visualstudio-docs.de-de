---
title: Verwenden des DebuggerDisplay-Attributs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/09/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- attributes [C#], debugger
- DebuggerDisplay attribute
- DebuggerDisplayAttribute class
ms.assetid: f4eb7c76-af4e-493b-9ab6-9cb05949d9b3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5dc83fc859e99a86b1057a02b7cfb9ff2e1232af
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42635524"
---
# <a name="using-the-debuggerdisplay-attribute"></a>Verwenden des DebuggerDisplay-Attributs
Die <xref:System.Diagnostics.DebuggerDisplayAttribute> steuert, wie ein Objekt, eine Eigenschaft oder ein Feld in den Variablenfenstern des Debuggers angezeigt wird. Dieses Attribut kann auf Typen, Delegaten, Eigenschaften, Felder und Assemblys angewendet werden.  
  
 Das `DebuggerDisplay` -Attribut verfügt über ein einziges Argument, das als Zeichenfolge in der Wertspalte für Instanzen des Typs angezeigt wird. Diese Zeichenfolge kann geschweifte Klammern (`{` und `}`) enthalten. Text innerhalb von Klammern wird als Feld, Eigenschaft oder Methode ausgewertet.  
  
 Wenn eine Klasse eine überschriebene `ToString()` -Methode aufweist, verwendet der Debugger die überschriebene Methode anstelle des standardmäßigen `{<typeName>}`. Wenn Sie also die `ToString()` -Methode überschrieben haben, verwendet der Debugger die überschriebene Methode anstelle des standardmäßigen`{<typeName>}`, und Sie brauchen `DebuggerDisplay`nicht zu verwenden. Wenn Sie beides verwenden, hat das `DebuggerDisplay` -Attribut Vorrang gegenüber der überschriebenen `ToString()` -Methode.  
  
 Ob der Debugger diesen impliziten `ToString()` -Aufruf auswertet, hängt von einer Benutzereinstellung im Dialogfeld **Extras / Optionen / Debugging** ab. Visual Basic implementiert diese implizite `ToString()` -Auswertung nicht.  
  
> [!IMPORTANT]
>  Wenn das Kontrollkästchen **Unformatierte Struktur von Objekten in Variablenfenstern anzeigen** im Dialogfeld **Extras / Optionen / Debugging** aktiviert ist, wird das `DebuggerDisplay` -Attribut ignoriert.  
  
 In der folgenden Tabelle werden einige Verwendungsmöglichkeiten des `DebuggerDisplay` -Attributs sowie Beispielausgaben gezeigt.  
  
|Attribut|Ausgabe in der Wertspalte angezeigt werden|  
|---------------|------------------------------------------------|  
|`[DebuggerDisplay("x = {x} y = {y}")]`<br /><br /> Angewendet auf einen Typ mit den Feldern `x` und `y`.|`x = 5 y = 18`|  
|`[DebuggerDisplay("String value is {getString()}")]`Die Parametersyntax kann je nach Sprache unterschiedlich sein. Achten Sie deshalb besonders auf die Syntax.|`String value is [5, 6, 6]`|  
  
 `DebuggerDisplay` kann auch benannte Parameter akzeptieren.  
  
|Parameter|Zweck|  
|----------------|-------------|  
|`Name`, `Type`|Diese Parameter beeinflussen die Spalten **Name** und **Typ** der Variablenfenster. (Sie können mit der gleichen Syntax wie der Konstruktor auf Zeichenfolgen eingerichtet werden.) Der übermäßige Gebrauch dieser Parameter oder ihr falscher Einsatz kann zu verwirrenden Ausgaben führen.|  
|`Target`, `TargetTypeName`|Gibt den Zieltyp an, wenn das Attribut auf Assemblyebene verwendet wird.|  
  
 In der Datei „autoexp.cs“ wird das DebuggerDisplay-Attribut auf Assemblyebene verwendet. Die Datei „autoexp.cs“ legt die Standarderweiterungen fest, die Visual Studio für .NET-Objekte verwendet. Suchen Sie in der Datei „autoexp.cs“ Beispiele zur Verwendung des DebuggerDisplay-Attributs, oder bearbeiten und kompilieren Sie die Datei „autoexp.cs“, um die Standarderweiterungen zu ändern. Erstellen Sie eine Sicherungskopie der Datei "autoexp.cs", bevor Sie sie ändern.  
  
 Um „autoexp.cs“ zu erstellen, öffnen Sie die Developer-Eingabeaufforderung für VS2015, und führen Sie die folgenden Befehle aus.  
  
```cmd
cd <directory containing autoexp.cs>  
csc /t:library autoexp.cs  
```  
  
 Die Änderungen an „autoexp.dll“ werden in der nächsten Debugsitzung übernommen.  
  
## <a name="using-expressions-in-debuggerdisplay"></a>Verwenden von Ausdrücken in DebuggerDisplay  
 Obwohl ein allgemeiner Ausdruck zwischen den geschweiften Klammern in einem DebuggerDisplay-Attribut verwendet werden kann, wird diese Vorgehensweise nicht empfohlen.  
  
 Ein allgemeiner Ausdruck in DebuggerDisplay hat nur für die aktuelle Instanz des Zieltyps impliziten Zugriff auf den `this` -Zeiger. Der Ausdruck hat keinen Zugriff auf Aliase, lokale Variablen oder Zeiger. Wenn der Ausdruck auf Eigenschaften verweist, werden deren Attribute nicht verarbeitet. Z. B. der C#-Code `[DebuggerDisplay("Object {count - 2}")]` visualisierungselements `Object 6` Wenn das Feld `count` 8 wäre.  
  
 Die Verwendung von Ausdrücken in DebuggerDisplay kann zu folgenden Problemen führen:  
  
-   Das Auswerten von Ausdrücken ist der aufwändigste Vorgang im Debugger. Außerdem wird ein Ausdruck bei jedem Anzeigen ausgewertet. Dies kann bei der schrittweisen Ausführung des Codes Leistungsprobleme verursachen. Beispielsweise kann ein komplexer Ausdruck, der zum Anzeigen der Werte in einer Auflistung verwendet wird, die Ausführung des Codes sehr verlangsamen, wenn viele Elemente vorhanden sind.  
  
-   Ausdrücke werden von der Ausdrucksauswertung in der Sprache des aktuellen Stapelrahmens und nicht von der Auswertung der Sprache ausgewertet, in der der Ausdruck geschrieben wurde. Dies kann unvorhersehbare Ergebnisse zur Folge haben, wenn die Sprachen unterschiedlich sind.  
  
-   Durch Auswerten eines Ausdrucks kann der Zustand der Anwendung geändert werden. Beispielsweise ändert ein Ausdruck, der den Wert einer Eigenschaft festlegt, den Eigenschaftswert im ausgeführten Code.  
  
 Eine Möglichkeit, eventuelle Probleme bei der Ausdrucksauswertung zu verringern, ist das Erstellen einer privaten Eigenschaft, die den Vorgang ausführt und eine Zeichenfolge zurückgibt. Das DebuggerDisplay-Attribut kann dann den Wert dieser privaten Eigenschaft anzeigen. Im folgenden Beispiel wird dieses Muster implementiert:  
  
```csharp  
[DebuggerDisplay("{DebuggerDisplay,nq}")]  
public sealed class MyClass   
{      
    public int count { get; set; }      
    public bool flag { get; set; }      
    private string DebuggerDisplay  
   {         
        get  
        {  
             return string.Format("Object {0}", count - 2);  
        }      
    }  
}  
```  
Die ", Nq" Suffix weist die ausdrucksauswertung die Anführungszeichen entfernen, bei der Anzeige des Endwert (Nq = ohne Anführungszeichen). 
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie `DebuggerDisplay`zusammen mit `DebuggerBrowseable` und `DebuggerTypeProxy`verwendet wird. Bei der Anzeige in einem Variablenfenster des Debuggers (z. B. im Fenster **Überwachen** ) wird dadurch eine Erweiterung erzeugt, die folgendermaßen aussieht:  
  
|**Name**|**Wert**|**Type**|  
|--------------|---------------|--------------|  
|Key|"three"|object {string}|  
|Wert|3|object {int}|  
  
```csharp  
[DebuggerDisplay("{value}", Name = "{key}")]  
internal class KeyValuePairs  
{  
    private IDictionary dictionary;  
    private object key;  
    private object value;  
    public KeyValuePairs(IDictionary dictionary, object key, object value)  
    {  
        this.value = value;  
        this.key = key;  
        this.dictionary = dictionary;  
    }  
  
    public object Key  
    {  
        get { return key; }  
        set  
        {  
            object tempValue = dictionary[key];  
            dictionary.Remove(key);  
            key = value;  
            dictionary.Add(key, tempValue);  
        }  
    }  
  
    public object Value  
    {  
        get { return this.value; }  
        set  
        {  
            this.value = value;  
            dictionary[key] = this.value;  
        }  
    }  
}  
  
[DebuggerDisplay("{DebuggerDisplay,nq}")]  
[DebuggerTypeProxy(typeof(HashtableDebugView))]  
class MyHashtable  
{  
    public Hashtable hashtable;  
  
    public MyHashtable()  
    {  
        hashtable = new Hashtable();    
    }
    
    private string DebuggerDisplay    {        get { return "Count = " + hashtable.Count); }    }  
  
    private class HashtableDebugView  
    {  
        private MyHashtable myhashtable;  
        public HashtableDebugView(MyHashtable myhashtable)  
        {  
            this.myhashtable = myhashtable;  
        }  
  
        [DebuggerBrowsable(DebuggerBrowsableState.RootHidden)]  
        public KeyValuePairs[] Keys  
        {  
            get  
            {  
                KeyValuePairs[] keys = new KeyValuePairs[myhashtable.hashtable.Count];  
  
                int i = 0;  
                foreach (object key in myhashtable.hashtable.Keys)  
                {  
                    keys[i] = new KeyValuePairs(myhashtable.hashtable, key, myhashtable.hashtable[key]);  
                    i++;  
                }  
                return keys;  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden des DebuggerTypeProxy-Attributs](../debugger/using-debuggertypeproxy-attribute.md)   
 [Erstellen Sie benutzerdefinierter Ansichten von verwalteten Objekten](../debugger/create-custom-views-of-dot-managed-objects.md)   
 [Formatbezeichner in c#](../debugger/format-specifiers-in-csharp.md)   
 [Verbessern des Debuggens mit den Debuggeranzeigeattributen](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)
