---
title: '@@PACKET_ERRORS (Transact-SQL) | Microsoft Docs'
ms.custom: ''
ms.date: 09/18/2017
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- '@@PACKET_ERRORS'
- '@@PACKET_ERRORS_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- '@@PACKET_ERRORS function'
- number of packet errors
- packets [SQL Server], errors
- networking [SQL Server], packet errors
- connections [SQL Server], packets
ms.assetid: f7da1b80-5cbe-42fa-be71-40c6af16383a
caps.latest.revision: 31
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: b996c2b6c344fc71008f830604471a60ee7d5583
ms.sourcegitcommit: 05e18a1e80e61d9ffe28b14fb070728b67b98c7d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/04/2018
ms.locfileid: "37788158"
---
# <a name="x40x40packeterrors-transact-sql"></a>&#x40;&#x40;PACKET_ERRORS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  返回自上次启动 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 后在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 连接上发生的网络数据包错误数。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
@@PACKET_ERRORS  
```  
  
## <a name="return-types"></a>返回类型  
 **integer**  
  
## <a name="remarks"></a>Remarks  
 要显示包含多个 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 统计信息（包括数据包错误）的报表，请运行 sp_monitor。  
  
## <a name="examples"></a>示例  
 下面的示例显示了使用 `@@PACKET_ERRORS`。  
  
```  
SELECT @@PACKET_ERRORS AS 'Packet Errors';  
```  
  
 下面是一个结果集示例。  
  
```  
Packet Errors  
-------------  
0  
```  
  
## <a name="see-also"></a>另请参阅  
 [@@PACK_RECEIVED (Transact-SQL)](../../t-sql/functions/pack-received-transact-sql.md)   
 [@@PACK_SENT (Transact-SQL)](../../t-sql/functions/pack-sent-transact-sql.md)   
 [sp_monitor (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-monitor-transact-sql.md)   
 [系统统计函数 (Transact-SQL)](../../t-sql/functions/system-statistical-functions-transact-sql.md)  
  
  
