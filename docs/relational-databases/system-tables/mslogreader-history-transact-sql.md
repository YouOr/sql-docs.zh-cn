---
title: MSlogreader_history (Transact SQL) |Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-tables
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- MSlogreader_history_TSQL
- MSlogreader_history
dev_langs:
- TSQL
helpviewer_keywords:
- MSlogreader_history system table
ms.assetid: 2e399fa1-3591-4c1c-96b7-7964fe82c7c4
caps.latest.revision: 29
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: def5bc1d69a3d5332f96752fcd5e6b1eaedff08e
ms.sourcegitcommit: a431ca21eac82117492d7b84c398ddb3fced53cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2018
ms.locfileid: "39103095"
---
# <a name="mslogreaderhistory-transact-sql"></a>MSlogreader_history (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **MSlogreader_history**表包含与本地分发服务器关联的日志读取器代理历史记录行。 此表存储在分发数据库中。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**agent_id**|**int**|日志读取器代理的 ID。|  
|**runstatus**|**int**|运行状态：<br /><br /> 1 = 开始。<br /><br /> 2 = 成功。<br /><br /> 3 = 正在进行。<br /><br /> 4 = 空闲。<br /><br /> 5 = 重试。<br /><br /> 6 = 失败。|  
|**start_time**|**datetime**|开始执行作业的时间。|  
|**time**|**datetime**|记录消息的时间。|  
|**duration**|**int**|消息会话的持续时间（秒）。|  
|**注释**|**nvarchar(255)**|消息文本。|  
|**xact_seqno**|**varbinary(16)**|上次处理的事务序列号。|  
|**delivery_time**|**int**|传递时第一个事务。|  
|**delivered_transactions**|**int**|会话中传递的事务总数。|  
|**delivered_commands**|**int**|在会话中传递的命令总数。|  
|**average_commands**|**int**|会话中传递的平均命令数。|  
|**delivery_rate**|**float**|平均每秒传递的命令数。|  
|**delivery_latency**|**int**|命令从进入发布数据库到进入分发数据库之间的滞后时间。 以毫秒为单位。|  
|**error_id**|**int**|中的错误的 ID **MSrepl_error**系统表。|  
|**timestamp**|**timestamp**|该表的时间戳列。|  
|**updateable_row**|**bit**|设置为**1**如果可以覆盖历史记录行。|  
  
## <a name="see-also"></a>请参阅  
 [复制表&#40;Transact SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [复制视图 (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
