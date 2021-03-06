---
title: TableMiningStructureColumn 数据类型 (ASSL) |Microsoft Docs
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
- TableMiningStructureColumn Data Type
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- TableMiningStructureColumn
helpviewer_keywords:
- TableMiningStructureColumn data type
ms.assetid: 350358b0-f2fc-43c3-957d-884c59fa879e
caps.latest.revision: 36
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 2e03fec81f796ccf87f19df9b2e43fe29b0e318e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37319397"
---
# <a name="tableminingstructurecolumn-data-type-assl"></a>TableMiningStructureColumn 数据类型 (ASSL)
  定义一个派生的数据类型，表示[MiningStructureColumn](miningstructurecolumn-data-type-assl.md)包含嵌套的表，而不是与关联的标量值的元素[ScalarMiningStructureColumn](scalarminingstructurecolumn-data-type-assl.md)元素包含标量值。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<TableMiningStructureColumn>  
   <!-- The following elements extend MiningStructureColumn -->  
   <ForeignKeyColumn>..</ForeignKeyColumn>  
   <SourceMeasureGroup>..</SourceMeasureGroup>  
   <Columns>..</Columns>  
   <Translations>..</Translations>  
</TableMiningStructureColumn>  
```  
  
## <a name="data-type-characteristics"></a>数据类型特征  
  
|特征|Description|  
|--------------------|-----------------|  
|基本数据类型|[MiningStructureColumn](miningstructurecolumn-data-type-assl.md)|  
|派生数据类型|InclusionThresholdSetting|  
  
## <a name="data-type-relationships"></a>数据类型关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|InclusionThresholdSetting|  
|子元素|[列](../collections/columns-element-assl.md)， [ForeignKeyColumn](../objects/column-element-assl.md)， [SourceMeasureGroup](../objects/group-element-assl.md)，[翻译](../collections/translations-element-assl.md)|  
|派生元素|[列](../objects/column-element-assl.md)([列](../collections/columns-element-assl.md)的集合[MiningStructure](../objects/miningstructure-element-assl.md))|  
  
## <a name="remarks"></a>Remarks  
 在 Analysis Management Objects (AMO) 对象模型中的相应元素是<xref:Microsoft.AnalysisServices.TableMiningStructureColumn>。  
  
## <a name="see-also"></a>请参阅  
 [Analysis Services 脚本语言 XML 数据类型&#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
