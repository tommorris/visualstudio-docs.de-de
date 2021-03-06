---
title: XML-Editor-Schemacache
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 35a7fcad-f3bf-4a96-9008-4306e7276223
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cf3c41c16f904077f884bc6cffcdf0ba97233a1a
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572786"
---
# <a name="schema-cache"></a>Schemacache

Der XML-Editor bietet einen Schemacache im Verzeichnis der *%InstallRoot%\Xml\Schemas* Verzeichnis. Der Schemacache ist global für alle Benutzer auf dem Computer und enthält XML-Standardschemata, die für IntelliSense und die Validierung von XML-Dokumenten verwendet werden.

Schemas der XML-Editor erhalten auch Schemas, die in der Projektmappe befindet, angegeben werden, der **Schemas** Feld des Dokuments **Eigenschaften** Fenster und Schemas, die durch identifiziert die `xsi:schemaLocation` und `xsi:noNamespaceSchemaLocation`Attribute.

In der folgenden Tabelle werden die mit dem XML-Editor installierten Schemata beschrieben.

|Dateiname|Beschreibung|
|--------------|-----------------|
|*Catalog.xsd*|Schema für Schemakatalogdateien des XML-Editors. Weitere Informationen zu den Schemakatalogen finden Sie weiter unten.|
|*DotNetConfig.xsd*|Schema für die Dateien "Web.config", "http://schemas.microsoft.com/.NETConfiguration/v2.0".|
|*MSBuild.xsd*|Schema für die MSBuild stellen Dateien "http://schemas.microsoft.com/developer/msbuild/2003".|
|*msdata.xsd*|Schema für XSD-Anmerkungen, die von der <xref:System.Data.DataSet>-Klasse hinzugefügt werden, "urn:schemas-microsoft-com:xml-msdata".|
|*msxsl.xsd*|Schema für Microsoft XSLT-Skriptblockerweiterungen, urn:schemas-microsoft-com:xslt.|
|*SnippetFormat.xsd*|Schema für die XML-Dateien von Codeausschnitten. Beispiele finden Sie unter *%InstallDir%\VC#\Expansions*.|
|*Soap1.1.xsd*|Schema für Simple Object Access Protocol (SOAP) 1.1 http://schemas.xmlsoap.org/soap/envelope/.|
|*Soap1.2.xsd*|Schema für Simple Object Access Protocol 1.2.|
|*SiteMapSchema.xsd*|Schema für ASP.NET Sitemap XML-Datei "http://schemas.microsoft.com/AspNet/SiteMap-File-1.0".|
|*WSDL.xsd*|Schema für Web Service Description Language http://schemas.xmlsoap.org/wsdl/.|
|*xenc.xsd*|Schema für XML-Verschlüsselung, http://www.w3.org/2000/09/xmldsig#.|
|*XHTML.xsd*|Schema für XHTML http://www.w3.org/1999/xhtml.|
|*xlink.xsd*|Schema für XLink1.0, http://www.w3.org/1999/xlink.|
|*XML.xsd*|Schema, XML: space "und" XML: lang-Attribute beschreibt http://www.w3.org/XML/1998/namespace.|
|*xmlsig.xsd*|Schema für digitale XML-Signaturen http://www.w3.org/2000/09/xmldsig#.|
|*XSDSchema.xsd*|Schema, beschreibt XSD selbst http://www.w3.org/2001/XMLSchema.|
|*XSLT.xsd*|Schemas für XML transformiert, http://www.w3.org/1999/XSL/Transform.|

## <a name="update-schemas-in-the-cache"></a>Aktualisieren von Schemata im cache
 Der Editor lädt das Verzeichnis des Schemacache beim Laden des XML-Editorpakets und überwacht während der Ausführung alle Änderungen. Wenn ein Schema hinzugefügt wurde, wird es automatisch in einen Index bekannter Schemata im Speicher geladen. Wenn ein Schema entfernt wurde, wird es automatisch vom Index im Speicher entfernt. Wenn ein Schema aktualisiert wurde, wird es automatisch im speicherinternen Cache dieses Schemas für ungültig erklärt.

> [!NOTE]
> Da das Verzeichnis des Schemacaches für Ihren Computer global ist, sollten Sie hier nur standardmäßige Schemas hinzufügen, die für alle auf dem Computer erstellten Visual Studio-Projekte nützlich sind.


 Der XML-Editor unterstützt eine beliebige Anzahl von Schemakatalogdateien im Verzeichnis des Schemacaches. Schemakataloge können auf andere Speicherorte von Schemata zeigen, die dem Editor immer bekannt sein sollen. Die *catalog.xsd* Datei definiert das Format für die Katalogdatei und ist im Verzeichnis Schemacache enthalten. Die *catalog.xml* Datei wird der Standardkatalog und enthält Links zu anderen Schemas in der *INSTALLDIR%*. Im folgenden werden eine Stichprobe der *catalog.xml* Datei:

```xml
<SchemaCatalog xmlns="http://schemas.microsoft.com/xsd/catalog">
  <Schema href="%InstallDir%/help/schemas/Favorites.xsd" targetNamespace="urn:Favorites-Schema"/>
  <Schema href="%InstallDir%/help/schemas/Links.xsd" targetNamespace="urn:Links-Schema"/>
  <Schema href="%InstallDir%/help/schemas/MyHelp.xsd" targetNamespace="urn:VSHelp-Schema"/>
</SchemaCatalog>
```

 Das `href`-Attribut kann jede/r Dateipfad oder HTTP-URL sein, der/die auf das Schema zeigt. Der Dateipfad kann relativ zum Katalogdokument sein. Die folgenden, durch %% getrennten Variablen werden vom Editor erkannt und im Pfad erweitert:

-   InstallDir

-   System

-   ProgramFiles

-   Programs

-   CommonProgramFiles

-   ApplicationData

-   CommonApplicationData

-   LCID

Das Katalogdokument kann ein `Catalog`-Element enthalten, das auf andere Kataloge zeigt. Mithilfe des `Catalog`-Elements können Sie auf einen für Ihr Team oder Ihr Unternehmen freigegebenen zentralen Katalog oder auf einen Onlinekatalog zeigen, den Sie gemeinsam mit Ihren Geschäftspartnern nutzen. Das `href`-Attribut ist der Dateipfad oder die HTTP-URL für die anderen Kataloge. Es folgt ein Beispiel für das `Catalog`-Element:

```xml
<Catalog href="file://c:/xcbl/xcblCatalog.xml"/>
```

 Der Katalog kann auch steuern, wie die Schemata den XML-Dokumenten mithilfe des speziellen `Association`-Elements zugeordnet werden. Dieses Element ordnet Schemas, die über keinen Zielnamespace verfügen, eine bestimmte Dateierweiterung zu. Dies ist nützlich, da der XML-Editor keine automatische Zuordnung für Schemas ausführt, die kein `targetNamespace`-Attribut aufweisen. Im folgenden Beispiel ordnet das `Association`-Element allen Dateien das dotNetConfig-Schema zu, die die config-Dateierweiterung aufweisen:

```xml
<Association extension="config" schema="%InstallDir%/xml/schemas/dotNetConfig.xsd"/>
```

## <a name="localized-schemas"></a>Lokalisierte schemas
 In vielen Fällen die *catalog.xml* Datei enthält keine Einträge für lokalisierte Schemas. Sie können zusätzliche Einträge zum Hinzufügen der *catalog.xml* Datei, die auf das lokalisierte Schemaverzeichnis verweisen.

 Im folgenden Beispiel wurde ein neues `Schema`-Element erstellt, das mithilfe der %LCID%-Variable auf das lokalisierte Schema verweist.

```xml
<Schema href="%InstallRoot%/Common7/IDE/Policy/Schemas/%LCID%/TDLSchema.xsd"
  targetNamespace="http://www.microsoft.com/schema/EnterpriseTemplates/TDLSchema"/>
```

## <a name="change-the-location-of-the-schema-cache"></a>Ändern Sie den Speicherort des Schemacaches

Sie können anpassen, dass den Speicherort für den Schemacache mithilfe der **Sonstiges** Seite "Optionen". Wenn Sie über ein Verzeichnis der bevorzugten Schemata verfügen, kann der Editor so konfiguriert werden, dass er stattdessen diese Schemata verwendet.

> [!NOTE]
> Von dieser Änderung ist nur der aktuelle Benutzer von Visual Studio betroffen.

### <a name="to-change-the-schema-cache-location"></a>So ändern Sie den Speicherort für den Schemacache

1.  Aus der **Tools** klicken Sie im Menü **Optionen**.

2.  Erweitern Sie **Texteditor**, erweitern Sie **XML**, und klicken Sie dann auf **Sonstiges**.

3.  Klicken Sie auf die **Durchsuchen** Schaltfläche auf der **Schemas** Feld.

4.  Wählen Sie den Ordner für den Schemacache aus, und klicken Sie auf **OK**.

### <a name="to-add-another-directory-of-common-schemas"></a>So fügen Sie ein anderes Verzeichnis für häufig verwendete Schemata hinzu

1.  Bearbeiten der *catalog.xml* Datei im XML-Editor-Verzeichnis Schemacache.

2.  Fügen Sie ein neues `<Catalog href="..."/>`-Element hinzu, das auf das Verzeichnis der zusätzlichen Schemata zeigt.

3.  Speichern Sie die Änderungen.

     Der Katalog wird automatisch neu geladen.

## <a name="see-also"></a>Siehe auch

- [XML-Editor](../xml-tools/xml-editor.md)