---
title: 了解本地执行与远程执行之间的差异 | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- integration-services
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, running
- packages [Integration Services], running
- packages [Integration Services], troubleshooting
ms.assetid: 610ee7d9-4fea-4aba-9395-57add826923b
caps.latest.revision: 20
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 946419fddf2e66afc7b3182e06c6dfa5b35385fc
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37170938"
---
# <a name="understanding-the-differences-between-local-and-remote-execution"></a>了解本地执行与远程执行之间的差异
  包开发人员和管理员应了解与 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 包运行位置相关的限制。  
  
-   **包要与启动包的程序运行在同一计算机上。** 即使程序加载的是远程存储于另一台计算机上的包，包也要在本地计算机上运行。  
  
-   **在开发环境外，只可以在安装了 Integration Services 的计算机上运行包。** 在 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] 外，您不能在未安装 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 的客户端计算机上运行包，您的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 许可条款可能不允许您在其他计算机上安装 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 是服务器组件，不可再分发至客户端计算机。 若要从客户端计算机运行包，您需要以可确保包运行于服务器上的方式启动包。  
  
 有关加载和运行已保存的包的详细信息，请参阅：  
  
-   [以编程方式加载和运行本地包](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md)  
  
-   [以编程方式加载和运行远程包](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)  
  
 有关运行包并将其输出加载到自定义程序的详细信息，请参阅：  
  
-   [加载本地包的输出](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
![集成服务图标 （小）](../media/dts-16.gif "Integration Services 图标 （小）")**保持最新的 Integration Services** <br /> 若要从 Microsoft 获得最新的下载内容、文章、示例和视频，以及从社区获得所选解决方案，请访问 MSDN 上的 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 页：<br /><br /> [访问 MSDN 上的 Integration Services 页](http://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> 若要获得有关这些更新的自动通知，请订阅该页上提供的 RSS 源。  
  
## <a name="see-also"></a>请参阅  
 [以编程方式加载和运行本地包](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md)   
 [以编程方式加载和运行远程包](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)   
 [加载本地包的输出](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
