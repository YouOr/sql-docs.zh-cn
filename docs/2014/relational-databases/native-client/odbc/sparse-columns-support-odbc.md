---
title: 稀疏列支持 (ODBC) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 11ae959f-2fb6-4b85-ac5d-1476a82136d4
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d50666d333a77f4a1e2188ac911d0866395b4cc9
ms.sourcegitcommit: 79d4dc820767f7836720ce26a61097ba5a5f23f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2018
ms.locfileid: "40395212"
---
# <a name="sparse-columns-support-odbc"></a>稀疏列支持 (ODBC)
  本主题描述对稀疏列的 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC 支持。 演示对稀疏列 ODBC 支持的示例，请参阅[对具有稀疏列的表调用 SQLColumns](../../native-client-odbc-how-to/call-sqlcolumns-on-a-table-with-sparse-columns.md)。 有关稀疏列的详细信息，请参阅[SQL Server Native Client 中的稀疏列支持](../features/sparse-columns-support-in-sql-server-native-client.md)。  
  
## <a name="statement-metadata"></a>语句元数据  
 应用程序参数描述符 (APD) 字段和 SQL_SOPT_SS_NAME_SCOPE 语句属性接受新增的值 SQL_SS_NAME_SCOPE_EXTENDED 和 SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET。 这些值指定哪些列包含在返回的结果集[SQLColumns](../../native-client-odbc-api/sqlcolumns.md)。 有关 SQL_SOPT_SS_NAME_SCOPE 的详细信息，请参阅[SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md)。  
  
 新的实现行描述符 (IRD) 是称为 SQL_CA_SS_IS_COLUMN_SET 的只读 SQLSMALLINT 字段，它可以用于确定列是否是 XML `column_set` 值。 SQL_CA_SS_IS_COLUMN_SET 接受值 SQL_TRUE 和 SQL_FALSE。  
  
## <a name="catalog-metadata"></a>目录元数据  
 两个[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]特定列 （SS_IS_SPARSE 和 SS_IS_COLUMN_SET） 已添加到结果集中[SQLColumns](../../native-client-odbc-api/sqlcolumns.md)。  
  
## <a name="odbc-function-support-for-sparse-columns"></a>对稀疏列的 ODBC 函数支持  
 以下 ODBC 函数已进行更新，以便在 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 中支持稀疏列：  
  
-   [SQLColAttribute](../../native-client-odbc-api/sqlcolattribute.md)  
  
-   [SQLColumns](../../native-client-odbc-api/sqlcolumns.md)  
  
-   [SQLGetDescField](../../native-client-odbc-api/sqlgetdescfield.md)  
  
-   [SQLSetDescField](../../native-client-odbc-api/sqlsetdescfield.md)  
  
-   [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md)  
  
## <a name="see-also"></a>请参阅  
 [SQL Server Native Client (ODBC)](sql-server-native-client-odbc.md)  
  
  
