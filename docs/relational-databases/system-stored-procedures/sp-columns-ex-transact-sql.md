---
title: sp_columns_ex (Transact SQL) |Microsoft 文档
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
- sp_columns_ex
- sp_columns_ex_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_columns_ex
ms.assetid: c12ef6df-58c6-4391-bbbf-683ea874bd81
caps.latest.revision: 38
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: a7f075de05288823c1ed290527de4005b1160c20
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33240067"
---
# <a name="spcolumnsex-transact-sql"></a>sp_columns_ex (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  返回指定链接服务器表的列信息，每列一行。 **sp_columns_ex**返回特定的列的列信息，如果*列*指定。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_columns_ex [ @table_server = ] 'table_server'   
     [ , [ @table_name = ] 'table_name' ]   
     [ , [ @table_schema = ] 'table_schema' ]   
     [ , [ @table_catalog = ] 'table_catalog' ]   
     [ , [ @column_name = ] 'column' ]   
     [ , [ @ODBCVer = ] 'ODBCVer' ]  
```  
  
## <a name="arguments"></a>参数  
 [  **@table_server =** ] *****table_server*****  
 要返回列信息的链接服务器的名称。 *table_server*是**sysname**，无默认值。  
  
 [  **@table_name =** ] *****table_name*****  
 要返回其列信息的表的名称。 *table_name*是**sysname**，默认值为 NULL。  
  
 [  **@table_schema =** ] *****table_schema*****  
 要返回其列信息的表的架构名。 *table_schema*是**sysname**，默认值为 NULL。  
  
 [  **@table_catalog =** ] *****table_catalog*****  
 要返回其列信息的表的目录名。 *table_catalog*是**sysname**，默认值为 NULL。  
  
 [  **@column_name =** ] *****列*****  
 要提供其信息的数据库列的名称。 *列*是**sysname**，默认值为 NULL。  
  
 [  **@ODBCVer =** ] *****ODBCVer*****  
 是正在使用的 ODBC 版本。 *ODBCVer*是**int**，默认值为 2。 这指示 ODBC 版本 2。 有效值为 2 或 3。 有关版本 2 和 3 之间的行为差异的信息，请参阅 ODBC SQLColumns 规范。  
  
## <a name="return-code-values"></a>返回代码值  
 InclusionThresholdSetting  
  
## <a name="result-sets"></a>结果集  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**TABLE_CAT**|**sysname**|表或视图限定符的名称。 各种 DBMS 产品支持三部分命名表 (*限定符 ***。*** 所有者 ***。*** 名称*)。 在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中，此列表示数据库名称。 在某些产品中，该列表示表所在的数据库环境的服务器名。 此字段可以为 NULL。|  
|**TABLE_SCHEM**|**sysname**|表或视图所有者的名称。 在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中，该列表示创建表的数据库用户的名称。 此字段始终返回值。|  
|**TABLE_NAME**|**sysname**|表或视图名称。 此字段始终返回值。|  
|**COLUMN_NAME**|**sysname**|列名称，为每个列的**TABLE_NAME**返回。 此字段始终返回值。|  
|**DATA_TYPE**|**int**|与 ODBC 类型指示符对应的整数值。 如果是无法映射到 ODBC 类型的数据类型，则该值为 NULL。 在中返回的本机数据类型名称**TYPE_NAME**列。|  
|**TYPE_NAME**|**varchar (** 13 **)**|表示数据类型的字符串。 基础 DBMS 提供此数据类型的名称。|  
|**COLUMN_SIZE**|**int**|有效数字位数。 返回值**精度**列是以 10 为基数。|  
|**BUFFER_LENGTH**|**int**|数据的传输大小。1|  
|**DECIMAL_DIGITS**|**int**|小数点右边的数字位数。|  
|**NUM_PREC_RADIX**|**int**|数字数据类型的基数。|  
|**可以为 NULL**|**int**|指定为 Null 性。<br /><br /> 1 = 可以为 NULL。<br /><br /> 0 = 不可以为 NULL。|  
|**备注**|**varchar (** 254 **)**|该字段总是返回 NULL。|  
|**COLUMN_DEF**|**varchar (** 254 **)**|列的默认值。|  
|**SQL_DATA_TYPE**|**int**|SQL 数据类型在描述符的 TYPE 字段中显示的值。 此列等同于**DATA_TYPE**列中，除**datetime**和 SQL 92**间隔**数据类型。 该列始终返回值。|  
|**SQL_DATETIME_SUB**|**int**|子类型代码**datetime**和 SQL 92**间隔**数据类型。 对于其他数据类型，该列返回 NULL。|  
|**CHAR_OCTET_LENGTH**|**int**|字符或整数数据类型的列的最大长度（字节）。 对于所有其他数据类型，该列返回 NULL。|  
|**ORDINAL_POSITION**|**int**|列在表中的序号位置。 表中的第一列为 1。 该列始终返回值。|  
|**IS_NULLABLE**|**varchar (** 254 **)**|表中的列的为 Null 性。 根据 ISO 规则确定为 Null 性。 遵从 ISO SQL 标准的 DBMS 不能返回空字符串。<br /><br /> YES = 列可以包含 NULL。<br /><br /> NO = 列不能包含 NULL。<br /><br /> 如果为 Null 性为未知，该列将返回零长度字符串。<br /><br /> 为此列返回的值不同，则返回该值**可以为 NULL**列。|  
|**SS_DATA_TYPE**|**tinyint**|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 使用扩展存储过程的数据类型。|  
  
 有关更多信息，请参见 Microsoft ODBC 文档。  
  
## <a name="remarks"></a>注释  
 **sp_columns_ex**由查询的列行集执行**IDBSchemaRowset**对应的 OLE DB 访问接口的接口*table_server*。 *Table_name*， *table_schema*， *table_catalog*，和*列*参数传递给此接口可限制的行返回。  
  
 **sp_columns_ex**返回空结果集，如果指定的链接服务器的 OLE DB 提供程序不支持列行集**IDBSchemaRowset**接口。  
  
## <a name="permissions"></a>权限  
 需要对架构的 SELECT 权限。  
  
## <a name="remarks"></a>注释  
 **sp_columns_ex**遵循分隔标识符的要求。 有关详细信息，请参阅 [Database Identifiers](../../relational-databases/databases/database-identifiers.md)。  
  
## <a name="examples"></a>示例  
 以下示例返回链接服务器 `JobTitle` 上的 [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] 数据库中的 `HumanResources.Employee` 表的 `Seattle1` 列的数据类型。  
  
```  
EXEC sp_columns_ex 'Seattle1',   
   'Employee',   
   'HumanResources',   
   'AdventureWorks2012',   
   'JobTitle';  
```  
  
## <a name="see-also"></a>另请参阅  
 [sp_catalogs &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-catalogs-transact-sql.md)   
 [sp_foreignkeys &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-foreignkeys-transact-sql.md)   
 [sp_indexes &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-indexes-transact-sql.md)   
 [sp_linkedservers & #40;Transact SQL & #41;](../../relational-databases/system-stored-procedures/sp-linkedservers-transact-sql.md)   
 [sp_primarykeys &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-primarykeys-transact-sql.md)   
 [sp_tables_ex &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-tables-ex-transact-sql.md)   
 [sp_table_privileges &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-table-privileges-transact-sql.md)   
 [系统存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
