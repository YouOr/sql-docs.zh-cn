---
title: 配置登录审核 (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.component: ssms
ms.reviewer: ''
ms.suite: sql
ms.technology: ssms
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- audits [SQL Server], logins
- logins [SQL Server], auditing
ms.assetid: 16961116-57ac-4eef-8037-791b26ade548
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: f2adb4b06480baf0411f8564a2de4815624cf470
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "33040054"
---
# <a name="configure-login-auditing-sql-server-management-studio"></a>配置登录审核 (SQL Server Management Studio)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
本主题介绍如何在 [!INCLUDE[ssCurrent](../includes/sscurrent_md.md)] 中配置登录审核以便监视登录 [!INCLUDE[ssDEnoversion](../includes/ssdenoversion_md.md)]活动。 可以将登录审核配置为在发生以下事件时向错误日志中写入信息。  
  
-   登录失败  
  
-   登录成功  
  
-   成功和失败的登录  
  
必须先重新启动 [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)] ，此选项才能生效。  
  
## <a name="SSMSProcedure"></a>使用 SQL Server Management Studio  
  
#### <a name="to-configure-login-auditing"></a>配置登录审核  
  
1.  在 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] 中，使用对象资源管理器连接至 [!INCLUDE[ssDEnoversion](../includes/ssdenoversion_md.md)]实例。  
  
2.  在对象资源管理器中，右键单击服务器名称，然后单击“属性”。  
  
3.  在“安全性”页上的“登录名审核”下，单击所需选项，然后关闭“服务器属性”页。  
  
4.  在对象资源管理器中，右键单击服务器名称，然后单击“重启”。  
  
