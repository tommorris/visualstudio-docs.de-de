---
title: Speichern von symbolischen Informationen mittels Leistungsdatendateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- packsymbols, in profiling tools reports
- profiling tools, packsymbols
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 15a1a6888ca35df54ff6073aefaf686327b4cd8a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2018
ms.locfileid: "31584931"
---
# <a name="saving-symbol-information-with-performance-data-files"></a>Speichern von symbolischen Informationen mittels Profilerstellungsdatendateien

Wenn Sie die Visual Studio-IDE zur Analyse von Dateien verwenden und Ihre VSP-Datei auf einen anderen Computer verschieben möchten, müssen Sie die Leistungsprojekteinstellungen so festlegen, dass Symbole in Ihrer Berichtsdatei gespeichert oder *serialisiert* werden. Dadurch vergrößert sich die Berichtsdatei. Die Serialisierung von Symbolen ist aus zwei Gründen erforderlich:

- Einbetten von Codesymbolen in einen Leistungsbericht, bevor die Zielassemblys an ihrem Speicherort im temporären Speicher verloren gehen.

- Beibehalten von Symbolen, sodass der Leistungsbericht vom profilierten Computer portierbar ist und die gleichen Informationen ausgibt, wenn der Bericht zur Analyse auf einem anderen Computer geöffnet wird, der andere Symbole haben kann.

Sie können Symbole über die Visual Studio-IDE oder über die Befehlszeile serialisieren:

- Zum Serialisieren von Symbolen im [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]-IDE zeigen Sie auf **Extras** in der Menüleiste, und klicken Sie dann auf **Optionen**. Wählen Sie im Fenster **Optionen** **Leistungstools** aus, und aktivieren Sie das Kontrollkästchen **Symbolinformationen automatisch serialisieren**.

- PACKSYMBOLS ist die entsprechende Befehlszeilenoption, wenn Sie Berichtsdateien speichern. Zum Serialisieren von Symbolen geben Sie **vsperfreport /summary:all /packsymbols filename.vsp** ein.

## <a name="troubleshooting-symbol-problems"></a>Problembehandlung bei Symbolen

Wenn Sie im eigenen Code keine Symbole sehen, sind einige allgemeine Lösungen verfügbar:

- Führen Sie vsperfreport /debugsympath auf einer Befehlszeile aus, um eine vollständige Liste der Speicherorte, in die Profilerkomponenten Symbolinformationen laden, und Informationen dazu anzuzeigen, ob die verwendeten Symboldateien mit den Dateien übereinstimmen, die Ihr Projekt verwendet.

- Stellen Sie sicher, dass Sie vsperfreport mit dem Flag /PACKSYMBOLS ausführen, bzw. dass Sie im [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]-IDE die Option für die Serialisierung von Symbolinformationen in den allgemeinen Leistungs-Explorer-Optionen ausgewählt haben.

- Wenn Sie Typdaten erfasst haben, fügen Sie der vsperfreport-Befehlszeile /SUMMARY:TYPE hinzu.

 Wenn Symbole von Windows oder anderen Microsoft-Programmen nicht angezeigt werden:

- Stellen Sie sicher, dass Sie den Pfad des Windows-Symbolcaches festgelegt haben. Führen Sie eine der folgenden Schritte durch, um den Symbolcachepfad festzulegen:

  - Legen Sie die Debugger-> Symbole-Option im [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]-IDE auf den richtigen Pfad fest.

  - Fügen Sie der VSPerfReport-Befehlszeile die Option -symbolpath hinzu, um Ihre Symbole einzuschließen.

- Wenn keine Symbole in [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] angezeigt werden, stellen Sie sicher, dass Sie den Symbolserver ordnungsgemäß für den ASP-Server eingerichtet haben.

## <a name="repacking-symbols"></a>Erneutes Packen von Symbolen

Wenn Sie Symbole erneut in einen Bericht packen möchten, können Sie dazu das Befehlszeilentool VsPerfReport verwenden. Verwenden Sie folgende Befehlszeilen:

VsPerfReport -clearpackedsymbols filename.vsp

VsPerfReport -packsymbols -summary:all filename.vsp

## <a name="see-also"></a>Siehe auch

[Speichern und Exportieren von Daten aus Leistungstools](../profiling/saving-and-exporting-performance-tools-data.md)  
[Gewusst wie: Verweisen auf Windows-Symbolinformationen](../profiling/how-to-reference-windows-symbol-information.md)  
[VSPerfReport](../profiling/vsperfreport.md)