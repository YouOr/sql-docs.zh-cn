---
title: sp_column_privileges (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_column_privileges_TSQL
- sp_column_privileges
dev_langs:
- TSQL
helpviewer_keywords:
- sp_column_privileges
ms.assetid: a3784301-2517-4b1d-bbd9-47404483fad0
caps.latest.revision: 36
author: edmacauley
ms.author: edmaca
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: 4742d442cf410d936706d5a67b50e08732ad253c
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "39545598"
---
# <a name="spcolumnprivileges-transact-sql"></a>sp_column_privileges (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  返回当前环境中单个表的列特权信息。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_column_privileges [ @table_name = ] 'table_name'   
     [ , [ @table_owner = ] 'table_owner' ]   
     [ , [ @table_qualifier = ] 'table_qualifier' ]   
     [ , [ @column_name = ] 'column' ]  
```  
  
## <a name="arguments"></a>参数  
 [ @table_name=] '*table_name*  
 用来返回目录信息的表。 *table_name*是**sysname**，无默认值。 不支持通配符模式匹配。  
  
 [ @table_owner=] '*table_owner*  
 用于返回目录信息的表的所有者。 *table_owner*是**sysname**，默认值为 NULL。 不支持通配符模式匹配。 如果*table_owner*未指定，则将应用默认表可见性规则的基础数据库管理系统 (DBMS)。  
  
 如果当前用户拥有具有指定名称的表，则返回该表的列。 如果*table_owner*未指定当前用户不拥有具有指定的表和*table_name*，sp_column 权限具有指定的表查找*table_name*由数据库所有者拥有。 如果有，则返回该表的列。  
  
 [ @table_qualifier=] '*table_qualifier*  
 表限定符的名称。 *table_qualifier*是*sysname*，默认值为 NULL。 多种 DBMS 产品支持表的三部分命名 (*限定符 ***。*** 所有者 ***。*** 名称*)。 在[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]，此列表示数据库名称。 在某些产品中，该列表示表所在的数据库环境的服务器名。  
  
 [ @column_name=] '*列*  
 只获取一列目录信息时所用的单独的列。 *列*是**nvarchar (** 384 **)**，默认值为 NULL。 如果*列*是未指定，则返回所有列。 在中[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]，*列*表示在 sys.columns 表中列出的列名称。 *列*可以包括使用通配符匹配模式的基础 DBMS 的通配符。 为了达到最佳的互操作性，网关客户端应只采用 ISO 标准模式匹配（% 和 _ 通配符）。  
  
## <a name="result-sets"></a>结果集  
 sp_column_privileges 与 ODBC 中的 SQLColumnPrivileges 等效。 返回的结果按 TABLE_QUALIFIER、TABLE_OWNER、TABLE_NAME、COLUMN_NAME 和 PRIVILEGE 排序。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|TABLE_QUALIFIER|**sysname**|表限定符名称。 此字段可以为 NULL。|  
|TABLE_OWNER|**sysname**|表所有者名称。 此字段始终返回值。|  
|TABLE_NAME|**sysname**|表名。 此字段始终返回值。|  
|COLUMN_NAME|**sysname**|所返回的 TABLE_NAME 中每列的列名。 此字段始终返回值。|  
|GRANTOR|**sysname**|向列出的 GRANTEE 授予对此 COLUMN_NAME 的权限的数据库用户名。 在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中，此列始终与 TABLE_OWNER 相同。 此字段始终返回值。<br /><br /> GRANTOR 列可以是数据库所有者 (TABLE_OWNER) 或数据库所有者通过在 GRANT 语句中使用 WITH GRANT OPTION 子句对其授予权限的用户。|  
|GRANTEE|**sysname**|已被所列 GRANTOR 授予对此 COLUMN_NAME 的权限的数据库用户名。 在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中，该列始终包括来自 sysusers 表的数据库用户。 此字段始终返回值。|  
|PRIVILEGE|**varchar(** 32 **)**|可用列权限中的一个。 列权限可以是下列值中的一个（或定义实现时数据源支持的其他值）：<br /><br /> SELECT = GRANTEE 可以检索列的数据。<br /><br /> INSERT = 当 (GRANTEE) 向表中插入新行时，GRANTEE 可以为此列提供数据。<br /><br /> UPDATE = GRANTEE 可以修改列中的现有数据。<br /><br /> REFERENCES = GRANTEE 可以用主键/外键关系引用外表中的列。 通过使用表约束定义主键/外键关系。|  
|IS_GRANTABLE|**varchar (** 3 **)**|指示是否允许被授权者向其他用户 （通常称为"授予再授予"权限） 授予权限。 可以是 YES、NO 或 NULL。 为未知或 NULL，值引用的"授予再授予"不适用于的数据源。|  
  
## <a name="remarks"></a>Remarks  
 使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]，可以用 GRANT 语句授予权限，用 REVOKE 语句除去权限。  
  
## <a name="permissions"></a>Permissions  
 需要对架构的 SELECT 权限。  
  
## <a name="examples"></a>示例  
 以下示例返回特定列的列特权信息。  
  
```  
USE AdventureWorks2012;  
GO  
EXEC sp_column_privileges @table_name = 'Employee'   
    ,@table_owner = 'HumanResources'  
    ,@table_qualifier = 'AdventureWorks2012'  
    ,@column_name = 'SalariedFlag';  
```  
  
## <a name="see-also"></a>请参阅  
 [GRANT (Transact-SQL)](../../t-sql/statements/grant-transact-sql.md)   
 [REVOKE (Transact-SQL)](../../t-sql/statements/revoke-transact-sql.md)   
 [系统存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
