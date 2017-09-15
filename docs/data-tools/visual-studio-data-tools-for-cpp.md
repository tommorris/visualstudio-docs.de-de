---
title: Visual Studio data tools for C++ | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 3a3849d9-1bc7-47d1-805e-1755223ccba2
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 33a857c2d8585e2e8da9bcd9158190366a3b6830
ms.openlocfilehash: 2c7549c0d09c8f7892dbebe34a6fbe3bcb67d4be
ms.contentlocale: de-de
ms.lasthandoff: 09/07/2017

---
# <a name="visual-studio-data-tools-for-c"></a>Visual Studio data tools for C++
Native C++ can often provide the fastest performance when you are accessing data sources. However, data tooling for C++ applications in Visual Studio is not as rich as it is for .NET applications. For example, the data sources windows cannot be used to drag and drop data sources onto a C++ design surface. If you need an object-relational layer, you will have to write your own, or use a third-party product.  The same is true for data-binding functionality, although applications that use the Microsoft Foundation Class library can use some database classes, together with documents and views, to store data in memory and display it to the user. For more information, see [Data Access in Visual C++](https://msdn.microsoft.com/en-us/library/7wtdsdkh.aspx) .  
  
 To connect to SQL databases, native C++ applications can use the ODBC and OLE DB drivers and the ADO provider that are included with Windows. These can connect to any database that supports those interfaces. The ODBC driver is the standard. OLE DB is provided for backward compatibility. For more information on those data technologies, see [Windows Data Access Components](https://msdn.microsoft.com/en-us/library/windows/desktop/aa968814\(v=vs.85\).aspx)  
  
 To take advantage of custom functionality in SQL Server 2005 and later, use the [SQL Server Native Client](https://msdn.microsoft.com/en-us/sqlserver/aa937733). The native client also contains the SQL Server ODBC driver and the SQL Server OLE DB provider in one native dynamic link library (DLL). These support applications using native-code APIs (ODBC, OLE DB and ADO) to Microsoft SQL Server.  SQL Server Native Client installs with SQL Server Data Tools. The programming guide is here: [SQL Server Native Client Programming](https://msdn.microsoft.com/en-us/library/ms130892.aspx).  
  
## <a name="to-connect-to-localdb-through-odbc-and-sql-native-client-from-a-c-application"></a>To connect to localDB through ODBC and SQL Native Client from a C++ application  
  
1.  Install SQL Server Data Tools.  
  
2.  If you need a sample SQL database to connect to, download the Northwind database and unzip it to a new location.  
  
3.  Use SQL Server Management Studio to attach the unzipped Northwind.mdf file to localDB. When SQL Server Management Studio starts, connect to (localdb)\MSSQLLocalDB.  
  
     ![SSMS connect dialog](../data-tools/media/raddata-ssms-connect-dialog.png "raddata SSMS connect dialog")  
  
     Then right-click on the localdb node in the left pane, and choose **Attach**.  
  
     ![SSMS Attach database](../data-tools/media/raddata-ssms-attach-database.png "raddata SSMS Attach database")  
  
4.  Download the ODBC Windows SDK Sample, and unzip it to a new location. This sample shows the basic ODBC commands that are used to connect to a database and issue queries and commands. You can learn more about those functions in the [Microsoft Open Database Connectivity (ODBC)](https://msdn.microsoft.com/en-us/library/windows/desktop/ms710252\(v=vs.85\).aspx). When you first load the solution (it's in the C++ folder), Visual Studio will offer to upgrade the solution to the current version of Visual Studio. Click **Yes**.  
  
5.  To use the native client, you need its header file and lib file. These files contain functions and definitions specific to SQL Server, beyond the ODBC functions defined in sql.h. In **Project** > **Properties** > **VC++ Directories**, add the following include directory:  
  
 **\<system drive>:\Program Files\Microsoft SQL Server\110\SDK\Include**     And this library directory:  
  
 **c:\Program Files\Microsoft SQL Server\110\SDK\Lib**  
  
6.  Add these lines in odbcsql.cpp. The #define prevents irrelevant OLE DB definitions from being compiled.  
  
    ```C++  
    #define _SQLNCLI_ODBC_  
    #include <sqlncli.h>  
    ```  
  
     Note that the sample does not actually use any of the native client functionality, so the preceding steps are not necessary for it to compile and run. But the project is now configured for you to use this functionality. For more information, see [SQL Server Native Client Programming](https://msdn.microsoft.com/en-us/library/ms130892\(v=sql.130\).aspx).  
  
7.  Specify which driver to use in the ODBC subsystem. The sample passes the DRIVER connection string attribute in as a command line argument. In **Project** > **Properties** > **Debugging**, add this command argument:  
  
    ```C++  
    DRIVER="SQL Server Native Client 11.0"  
    ```  
  
8.  Press F5 to build and run the application. You should see a dialog box from the driver that prompts you to enter a database. Enter `(localdb)\MSSQLLocalDB`, and check **Use Trusted Connection**. Press **OK**. You should see a console with messages that indicate a successful connection. You should also see a command prompt where you can type in a SQL statement. The following screen shows an example query and the results:  
  
     ![ODBC Sample query output](../data-tools/media/raddata-odbc-sample-query-output.png "raddata ODBC Sample query output")  
  
## <a name="see-also"></a>See Also  
 [Accessing data in Visual Studio](../data-tools/accessing-data-in-visual-studio.md)