---
title: 测量元素 (ASSL) |Microsoft 文档
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 3122fba8b3625a9052e7788d7f491eaad96438d4
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "34036858"
---
# <a name="measure-element-assl"></a>Measure 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  定义一个度量值。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Measures>  
   <Measure> <!-- ancestor: MeasureGroup -->  
      <Name>...</Name>  
      <ID>...</ID>  
      <Description>...</Description>  
      <AggregateFunction>...</AggregateFunction>  
            <DataType>...</DataType>  
            <Source>...</Source>  
      <Visible>...</Visible>  
      <MeasureExpression>...</MeasureExpression>  
      <DisplayFolder>...</DisplayFolder>  
      <FormatString>...</FormatString>  
      <BackColor>...</BackColor>  
      <ForeColor>...</ForeColor>  
            <FontName>...</FontName>  
            <FontSize>...</FontSize>  
            <FontFlags>...</FontFlags>  
            <Translations>...</Translations>  
      <Annotations>...</Annotations>  
   </Measure>  
   <!-- or  -->  
   <Measure xsi:type="AggregationInstanceMeasure">...</Measure> <!-- parent: AggregationInstance -->  
      <!-- or  -->  
   <Measure xsi:type="MeasureBinding">...</Measure> <!-- ancestor: MeasureGroupBinding (out-of-line) -->  
   <!-- or  -->  
   <Measure xsi:type="PerspectiveMeasure">...</Measure> <!-- ancestor: PerspectiveMeasureGroup -->  
</Measures>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|说明|  
|--------------------|-----------------|  
|数据类型和长度|请参阅下表。|  
|默认值|无|  
|基数|0-n：可多次出现的可选元素。|  
  
|祖先或父级|数据类型|  
|------------------------|---------------|  
|[AggregationInstance](../../../analysis-services/scripting/objects/aggregationinstance-element-assl.md)|[AggregationInstanceMeasure](../../../analysis-services/scripting/data-type/measurebinding-data-type-assl.md)|  
|[度量值组](../../../analysis-services/scripting/objects/measuregroup-element-assl.md)|無|  
|[MeasureGroupBinding （外部）](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-out-of-line-assl.md)|[MeasureBinding](../../../analysis-services/scripting/data-type/measurebinding-data-type-assl.md)|  
|[PerspectiveMeasureGroup](../../../analysis-services/scripting/data-type/perspectivemeasuregroup-data-type-assl.md)|[度量值](../../../analysis-services/scripting/data-type/perspectivemeasure-data-type-assl.md)|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[度量值](../../../analysis-services/scripting/collections/measures-element-assl.md)|  
|子元素|请参阅下表。|  
  
|祖先或父级|子元素|  
|------------------------|--------------------|  
|[度量值组](../../../analysis-services/scripting/objects/measuregroup-element-assl.md)|[AggregateFunction](../../../analysis-services/scripting/properties/aggregatefunction-element-assl.md)，[批注](../../../analysis-services/scripting/collections/annotations-element-assl.md)， [BackColor](../../../analysis-services/scripting/properties/backcolor-element-assl.md)， [DataType](../../../analysis-services/scripting/properties/datatype-element-assl.md)，[说明](../../../analysis-services/scripting/properties/description-element-assl.md)， [DisplayFolder](../../../analysis-services/scripting/properties/displayfolder-element-assl.md)， [FontFlags](../../../analysis-services/scripting/properties/fontflags-element-assl.md)，[字体名称](../../../analysis-services/scripting/properties/fontname-element-assl.md)， [FontSize](../../../analysis-services/scripting/properties/fontsize-element-assl.md)， [ForeColor](../../../analysis-services/scripting/properties/forecolor-element-assl.md)， [FormatString](../../../analysis-services/scripting/properties/formatstring-element-assl.md)， [ID](../../../analysis-services/scripting/properties/id-element-assl.md)， [MeasureExpression](../../../analysis-services/scripting/properties/measureexpression-element-assl.md)，[名称](../../../analysis-services/scripting/properties/name-element-assl.md)，[源](../../../analysis-services/scripting/properties/source-element-measure-assl.md)，[翻译](../../../analysis-services/scripting/collections/translations-element-assl.md)，[可见](../../../analysis-services/scripting/properties/visible-element-assl.md)|  
|其他|無|  
  
## <a name="remarks"></a>備註  
 可以为度量值提供绑定详细信息。 这些详细信息可用作每个分区的默认值。  
  
 在较大的多维数据集中，可能有几百个度量值和层次结构。 **DisplayFolder**属性定义客户端上的用户外观。 值**DisplayFolder**属性可以包含以下选项之一：  
  
-   为空，表示该度量值不属于文件夹。  
  
-   包含单个文件夹名称，表示该度量值应呈现为属于具有相同名称的文件夹。  
  
-   包含由反斜杠分隔的多个文件夹名称 (\\)，表示嵌入的文件夹层次结构。  
  
 **DisplayFolder**属性也适用于计算度量值和层次结构。  
  
 在 Analysis Management Objects (AMO) 对象模型中，对应的元素为 <xref:Microsoft.AnalysisServices.Measure> 和 <xref:Microsoft.AnalysisServices.PerspectiveMeasure>。  
  
## <a name="see-also"></a>另请参阅  
 [对象 & #40;ASSL & #41;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  
