---
title: MasterDatasourceID 元素 (ASSL) |Microsoft Docs
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
- MasterDatasourceID Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- MasterDatasourceID
helpviewer_keywords:
- MasterDatasourceID element
ms.assetid: a9cbd3a9-581f-4a08-93d8-e1eea8757ce9
caps.latest.revision: 34
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 70258c84b128c879406a8c0cdda837d9f0475789
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37228457"
---
# <a name="masterdatasourceid-element-assl"></a>MasterDatasourceID 元素 (ASSL)
  包含主数据源标识符 (ID)[数据库](../objects/database-element-assl.md)元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Database>  
   ...  
   <MasterDatasourceID>...</MasterDatasourceID>  
   ...  
</Database>  
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
|父元素|[“数据库”](../objects/database-element-assl.md)|  
|子元素|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Remarks  
 远程实例上的数据库[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]包含远程分区`MasterDatasourceID`元素中包含的数据源 ID 用于标识的主实例的数据源[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]管理远程分区。  
  
 父级对应的元素`MasterDatasourceID`在 Analysis Management Objects (AMO) 对象模型是<xref:Microsoft.AnalysisServices.Database>。  
  
## <a name="see-also"></a>请参阅  
 [属性&#40;ASSL&#41;](properties-assl.md)  
  
  
