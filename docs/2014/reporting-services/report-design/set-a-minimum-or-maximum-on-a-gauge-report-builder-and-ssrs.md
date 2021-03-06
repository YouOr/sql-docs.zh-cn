---
title: 设置仪表的最小值或最大值（报表生成器和 SSRS）| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: b4c260c0-5a88-4f30-8977-eb5cc78fc146
caps.latest.revision: 6
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: 4bb8b841b4835d74eb37ff531f21b4942cc32738
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37278473"
---
# <a name="set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs"></a>设置仪表的最小值或最大值（报表生成器和 SSRS）
  与其中定义了多个组的图表不同，仪表上只显示一个值。 由于报表生成器和报表设计器确定要在仪表上显示的一个值的上下文或相对重要性，因此必须定义刻度的最小值和最大值。 例如，如果数据值是介于 0 到 10 之间的评分，则需要将最小值设置为 0，将最大值设置为 10。 间隔数值会根据指定的最小值和最大值自动计算。 默认情况下，最小值设置为 0，最大值设置为 100，但这是您可任意更改的值。 应用程序不会将您的值计算为百分比。  
  
 如果您的值范围较大，例如从 0 到 10000，可考虑使用乘数以减少仪表上零的数量。 乘数只会减小仪表上数值的刻度，但不会减小值本身。  
  
 您可以使用表达式来设置 **“最小值”** 和 **“最大值”** 选项的值。 有关详细信息，请参阅[表达式（报表生成器和 SSRS）](expressions-report-builder-and-ssrs.md)。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-the-minimum-and-maximum-on-the-gauge"></a>在仪表上设置最小值和最大值  
  
1.  右键单击刻度并选择“刻度属性”。 此时将显示 **“刻度属性”** 对话框。  
  
2.  在 **“常规”** 中，为 **“最小值”** 指定一个值。 默认情况下，此值为 0。 或者，单击“表达式”(fx) 按钮，编辑设置该选项值的表达式。  
  
3.  为 **“最大值”** 指定一个值。 默认情况下，此值为 100。 或者，单击“表达式”(fx) 按钮，编辑设置该选项值的表达式。  
  
4.  （可选）如果最大值和最小值较大，请为“刻度标签乘以”选项指定一个值。 若要指定可减小刻度的乘数，请使用小数。 例如，如果刻度范围为 0 到 1000，则可指定乘数值 0.01，以将刻度范围减少到只显示 0 到 10。  
  
## <a name="see-also"></a>请参阅  
 [设置仪表上刻度的格式（报表生成器和 SSRS）](formatting-scales-on-a-gauge-report-builder-and-ssrs.md)   
 [设置仪表上指针的格式（报表生成器和 SSRS）](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md)   
 [仪表（报表生成器和 SSRS）](gauges-report-builder-and-ssrs.md)  
  
  
