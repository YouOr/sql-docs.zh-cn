---
title: ProductName 元素 (ASSL) |Microsoft Docs
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
- ProductName Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- ProductName
helpviewer_keywords:
- ProductName element
ms.assetid: f8129bb2-55c9-44e1-8857-82dc01c04a7f
caps.latest.revision: 37
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: be8078f2e3949513f76d6aed6dfdd3e66c50ed18
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37187034"
---
# <a name="productname-element-assl"></a>ProductName 元素 (ASSL)
  包含的实例的只读产品名称[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]关联[Server](../objects/server-element-assl.md)元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Server>  
      ...  
      <ProductName>...</ProductName>  
   ...  
</Server>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|String|  
|默认值|InclusionThresholdSetting|  
|基数|0-1：可出现一次且仅出现一次的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[Server](../objects/server-element-assl.md)|  
|子元素|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Remarks  
 `ProductName` 元素提供对与 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] 实例关联的产品名的只读访问。  
  
 父级对应的元素`ProductName`在 Analysis Management Objects (AMO) 对象模型是<xref:Microsoft.AnalysisServices.Server>。  
  
## <a name="see-also"></a>请参阅  
 [属性&#40;ASSL&#41;](properties-assl.md)  
  
  
