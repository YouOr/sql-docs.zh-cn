---
title: For 循环编辑器 |Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.forloopcontainer.f1
ms.assetid: c4db9df6-d2f4-44da-9f4d-628893e86956
caps.latest.revision: 26
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: af80869fbba015492b469af030d5cc297e7127e6
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37205817"
---
# <a name="for-loop-editor"></a>For 循环编辑器
  可以使用 **“For 循环编辑器”** 对话框的 **“For 循环”** 页，配置只有在指定条件的计算结果为 False 时才会停止重复执行工作流的循环。  
  
 若要了解有关 For 循环容器以及如何在包中使用它的信息，请参阅 [For Loop Container](control-flow/for-loop-container.md)。  
  
## <a name="options"></a>“常规”  
 **InitExpression**  
 提供初始化该循环所用值的表达式（可选）。  
  
 **EvalExpression**  
 提供用于计算循环应停止还是继续的表达式。  
  
 **AssignExpression**  
 提供在每次循环重复时更改条件的表达式（可选）。  
  
 **名称**  
 为 For 循环容器提供唯一的名称。 此名称用作任务图标中的标签。  
  
> [!NOTE]  
>  对象名称在一个包内必须是唯一的。  
  
 **Description**  
 提供 For 循环容器的说明。  
  
## <a name="see-also"></a>请参阅  
 [Integration Services 错误和消息引用](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [表达式页](expressions/expressions-page.md)   
 [Foreach 循环容器](control-flow/foreach-loop-container.md)   
 [配置 For Loop 容器](../../2014/integration-services/configure-a-for-loop-container.md)  
  
  
