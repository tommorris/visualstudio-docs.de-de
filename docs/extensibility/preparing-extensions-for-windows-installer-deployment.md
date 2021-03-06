---
title: Vorbereiten von Erweiterungen für Windows Installer-Bereitstellung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- vsix msi
ms.assetid: 5ee2d1ba-478a-4cb7-898f-c3b4b2ee834e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: cc742fecbbe03ff3d3aa0fb3f8d61a9c5f09254b
ms.sourcegitcommit: 9765b3fcf89375ca499afd9fc42cf4645b66a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46495270"
---
# <a name="prepare-extensions-for-windows-installer-deployment"></a>Vorbereiten von Erweiterungen für Windows Installer-Bereitstellung
Ein Windows Installer-Paket (MSI) können Sie ein VSIX-Paket bereitstellen. Allerdings können Sie den Inhalt einer VSIX-Pakets für die Bereitstellung der MSI-Datei extrahieren. Diesem Dokument wird erläutert, wie Sie ein Projekt vorbereiten, deren Standardausgabe ein VSIX-Paket für die Aufnahme in ein Setup-Projekt ist.  
  
## <a name="prepare-an-extension-project-for-windows-installer-deployment"></a>Bereiten Sie ein Erweiterungsprojekt für Windows Installer-Bereitstellung vor.  
 Führen Sie diese Schritte können Sie neue Erweiterung-Projekte aus, bevor Sie ein Setup-Projekt hinzufügen.  
  
### <a name="to-prepare-an-extension-project-for-windows-installer-deployment"></a>So bereiten Sie ein Erweiterungsprojekt für Windows Installer-Bereitstellung vor  
  
1.  Erstellen Sie ein VSPackage, MEF-Komponente, Editor Zusatzelement oder anderen Projekttyp für Erweiterbarkeit, die einem VSIX-Manifest enthält.  
  
2.  Öffnen Sie das VSIX-Manifest im Code-Editor ein.  
  
3.  Legen Sie die `InstalledByMsi` -Elements des VSIX-Manifests, das `true`. Weitere Informationen zu VSIX-Manifest, finden Sie unter [VSIX-Erweiterung Schemareferenz 2.0](../extensibility/vsix-extension-schema-2-0-reference.md).  
  
     Dadurch wird verhindert, dass das VSIX-Installationsprogramm die Komponente installieren möchten.  
  
4.  Mit der rechten Maustaste in des Projekts im **Projektmappen-Explorer** , und klicken Sie auf **Eigenschaften**.  
  
5.  Wählen Sie die **VSIX** Registerkarte.  
  
6.  Aktivieren Sie das Kontrollkästchen mit der Bezeichnung **Kopie VSIX-Inhalt am folgenden Speicherort** , und geben Sie den Pfad zur, in dem das Setup-Projekt die Dateien abruft.  
  
## <a name="extract-files-from-an-existing-vsix-package"></a>Extrahieren von Dateien aus einem vorhandenen VSIX-Paket  
 Führen Sie diese Schritte aus, um den Inhalt eines vorhandenen VSIX-Pakets zu einem Setupprojekt hinzufügen, wenn Sie nicht über die Quelldateien verfügen.  
  
### <a name="to-extract-files-from-an-existing-vsix-package"></a>Um Dateien aus einem vorhandenen VSIX-Paket zu extrahieren.  
  
1.  Benennen Sie die *. VSIX* -Datei mit der Erweiterung *filename.vsix* zu *filename.zip*.  
  
2.  Kopieren Sie den Inhalt von der *ZIP* -Datei in ein Verzeichnis.  
  
3.  Löschen der *[Content_types] .xml* Datei aus dem Verzeichnis.  
  
4.  Bearbeiten Sie das VSIX-Manifest aus, wie im vorherigen Verfahren dargestellt.  
  
5.  Fügen Sie die restlichen Dateien zu Ihrem Setup-Projekt hinzu.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Studio-Installer-Bereitstellung](https://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [Exemplarische Vorgehensweise: Erstellen einer benutzerdefinierten Aktion](/previous-versions/visualstudio/visual-studio-2010/d9k65z2d(v=vs.100))