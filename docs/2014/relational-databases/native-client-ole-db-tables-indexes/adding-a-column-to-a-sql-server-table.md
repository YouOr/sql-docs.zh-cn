---
title: 向 SQL Server 表添加列 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- columns [OLE DB]
- AddColumn function
- SQL Server Native Client OLE DB provider, columns
- adding columns
ms.assetid: 22bae18a-bc9d-4617-8660-ed8b17a468d4
caps.latest.revision: 29
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: e79886f09783737a392fa67899feb59cd7deb2a1
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37425266"
---
# <a name="adding-a-column-to-a-sql-server-table"></a>向 SQL Server 表添加列
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB 访问接口公开**itabledefinition:: Addcolumn**函数。 这允许使用者添加到列[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]表。  
  
 当您添加到列[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]表， [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB 访问接口使用者约束，如下所示：  
  
-   如果 DBPROP_COL_AUTOINCREMENT 为 VARIANT_TRUE，则 DBPROP_COL_NULLABLE 必须为 VARIANT_FALSE。  
  
-   如果使用已定义该列[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**时间戳**数据类型，则 DBPROP_COL_NULLABLE 必须为 VARIANT_FALSE。  
  
-   对于任何其他列定义，DBPROP_COL_NULLABLE 都必须为 VARIANT_TRUE。  
  
 使用者指定为 Unicode 字符串中的表名*pwszName*的成员*uName*联合*pTableID*参数。 *EKind*的成员*pTableID*必须为 DBKIND_NAME。  
  
 新的列名称指定为中的 Unicode 字符字符串*pwszName*的成员*uName*联合*dbcid*的 DBCOLUMNDESC 参数成员*pColumnDesc*。 *EKind*成员必须为 DBKIND_NAME。  
  
## <a name="see-also"></a>请参阅  
 [表和索引](tables-and-indexes.md)   
 [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql)  
  
  
