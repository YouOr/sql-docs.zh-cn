---
title: Original 元素 (XMLA) |Microsoft Docs
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 0ddf701f236e66680f562fa0721bcc8a2eb179f8
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38050385"
---
# <a name="original-element-xmla"></a>Original 元素 (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  包含由原始文件系统存储位置[文件夹](../../../analysis-services/xmla/xml-elements-properties/folder-element-xmla.md)元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Folder>  
   ...  
   <Original>...</Original>  
   ...  
</Folder>  
```  
  
## <a name="element-characteristics"></a>元素的特性  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|String|  
|默认值|InclusionThresholdSetting|  
|基数|1-1：出现一次且仅出现一次的必需元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[文件夹](../../../analysis-services/xmla/xml-elements-properties/folder-element-xmla.md)|  
|子元素|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Remarks  
 **原始**元素包含要替换的值的 UNC 路径[新建](../../../analysis-services/xmla/xml-elements-properties/new-element-xmla.md)包含父元素**文件夹**还原的所有对象的元素或已同步，分别期间[还原](../../../analysis-services/xmla/xml-elements-commands/restore-element-xmla.md)或[同步](../../../analysis-services/xmla/xml-elements-commands/synchronize-element-xmla.md)命令。 此元素的值进行比较的值[StorageLocation](../../../analysis-services/scripting/properties/storagelocation-element-assl.md)元素为每个多维数据集、 度量值组或分区，如果找到匹配项，则**新建**元素用于更新**StorageLocation**在还原或同步期间的对象。  
  
 有关备份和还原对象的详细信息，请参阅[备份、 还原和同步数据库&#40;XMLA&#41;](../../../analysis-services/multidimensional-models-scripting-language-assl-xmla/backing-up-restoring-and-synchronizing-databases-xmla.md)。  
  
## <a name="see-also"></a>另请参阅
 [属性&#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
