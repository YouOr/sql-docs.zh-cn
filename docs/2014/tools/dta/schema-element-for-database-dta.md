---
title: 架构数据库的元素 (DTA) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Schema element
ms.assetid: d932e59c-953f-4ab4-934d-b6baf344835c
caps.latest.revision: 13
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: d334d41335d0065fe1883da8b1f5fceae063751e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37306697"
---
# <a name="schema-element-for-database-dta"></a>数据库的架构元素 (DTA)
  指定要优化的数据库的架构。  
  
## <a name="syntax"></a>语法  
  
```  
  
<Database>  
...code removed here...  
    <Schema>...</Schema>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|**数据类型和长度**|无。|  
|**默认值**|无。|  
|**出现次数**|对于在 **Server** 元素下指定的 **Database** 元素，需要使用一次。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|--------------|  
|**父元素**|[服务器的数据库元素&#40;DTA&#41;](database-element-for-server-dta.md)|  
|**子元素**|[架构的名称元素&#40;DTA&#41;](name-element-for-schema-dta.md)<br /><br /> [表的架构元素&#40;DTA&#41;](table-element-for-schema-dta.md)|  
  
## <a name="example"></a>示例  
 有关此元素的使用示例，请参阅[服务器元素 (DTA)](server-element-dta.md)。  
  
## <a name="see-also"></a>请参阅  
 [XML 输入文件引用（数据库引擎优化顾问）](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
