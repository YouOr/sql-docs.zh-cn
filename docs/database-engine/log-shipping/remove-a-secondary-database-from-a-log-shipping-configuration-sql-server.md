---
title: "从日志传送配置中删除辅助数据库 (SQL Server) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-high-availability
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting secondary databases
- secondary databases [SQL Server], in log shipping
- removing secondary databases
- secondary data files [SQL Server], removing
- log shipping [SQL Server], secondary databases
ms.assetid: ebe368a4-ca1c-45d0-9a71-3ddbd5b26a8e
caps.latest.revision: 19
author: MikeRayMSFT
ms.author: mikeray
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 9c0ced4d63693c2d299556a28796e55fccbcc2b5
ms.contentlocale: zh-cn
ms.lasthandoff: 08/02/2017

---
# <a name="remove-a-secondary-database-from-a-log-shipping-configuration-sql-server"></a>从日志传送配置中删除辅助数据库 (SQL Server)
  本主题说明如何使用 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 或 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 在 [!INCLUDE[tsql](../../includes/tsql-md.md)]中删除日志传送辅助数据库。  
  
 **本主题内容**  
  
-   **开始之前：**  
  
     [安全性](#Security)  
  
-   **若要删除日志传送辅助数据库，请使用：**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
-   [相关任务](#RelatedTasks)  
  
##  <a name="BeforeYouBegin"></a> 开始之前  
  
###  <a name="Security"></a> 安全性  
  
####  <a name="Permissions"></a> 权限  
 日志传送存储过程要求 **sysadmin** 固定服务器角色中的成员身份。  
  
##  <a name="SSMSProcedure"></a> 使用 SQL Server Management Studio  
  
#### <a name="to-remove-a-log-shipping-secondary-database"></a>删除日志传送辅助数据库  
  
1.  连接到当前是日志传送主服务器的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例并展开该实例。  
  
2.  展开“数据库”，右键单击日志传送主数据库，再单击“属性”。  
  
3.  在 **“选择页”**下，单击 **“事务日志传送”**。  
  
4.  在 **“辅助服务器实例和数据库”**下，单击要删除的数据库。  
  
5.  单击 **“删除”**。  
  
6.  单击 **“确定”** 更新配置。  
  
##  <a name="TsqlProcedure"></a> 使用 Transact-SQL  
  
#### <a name="to-remove-a-secondary-database"></a>删除辅助数据库  
  
1.  在主服务器上，执行 [sp_delete_log_shipping_primary_secondary](../../relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql.md) 从主服务器上删除有关辅助数据库的信息。  
  
2.  在辅助服务器上，执行 [sp_delete_log_shipping_secondary_database](../../relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql.md) 以删除辅助数据库。  
  
    > [!NOTE]  
    >  如果不存在具有相同辅助 ID 的其他辅助数据库，则从 **sp_delete_log_shipping_secondary_database** 调用 **sp_delete_log_shipping_secondary_primary** ，以删除该辅助 ID 的项并删除复制和还原作业。  
  
3.  在辅助服务器上，禁用复制和还原作业。 有关详细信息，请参阅 [Disable or Enable a Job](http://msdn.microsoft.com/library/5041261f-0c32-4d4a-8bee-59a6c16200dd)。  
  
##  <a name="RelatedTasks"></a> 相关任务  
  
-   [将日志传送升级至 SQL Server 2016 (Transact-SQL)](../../database-engine/log-shipping/upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [配置日志传送 (SQL Server)](../../database-engine/log-shipping/configure-log-shipping-sql-server.md)  
  
-   [向日志传送配置添加辅助数据库 (SQL Server)](../../database-engine/log-shipping/add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [删除日志传送 (SQL Server)](../../database-engine/log-shipping/remove-log-shipping-sql-server.md)  
  
-   [查看日志传送报告 (SQL Server Management Studio)](../../database-engine/log-shipping/view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [监视日志传送 (Transact-SQL)](../../database-engine/log-shipping/monitor-log-shipping-transact-sql.md)  
  
-   [故障转移到日志传送辅助服务器 (SQL Server)](../../database-engine/log-shipping/fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a>另请参阅  
 [关于日志传送 (SQL Server)](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [日志传送表和存储过程](../../database-engine/log-shipping/log-shipping-tables-and-stored-procedures.md)  
  
  