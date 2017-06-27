---
title: "准备实现传递扩展插件 |Microsoft 文档"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- interfaces [Reporting Services]
- delivery extensions [Reporting Services], implementing
ms.assetid: aee1608d-374f-4ad3-bc23-fe07fdaa52b7
caps.latest.revision: 34
author: sabotta
ms.author: carlasab
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: f560fa7b7947849d8f9d5d1072d692a0f28dca37
ms.contentlocale: zh-cn
ms.lasthandoff: 06/22/2017

---
# <a name="preparing-to-implement-a-delivery-extension"></a>准备实现传递扩展插件
  在实现 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 传递扩展插件之前，应定义要实现的接口。 首先需要确定使用传递扩展插件的方式、传递扩展插件需要哪些设置以及为传递报表通知而需要实现的特定功能。  
  
 每个 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 传递扩展插件都必须提供以下功能：  
  
-   <xref:Microsoft.ReportingServices.Interfaces.IExtension> 接口实现，它表示此扩展插件和本地化的扩展插件名称。  
  
-   <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> 实现，它创建可用来向最终用户传递报表通知的传递扩展插件。  
  
-   为订阅处理特定用户数据的功能。  
  
 可以增强每个传递扩展插件以包含以下功能：  
  
-   [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 用户控件实现，它使最终用户能够使用报表管理器创建使用传递扩展插件的报表订阅。  
  
 下表介绍传递扩展插件的可用接口和类。  
  
|接口或类|Description|  
|------------------------|-----------------|  
|<xref:Microsoft.ReportingServices.Interfaces.IExtension> 接口|表示 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 中的一个扩展插件。|  
|<xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> 接口|表示 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 中的一个传递扩展插件。|  
|<xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> 接口|包含传递扩展插件所需的有关报表服务器的信息（例如，可用呈现扩展插件的列表）。|  
|<xref:Microsoft.ReportingServices.Interfaces.Setting>类|表示扩展插件的设置。|  
|<xref:Microsoft.ReportingServices.Interfaces.Notification>类|包含传递扩展插件用于传递报表的订阅信息。|  
|<xref:Microsoft.ReportingServices.Interfaces.Report>类|表示报表特定的信息以及使传递扩展插件能够向用户传递报表的方法。|  
|<xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>类|表示来自呈现扩展插件的输出。 <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> 对象包含关联的文件名和类型信息，传递扩展插件需要这些信息以处理由呈现扩展插件返回的流。|  
|<xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> 接口|一个用户控件，表示在报表管理器中从用户检索传递扩展插件特定的订阅信息的方法（例如，电子邮件地址或指向文件共享的路径）。|  
  
## <a name="see-also"></a>另请参阅  
 [Reporting Services 扩展插件](../../../reporting-services/extensions/reporting-services-extensions.md)   
 [Implementing a Delivery Extension](../../../reporting-services/extensions/delivery-extension/implementing-a-delivery-extension.md)   
 [Reporting Services 扩展库](../../../reporting-services/extensions/reporting-services-extension-library.md)  
  
  