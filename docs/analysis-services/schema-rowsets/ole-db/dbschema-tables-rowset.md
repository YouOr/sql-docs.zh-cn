---
title: DBSCHEMA_TABLES 行集 |Microsoft 文档
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: schema-rowsets
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 06fc718e4d4bde23bfee4240e89d77bcde3bbf50
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "34032058"
---
# <a name="dbschematables-rowset"></a>DBSCHEMA_TABLES 行集
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  标识的度量值组和维度中的表作为公开[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]。  
  
## <a name="rowset-columns"></a>行集列  
 **DBSCHEMA_TABLES**行集包含以下各列。  
  
|列名|类型指示符|长度|Description|  
|-----------------|--------------------|------------|-----------------|  
|**TABLE_CATALOG**|**DBTYPE_WSTR**|255|此对象所属目录的名称。|  
|**TABLE_SCHEMA**|**DBTYPE_WSTR**|255|此对象所属多维数据集的名称。|  
|**TABLE_NAME**|**DBTYPE_WSTR**|255|对象的名称，如果**TABLE_TYPE**是**表**。|  
|**TABLE_TYPE**|**DBTYPE_WSTR**||表的类型。<br /><br /> **表**指示对象是度量值组。<br /><br /> **系统表**指示对象是一个维度。|  
|**TABLE_GUID**|**DBTYPE_GUID**||不提供支持。|  
|**DESCRIPTION**|**DBTYPE_WSTR**||用户可以阅读的对象说明。|  
|**TABLE_PROPID**|**DBTYPE_UI4**||不提供支持。|  
|**DATE_CREATED**|**DBTYPE_DBTIMESTAMP**||不提供支持。|  
|**DATE_MODIFIED**|**DBTYPE_DBTIMESTAMP**||上次修改对象的日期。|  
|**TABLE_OLAP_TYPE**|**DBTYPE_WSTR**||对象的 OLAP 类型。<br /><br /> **MEASURE_GROUP**指示对象是度量值组。<br /><br /> **CUBE_DIMENSION**指示对象是一个维度。|  
  
 行集按排序**TABLE_TYPE**， **TABLE_CATALOG**， **TABLE_SCHEMA**，和**TABLE_NAME**。  
  
## <a name="restriction-columns"></a>限制列  
 **DBSCHEMA_TABLES**行集可限制在下表中列出的列。  
  
|列名|类型指示符|限制状态|  
|-----------------|--------------------|-----------------------|  
|**TABLE_CATALOG**|**DBTYPE_WSTR**|選擇性|  
|**TABLE_SCHEMA**|**DBTYPE_WSTR**|選擇性|  
|**TABLE_NAME**|**DBTYPE_WSTR**|選擇性|  
|**TABLE_TYPE**|**DBTYPE_WSTR**|選擇性|  
|**TABLE_OLAP_TYPE**|**DBTYPE_WSTR**|選擇性|  
  
## <a name="see-also"></a>另请参阅  
 [OLE DB 架构行集合](../../../analysis-services/schema-rowsets/ole-db/ole-db-schema-rowsets.md)  
  
  
