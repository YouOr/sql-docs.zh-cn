---
title: MeasureGroup 元素 (ASSL) |Microsoft 文档
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 9372024e5a50e6f512f45915e464d264ee4367f2
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "34036908"
---
# <a name="measuregroup-element-assl"></a>MeasureGroup 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  定义一组属于同一粒度级别的度量值。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<MeasureGroups>  
   <MeasureGroup> <!-- ancestor: Cube -->  
      <Name>...</Name>  
      <ID>...</ID>  
      <CreatedTimestamp>...</<Create  
      <LastSchemaUpdate>...</LastSchemaUpdate>  
      <Description>...</Description>  
      <LastProcessed>...</LastProcessed>  
      <Translations>...</Translations>  
      <Type>...</Type>  
      <State>...</State>  
      <MeasureQualification>...</MeasureQualification>  
      <Measures>...</Measures>  
      <DataAggregation>...</DataAggregation>  
      <Source>...</Source>  
            <StorageMode>...</StorageMode>  
      <StorageLocation>...</StorageLocation>  
      <IgnoreUnrelatedDimensions>...</IgnoreUnrelatedDimensions>  
            <ProactiveCaching>...</ProactiveCaching>  
      <EstimatedRows>...</EstimatedRows>  
      <ErrorConfiguration>...</ErrorConfiguration>  
      <EstimatedSize>...</EstimatedSize>  
      <ProcessingMode>...</ProcessingMode>  
      <Dimensions>...</Dimensions>  
      <Partitions>...</Partitions>  
      <AggregationPrefix>...</AggregationPrefix>  
      <ProcessingPriority>...</ProcessingPriority>  
            <AggregationDesigns>...</AggregationDesigns>  
      <Annotations>...</Annotations>  
   </MeasureGroup>  
   <!-- or  -->  
   <MeasureGroup xsi:type="MeasureGroupBinding">...</MeasureGroup> <!-- ancestor: CubeBinding -->  
   <!-- or  -->  
   <MeasureGroup xsi:type="PerspectiveMeasureGroup">...</MeasureGroup> <!-- ancestor: Perspective -->  
</MeasureGroups>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|说明|  
|--------------------|-----------------|  
|数据类型和长度|请参阅下表。|  
|默认值|无|  
|基数|0-n：可多次出现的可选元素。|  
  
|祖先或父级|数据类型|  
|------------------------|---------------|  
|[Cube](../../../analysis-services/scripting/objects/cube-element-assl.md)|無|  
|[CubeBinding](../../../analysis-services/scripting/data-type/cubebinding-data-type-out-of-line-assl.md)|[MeasureGroupBinding](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-assl.md)|  
|[透视](../../../analysis-services/scripting/objects/perspective-element-assl.md)|[PerspectiveMeasureGroup](../../../analysis-services/scripting/data-type/perspectivemeasuregroup-data-type-assl.md)|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[MeasureGroups](../../../analysis-services/scripting/collections/measuregroups-element-assl.md)|  
|子元素|请参阅下表。|  
  
|祖先或父级|子元素|  
|------------------------|--------------------|  
|[Cube](../../../analysis-services/scripting/objects/cube-element-assl.md)|[AggregationDesigns](../../../analysis-services/scripting/collections/aggregationdesigns-element-assl.md)， [AggregationPrefix](../../../analysis-services/scripting/properties/aggregationprefix-element-assl.md)，[批注](../../../analysis-services/scripting/collections/annotations-element-assl.md)， [CreatedTimestamp](../../../analysis-services/scripting/properties/createdtimestamp-element-assl.md)， [DataAggregation](../../../analysis-services/scripting/properties/dataaggregation-element-assl.md)，[说明](../../../analysis-services/scripting/properties/description-element-assl.md)，[维度](../../../analysis-services/scripting/collections/dimensions-element-assl.md)， [ErrorConfiguration](../../../analysis-services/scripting/objects/errorconfiguration-element-assl.md)， [EstimatedRows](../../../analysis-services/scripting/properties/estimatedrows-element-assl.md)， [EstimatedSize](../../../analysis-services/scripting/properties/estimatedsize-element-assl.md)， [ID](../../../analysis-services/scripting/properties/id-element-assl.md)， [IgnoreUnrelatedDimensions](../../../analysis-services/scripting/properties/ignoreunrelateddimensions-element-assl.md)， [LastProcessed](../../../analysis-services/scripting/properties/lastprocessed-element-assl.md)， [LastSchemaUpdate](../../../analysis-services/scripting/properties/lastschemaupdate-element-assl.md)， [MeasureQualification](../../../analysis-services/scripting/properties/measurequalificaton-element-assl.md)，[度量值](../../../analysis-services/scripting/collections/measures-element-assl.md)，[名称](../../../analysis-services/scripting/properties/name-element-assl.md)，[分区](../../../analysis-services/scripting/collections/partitions-element-assl.md)， [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md)， [ProcessingMode](../../../analysis-services/scripting/properties/processingmode-element-assl.md)， [ProcessingPriority](../../../analysis-services/scripting/properties/processingpriority-element-assl.md)，[源](../../../analysis-services/scripting/properties/source-element-measure-assl.md)，[状态](../../../analysis-services/scripting/properties/state-element-assl.md)， [StorageLocation](../../../analysis-services/scripting/properties/storagelocation-element-assl.md)， [StorageMode](../../../analysis-services/scripting/properties/storagemode-element-assl.md)，[翻译](../../../analysis-services/scripting/collections/translations-element-assl.md)，[类型](../../../analysis-services/scripting/properties/type-element-measuregroup-assl.md)|  
|[CubeBinding](../../../analysis-services/scripting/data-type/cubebinding-data-type-out-of-line-assl.md)|無|  
|[透视](../../../analysis-services/scripting/objects/perspective-element-assl.md)|無|  
  
## <a name="remarks"></a>注释  
 度量值组中的所有度量值都必须源自单个表。 度量值组可定义可为每个分区重写的默认绑定。  
  
 **MeasureGroup** 元素定义常规多维数据集和虚拟多维数据集上的度量值组共有的详细信息。 单独的子类型定义特定于每种类型的详细信息。  
  
 **State** 的 **MeasureGroup** 属性具有以下值：  
  
-   处理了所有分区后，值为*FullyProcessed* 。  
  
-   处理了至少一个分区后，值为*PartiallyProcessed* 。  
  
-   如果未处理任何分区，则值为*Unprocessed* 。  
  
 在 Analysis Management Objects (AMO) 对象模型中，对应的元素为 <xref:Microsoft.AnalysisServices.MeasureGroup> 和 <xref:Microsoft.AnalysisServices.PerspectiveMeasureGroup>。  
  
## <a name="see-also"></a>另请参阅  
 [对象 & #40;ASSL & #41;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  
