---
title: "命令和參數 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b623f810-d871-49a5-b0f5-078cc3c34db6
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 命令和參數
建立連至資料來源的連接後，您可以執行命令，並使用 <xref:System.Data.Common.DbCommand> 物件從資料來源傳回結果。  您可以使用目前使用中 .NET Framework 資料提供者的其中一個命令建構函式 \(Constructor\) 來建立命令。  建構函式可以接受選擇性引數，例如要在資料來源執行的 SQL 陳述式、<xref:System.Data.Common.DbConnection> 物件或 <xref:System.Data.Common.DbTransaction> 物件。  此外，您也可以將這些物件設定為命令的屬性。  您還可以使用 `DbConnection` 物件的 <xref:System.Data.Common.DbConnection.CreateCommand%2A> 方法，針對特定連接建立命令。  您可以使用 <xref:System.Data.Common.DbCommand.CommandText%2A> 屬性來設定正由命令執行的 SQL 陳述式。  
  
 內含在 .NET Framework 中的每個 .NET Framework 資料提供者都有一個 `Command` 物件。  .NET Framework Data Provider for OLE DB 包含 <xref:System.Data.OleDb.OleDbCommand> 物件、.NET Framework Data Provider for SQL Server 包含 <xref:System.Data.SqlClient.SqlCommand> 物件、.NET Framework Data Provider for ODBC 包含 <xref:System.Data.Odbc.OdbcCommand> 物件，而 .NET Framework Data Provider for Oracle 包含 <xref:System.Data.OracleClient.OracleCommand> 物件。  
  
## 在本節中  
 [執行命令](../../../../docs/framework/data/adonet/executing-a-command.md)  
 說明 ADO.NET `Command` 物件，以及如何用它來針對資料來源執行查詢和命令。  
  
 [設定參數和參數資料類型](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 說明如何使用 `Command` 參數，包括方向、資料型別和參數語法。  
  
 [使用 CommandBuilders 產生命令](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md)  
 說明如何使用命令產生器，針對具有單一資料表 SELECT 命令的 `DataAdapter` 自動產生 INSERT、UPDATE 和 DELETE 命令。  
  
 [從資料庫取得單一數值](../../../../docs/framework/data/adonet/obtaining-a-single-value-from-a-database.md)  
 說明如何使用 `Command` 物件的 `ExecuteScalar` 方法，從資料庫查詢傳回單一值。  
  
 [使用命令來修改資料](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 說明如何使用資料提供者來執行預存程序 \(Stored Procedure\) 或資料定義語言 \(DDL\) 陳述式。  
  
## 請參閱  
 [DataAdapter 和 DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [DataSet、DataTable 及 DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [連接資料來源](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [ADO.NET Managed 提供者和資料集開發人員中心](http://go.microsoft.com/fwlink/?LinkId=217917)