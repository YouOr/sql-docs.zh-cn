---
title: "@@TOTAL_ERRORS (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '@@TOTAL_ERRORS'
- '@@TOTAL_ERRORS_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- '@@TOTAL_ERRORS function'
- total errors [SQL Server]
- errors [SQL Server], read/write
- number of disk read/write errors
- disks [SQL Server], errors
- write errors [SQL Server]
- read/write errors
ms.assetid: 09e62428-ee0e-4ef5-b969-da9d255f1199
caps.latest.revision: 18
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 83d639209d35d6516bd9348f40f4eddfd30ddff5
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="totalerrors-transact-sql"></a>@@TOTAL_ERRORS (Transact SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  返回自上次启动 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 之后 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 所遇到的磁盘写入错误数。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
@@TOTAL_ERRORS  
```  
  
## <a name="return-types"></a>返回类型  
 **integer**  
  
## <a name="remarks"></a>注释  
 并非 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 所遇到的所有写入错误都由该函数进行处理。 偶尔发生的非致命写入错误由服务器本身进行处理，并不将其视为错误。 若要显示报表包含若干个[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]运行统计信息，包括的错误，总数**sp_monitor**。  
  
## <a name="examples"></a>示例  
 以下示例显示了 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 到当前日期和时间为止所遇到的错误数。  
  
```  
SELECT @@TOTAL_ERRORS AS 'Errors', GETDATE() AS 'As of';  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
Errors      As of                   
----------- ----------------------  
0           3/28/2003 12:32:11 PM   
```  
  
## <a name="see-also"></a>另请参阅  
 [sp_monitor &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-monitor-transact-sql.md)   
 [系统统计函数 &#40;Transact SQL &#41;](../../t-sql/functions/system-statistical-functions-transact-sql.md)  
  
  