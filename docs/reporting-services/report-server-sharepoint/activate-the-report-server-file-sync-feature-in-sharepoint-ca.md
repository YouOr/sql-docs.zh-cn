---
title: 在 SharePoint 中激活报表服务器文件同步功能 | Microsoft Docs
ms.custom: ''
ms.date: 09/25/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.component: report-server-sharepoint
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 0ee22d38c2b15a8b2527d2c83be447133aba82f0
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38052105"
---
# <a name="activate-the-report-server-file-sync-feature-in-sharepoint"></a>在 SharePoint 中激活报表服务器文件同步功能

[!INCLUDE[ssrs-appliesto](../../includes/ssrs-appliesto.md)] [!INCLUDE[ssrs-appliesto-2016-and-later](../../includes/ssrs-appliesto-2016-and-later.md)] [!INCLUDE[ssrs-appliesto-sharepoint-2013-2016i](../../includes/ssrs-appliesto-sharepoint-2013-2016.md)] [!INCLUDE[ssrs-appliesto-not-pbirsi](../../includes/ssrs-appliesto-not-pbirs.md)]

[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 报表服务器文件同步功能利用 SharePoint 事件处理程序将报表服务器目录与文档库中的项进行同步。 当用户经常直接将已发布的报表项上载到 SharePoint 文档库时，此功能很有用。 如果文件同步功能未激活，则内容仍将（但不会频繁地）保持同步。

> [!NOTE]
> 自 SQL Server 2016 之后，不再提供 Reporting Services 与 SharePoint 的集成这一功能。
  
 在安装了用于 SharePoint 产品的 [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)] 外接程序之后，可以在 SharePoint 站点管理中激活该文件同步功能。  
  
 可对于每个站点（但不在网站集级别）手动激活和停用此功能。  
  
## <a name="prerequisites"></a>必备条件

 必须安装用于 SharePoint 的 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 外接程序。 如果未安装该外接程序，则文件同步功能在站点功能列表上将不可见。  
  
 若要验证是否已安装，请在 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows **“控制面板”** 中查看已安装应用程序的列表。 如果 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 外接程序已安装，请按照本主题中的说明激活报表服务器文件同步功能。  
  
### <a name="to-activate-or-deactivate-the-reporting-services-file-sync-feature-on-a-site"></a>在站点上激活或停用 Reporting Services 文件同步功能
  
1.  从您站点的主页中，单击 **“站点操作”** 菜单，然后单击 **“站点设置”**。  
  
2.  在 **“站点操作”** 中，单击 **“管理站点功能”**。  
  
3.  在列表中找到 **“报表服务器文件同步”** 。  
  
4.  单击 **“激活”**。  

> [!NOTE]
> 若要停用报表服务器文件同步功能，可以使用相同的过程，但单击“停用”。

## <a name="see-also"></a>另请参阅

 [报表部件故障排除（报表生成器和 SSRS）](http://msdn.microsoft.com/d9fe1932-46e7-421b-a8a9-4c54d9576e94)   
 [在 SharePoint 中激活报表服务器和 Power View 集成功能](../../reporting-services/report-server-sharepoint/site-collection-features-report-server-and-power-view.md)   
 [安装或卸载用于 SharePoint 的 Reporting Services 外接程序](../../reporting-services/install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)   
 [安装或卸载用于 SharePoint 的 Reporting Services 外接程序](../../reporting-services/install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  

更多疑问？ [请访问 Reporting Services 论坛](http://go.microsoft.com/fwlink/?LinkId=620231)
