---
title: SQL 一致性级别 （适用于 Oracle 的 ODBC 驱动程序） |Microsoft 文档
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- conformance levels [ODBC], SQL
- SQL conformance levels [ODBC]
- ODBC driver for Oracle [ODBC], conformance levels
ms.assetid: 077a6c6a-2c57-42c9-a4fd-4cf0e65cf7e2
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 6124577353292209f2bcbd2ca35b6b33add34ca6
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32904922"
---
# <a name="sql-conformance-levels-odbc-driver-for-oracle"></a>SQL 一致性级别 （适用于 Oracle 的 ODBC 驱动程序）
> [!IMPORTANT]  
>  将 Windows 的未来版本中删除该功能。 请避免在新的开发工作中使用该功能，并着手修改当前还在使用该功能的应用程序。 相反，使用提供的 Oracle 的 ODBC 驱动程序。  
  
 用于 Oracle 的 ODBC 驱动程序支持的最低 SQL 语法和核心 SQL 语法，还支持以下 to SQL 的 ODBC 扩展：  
  
-   日期、 时间和时间戳数据  
  
-   左和右外部联接  
  
-   数值函数：  
  
    |||||  
    |-|-|-|-|  
    |Abs|日志|round|tan|  
    |上限|Log10|second|truncate|  
    |Cos|Mod|登录||  
    |Exp|pi|sin||  
    |floor|Power|sqrt||  
  
-   日期函数：  
  
    |||||  
    |-|-|-|-|  
    |Curdate|dayofweek|月份名称|second|  
    |Curtime|Dayofyear|minute|week|  
    |Dayname|Hour|现在|year|  
    |dayofmonth|Month|季度||  
  
-   字符串函数：  
  
    |||||  
    |-|-|-|-|  
    |ascii|Left|右|ucase|  
    |Char|长度|rtrim||  
    |Concat|Ltrim|soundex||  
    |Lcase|替换|substring||  
  
-   类型转换函数：  
  
    ||  
    |-|  
    |转换|  
  
-   系统函数：  
  
    ||  
    |-|  
    |Ifnull|  
    |用户|
