---
title: 报表属性对话框，引用 （报表生成器） |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- "10082"
ms.assetid: 3414c857-8ea6-4fc4-a6d5-b4883c039efa
caps.latest.revision: 11
author: maggiesmsft
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 99be366023499607a5798ea202445f2b4a57b6c4
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37286663"
---
# <a name="report-properties-dialog-box-references-report-builder"></a>“报表属性”对话框 ->“引用”（报表生成器）
  选择 **“报表属性”** 对话框中的 **“引用”** 可以添加或删除对报表定义中的表达式所使用的自定义程序集或其他外部程序集以及自定义类实例的引用。 在报表生成器本地模式中，不支持自定义程序集。 为使用自定义程序集，请使用报表设计器中创作报表[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]。  
  
## <a name="options"></a>“常规”  
 **添加或删除程序集**  
 列出报表引用的程序集。 该程序集在安装报表设计工具的计算机上以及报表服务器上必须可用。 引用的名称必须匹配的内容 **\<CodeModule >** 完全标记报表定义语言 (.rdl) 文件中。  
  
 **“添加”**  
 单击该选项可以添加程序集。 单击省略号 (…) 按钮可以打开“打开”对话框，并选择完成报表处理和表达式计算所需的程序集。  
  
 **删除**  
 若要从列表中删除程序集引用，请选择程序集名并单击“删除”按钮。  
  
 **添加或删除类**  
 列出报表使用的类实例。 该类列表仅适用于基于实例的成员，而不适用于静态成员。  
  
 **“添加”**  
 单击该选项可以添加类引用。 单击省略号 (…) 按钮可以打开“打开”对话框，并选择完成报表处理和表达式计算所需的类。  
  
 **删除**  
 若要删除类实例，请选中该实例并单击“删除”按钮。  
  
 **向上**  
 可为有依赖关系的类在列表中上移该引用。  
  
 **向下**  
 可为有依赖关系的类在列表中下移该引用。  
  
## <a name="see-also"></a>请参阅  
 [用于对话框、窗格和向导的报表生成器帮助](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md)   
 [表达式（报表生成器和 SSRS）](report-design/expressions-report-builder-and-ssrs.md)  
  
  
