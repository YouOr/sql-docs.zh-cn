---
title: XML 输出文件格式 (ssbdiagnose) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- XML output file format [ssbdiagnose]
- ssbdiagnose
ms.assetid: 3ceb991b-6f15-4504-8828-de5adf448bc5
caps.latest.revision: 12
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: fd4555fdcf53aace8eb48b74f0c62c7da9bf21e8
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37183474"
---
# <a name="xml-output-file-format-ssbdiagnose"></a>XML 输出文件格式 (ssbdiagnose)
  通过 **-XML** 开关运行 **ssbdiagnose** 实用工具时，该实用工具会将其结果输出为 XML 文件。 XML 输出文件将列出在分析 [!INCLUDE[ssSB](../../includes/sssb-md.md)] 配置或会话时发现的标头信息和错误。 您可以编写应用程序分析或报告文件中列出的错误。 或者，您还可以在常规 XML 编辑器（如 XML Notepad）中查看该 XML 文件。  
  
 **ssbdiangose** 输出文件包含具有两种子类型的 DiagnosticInformation 根元素：  
  
-   带有标头信息的 Banner 元素。  
  
-   **ssbdiagnose**报告的每个问题对应的 Issue 元素。  
  
## <a name="diagnosticinformation-root-element"></a>DiagnosticInformation 根元素  
  
-   [DiagnosticInformation 元素&#40;ssbdiagnose&#41;](diagnosticinformation-element-ssbdiagnose.md)  
  
## <a name="banner-element"></a>Banner 元素  
  
-   [Banner 元素&#40;ssbdiagnose&#41;](banner-element-ssbdiagnose.md)  
  
## <a name="issue-element"></a>Issue 元素  
  
-   [Issue 元素&#40;ssbdiagnose&#41;](issue-element-ssbdiagnose.md)  
  
## <a name="see-also"></a>请参阅  
 [ssbdiagnose 实用工具 (Service Broker)](ssbdiagnose-utility-service-broker.md)  
  
  
