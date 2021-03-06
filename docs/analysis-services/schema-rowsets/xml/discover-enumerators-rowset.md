---
title: DISCOVER_ENUMERATORS 行集 |Microsoft 文档
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: schema-rowsets
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 3c67c7e2a87931aee05af6fcdadabb3263cf66a8
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "34028518"
---
# <a name="discoverenumerators-rowset"></a>DISCOVER_ENUMERATORS 行集
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  返回特定数据源的 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] XML for Analysis (XMLA) 访问接口支持的枚举器的名称列表、数据类型和枚举值。 XMLA 访问接口可发布它所识别的所有枚举常量。  
  
 如果调用[发现](../../../analysis-services/xmla/xml-elements-methods-discover.md)方法替换**DISCOVER_ENUMERATORS**中的枚举值[RequestType](../../../analysis-services/xmla/xml-elements-properties/requesttype-element-xmla.md)元素，**发现**方法返回**DISCOVER_ENUMERATORS**架构行集。  
  
## <a name="rowset-columns"></a>行集列  
 每个枚举器都包含多个元素，枚举中的每个值都对应一个元素。 表示每个枚举器的行集是平面的，可以对属于同一枚举的多个元素重复使用相应枚举器的名称。  
  
 **DISCOVER_ENUMERATORS**行集包含以下各列。  
  
|列名|类型指示符|长度|Description|  
|-----------------|--------------------|------------|-----------------|  
|**枚举名称**|**DBTYPE_WSTR**||包含一组值的枚举器的名称。|  
|**EnumDescription**|**DBTYPE_WSTR**||枚举器的可本地化说明。 可以是**NULL**。|  
|**EnumType**|**DBTYPE_WSTR**||枚举值的数据类型。|  
|**ElementName**|**DBTYPE_WSTR**||枚举器集中一个值元素的名称。<br /><br /> 示例： **TDP，**|  
|**ElementDescription**|**DBTYPE_WSTR**||（可选）元素的可本地化说明。 可以是**NULL**。|  
|**ElementValue**|**DBTYPE_WSTR**||元素的值。 可以是**NULL**。<br /><br /> 示例： **01**|  
  
 未对此架构行集进行排序。  
  
## <a name="restriction-columns"></a>限制列  
 **DISCOVER_ENUMERATORS**行集可限制在下表中列出的列。  
  
|列名|类型指示符|限制状态|  
|-----------------|--------------------|-----------------------|  
|**枚举名称**|**DBTYPE_WSTR**||  
  
## <a name="see-also"></a>另请参阅  
 [XML for Analysis 架构行集](../../../analysis-services/schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
  
