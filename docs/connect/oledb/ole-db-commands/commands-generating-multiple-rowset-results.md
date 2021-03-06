---
title: 生成多个行集结果的命令 |Microsoft Docs
description: 生成多个行集结果的命令
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: oledb|ole-db-commands
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- multiple rowsets
- rowsets [OLE DB], multiple
- OLE DB Driver for SQL Server, commands
- OLE DB Driver for SQL Server, multiple rowsets
- commands [OLE DB]
- multiple-rowset results
author: pmasl
ms.author: Pedro.Lopes
manager: craigg
ms.openlocfilehash: 579fae980b0f612aa1317407f797be9d1ff02ed3
ms.sourcegitcommit: 50838d7e767c61dd0b5e677b6833dd5c139552f2
ms.translationtype: MTE75
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2018
ms.locfileid: "39109619"
---
# <a name="commands-generating-multiple-rowset-results"></a>生成多个行集结果的命令
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  SQL Server 的 OLE DB 驱动程序可以返回多个行集从[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]语句。 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 语句在以下条件下返回具有多个行集的结果：  
  
-   以单个命令的形式提交成批的 SQL 语句。  
  
-   存储过程实现一批 SQL 语句。  
  
## <a name="batches"></a>批处理  
 SQL Server 的 OLE DB 驱动程序将分号字符识别为 SQL 语句的批处理分隔符：  
  
```  
WCHAR*       wSQLString = L"SELECT * FROM Categories; "  
                          L"SELECT * FROM Products";  
```  
  
 通过一个批处理发送多个 SQL 语句比单独执行每个 SQL 语句更有效。 发送一个批处理减少了客户端和服务器之间的网络往返。  
  
## <a name="stored-procedures"></a>存储过程  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 为存储过程中的每个语句返回一个结果集，因此大多数 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 存储过程返回多个结果集。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 IMultipleResults 处理多个结果集](../../oledb/ole-db-commands/using-imultipleresults-to-process-multiple-result-sets.md)  
  
## <a name="see-also"></a>另请参阅  
 [命令](../../oledb/ole-db-commands/commands.md)  
  
  
