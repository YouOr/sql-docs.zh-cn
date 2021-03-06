---
title: DiscoverResponse 元素 (XMLA) |Microsoft 文档
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: b9ad13a08b6afa19b59dbdaf8d43686c13649a43
ms.sourcegitcommit: 808d23a654ef03ea16db1aa23edab496b73e5072
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34574340"
---
# <a name="xml-elements---objects---discoverresponse"></a>XML 元素的对象-DiscoverResponse
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
  包含返回到响应中的 Analysis Services 实例的信息[发现](../../analysis-services/xmla/xml-elements-methods-discover.md)方法调用。  
  
 **Namespace** urn： 架构-microsoft-com:xml-分析  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<DiscoverResponse>  
   <return>  
</DiscoverResponse>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|InclusionThresholdSetting|  
|默认值|InclusionThresholdSetting|  
|基数|1-1：可出现一次且仅出现一次的必需元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|InclusionThresholdSetting|  
|子元素|[返回](../../analysis-services/xmla/xml-elements-properties/return-element-xmla.md)|  
  
## <a name="remarks"></a>Remarks  
 **DiscoverResponse**元素是在主体中的 SOAP 响应的最顶端元素**发现**方法。  
  
## <a name="see-also"></a>另请参阅
 [ExecuteResponse 元素&#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-objects-executeresponse.md)   
 [对象&#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-objects.md)  
  
  
