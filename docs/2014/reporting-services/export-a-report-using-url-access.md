---
title: 使用 URL 访问导出报表 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- formats [Reporting Services], URL rendering
- URL access [Reporting Services], rendering formats
ms.assetid: 6a3b7fc3-3d91-4d12-8371-42ea12e74517
caps.latest.revision: 38
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: d44c68f381ee1fd7b6fed31e15bf2639dd57976e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37327437"
---
# <a name="export-a-report-using-url-access"></a>使用 URL 访问导出报表
  您可以选择指定用来通过使用来呈现报表的格式*rs: Format*参数。 例如，若要直接从本机模式报表服务器获取报表的 PDF 副本：  
  
```  
http://myrshost/ReportServer?/myreport&rs:Format=PDF  
```  
  
 此外，若要从 SharePoint 集成模式的报表服务器获取：  
  
```  
http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/myrereport.rdl&rs:Format=PDF  
```  
  
 对于此参数，有效值为何随要访问的报表服务器上所安装的报表呈现扩展插件而异。 常见的扩展插件有 HTML4.0、MHTML、IMAGE、EXCEL、WORD、CSV、PDF、XML 和 NULL。 如果指定的呈现扩展插件未安装在相应的报表服务器上，则相应报表将不能呈现，并将生成错误，同时通过浏览器来显示该错误。  
  
 如果未在 URL 中纳入 *Format* 参数，则报表服务器将检测浏览器，并将相应报表呈现为合适的 HTML 格式。  
  
## <a name="see-also"></a>请参阅  
 [URL 访问&#40;SSRS&#41;](url-access-ssrs.md)   
 [URL 访问参数引用](url-access-parameter-reference.md)  
  
  
