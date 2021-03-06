---
title: OverrideBehavior 元素 (ASSL) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- OverrideBehavior Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
helpviewer_keywords:
- OverrideBehavior element
ms.assetid: 6a5b361a-6061-4b73-b1a7-1237fb77606c
caps.latest.revision: 14
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: aecabbb04cefa1abf706c5f725c3a7f8e41aad07
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37241367"
---
# <a name="overridebehavior-element-assl"></a>OverrideBehavior 元素 (ASSL)
  指示描述的关系的覆盖行为[AttributeRelationship](../objects/attributerelationship-element-assl.md)元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<AttributeRelationship>  
   ...  
   <OverrideBehavior>...</OverrideBehavior>  
   ...  
</AttributeRelationship>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|String（枚举）|  
|默认值|*强*|  
|基数|0-1：可出现一次且仅出现一次的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[AttributeRelationship](../objects/attributerelationship-element-assl.md)|  
|子元素|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Remarks  
 `OverrideBehavior` 元素确定相关属性的定位如何影响属性的定位。  
  
 此元素的值限定为下表中列出的字符串之一。  
  
|ReplTest1|Description|  
|-----------|-----------------|  
|*强*|指示 AttributeRelationship 元素描述的关系的覆盖行为。 决定一个属性的位置如何影响另一个属性的位置。|  
|*无*|无效。|  
  
 与允许的值相对应的枚举`OverrideBehavior`在 Analysis Management Objects (AMO) 对象模型是<xref:Microsoft.AnalysisServices.OverrideBehavior>。  
  
## <a name="see-also"></a>请参阅  
 [属性和属性层次结构](../../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md)   
 [属性&#40;ASSL&#41;](properties-assl.md)  
  
  
