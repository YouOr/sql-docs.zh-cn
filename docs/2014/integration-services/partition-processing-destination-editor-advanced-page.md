---
title: 分区处理目标编辑器 （高级页） |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.advanced.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: 2039ee0f-069d-479d-90b2-2a12481b1162
caps.latest.revision: 32
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 996373337fe9c54218350cb23ca4f12f8d5869c8
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37164958"
---
# <a name="partition-processing-destination-editor-advanced-page"></a>分区处理目标编辑器（“高级”页）
  可以使用 **“分区处理目标编辑器”** 对话框的 **“高级”** 页配置错误处理方式。  
  
 若要了解有关分区处理目标的详细信息，请参阅 [Partition Processing Destination](data-flow/partition-processing-destination.md)。  
  
> [!NOTE]  
>  此处所述的任何不适用于 Analysis Services 表格模型。  你无法将输入列映射到表格模型的分区列。 您可以改用 [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) 处理分区。  
  
## <a name="options"></a>“常规”  
 **使用默认错误配置**  
 指定是否使用 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] 的默认错误处理方式。 默认情况下，此值为 `True`。  
  
 **键错误操作**  
 指定如何处理包含不可接受的键值的记录。  
  
|ReplTest1|Description|  
|-----------|-----------------|  
|**ConvertToUnknown**|将无法接受的键值转换为 Unknown 值。|  
|**DiscardRecord**|放弃记录。|  
  
 **忽略错误**  
 指定将忽略错误。  
  
 **出错时停止**  
 指定在出现错误时应停止处理。  
  
 **错误数**  
 如果选择了“出错时停止”，请指定应停止处理的错误阈值。  
  
 **出错时要执行的操作**  
 如果选择了“出错时停止”，请指定在达到错误阈值时要执行的操作。  
  
|ReplTest1|Description|  
|-----------|-----------------|  
|**StopProcessing**|停止处理。|  
|**StopLogging**|停止记录错误。|  
  
 **找不到键**  
 指定在出现“找不到键”错误时执行的操作。 默认情况下，此值为 **ReportAndContinue**。  
  
|ReplTest1|Description|  
|-----------|-----------------|  
|**IgnoreError**|忽略错误并继续处理。|  
|**ReportAndContinue**|报告错误并继续处理。|  
|**ReportAndStop**|报告错误并停止处理。|  
  
 **重复键**  
 指定在出现“重复键”错误时执行的操作。 默认情况下，此值为 **IgnoreError**。  
  
|ReplTest1|Description|  
|-----------|-----------------|  
|**IgnoreError**|忽略错误并继续处理。|  
|**ReportAndContinue**|报告错误并继续处理。|  
|**ReportAndStop**|报告错误并停止处理。|  
  
 **空键转换为未知键**  
 指定在将空键转换为 Unknown 值后所采取的操作。 默认情况下，此值为 **IgnoreError**。  
  
|ReplTest1|Description|  
|-----------|-----------------|  
|**IgnoreError**|忽略错误并继续处理。|  
|**ReportAndContinue**|报告错误并继续处理。|  
|**ReportAndStop**|报告错误并停止处理。|  
  
 **不允许空键**  
 指定在不允许空键而又遇到空键时执行的操作。 默认情况下，此值为 **ReportAndContinue**。  
  
|ReplTest1|Description|  
|-----------|-----------------|  
|**IgnoreError**|忽略错误并继续处理。|  
|**ReportAndContinue**|报告错误并继续处理。|  
|**ReportAndStop**|报告错误并停止处理。|  
  
 **错误日志路径**  
 键入错误日志的路径，或者使用浏览按钮 **(...)** 选择目标。  
  
 **浏览(...)**  
 选择错误日志的路径。  
  
## <a name="see-also"></a>请参阅  
 [Integration Services 错误和消息引用](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [分区处理目标编辑器&#40;映射页&#41;](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md)  
  
  
