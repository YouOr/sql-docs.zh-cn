---
title: sp_delete_log_shipping_secondary_database (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_delete_log_shipping_secondary_database_TSQL
- sp_delete_log_shipping_secondary_database
dev_langs:
- TSQL
helpviewer_keywords:
- sp_delete_log_shipping_secondary_database
ms.assetid: c71b21c0-ec04-4fbd-9735-01128b736935
caps.latest.revision: 20
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 7c9d8c89292eaee178b71e278d740cdddff67bcd
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257059"
---
# <a name="spdeletelogshippingsecondarydatabase-transact-sql"></a>sp_delete_log_shipping_secondary_database (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  此存储过程删除辅助数据库、本地历史记录和远程历史记录。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_delete_log_shipping_secondary_database  
[ @secondary_database = ] 'secondary_database'  
```  
  
## <a name="arguments"></a>参数  
 [  **@secondary_database =** ]*secondary_database*  
 辅助数据库的名称。 *secondary_database*是**sysname**，无默认值。  
  
## <a name="return-code-values"></a>返回代码值  
 0（成功）或 1（失败）  
  
## <a name="result-sets"></a>结果集  
 无。  
  
## <a name="remarks"></a>注释  
 **sp_delete_log_shipping_secondary_database**必须从运行**master**辅助服务器上的数据库。  
  
## <a name="permissions"></a>权限  
 只有的成员**sysadmin**固定的服务器角色可以运行此过程。  
  
## <a name="see-also"></a>另请参阅  
 [有关日志传送 & #40;SQL server& #41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [系统存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
