---
title: SQL Server 2016 的 SQL Server Reporting Services 中的重大更改 | Microsoft Docs
ms.date: 07/02/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.component: reporting-services
ms.reviewer: ''
ms.suite: pro-bi
ms.custom: ''
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Me.Value references
- Reporting Services, backward compatibility
- breaking changes [Reporting Services]
ms.assetid: 39c7aafd-dcb9-4317-b8f7-d15828eb4f9a
caps.latest.revision: 121
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: f034cad035750603705d17e31becdc8496b99893
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "37991659"
---
# <a name="breaking-changes-in-sql-server-reporting-services-in-sql-server-2016"></a>SQL Server 2016 的 SQL Server Reporting Services 中的重大更改

[!INCLUDE [ssrs-appliesto](../includes/ssrs-appliesto.md)] [!INCLUDE [ssrs-appliesto-2016](../includes/ssrs-appliesto-2016.md)] [!INCLUDE [ssrs-appliesto-not-2017](../includes/ssrs-appliesto-not-2017.md)] [!INCLUDE [ssrs-appliesto-not-pbirs](../includes/ssrs-appliesto-not-pbirs.md)]

[!INCLUDE [ssrs-previous-versions](../includes/ssrs-previous-versions.md)]

本主题介绍 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]中的重大更改。 这些更改可能导致基于 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]的早期版本的应用程序、脚本或功能无法继续使用。 您在升级时，或在自定义脚本或报表中可能会遇到这些问题。

## <a name="security-extensions"></a>安全扩展插件

自定义安全扩展插件需要进行某些修改，才可使用新 [!INCLUDE[ssRSWebPortal](../includes/ssrswebportal.md)]。 安全扩展插件需要使用 IAuthenticationExtension2 接口。

## <a name="wmi-provider"></a>WMI 提供程序

[!INCLUDE[ssRSWebPortal](../includes/ssrswebportal.md)] 应用程序名称从 "ReportManager" 更改为 "ReportServerWebApp"。

## <a name="next-steps"></a>后续步骤

[SQL Server 2016 的 SQL Server Reporting Services 中的行为更改](../reporting-services/behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md)  
[Reporting Services (SSRS) 中的新增功能](../reporting-services/what-s-new-in-sql-server-reporting-services-ssrs.md)   
[SQL Server 2016 的 SQL Server Reporting Services 中弃用的功能](../reporting-services/deprecated-features-in-sql-server-reporting-services-ssrs.md)    
[SQL Server 2016 的 SQL Server Reporting Services 中停止使用的功能](../reporting-services/discontinued-functionality-to-sql-server-reporting-services-in-sql-server.md)  

更多疑问？ [请访问 Reporting Services 论坛](http://go.microsoft.com/fwlink/?LinkId=620231)
