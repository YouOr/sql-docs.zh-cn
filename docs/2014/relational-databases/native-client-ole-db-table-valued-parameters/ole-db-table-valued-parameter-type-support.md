---
title: OLE DB 表值参数类型支持 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (OLE DB), API support (OLE DB)
ms.assetid: 147036a0-260e-4f81-8b3b-89209e023a32
caps.latest.revision: 22
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: ab07f68b1d83894f04c00883a3a50eb0052d93b0
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37422976"
---
# <a name="ole-db-table-valued-parameter-type-support"></a>OLE DB 表值参数类型支持
  本主题介绍了表值参数的 OLE DB 类型支持。  
  
## <a name="table-valued-parameter-rowset-object"></a>表值参数行集对象  
 您可以创建表值参数的专用行集对象。 使用 ITableDefinitionWithConstraints::CreateTableWithConstraints 或 iopenrowset:: Openrowset 创建表值参数行集对象。 若要执行此操作，设置*eKind*的成员*pTableID*参数为 DBKIND_GUID_NAME 并提供 CLSID_ROWSET_INMEMORY 作为*guid*成员。 必须在指定服务器类型名称为表值参数*pwszName*的成员*pTableID*使用 iopenrowset:: Openrowset 时。 表值参数行集对象行为与常规 SQL Server Native Client OLE DB Provider 对象类似。  
  
```  
const GUID CLSID_ROWSET_TVP =   
{0xc7ef28d5, 0x7bee, 0x443f, {0x86, 0xda, 0xe3, 0x98, 0x4f, 0xcd, 0x4d, 0xf9}};  
  
CoType RowsetTVP  
{  
[mandatory] interface IAccessor;  
[mandatory] interface IColumnsInfo;  
[mandatory] interface IConvertType;  
[mandatory] interface IRowset;  
[mandatory] interface IRowsetInfo;  
[optional]  interface IColumnsRowset;  
[optional]  interface IRowsetChange;  
[optional]  interface ISupportErrorInfo;  
};  
```  
  
## <a name="dbtypetable"></a>DBTYPE_TABLE  
 新类型 DBTYPE_TABLE 表示表类型。 该类型在需要 DBTYPE 的多个 OLE DB 接口中指定了表值参数。  
  
```  
#define DBTYPE_TABLE (143)  
```  
  
 DBTYPE_TABLE 具有与 DBTYPE_IUNKNOWN 相同的格式。 它是指向数据缓冲区中某个对象的指针。 有关在绑定中的完整说明，请使用者应填充 DBOBJECT 缓冲区，使用*iid*设置为行集对象接口 (IID_IRowset) 之一。 如果在绑定中不指定任何 DBOBJECT，则将假定 IID_IRowset。  
  
 不支持任何其他类型转换为 DBTYPE_TABLE 或从 DBTYPE_TABLE 转换为任何其他类型。 IConvertType::CanConvert 将为不支持的之外的任何请求转换为 DBTYPE_TABLE 的转换返回 S_FALSE。 此操作假定命令对象进行 dbconvertflags_parameter 转换。  
  
## <a name="methods"></a>方法  
 有关支持表值参数的 OLE DB 方法的信息，请参阅[OLE DB Table-Valued 参数类型支持&#40;方法&#41;](ole-db-table-valued-parameter-type-support-methods.md)。  
  
## <a name="properties"></a>属性  
 有关支持表值参数的 OLE DB 属性有关的信息，请参阅[OLE DB Table-Valued 参数类型支持&#40;属性&#41;](ole-db-table-valued-parameter-type-support-properties.md)。  
  
## <a name="see-also"></a>请参阅  
 [表值参数&#40;OLE DB&#41;](table-valued-parameters-ole-db.md)   
 [使用表值参数&#40;OLE DB&#41;](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
