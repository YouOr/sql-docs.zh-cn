---
title: PPTX 设备信息设置 | Microsoft Docs
ms.custom: ''
ms.date: 09/11/2015
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.component: reporting-services
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- render
- powerpoint
- pptx
- export
ms.assetid: 4dc2045f-8025-41a3-8f9d-5635fb24cf4a
caps.latest.revision: 6
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 67510c7caebe9497ccd827f5afe258f09fae7102
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "33019876"
---
# <a name="pptx-device-information-settings"></a>PPTX 设备信息设置
  下表列出以 PPTX 格式呈现 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 报表时的设备信息设置。  
  
|设置|ReplTest1|  
|-------------|-----------|  
|**“列”**|要为报表设置的列数。 此值将覆盖报表的原始设置。|  
|**ColumnSpacing**|要为报表设置的列间距。 此值将覆盖报表的原始设置。|  
|**DpiX**|输出图像的水平分辨率。 默认值为 **96**。 适用于 **BMP**、 **GIF**、 **PNG**和 **TIFF** 输出格式。|  
|**DpiY**|输出图像的垂直分辨率。 默认值为 **96**。 适用于 **BMP**、 **GIF**、 **PNG**和 **TIFF** 输出格式。|  
|**EndPage**|要呈现的报表的最后一页。 默认值为 **StartPage**的值。|  
|**MarginBottom**|要为报表设置的下边距值，以英寸为单位。 必须包含一个整数或小数值，后跟“in”（例如， **1in**）。 此值将覆盖报表的原始设置。|  
|**MarginLeft**|要为报表设置的左边距值，以英寸为单位。 必须包含一个整数或小数值，后跟“in”（例如， **1in**）。 此值将覆盖报表的原始设置。|  
|**MarginRight**|要为报表设置的右边距值，以英寸为单位。 必须包含一个整数或小数值，后跟“in”（例如， **1in**）。 此值将覆盖报表的原始设置。|  
|**MarginTop**|要为报表设置的上边距值，以英寸为单位。 必须包含一个整数或小数值，后跟“in”（例如， **1in**）。 此值将覆盖报表的原始设置。|  
|**PageHeight**|要为报表设置的页高，以英寸为单位。 必须包含一个整数或小数值，后跟“in”（例如， **11in**）。 此值将覆盖报表的原始设置。|  
|**PageWidth**|要为报表设置的页宽，以英寸为单位。 必须包含一个整数或小数值，后跟“in”（例如， **8.5in**）。 此值将覆盖报表的原始设置。|  
|**StartPage**|要呈现的报表的第一页。 值为 **0** 指示将呈现所有页。 默认值是 **1**秒。|  
|**UseReportPageSize**|如果 UseReportPageSize =**false** ，则默认幻灯片大小为 PowerPoint 的默认值 13.333” x 7.5”（16:9 纵横比）。 如果 UseReportPageSize = true，则默认幻灯片大小是报表的定义页面大小。<br /><br /> 默认值为 **false**。<br /><br /> 请注意，PageWidth 和 PageHeight 设置会覆盖默认宽度和高度。|  
  
## <a name="see-also"></a>另请参阅  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 [将设备信息设置传递给呈现扩展插件](../reporting-services/report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md)   
 [在 RSReportServer.Config 中自定义呈现扩展插件参数](../reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config.md)   
 [技术参考 (SSRS)](../reporting-services/technical-reference-ssrs.md)  
  
  
