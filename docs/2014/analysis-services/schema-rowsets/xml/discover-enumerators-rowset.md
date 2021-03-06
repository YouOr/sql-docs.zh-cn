---
title: DISCOVER_ENUMERATORS 行集 |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- DISCOVER_ENUMERATORS
topic_type:
- apiref
helpviewer_keywords:
- DISCOVER_ENUMERATORS rowset
ms.assetid: ddc7b13c-3135-4419-8166-eddd459167da
caps.latest.revision: 31
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 328d37a9d010388c0cb8d0e7e9d251601e35f949
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37302707"
---
# <a name="discoverenumerators-rowset"></a>DISCOVER_ENUMERATORS 行集
  返回特定数据源的 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] XML for Analysis (XMLA) 访问接口支持的枚举器的名称列表、数据类型和枚举值。 XMLA 访问接口可发布它所识别的所有枚举常量。  
  
 如果您调用[Discover](../../xmla/xml-elements-methods-discover.md)方法替换`DISCOVER_ENUMERATORS`中的枚举值[RequestType](../../xmla/xml-elements-properties/type-element-xmla.md)元素，`Discover`方法将返回`DISCOVER_ENUMERATORS`架构行集。  
  
## <a name="rowset-columns"></a>行集列  
 每个枚举器都包含多个元素，枚举中的每个值都对应一个元素。 表示每个枚举器的行集是平面的，可以对属于同一枚举的多个元素重复使用相应枚举器的名称。  
  
 `DISCOVER_ENUMERATORS`行集包含以下列。  
  
|列名|类型指示符|长度|Description|  
|-----------------|--------------------|------------|-----------------|  
|`EnumName`|`DBTYPE_WSTR`||包含一组值的枚举器的名称。|  
|`EnumDescription`|`DBTYPE_WSTR`||枚举器的可本地化说明。 可以是`NULL`。|  
|`EnumType`|`DBTYPE_WSTR`||枚举值的数据类型。|  
|`ElementName`|`DBTYPE_WSTR`||枚举器集中一个值元素的名称。<br /><br /> 例如：`TDP`|  
|`ElementDescription`|`DBTYPE_WSTR`||（可选）元素的可本地化说明。 可以是`NULL`。|  
|`ElementValue`|`DBTYPE_WSTR`||元素的值。 可以是`NULL`。<br /><br /> 例如：`01`|  
  
 未对此架构行集进行排序。  
  
## <a name="restriction-columns"></a>限制列  
 `DISCOVER_ENUMERATORS`行集可以限制下表中列出的列。  
  
|列名|类型指示符|限制状态|  
|-----------------|--------------------|-----------------------|  
|`EnumName`|`DBTYPE_WSTR`||  
  
## <a name="see-also"></a>请参阅  
 [XML for Analysis 架构行集](xml-for-analysis-schema-rowsets.md)  
  
  
