---
title: Reporting Services 异常处理的最佳做法 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.component: report-server-web-service-net-framework-exception-handling
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- exceptions [Reporting Services], best practices
ms.assetid: 72fecf28-f02e-4338-b50f-0b21f520302d
caps.latest.revision: 34
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 0e56cbdf3023c2958ee7eb37c2dfc9f606ad45e8
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "33025094"
---
# <a name="best-practices-for-reporting-services-exception-handling"></a>Reporting Services 异常处理的最佳实践
  当开发 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 应用程序时，可以使用多种方法来消除或减少异常的发生。 当确实发生异常时，请向用户提供明确和简洁的错误消息，并添加适当的异常处理以防止应用程序意外结束。  
  
 向报表服务器 Web 服务发送请求的应用程序应执行以下操作：  
  
-   通过尽量防止无效请求，以避免导致异常。  
  
-   尽可能捕获异常并提供有针对性的错误处理代码。  
  
-   处理不引发异常的错误情况。  
  
## <a name="in-this-section"></a>本节内容  
  
|主题|Description|  
|-----------|-----------------|  
|[阻止无效请求](../../../reporting-services/report-server-web-service-net-framework-exception-handling/best-practices/preventing-invalid-requests.md)|介绍防止将无效请求发送到报表服务器的方法。|  
|[使用 Try 和 Catch 块](../../../reporting-services/report-server-web-service-net-framework-exception-handling/best-practices/using-try-and-catch-blocks.md)|介绍如何通过 try/catch 块进一步增强应用程序的可靠性。|  
|[处理不导致异常的警告和事例](../../../reporting-services/report-server-web-service-net-framework-exception-handling/best-practices/handling-warnings-and-cases-that-do-not-cause-exceptions.md)|说明如何处理不会导致由 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 引发的异常的错误。|  
|[使用 Detail 属性处理特定错误](../../../reporting-services/report-server-web-service-net-framework-exception-handling/best-practices/using-the-detail-property-to-handle-specific-errors.md)|说明如何通过使用 SoapException 对象的 Detail 属性以编程方式处理特定的错误。|  
  
## <a name="see-also"></a>另请参阅  
 [Detail 属性](../../../reporting-services/report-server-web-service-net-framework-exception-handling/soapexception-class/detail-property.md)   
 [介绍 Reporting Services 中的异常处理](../../../reporting-services/report-server-web-service-net-framework-exception-handling/introducing-exception-handling-in-reporting-services.md)   
 [Reporting Services SoapException 类](../../../reporting-services/report-server-web-service-net-framework-exception-handling/soapexception-class/reporting-services-soapexception-class.md)  
  
  
