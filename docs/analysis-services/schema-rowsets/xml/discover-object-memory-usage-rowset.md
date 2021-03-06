---
title: DISCOVER_OBJECT_MEMORY_USAGE 行集 |Microsoft 文档
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: schema-rowsets
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 70a316189077598ee275074394a499d253fe2188
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "34030478"
---
# <a name="discoverobjectmemoryusage-rowset"></a>DISCOVER_OBJECT_MEMORY_USAGE 行集
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  提供对象使用的内存资源的相关信息。  
  
## <a name="rowset-columns"></a>行集列  
 **DISCOVER_OBJECT_MEMORY_USAGE**行集包含以下各列。  
  
|列名|类型指示符|长度|Description|  
|-----------------|--------------------|------------|-----------------|  
|**OBJECT_PARENT_PATH**|**DBTYPE_WSTR**||当前对象的父路径。|  
|**OBJECT_ID**|**DBTYPE_WSTR**||创建时定义的对象的 ID。|  
|**OBJECT_MEMORY_SHRINKABLE**|**DBTYPE_I8**||当前对象直接拥有的所有可收缩对象使用的内存总量（字节）。 当前值不包括从归当前对象拥有的命名对象的对象的内存。|  
|**OBJECT_MEMORY_NONSHRINKABLE**|**DBTYPE_I8**||当前对象直接拥有的所有不可收缩对象的内存量（字节）。 当前值不包括当前对象拥有的命名对象所拥有的对象的内存。|  
|**OBJECT_VERSION**|**DBTYPE_I4**||对象的元数据版本号。 每次更改对象时，此编号随之发生变化。|  
|**OBJECT_DATA_VERSION**|**DBTYPE_I4**||对象中数据的沿袭编号。 每次处理对象时，此编号随之递增。|  
|**OBJECT_TYPE_ID**|**DBTYPE_I4**||保留以供内部使用。|  
|**OBJECT_TIME_CREATED**|**DBTYPE_DBTIMESTAMP**||创建对象时的 UTC 服务器时间。|  
  
 未对此架构行集进行排序。  
  
## <a name="restriction-columns"></a>限制列  
 **DISCOVER_OBJECT_MEMORY_USAGE**行集可限制在下表中列出的列。  
  
|列名|类型指示符|限制状态|  
|-----------------|--------------------|-----------------------|  
|**OBJECT_PARENT_PATH**|**DBTYPE_WSTR**|選擇性。|  
|**OBJECT_ID**|**DBTYPE_WSTR**|選擇性|  
  
## <a name="see-also"></a>另请参阅  
 [XML for Analysis 架构行集](../../../analysis-services/schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
  
