---
title: 使用 IOpenRowset 创建行集 |Microsoft Docs
description: 使用 IOpenRowset 接口的 OLE DB 驱动程序的 SQL Server 中创建行集
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: oledb|ole-db-rowsets
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IOpenRowset interface
- rowsets [OLE DB], creating
- OLE DB Driver for SQL Server, rowsets
- OLE DB rowsets, creating
author: pmasl
ms.author: Pedro.Lopes
manager: craigg
ms.openlocfilehash: 53a9b42461fd9c7ba194af62f86d8670b8539ddf
ms.sourcegitcommit: 50838d7e767c61dd0b5e677b6833dd5c139552f2
ms.translationtype: MTE75
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2018
ms.locfileid: "39105943"
---
# <a name="creating-a-rowset-with-iopenrowset"></a>使用 IOpenRowset 创建行集
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  适用于 SQL Server 的 OLE DB 驱动程序支持**iopenrowset:: Openrowset**方法有以下限制：  
  
-   必须在 pTableID 参数指向的数据库 ID (DBID) 结构中指定基表或视图。  
  
-   DBID eKind 成员必须指示 DBKIND_NAME。  
  
-   DBID uName 成员必须将现有基表或视图的名称指定为 Unicode 字符串。  
  
-   OpenRowset 的 pIndexID 参数必须为 NULL。  
  
 IOpenRowset::OpenRowset 的结果集包含单个行集。 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 游标可以支持包含单个行集的结果集。 游标支持允许开发人员使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 并发控制机制。  
  
## <a name="see-also"></a>另请参阅  
 [行集](../../oledb/ole-db-rowsets/rowsets.md)  
  
  
