---
title: NullKeyConvertedToUnknown 元素 (ASSL) |Microsoft Docs
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
- NullKeyConvertedToUnknown Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- NullKeyConvertedToUnknown
helpviewer_keywords:
- NullKeyConvertedToUnknown element
ms.assetid: 1a6cde33-01ba-4095-b464-16d1ad3c6905
caps.latest.revision: 37
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: cebeef3421533b429a38f6c5696780cb008eca69
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37316917"
---
# <a name="nullkeyconvertedtounknown-element-assl"></a>NullKeyConvertedToUnknown 元素 (ASSL)
  指定遇到空转换错误时要执行的操作。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<ErrorConfiguration>  
   ...  
      <NullKeyConvertedToUnknown>...</NullKeyConvertedToUnknown>  
   ...  
</ErrorConfiguration>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|String（枚举）|  
|默认值|*IgnoreError*|  
|基数|0-1：可出现一次且仅出现一次的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[ErrorConfiguration](../objects/errorconfiguration-element-assl.md)|  
|子元素|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Remarks  
 在键列中遇到空值并被解释为 `Unknown` 成员时，将引发空转换错误。 但是，此错误发生才[NullProcessing](nullprocessing-element-assl.md)元素[DataItem](../data-type/dataitem-data-type-assl.md)的祖先`ErrorConfiguration`父元素设置为*UnknownMember*。  
  
 此元素的值限定为下表中列出的字符串之一。  
  
|ReplTest1|Description|  
|-----------|-----------------|  
|*IgnoreError*|处理会忽略该错误并继续。|  
|*ReportAndContinue*|处理报告错误并继续。|  
|*ReportAndStop*|处理报告错误并停止。|  
  
 与允许的值相对应的枚举`NullKeyConvertedToUnknown`在 Analysis Management Objects (AMO) 对象模型是<xref:Microsoft.AnalysisServices.ErrorOption>。  
  
## <a name="see-also"></a>请参阅  
 [ErrorConfiguration 元素&#40;ASSL&#41;](../objects/errorconfiguration-element-assl.md)   
 [属性&#40;ASSL&#41;](properties-assl.md)  
  
  
