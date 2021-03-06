---
title: 数据源属性 (OLE DB) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, data source properties
- properties [OLE DB]
- data source properties [OLE DB]
- OLE DB data source properties [SQL Server Native Client]
ms.assetid: 6e14fefc-4e0b-4847-a833-4cf0abe65d50
caps.latest.revision: 36
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 29df5d4c99c19b606a1c5b66761e653f6ce924b1
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37416976"
---
# <a name="data-source-properties-ole-db"></a>数据源属性 (OLE DB)
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB 提供程序实现数据源属性，如下所示。  
  
|属性 ID|Description|  
|-----------------|-----------------|  
|DBPROP_CURRENTCATALOG|R/W：读/写 默认值：无<br /><br /> 说明： DBPROP_CURRENTCATALOG 的值报告的当前数据库[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Native Client OLE DB 访问接口会话。 设置属性值已设置当前数据库使用相同的效果[!INCLUDE[tsql](../../includes/tsql-md.md)]使用*数据库*语句。<br /><br /> 开头[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]，如果调用[sp_defaultdb](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql)并指定数据库名称在较低的情况下，即使最初创建数据库时的混合大小写名称，DBPROP_CURRENTCATALOG 将返回名称以小写形式。 对于 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的早期版本，DBPROP_CURRENTCATALOG 将返回预期的大小写混合形式。|  
|DBPROP_MULTIPLECONNECTIONS|R/W：读/写 默认值：VARIANT_FALSE<br /><br /> 说明：如果将 DBPROP_MULTIPLECONNECTIONS 设置为 VARIANT_TRUE，当连接运行的命令未生成行集或生成的行集不是服务器游标时，执行其他命令时将新建一个连接，以便执行该命令。<br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB 提供程序将不会创建另一个连接，如果 DBPROP_MULTIPLECONNECTION 为 VARIANT_FALSE，或一个事务处于活动状态的连接上。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB 访问接口返回 DB_E_OBJECTOPEN，如果 DBPROP_MULTIPLECONNECTIONS 为 VARIANT_FALSE，并且如果没有活动事务，则返回 E_FAIL。 事务和锁定是在每个连接的基础上通过 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 来管理的。 如果生成第二个连接，则该独立连接上的命令不共享锁。 若要确保一个命令不会阻塞另一个命令，请对其他命令所请求的行保持锁定。 当创建多个会话时，将同样保持该锁定。<br /><br /> 每个会话都具有一个单独的连接。|  
  
 在特定于提供程序的属性集 DBPROPSET_SQLSERVERDATASOURCE 中， [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB 访问接口定义以下的其他数据源属性。  
  
|属性 ID|Description|  
|-----------------|-----------------|  
|SSPROP_ENABLEFASTLOAD|R/W：读/写 默认值：VARIANT_FALSE<br /><br /> 说明：若要从内存启用大容量复制，应将 SSPROP_ENABLEFASTLOAD 属性设置为 VARIANT_TRUE。 通过在数据源上设置此属性，新创建的会话将允许使用者访问[IRowsetFastLoad](../native-client-ole-db-interfaces/irowsetfastload-ole-db.md)接口。<br /><br /> 如果属性设置为 VARIANT_TRUE， **IRowsetFastLoad**接口是通过提供**iopenrowset:: Openrowset**通过请求**则**接口或通过设置**SSPROP_IRowsetFastLoad**为 VARIANT_TRUE。|  
|SSPROP_ENABLEBULKCOPY|R/W：读/写 默认值：VARIANT_FALSE<br /><br /> 说明：若要从文件启用大容量复制，应将 SSPROP_ENABLEBULKCOPY 属性设置为 VARIANT_TRUE。 对数据源设置该属性之后，使用者可以访问与会话位于同一级别的 IBCPSession 接口。<br /><br /> 此外，还必须将 SSPROP_IRowsetFastLoad 设置为 VARIANT_TRUE。|  
  
## <a name="see-also"></a>请参阅  
 [数据源对象&#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-data-source-objects/data-source-objects-ole-db.md)  
  
  
