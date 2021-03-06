---
title: sp_helpdynamicsnapshot_job (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- sp_helpdynamicsnapshot_TSQL
- sp_helpdynamicsnapshot_job_TSQL
- job_TSQL
- helpdynamicsnapshot
- job
- sp_helpdynamicsnapshot
- sp_helpdynamicsnapshot_job
- helpdynamicsnapshot_TSQL
helpviewer_keywords:
- sp_helpdynamicsnapshot_job
ms.assetid: d6dfdf26-f874-495f-a8a6-8780699646d7
caps.latest.revision: 29
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: 17a7d69869e9879d485f1a8cac107836a5984a44
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "33001244"
---
# <a name="sphelpdynamicsnapshotjob-transact-sql"></a>sp_helpdynamicsnapshot_job (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  返回有关生成筛选数据快照的代理作业的信息。 在发布服务器的发布数据库上执行此存储的过程。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_helpdynamicsnapshot_job [ [ @publication = ] 'publication' ]   
    [ , [ @dynamic_snapshot_jobname = ] 'dynamic_snapshot_jobname' ]  
    [ , [ @dynamic_snapshot_jobid = ] 'dynamic_snapshot_jobid' ]  
```  
  
## <a name="arguments"></a>参数  
 [ **@publication =** ] **'***publication***'**  
 发布的名称。 *发布*是**sysname**，默认值为**%**，它返回的匹配指定的所有已筛选的数据快照作业的信息*dynamic_snapshot_jobid*和*dynamic_snapshot_jobname*所有发布。  
  
 [ **@dynamic_snapshot_jobname =** ] **'***dynamic_snapshot_jobname***'**  
 筛选数据快照作业的名称。 *dynamic_snapshot_jobname*是**sysname**，使用默认的**%**，这将返回具有指定的发布的所有动态作业*dynamic_snapshot_jobid*。 如果创建作业时未显式指定作业名称，则作业名称具有以下格式：  
  
```  
'dyn_' + <name of the standard snapshot job> + <GUID>  
```  
  
 [ **@dynamic_snapshot_jobid =** ] **'***dynamic_snapshot_jobid***'**  
 筛选数据快照作业的标识符。 *dynamic_snapshot_jobid*是**uniqueidentifier**，使用默认值为 NULL，它返回具有指定的所有快照作业*dynamic_snapshot_jobname*。  
  
## <a name="result-sets"></a>结果集  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**id**|**int**|标识已筛选的数据快照作业。|  
|**job_name**|**sysname**|已筛选数据快照作业的名称。|  
|**job_id**|**uniqueidentifier**|标识[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]分发服务器上的代理作业。|  
|**dynamic_filter_login**|**sysname**|值用于评估[SUSER_SNAME](../../t-sql/functions/suser-sname-transact-sql.md)为发布定义参数化的行筛选器中的函数。|  
|**dynamic_filter_hostname**|**sysname**|值用于评估[HOST_NAME](../../t-sql/functions/host-name-transact-sql.md)为发布定义参数化的行筛选器中的函数。|  
|**dynamic_snapshot_location**|**nvarchar(255)**|在使用参数化行筛选器时，从中读取快照文件的文件夹的路径。|  
|**frequency_type**|**int**|代理计划运行的频率，可以为下列值之一：<br /><br /> **1** = 一次<br /><br /> **2** = 按需<br /><br /> **4** = 每日<br /><br /> **8** = 每周<br /><br /> **16** = 每月<br /><br /> **32** = 每月相对<br /><br /> **64** = 自动启动<br /><br /> **128** = 重复执行|  
|**frequency_interval**|**int**|代理运行的日期，可以为下列值之一：<br /><br /> **1** = 星期日<br /><br /> **2** = 星期一<br /><br /> **3** = 星期二<br /><br /> **4** = 星期三<br /><br /> **5** = 星期四<br /><br /> **6** = 星期五<br /><br /> **7** = 星期六<br /><br /> **8** = 某一天<br /><br /> **9** = 工作日<br /><br /> **10** = 周末|  
|**frequency_subday_type**|**int**|是定义代理运行时的频率的类型*frequency_type*是**4** （每日），并且可以为这些值之一。<br /><br /> **1** = 在指定的时间<br /><br /> **2** = 秒<br /><br /> **4** = 分钟<br /><br /> **8** = 小时数|  
|**frequency_subday_interval**|**int**|间隔数*frequency_subday_type*发生之间的代理的计划执行。|  
|**frequency_relative_interval**|**int**|是在给定月份中运行代理的周时*frequency_type*是**32** （每月相对），并且可以为这些值之一。<br /><br /> **1** = 第一次<br /><br /> **2** = 秒<br /><br /> **4** = 第三<br /><br /> **8** = 第四个<br /><br /> **16** = 最后一次|  
|**frequency_recurrence_factor**|**int**|在计划的代理执行之间间隔的周数或月数。|  
|**active_start_date**|**int**|计划第一次运行代理的日期，格式为 YYYYMMDD。|  
|**active_end_date**|**int**|计划最后一次运行代理的日期，格式为 YYYYMMDD。|  
|**active_start_time**|**int**|计划第一次运行代理的时间，格式为 HHMMSS。|  
|**active_end_time**|**int**|计划最后一次运行代理的时间，格式为 HHMMSS。|  
  
## <a name="return-code-values"></a>返回代码值  
 **0** （成功） 或**1** （失败）  
  
## <a name="remarks"></a>注释  
 **sp_helpdynamicsnapshot_job**合并复制中使用。  
  
 如果使用所有默认参数值，则将返回用于整个发布数据库的所有已分区数据快照作业的信息。  
  
## <a name="permissions"></a>权限  
 只有的成员**sysadmin**固定服务器角色、 **db_owner**固定数据库角色和发布访问列表的发布可以执行**sp_helpdynamicsnapshot_job**.  
  
## <a name="see-also"></a>另请参阅  
 [系统存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
