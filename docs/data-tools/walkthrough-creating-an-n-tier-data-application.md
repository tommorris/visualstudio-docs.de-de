---
title: 'Exemplarische Vorgehensweise: Erstellen einer N-Tier-Datenanwendung'
ms.date: 09/08/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- n-tier applications, creating
- n-tier applications, walkthroughs
ms.assetid: d15e4d31-2839-48d9-9e0e-2e73404d82a2
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 007a0a85bf9d7200860194b881a3d0505f6bee45
ms.sourcegitcommit: f37affbc1b885dfe246d4b2c295a6538b383a0ca
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37175342"
---
# <a name="walkthrough-create-an-n-tier-data-application"></a>Exemplarische Vorgehensweise: Erstellen einer n-Tier-datenanwendung
*N-schichtige* -datenanwendungen sind Anwendungen, die auf Daten zugreifen und werden in mehrere logische Ebenen, getrennt oder *Ebenen*. Die Aufteilung der Anwendungskomponenten in verschiedene Ebenen erhöht die Verwaltbarkeit und die Skalierbarkeit der Anwendung. Auf diese Weise wird das Einarbeiten neuer, eine einzelne Ebene betreffender Technologien vereinfacht, ein erneutes Entwerfen der Anwendung ist nicht notwendig. Zur N-Tier-Architektur gehören eine Präsentationsebene, eine mittlere Ebene und eine Datenebene. Die mittlere Ebene enthält eine Datenzugriffsschicht, eine Geschäftslogikschicht und gemeinsame Komponenten, wie beispielsweise Authentifizierung und Validierung. Die Datenebene enthält eine relationale Datenbank. N-Tier-Anwendungen speichern vertrauliche Informationen in der Datenzugriffsschicht der mittleren Ebene, um diese von Endbenutzern, die auf die Präsentationsebene zugreifen, getrennt zu halten. Weitere Informationen finden Sie unter [Übersicht über N-schichtige datenanwendungen](../data-tools/n-tier-data-applications-overview.md).

Eine Möglichkeit zum Trennen der verschiedenen Ebenen einer N-Tier-Anwendung besteht im Erstellen separater Projekte für jede Ebene, die in der Anwendung enthalten sein soll. Typisierte DataSets enthalten eine `DataSet Project`-Eigenschaft, mit der festgelegt wird, in welche Projekte der erzeugte DataSet-Code und der erzeugte `TableAdapter`-Code eingefügt werden.

In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie zum Trennen von Datasets und `TableAdapter` Code in einzelne Klassenbibliotheksprojekte mithilfe der **Dataset-Designer**. Nachdem Sie das Dataset und TableAdapter-Code zu trennen, Sie erstellen eine [Windows Communication Foundation-Dienste und WCF Data Services in Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md) Dienst in der Datenzugriffsebene aufrufen. Abschließend erstellen Sie eine Windows Forms-Anwendung als Präsentationsebene. Diese Ebene greift auf Daten des Datendiensts zu.

Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Schritte aus:

-   Erstellen Sie eine neue n-Tier-Projektmappe, die mehrere Projekte enthält.

-   Hinzufügen von zwei Klassenbibliotheksprojekten zur N-Tier-Projektmappe.

-   Erstellen eines typisierten Datasets mithilfe der **Assistenten zur Datenquellenkonfiguration**.

-   Trennen von generierten [TableAdapters](create-and-configure-tableadapters.md) und Dataset-Code in einzelne Projekte.

-   Erstellen eines WCF (Windows Communication Foundation)-Diensts für Aufrufe an die Datenzugriffsebene.

-   Erstellen von Dienstfunktionen, um Daten von der Datenzugriffsebene abzurufen.

-   Erstellen einer Windows Forms-Anwendung, die als Präsentationsebene dient.

-   Erstellen von Windows Forms-Steuerelementen, die an die Datenquelle gebunden werden.

-   Schreiben von Code zum Füllen der Datentabellen.

![Link zum Video](../data-tools/media/playvideo.gif) eine Videoversion dieses Themas finden Sie unter [Video How to: Erstellen einer n-Tier-datenanwendung](http://go.microsoft.com/fwlink/?LinkId=115188).

## <a name="prerequisites"></a>Erforderliche Komponenten
In dieser exemplarischen Vorgehensweise verwendet SQL Server Express LocalDB und der Beispieldatenbank Northwind.

1.  Wenn Sie SQL Server Express LocalDB nicht haben, installieren Sie es entweder über die [Downloadseite für SQL Server Express](https://www.microsoft.com/sql-server/sql-server-editions-express), oder über die **Visual Studio-Installer**. In der **Visual Studio-Installer**, können Sie SQL Server Express LocalDB installieren, als Teil der **.NET Desktopentwicklung** Workload oder als eine einzelne Komponente.

2.  Installieren der Northwind-Beispieldatenbank mit folgenden Schritten:

    1. Öffnen Sie in Visual Studio die **Objekt-Explorer von SQL Server** Fenster. (**Objekt-Explorer von SQL Server** installiert ist, als Teil der **datenspeicherung und-Verarbeitung** Workload im Visual Studio-Installer.) Erweitern Sie die **SQL Server** Knoten. Mit der rechten Maustaste auf der LocalDB-Instanz, und wählen Sie **neue Abfrage**.

       Ein Abfrage-Editor-Fenster wird geöffnet.

    2. Kopieren der [Northwind Transact-SQL-Skript](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) in die Zwischenablage. Dieses T-SQL-Skript wird die Northwind-Datenbank von Grund auf neu erstellt und mit Daten aufgefüllt.

    3. Fügen Sie das T-SQL-Skript im Abfrage-Editor, und wählen Sie dann die **Execute** Schaltfläche.

       Klicken Sie nach kurzer Zeit die Ausführung die Abfrage abgeschlossen ist, und die Northwind-Datenbank wird erstellt.

## <a name="create-the-n-tier-solution-and-class-library-to-hold-the-dataset-dataentitytier"></a>Erstellen der n-Tier-Projektmappe und der Klassenbibliothek um das Dataset (DataEntityTier)
 Im ersten Schritt dieser exemplarischen Vorgehensweise werden eine Projektmappe und zwei Klassenbibliotheksprojekte erstellt. Die erste Klassenbibliothek enthält das Dataset (die generierte typisierte `DataSet` -Klasse und Datentabellen, die die Daten der Anwendung enthalten). Dieses Projekt wird als Datenentitätsschicht der Anwendung verwendet und befindet sich normalerweise in der mittleren Ebene. Das Dataset, das ursprüngliche Dataset erstellt und trennt automatisch den Code, in zwei Klassenbibliotheken.

> [!NOTE]
>  Achten Sie darauf, dass Sie das Projekt und Projektmappe ordnungsgemäß benannt wurden, bevor Sie auf **OK**. Das erleichtert die Durchführung der exemplarischen Vorgehensweise.

### <a name="to-create-the-n-tier-solution-and-dataentitytier-class-library"></a>So erstellen Sie die N-Tier-Projektmappe und die DataEntityTier-Klassenbibliothek

1. In Visual Studio auf die **Datei** , wählen Sie im Menü **neu** > **Projekt**.

2. Erweitern Sie entweder **Visual C#-** oder **Visual Basic** wählen Sie im linken Bereich **Windows Desktop**.

3. Wählen Sie im mittleren Bereich die **Klassenbibliothek** Projekttyp.

4. Nennen Sie das Projekt **DataEntityTier**.

5. Nennen Sie die Projektmappe **NTierWalkthrough**, und wählen Sie dann **OK**.

     Eine Projektmappe NTierWalkthrough mit dem Projekt DataEntityTier wird erstellt und hinzugefügt **Projektmappen-Explorer**.

## <a name="create-the-class-library-to-hold-the-tableadapters-dataaccesstier"></a>Erstellen der Klassenbibliothek für die TableAdapter (DataAccessTier) enthalten.
 Nach dem Erstellen des Projekts DataEntityTier besteht der nächste Schritt darin, ein zweites Klassenbibliotheksprojekt zu erstellen. Dieses Projekt enthält die generierten TableAdapter und wird aufgerufen, die *Datenzugriffsebene* der Anwendung. Die Datenzugriffsebene enthält die zum Herstellen einer Verbindung mit der Datenbank notwendigen Informationen und befindet sich normalerweise in der mittleren Ebene.

### <a name="to-create-a-separate-class-library-for-the-tableadapters"></a>Erstellen Sie eine separate Klassenbibliothek für die TableAdapter-Steuerelemente

1.  Mit der rechten Maustaste auf die Projektmappe im **Projektmappen-Explorer** , und wählen Sie **hinzufügen** > **neues Projekt**.

2.  In der **neues Projekt** im Dialogfeld im mittleren Bereich wählen **Klassenbibliothek**.

3.  Nennen Sie das Projekt **DataAccessTier** , und wählen Sie **OK**.

     Das Projekt DataAccessTier wird erstellt und zur Projektmappe NTierWalkthrough hinzugefügt.

## <a name="create-the-dataset"></a>Erstellen Sie das Dataset
 Der nächste Schritt besteht darin, ein typisiertes DataSet zu erstellen. Typisierte Datasets werden mit beiden Dataset-Klassen erstellt (einschließlich `DataTables` Klassen) und die `TableAdapter` Klassen in einem einzelnen Projekt. (Jede Klasse wird in einer einzelnen Datei generiert.) Wenn Sie die Datasets und TableAdapters in verschiedene Projekte trennen, ist es die Dataset-Klasse, die in ein anderes Projekt, sodass verschoben werden die `TableAdapter` Klassen im ursprünglichen Projekt. Aus diesem Grund erstellen Sie das Dataset im Projekt, das letztendlich die TableAdapter (DataAccessTier-Projekt) enthalten wird. Erstellen Sie das Dataset mithilfe der **Assistenten zur Datenquellenkonfiguration**.

> [!NOTE]
>  Sie benötigen Zugriff auf die Beispieldatenbank Northwind, um die Verbindung herstellen zu können. Weitere Informationen zum Einrichten der Northwind-Beispieldatenbank, finden Sie unter [Vorgehensweise: Installieren von Beispieldatenbanken](../data-tools/installing-database-systems-tools-and-samples.md).

### <a name="to-create-the-dataset"></a>So erstellen Sie das DataSet

1.  Wählen Sie die **DataAccessTier** in **Projektmappen-Explorer**.

2.  Auf der **Daten** , wählen Sie im Menü **Datenquellen anzeigen**.

3.  In der **Datenquellen** wählen Sie im Fenster **neue Datenquelle hinzufügen** zum Starten der **Assistenten zur Datenquellenkonfiguration**.

4.  Auf der **wählen Sie einen Datenquellentyp** Seite **Datenbank** und wählen Sie dann **Weiter**.

5.  Auf der **wählen Sie Ihre Datenverbindung** führen eine der folgenden Aktionen aus:

     Wenn in der Dropdownliste eine Datenverbindung zur Beispieldatenbank „Northwind“ verfügbar ist, wählen Sie diese aus.

     - oder - 

     Wählen Sie **neue Verbindung** zum Öffnen der **Verbindung hinzufügen** Dialogfeld.

6.  Wählen Sie die Option Einbeziehung vertraulicher Daten ein, und wählen Sie dann, wenn die Datenbank ein Kennwort erfordert, **Weiter**.

    > [!NOTE]
    >  Wenn Sie eine lokale Datenbankdatei ausgewählt haben (statt eine Verbindung mit SQL Server herzustellen), werden Sie möglicherweise gefragt, ob Sie die Datei zum Projekt hinzufügen möchten. Wählen Sie **Ja** die Datenbankdatei zum Projekt hinzufügen.

7.  Wählen Sie **Weiter** auf die **Verbindungszeichenfolge in der Anwendungskonfigurationsdatei speichern** Seite.

8.  Erweitern Sie auf der Seite **Datenbankobjekte auswählen** den Knoten **Tabellen** .

9.  Wählen Sie die Kontrollkästchen für die **Kunden** und **Bestellungen** -Tabelle aus, und wählen Sie dann **Fertig stellen**.

     NorthwindDataSet wird zur DataAccessTier hinzugefügt und wird in der **Datenquellen** Fenster.

## <a name="separate-the-tableadapters-from-the-dataset"></a>Trennen Sie die TableAdapters im DataSet
 Nach dem Erstellen des DataSets wird die generierte DataSet-Klasse von den TableAdaptern getrennt. Sie tun dies durch Festlegen der **DataSet-Projekt** Eigenschaft auf den Namen des Projekts, dem die getrennten Dataset-Klassen gespeichert.

### <a name="to-separate-the-tableadapters-from-the-dataset"></a>So trennen Sie die TableAdapter vom DataSet

1.  Doppelklicken Sie auf **NorthwindDataSet.xsd** in **Projektmappen-Explorer** , öffnen Sie das Dataset in den **Dataset-Designer**.

2.  Wählen Sie einen leeren Bereich im Designer.

3.  Suchen Sie die **DataSet-Projekt** Knoten in der **Eigenschaften** Fenster.

4.  In der **DataSet-Projekt** Liste **DataEntityTier**.

5.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.

 DataSet und TableAdapter werden in die zwei Klassenbibliotheksprojekte aufgeteilt. Das Projekt, das ursprünglich das gesamte Dataset enthalten (`DataAccessTier`) enthält jetzt nur noch die TableAdapter. Das Projekt festgelegt wird, der **DataSet-Projekt** Eigenschaft (`DataEntityTier`) enthält das typisierte Dataset: *NorthwindDataSet.Dataset.Designer.vb* (oder  *NorthwindDataSet.Dataset.Designer.cs*).

> [!NOTE]
>  Bei einer Abtrennung der Datasets und TableAdapters (durch Festlegen der **DataSet-Projekt** Eigenschaft), werden vorhandene partielle Dataset-Klassen im Projekt nicht automatisch verschoben werden. Vorhandene partielle DataSet-Klassen müssen manuell in das DataSet-Projekt verschoben werden.

## <a name="create-a-new-service-application"></a>Erstellen einer neuen Dienstanwendung
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie auf die Datenzugriffsebene mit einem WCF-Dienst zugreifen kann, erstellen wir eine neue WCF-dienstanwendung.

### <a name="to-create-a-new-wcf-service-application"></a>So erstellen Sie eine neue WCF-Dienstanwendung

1.  Mit der rechten Maustaste auf die Projektmappe im **Projektmappen-Explorer** , und wählen Sie **hinzufügen** > **neues Projekt**.

2.  In der **neues Projekt** im Dialogfeld im linken Bereich auf **WCF**.  Wählen Sie im mittleren Bereich **WCF-Dienstbibliothek**.

3.  Nennen Sie das Projekt **"DataService"** , und wählen Sie **OK**.

     Das Projekt DataService wird erstellt und zur Projektmappe NTierWalkthrough hinzugefügt.

## <a name="create-methods-in-the-data-access-tier-to-return-the-customers-and-orders-data"></a>Erstellen Sie Methoden in der Datenzugriffsebene, die Daten Customers und Orders zurückgibt
 Der Datendienst muss zwei Methoden in der Datenzugriffsebene aufrufen: `GetCustomers` und `GetOrders`. Diese Methode gibt zurück, den Northwind `Customers` und `Orders` Tabellen. Erstellen der `GetCustomers` und `GetOrders` Methoden in der `DataAccessTier` Projekt.

### <a name="to-create-a-method-in-the-data-access-tier-that-returns-the-customers-table"></a>So erstellen Sie eine Methode in der Datenzugriffsebene, die die Tabelle Customers zurückgibt

1.  In **Projektmappen-Explorer**, doppelklicken Sie auf **NorthwindDataset.xsd** um das Dataset öffnen.

2.  Mit der rechten Maustaste **CustomersTableAdapter** , und klicken Sie auf **Abfrage hinzufügen**.

3.  Auf der **wählen Sie einen Befehlstyp aus** Seite, übernehmen Sie den Standardwert des **SQL-Anweisungen** , und klicken Sie auf **Weiter**.

4.  Auf der **Abfragetyp auswählen** Seite, übernehmen Sie den Standardwert des **wählen Sie die Zeilen zurückgibt** , und klicken Sie auf **Weiter**.

5.  Auf der **Geben Sie eine SQL-SELECT-Anweisung** Seite, lassen Sie die Standardabfrage, und klicken Sie auf **Weiter**.

6.  Auf der **zu generierende Methode auswählen** geben **GetCustomers** für die **Methodenname** in die **DataTable zurückgeben** Abschnitt.

7.  Klicken Sie auf **Fertig stellen**.

### <a name="to-create-a-method-in-the-data-access-tier-that-returns-the-orders-table"></a>So erstellen Sie eine Methode in der Datenzugriffsebene, die die Tabelle Orders zurückgibt

1.  Mit der rechten Maustaste **OrdersTableAdapter** , und klicken Sie auf **Abfrage hinzufügen**.

2.  Auf der **wählen Sie einen Befehlstyp aus** Seite, übernehmen Sie den Standardwert des **SQL-Anweisungen** , und klicken Sie auf **Weiter**.

3.  Auf der **Abfragetyp auswählen** Seite, übernehmen Sie den Standardwert des **wählen Sie die Zeilen zurückgibt** , und klicken Sie auf **Weiter**.

4.  Auf der **Geben Sie eine SQL-SELECT-Anweisung** Seite, lassen Sie die Standardabfrage, und klicken Sie auf **Weiter**.

5.  Auf der **zu generierende Methode auswählen** geben **GetOrders** für die **Methodenname** in die **DataTable zurückgeben** Abschnitt.

6.  Klicken Sie auf **Fertig stellen**.

7.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.

## <a name="add-a-reference-to-the-data-entity-and-data-access-tiers-to-the-data-service"></a>Fügen Sie einen Verweis auf die Datenentitätsebene und die Datenzugriffsebene an den Datendienst hinzu.
 Da der Datendienst Informationen von Dataset und TableAdaptern erfordert, fügen Sie Verweise auf die **DataEntityTier** und **DataAccessTier** Projekte.

### <a name="to-add-references-to-the-data-service"></a>So fügen Sie Verweise zum Datendienst hinzu

1.  Mit der rechten Maustaste **"DataService"** in **Projektmappen-Explorer** , und klicken Sie auf **Verweis hinzufügen**.

2.  Klicken Sie auf die **Projekte** Registerkarte die **Verweis hinzufügen** Dialogfeld.

3.  Wählen Sie die Optionen der **DataAccessTier** und **DataEntityTier** Projekte.

4.  Klicken Sie auf **OK**.

## <a name="add-functions-to-the-service-to-call-the-getcustomers-and-getorders-methods-in-the-data-access-tier"></a>Hinzufügen von Funktionen mit dem Dienst die GetCustomers und GetOrders-Methode in der Datenzugriffsebene aufrufen
 Nachdem die Datenzugriffsebene die Methoden zur Rückgabe der Daten enthält, müssen Sie im Datendienst Methoden erstellen, um die Methoden in der Datenzugriffsebene aufzurufen.

> [!NOTE]
>  In C#-Projekten muss ein Verweis auf die `System.Data.DataSetExtensions`-Assembly für die Kompilierung des nachfolgenden Codes hinzugefügt werden.

### <a name="to-create-the-getcustomers-and-getorders-functions-in-the-data-service"></a>So erstellen Sie im Datendienst die GetCustomers-Funktion und die GetOrders-Funktion

1.  In der **"DataService"** Projekt, doppelklicken Sie auf **"IService1.vb"** oder **IService1.cs**.

2.  Fügen Sie den folgenden Code unter der **Hier Dienstvorgänge hinzufügen** Kommentar:

    ```vb
    <OperationContract()> _
    Function GetCustomers() As DataEntityTier.NorthwindDataSet.CustomersDataTable

    <OperationContract()> _
    Function GetOrders() As DataEntityTier.NorthwindDataSet.OrdersDataTable
    ```

    ```csharp
    [OperationContract]
    DataEntityTier.NorthwindDataSet.CustomersDataTable GetCustomers();

    [OperationContract]
    DataEntityTier.NorthwindDataSet.OrdersDataTable GetOrders();
    ```

3.  Doppelklicken Sie im Projekt DataService auf **Service1.vb** (oder **Service1.cs**).

4.  Fügen Sie den folgenden Code der **"Service1"** Klasse:

    ```vb
    Public Function GetCustomers() As DataEntityTier.NorthwindDataSet.CustomersDataTable Implements IService1.GetCustomers
        Dim CustomersTableAdapter1 As New DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter
        Return CustomersTableAdapter1.GetCustomers()
    End Function

    Public Function GetOrders() As DataEntityTier.NorthwindDataSet.OrdersDataTable Implements IService1.GetOrders
        Dim OrdersTableAdapter1 As New DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter
        Return OrdersTableAdapter1.GetOrders()
    End Function
    ```

    ```csharp
    public DataEntityTier.NorthwindDataSet.CustomersDataTable GetCustomers()
    {
        DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter
             CustomersTableAdapter1
            = new DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter();
        return CustomersTableAdapter1.GetCustomers();
    }
    public DataEntityTier.NorthwindDataSet.OrdersDataTable GetOrders()
    {
        DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter
             OrdersTableAdapter1
            = new DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter();
        return OrdersTableAdapter1.GetOrders();
    }
    ```

5.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.

## <a name="create-a-presentation-tier-to-display-data-from-the-data-service"></a>Erstellen einer Präsentationsebene zum Anzeigen von Daten aus dem Datendienst
 Nun, dass die Projektmappe enthält Zugriff auf die Ebene der Datendienst mit Methoden, die in den Daten aufrufen, erstellen ein anderes Projekt, das den Datendienst aufruft und für Benutzer bereitzustellen. Erstellen Sie für diese exemplarische Vorgehensweise eine Windows Forms-Anwendung als Präsentationsebene der N-Tier-Anwendung.

### <a name="to-create-the-presentation-tier-project"></a>So erstellen Sie das Präsentationsebenenprojekt

1.  Mit der rechten Maustaste auf die Projektmappe im **Projektmappen-Explorer** , und wählen Sie **hinzufügen** > **neues Projekt**.

2.  In der **neues Projekt** im Dialogfeld im linken Bereich auf **Windows Desktop**. Wählen Sie im mittleren Bereich **Windows Forms-App**.

3.  Nennen Sie das Projekt **PresentationTier** , und klicken Sie auf **OK**.

    Das Projekt PresentationTier wird erstellt und zur Projektmappe NTierWalkthrough hinzugefügt.

## <a name="set-the-presentationtier-project-as-the-startup-project"></a>Das Projekt PresentationTier als Startprojekt festlegen
Legen wir die **PresentationTier** Projekt das Startprojekt für die Lösung sein, da es sich um die aktuelle Clientanwendung handelt, stellt und mit den Daten interagiert.

### <a name="to-set-the-new-presentation-tier-project-as-the-startup-project"></a>Das neue Präsentationsebenenprojekt als Startprojekt festlegen

-   In **Projektmappen-Explorer**, mit der rechten Maustaste **PresentationTier** , und klicken Sie auf **als Startprojekt festlegen**.

## <a name="add-references-to-the-presentation-tier"></a>Fügen Sie Verweise auf die Präsentationsebene hinzu
 Die Client-Anwendung PresentationTier erfordert einen Dienstverweis auf den Datendienst, um den Zugriff auf die Methoden im Dienst. Außerdem ist ein Verweis auf das DataSet erforderlich, um die Typfreigabe des WCF-Diensts zu aktivieren. Erst nach Aktivierung der Typfreigabe durch den Datendienst ist zu partiellen Dataset-Klassen hinzugefügter Code nicht auf der Präsentationsebene verfügbar. Da Sie in der Regel Code, z. B. Validierungscode zu den Spalten- und Zeilenänderungsereignissen einer Datentabelle hinzufügen, ist es wahrscheinlich, dass Sie diesen Code aus dem Client zugreifen möchten.

### <a name="to-add-a-reference-to-the-presentation-tier"></a>So fügen Sie einen Verweis auf die Präsentationsebene hinzu

1.  In **Projektmappen-Explorer**, mit der rechten Maustaste **PresentationTier** , und wählen Sie **Verweis hinzufügen**.

2.  In der **Verweis hinzufügen** wählen Sie im Dialogfeld die **Projekte** Registerkarte.

3.  Wählen Sie **DataEntityTier** , und wählen Sie **OK**.

### <a name="to-add-a-service-reference-to-the-presentation-tier"></a>So fügen Sie einen Dienstverweis auf die Präsentationsebene hinzu

1.  In **Projektmappen-Explorer**, mit der rechten Maustaste **PresentationTier** , und wählen Sie **Hinzufügen eines Dienstverweises**.

2.  In der **Hinzufügen eines Dienstverweises** wählen Sie im Dialogfeld **Discover**.

3.  Wählen Sie **"Service1"** , und wählen Sie **OK**.

    > [!NOTE]
    >  Wenn Sie mehrere Dienste auf dem aktuellen Computer verfügen, wählen Sie den Dienst, die Sie zuvor in dieser exemplarischen Vorgehensweise erstellt haben (der Dienst, enthält die `GetCustomers` und `GetOrders` Methoden).

## <a name="add-datagridviews-to-the-form-to-display-the-data-returned-by-the-data-service"></a>Hinzufügen von DataGridViews zum Formular zum Anzeigen der Daten, die vom Datendienst zurückgegeben
 Nach dem Hinzufügen der Dienstverweis zum Datendienst, der **Datenquellen** Fenster wird automatisch aufgefüllt, mit den Daten, die vom Dienst zurückgegeben wird.

### <a name="to-add-two-data-bound-datagridviews-to-the-form"></a>So fügen Sie zwei datengebundene DataGridViews zum Formular hinzu

1.  In **Projektmappen-Explorer**, wählen die **PresentationTier** Projekt.

2.  In der **Datenquellen** Fenster erweitern **NorthwindDataSet** und suchen Sie nach der **Kunden** Knoten.

3.  Ziehen Sie die **Kunden** Knoten auf Form1.

4.  In der **Datenquellen** Fenster erweitern Sie die **Kunden** Knoten und suchen Sie den zugehörigen **Bestellungen** Knoten (die **Bestellungen** geschachtelten Knoten die  **Kunden** Knoten).

5.  Ziehen Sie den zugehörigen **Bestellungen** Knoten auf Form1.

6.  Erstellen Sie einen `Form1_Load`-Ereignishandler, indem Sie auf einen leeren Bereich des Formulars doppelklicken.

7.  Fügen Sie dem `Form1_Load`-Ereignishandler den folgenden Code hinzu.

    ```vb
    Dim DataSvc As New ServiceReference1.Service1Client
    NorthwindDataSet.Customers.Merge(DataSvc.GetCustomers)
    NorthwindDataSet.Orders.Merge(DataSvc.GetOrders)
    ```

    ```csharp
    ServiceReference1.Service1Client DataSvc =
        new ServiceReference1.Service1Client();
    northwindDataSet.Customers.Merge(DataSvc.GetCustomers());
    northwindDataSet.Orders.Merge(DataSvc.GetOrders());
    ```

## <a name="increase-the-maximum-message-size-allowed-by-the-service"></a>Erhöhen Sie die maximale Nachrichtengröße, die vom Dienst zugelassenen
Der Standardwert für `maxReceivedMessageSize` ist nicht groß genug zum Speichern der Daten abgerufen, die von der `Customers` und `Orders` Tabellen. In den folgenden Schritten müssen Sie den Wert in 6553600 erhöhen. Ändern Sie den Wert auf dem Client den Dienstverweis automatisch aktualisiert.

> [!NOTE]
>  Die niedrigere Standardgröße dient dazu, die Anfälligkeit für Denial-of-Service (DoS)-Angriffe zu verringern. Weitere Informationen finden Sie unter <xref:System.ServiceModel.WSHttpBindingBase.MaxReceivedMessageSize%2A>.

### <a name="to-increase-the-maxreceivedmessagesize-value"></a>So erhöhen Sie den maxReceivedMessageSize-Wert

1.  In **Projektmappen-Explorer**, doppelklicken Sie auf die **"App.config"** Datei die **PresentationTier** Projekt.

2.  Suchen Sie die **MaxReceivedMessage** Größenattribut, und ändern Sie den Wert auf `6553600`.

## <a name="test-the-application"></a>Testen der Anwendung
Führen Sie die Anwendung durch Drücken von **F5**. Die Daten aus der `Customers` und `Orders` Tabellen aus dem Datendienst abgerufen und im Formular angezeigt.

## <a name="next-steps"></a>Nächste Schritte
 Abhängig von den Anforderungen Ihrer Anwendung können nach dem Speichern der verknüpften Daten in der Windows-Anwendung weitere Schritte sinnvoll sein. Beispielsweise können Sie der Anwendung folgende Erweiterungen hinzufügen:

-   Hinzufügen der Validierung zum DataSet.

-   Hinzufügen von zusätzlichen Methoden zum Dienst für das Aktualisieren der Daten in der Datenbank.

## <a name="see-also"></a>Siehe auch

- [Arbeiten mit Datasets in N-Tier-Anwendungen](../data-tools/work-with-datasets-in-n-tier-applications.md)
- [Hierarchische Aktualisierung](../data-tools/hierarchical-update.md)
- [Zugreifen auf Daten in Visual Studio](../data-tools/accessing-data-in-visual-studio.md)