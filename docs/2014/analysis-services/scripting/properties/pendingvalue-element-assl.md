---
title: PendingValue 元素 (ASSL) |Microsoft Docs
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
- PendingValue Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- PendingValue
helpviewer_keywords:
- PendingValue element
ms.assetid: 386b2ec6-3d83-42d2-b83a-83e375fbdcbd
caps.latest.revision: 34
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: ef24ae229f879adc15fa9f2ecfd8cb10a19d09ff
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37263393"
---
# <a name="pendingvalue-element-assl"></a>PendingValue 元素 (ASSL)
  包含只读挂起值关联的[ServerProperty](../objects/serverproperty-element-assl.md)元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<ServerProperty>  
   ...  
   <PendingValue>...</PendingValue>  
   ...  
</ServerProperty>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|任何 simpleType|  
|默认值|InclusionThresholdSetting|  
|基数|0-1：可出现一次且仅出现一次的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[ServerProperty](../objects/serverproperty-element-assl.md)|  
|子元素|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Remarks  
 此元素包含的值`ServerProperty`，将使用下一次的当前实例[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]已启动。 通常，此值是从服务器属性值的存储位置（初始化文件、[!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 注册表或其他存储机制）检索而来。  
  
 父级对应的元素`PendingValue`在 Analysis Management Objects (AMO) 对象模型是<xref:Microsoft.AnalysisServices.ServerProperty>。  
  
## <a name="see-also"></a>请参阅  
 [ServerProperties 元素&#40;ASSL&#41;](../collections/serverproperties-element-assl.md)   
 [服务器元素&#40;ASSL&#41;](../objects/server-element-assl.md)   
 [属性&#40;ASSL&#41;](properties-assl.md)  
  
  
