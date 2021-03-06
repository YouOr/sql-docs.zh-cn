---
title: 查看存储过程的依赖关系 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], dependencies
- displaying stored procedure dependencies
- viewing stored procedure dependencies
ms.assetid: 6ae0a369-1bc7-4ae4-be89-2b483697cd1f
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 7693ac696484bfb67df337232dd50822598f9c61
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37149478"
---
# <a name="view-the-dependencies-of-a-stored-procedure"></a>查看存储过程的依赖关系
    
##  <a name="Top"></a> 本主题介绍如何查看存储的过程中的依赖关系[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]通过使用[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]或[!INCLUDE[tsql](../../includes/tsql-md.md)]。  
  
-   **开始之前：**  [安全性](#Security)  
  
-   **若要查看过程的依赖关系，请使用：**[SQL Server Management Studio](#SSMSProcedure)[Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> 开始之前  
  
###  <a name="Security"></a> 安全性  
  
####  <a name="Permissions"></a> Permissions  
 系统函数：`sys.dm_sql_referencing_entities`  
 要求对被引用的实体拥有 CONTROL 权限，并且对 sys.dm_sql_referencing_entities 拥有 SELECT 权限。 当被引用的实体是分区函数时，要求对数据库拥有 CONTROL 权限。 默认情况下，SELECT 权限授予 public。  
  
 系统函数：`sys.dm_sql_referenced_entities`  
 要求对 sys.dm_sql_referenced_entities 拥有 SELECT 权限并对引用实体拥有 VIEW DEFINITION 权限。 默认情况下，SELECT 权限授予 public。 要求对数据库拥有 VIEW DEFINITION 权限或 ALTER DATABASE DDL TRIGGER 权限（当引用实体为数据库级 DDL 触发器时）。 当引用实体为服务器级 DDL 触发器时，要求对服务器拥有 VIEW ANY DEFINITION 权限。  
  
 对象目录视图：`sys.sql_expression_dependencies`  
 要求对数据库具有 VIEW DEFINITION 权限，并对数据库的 sys.sql_expression_dependencies 具有 SELECT 权限。 默认情况下，SELECT 权限仅授予 db_owner 固定数据库角色的成员。 将 SELECT 和 VIEW DEFINITION 权限授予其他用户时，被授权者可以查看数据库中的所有依赖关系。  
  
##  <a name="Procedures"></a> 如何查看存储过程的依赖关系  
 您可以使用以下项之一：  
  
-   [SQL Server Management Studio](#SSMSProcedure)  
  
-   [Transact-SQL](#TsqlProcedure)  
  
###  <a name="SSMSProcedure"></a> 使用 SQL Server Management Studio  
 **在对象资源管理器中查看过程的依赖关系**  
  
1.  在对象资源管理器中，连接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 的实例，然后展开该实例。  
  
2.  展开 **“数据库”**、过程所属的数据库以及 **“可编程性”**。  
  
3.  展开“存储过程”，右键单击此过程，再单击“查看依赖关系”。  
  
4.  查看依赖于过程的对象的列表。  
  
5.  查看过程所依赖的对象的列表。  
  
6.  单击“确定” 。  
  
###  <a name="TsqlProcedure"></a> 使用 Transact-SQL  
 **在查询编辑器中查看过程的依赖关系**  
  
 系统函数：`sys.dm_sql_referencing_entities`  
 此函数用于显示依赖于过程的对象。  
  
1.  在 **“对象资源管理器”** 中，连接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 的实例，然后展开该实例。  
  
2.  展开 **“数据库”**，然后展开过程所属的数据库。  
  
3.  在 **“文件”** 菜单下，单击 **“新建查询”** 。  
  
4.  复制以下示例并将其粘贴到查询编辑器中。 第一个示例创建 `uspVendorAllInfo` 过程，该过程返回 [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] 数据库中所有供应商的名称、所提供的产品、信用等级以及可用性。  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  创建该过程后，第二个示例使用 sys.dm_sql_referencing_entities 函数来显示依赖于该过程的对象。  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT referencing_schema_name, referencing_entity_name, referencing_id, referencing_class_desc, is_caller_dependent  
    FROM sys.dm_sql_referencing_entities ('Purchasing.uspVendorAllInfo', 'OBJECT');   
    GO  
  
    ```  
  
 系统函数：`sys.dm_sql_referenced_entities`  
 此函数用于显示过程所依赖的对象。  
  
1.  在 **“对象资源管理器”** 中，连接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 的实例，然后展开该实例。  
  
2.  展开 **“数据库”**，然后展开过程所属的数据库。  
  
3.  在 **“文件”** 菜单下，单击 **“新建查询”** 。  
  
4.  复制以下示例并将其粘贴到查询编辑器中。 第一个示例创建 `uspVendorAllInfo` 过程，该过程返回 [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] 数据库中所有供应商的名称、所提供的产品、信用等级以及可用性。  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  创建该过程后，第二个示例使用 sys.dm_sql_referenced_entities 函数来显示该过程依赖的对象。  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT referenced_schema_name, referenced_entity_name,  
    referenced_minor_name,referenced_minor_id, referenced_class_desc,  
    is_caller_dependent, is_ambiguous  
    FROM sys.dm_sql_referencing_entities ('Purchasing.uspVendorAllInfo', 'OBJECT');  
    GO  
    ```  
  
 对象目录视图：`sys.sql_expression_dependencies`  
 此视图可以用于显示过程所依赖的对象或依赖于过程的对象。  
  
 显示依赖于过程的对象。  
 1.  在 **“对象资源管理器”** 中，连接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 的实例，然后展开该实例。  
  
2.  展开 **“数据库”**，然后展开过程所属的数据库。  
  
3.  在 **“文件”** 菜单下，单击 **“新建查询”** 。  
  
4.  复制以下示例并将其粘贴到查询编辑器中。 第一个示例创建 `uspVendorAllInfo` 过程，该过程返回 [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] 数据库中所有供应商的名称、所提供的产品、信用等级以及可用性。  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  创建该过程后，第二个示例使用 sys.sql_expression_dependencies 视图来显示依赖于该过程的对象。  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_SCHEMA_NAME ( referencing_id ) AS referencing_schema_name,  
        OBJECT_NAME(referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        referencing_class_desc, referenced_class_desc,  
        referenced_server_name, referenced_database_name, referenced_schema_name,  
        referenced_entity_name,   
        COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,  
        is_caller_dependent, is_ambiguous  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    WHERE referenced_id = OBJECT_ID(N'Purchasing.uspVendorAllInfo')  
    GO  
    ```  
  
 显示过程所依赖的对象。  
 1.  在 **“对象资源管理器”** 中，连接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 的实例，然后展开该实例。  
  
2.  展开 **“数据库”**，然后展开过程所属的数据库。  
  
3.  在 **“文件”** 菜单下，单击 **“新建查询”** 。  
  
4.  复制以下示例并将其粘贴到查询编辑器中。 第一个示例创建 `uspVendorAllInfo` 过程，该过程返回 [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] 数据库中所有供应商的名称、所提供的产品、信用等级以及可用性。  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  创建该过程后，第二个示例使用 sys.sql_expression_dependencies 视图来显示该过程依赖的对象。  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_NAME(referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        referencing_class_desc, referenced_class_desc,  
        referenced_server_name, referenced_database_name, referenced_schema_name,  
        referenced_entity_name,   
        COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,  
        is_caller_dependent, is_ambiguous  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    WHERE referencing_id = OBJECT_ID(N'Purchasing.uspVendorAllInfo')  
    GO  
    ```  
  
## <a name="see-also"></a>请参阅  
 [重命名存储过程](rename-a-stored-procedure.md)   
 [sys.dm_sql_referencing_entities (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)   
 [sys.dm_sql_referenced_entities (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)   
 [sys.sql_expression_dependencies (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
  
