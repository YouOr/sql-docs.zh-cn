---
title: "sys.dm_audit_actions (TRANSACT-SQL) |Microsoft 文档"
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.dm_audit_actions_TSQL
- sys.dm_audit_actions
- dm_audit_actions_TSQL
- dm_audit_actions
dev_langs: TSQL
helpviewer_keywords: sys.dm_audit_actions dynamic management view
ms.assetid: b987c2b9-998a-4a5f-a82d-280dc6963cbe
caps.latest.revision: "19"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 05df5e1a430a1be729510cd0c8612f6d23a41480
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmauditactions-transact-sql"></a>sys.dm_audit_actions (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  为可在审核日志中报告的每项审核操作以及可配置为 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Audit 一部分的每个审核操作组返回一行。 有关详细信息[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]审核，请参阅[SQL Server Audit &#40; 数据库引擎 &#41;](../../relational-databases/security/auditing/sql-server-audit-database-engine.md)。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**action_id**|**varchar(4)**|审核操作的 ID。 与相关**action_id**写入每个审核记录的值。 可以为 Null。 对于审核组，为 NULL。|  
|**action_in_log**|**bit**|指示是否可以将操作写入审核日志。 值如下：<br /><br /> 1 = 是<br /><br /> 0 = 否|  
|**名称**|**sysname**|审核操作或审核组的名称。 不可为 null。|  
|**class_desc**|**nvarchar(120)**|应用审核操作对象的类的名称。 可以为任何 Server、Database 或 Schema 作用域对象之一，但是不包括 Schema 对象。 不可为 null。|  
|**parent_class_desc**|**nvarchar(120)**|class_desc 所描述对象的父类的名称。 如果 class_desc 为 Server，则为 NULL。|  
|**covering_parent_action_name**|**nvarchar(120)**|包含此行中所述的审核操作的审核操作或审核组的名称。 该名称用于创建操作和覆盖操作的层次结构。 可以为 Null。|  
|**configuration_level**|**nvarchar(10)**|指示此行中指定的操作或操作组在“组”或“操作”级别是可配置的。 如果操作不可配置，则为 NULL。|  
|**containing_group_name**|**nvarchar(120)**|包含指定操作的审核组的名称。 如果名称中的值为组，则为 NULL。|  
  
## <a name="permissions"></a>Permissions  
 主体必须具有**选择**权限。 默认情况下，此权限授予 Public。  
  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)]。 有关详细信息，请参阅 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)。  
  
## <a name="see-also"></a>另请参阅  
 [创建服务器审核 &#40;Transact SQL &#41;](../../t-sql/statements/create-server-audit-transact-sql.md)   
 [ALTER SERVER AUDIT &#40;Transact SQL &#41;](../../t-sql/statements/alter-server-audit-transact-sql.md)   
 [DROP SERVER AUDIT &#40;Transact SQL &#41;](../../t-sql/statements/drop-server-audit-transact-sql.md)   
 [创建服务器审核规范 &#40;Transact SQL &#41;](../../t-sql/statements/create-server-audit-specification-transact-sql.md)   
 [ALTER SERVER AUDIT SPECIFICATION &#40;Transact SQL &#41;](../../t-sql/statements/alter-server-audit-specification-transact-sql.md)   
 [删除服务器审核规范 &#40;Transact SQL &#41;](../../t-sql/statements/drop-server-audit-specification-transact-sql.md)   
 [创建数据库审核规范 &#40;Transact SQL &#41;](../../t-sql/statements/create-database-audit-specification-transact-sql.md)   
 [ALTER DATABASE AUDIT SPECIFICATION &#40;Transact SQL &#41;](../../t-sql/statements/alter-database-audit-specification-transact-sql.md)   
 [删除数据库审核规范 &#40;Transact SQL &#41;](../../t-sql/statements/drop-database-audit-specification-transact-sql.md)   
 [ALTER AUTHORIZATION &#40;Transact SQL &#41;](../../t-sql/statements/alter-authorization-transact-sql.md)   
 [sys.fn_get_audit_file &#40;Transact SQL &#41;](../../relational-databases/system-functions/sys-fn-get-audit-file-transact-sql.md)   
 [sys.server_audits &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-server-audits-transact-sql.md)   
 [sys.server_file_audits &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-server-file-audits-transact-sql.md)   
 [sys.server_audit_specifications &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-server-audit-specifications-transact-sql.md)   
 [sys.server_audit_specification_details &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-server-audit-specification-details-transact-sql.md)   
 [sys.database_audit_specifications &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-database-audit-specifications-transact-sql.md)   
 [sys.database_audit_specification_details &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-database-audit-specification-details-transact-sql.md)   
 [sys.dm_server_audit_status &#40;Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-server-audit-status-transact-sql.md)   
 [sys.dm_audit_class_type_map &#40;Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-audit-class-type-map-transact-sql.md)   
 [创建服务器审核和服务器审核规范](../../relational-databases/security/auditing/create-a-server-audit-and-server-audit-specification.md)  
  
  