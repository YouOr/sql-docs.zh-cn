---
title: 固定和变化的属性选项（渐变维度向导）| Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.dts.loaddimwizard.attriboption.f1
ms.assetid: c841345c-7d03-452f-9379-1c8c464f029c
caps.latest.revision: 29
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 1fd45830c3556bb35148ad857f024bcb512523de
ms.sourcegitcommit: cc46afa12e890edbc1733febeec87438d6051bf9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2018
ms.locfileid: "35407479"
---
# <a name="fixed-and-changing-attribute-options-slowly-changing-dimension-wizard"></a>固定的属性选项和变化的属性选项（渐变维度向导）
  可以使用 **“固定的属性选项和变化的属性选项”** 对话框，指定如何对固定的属性和变化的属性中的更改进行响应。  
  
 若要了解有关此向导的详细信息，请参阅 [Slowly Changing Dimension Transformation](../../../integration-services/data-flow/transformations/slowly-changing-dimension-transformation.md)。  
  
## <a name="options"></a>“常规”  
 **固定的属性**  
 对于固定的属性，指示在固定的属性中检测到更改时，任务是否失败。  
  
 **变化的属性**  
 对于变化的属性，指示在变化的属性中检测到更改时，任务是否应更改除当前记录之外的过时记录或过期记录。 过期记录指被历史特性中的更改（类型 2 更改）替换为较新记录的记录。 选中此选项可能会对在关系数据仓库上构造的多维对象施加其他处理要求。  
  
## <a name="see-also"></a>另请参阅  
 [使用渐变维度向导配置输出](../../../integration-services/data-flow/transformations/configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
