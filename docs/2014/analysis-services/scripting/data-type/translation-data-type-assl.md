---
title: Translation 数据类型 (ASSL) |Microsoft Docs
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
- Translation Data Type
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
helpviewer_keywords:
- Translation data type
ms.assetid: d40039e1-3ff6-4e20-8d8b-5baf501f726f
caps.latest.revision: 10
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 96c0f9a1ea7d6e3a081230c43fc95d785b1cf449
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37300877"
---
# <a name="translation-data-type-assl"></a>Translation 数据类型 (ASSL)
  定义表示本地化翻译的基元数据类型。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Translation>  
   <Language>...</Language>  
   <Caption>...</Caption>  
   <Description>...</Description>  
   <DisplayFolder>...</DisplayFolder>  
   <Annotations>...</Annotations>  
</Translation>  
```  
  
## <a name="data-type-characteristics"></a>数据类型特征  
  
|特征|Description|  
|--------------------|-----------------|  
|基本数据类型|InclusionThresholdSetting|  
|派生数据类型|[AttributeTranslation](translation-data-type-assl.md)|  
  
## <a name="data-type-relationships"></a>数据类型关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|InclusionThresholdSetting|  
|子元素|[批注](../collections/annotations-element-assl.md)，[标题](../properties/caption-element-assl.md)，[说明](../properties/description-element-assl.md)， [DisplayFolder](../properties/displayfolder-element-assl.md)，[语言](../properties/language-element-assl.md)|  
|派生元素|[AllMemberTranslation](../objects/translation-element-assl.md)， [AttributeAllMemberTranslation](../objects/attributeallmembertranslation-element-assl.md)， [NamingTemplateTranslation](../objects/namingtemplatetranslation-element-assl.md)， [UnknownMemberTranslation](../objects/unknownmembertranslation-element-assl.md)|  
  
## <a name="remarks"></a>Remarks  
 在 Analysis Management Objects (AMO) 对象模型中的相应元素是<xref:Microsoft.AnalysisServices.Translation>。  
  
## <a name="see-also"></a>请参阅  
 [Analysis Services 脚本语言 XML 数据类型&#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
