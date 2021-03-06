---
title: 架构元素 (ASSL) |Microsoft Docs
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
- Schema Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- Schema
helpviewer_keywords:
- Schema element
ms.assetid: 4b6375fb-7ad8-4d5f-88b1-abd3da2654db
caps.latest.revision: 34
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 3bcf275eafb8a982fa2ddf9d5ecb82d45e435fa5
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37200037"
---
# <a name="schema-element-assl"></a>Schema 元素 (ASSL)
  包含数据源视图的架构。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<DataSourceView>  
   ...  
   <Schema>...</Schema>  
   ...  
</DataSourceView>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|架构|  
|默认值|InclusionThresholdSetting|  
|基数|1-1：出现一次且仅出现一次的必需元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[DataSourceView](../objects/datasourceview-element-assl.md)|  
|子元素|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Remarks  
 `Schema` 是通过使用 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework 中 DataSet 的 XML 架构定义 (XSD) 语言格式、以及 DataSet 的某些扩展和数据定义语言 (DDL) 中的特定于此用法的其他扩展来表示的。 DataSet 可定义从 XSD 到关系架构的灵活映射，然后以更为规范化的格式返回 XSD。 只有此规范化的格式在数据源中才有效。  
  
 父级对应的元素`Schema`在 Analysis Management Objects (AMO) 对象模型是<xref:Microsoft.AnalysisServices.DataSourceView>。  
  
## <a name="see-also"></a>请参阅  
 [属性&#40;ASSL&#41;](properties-assl.md)  
  
  
