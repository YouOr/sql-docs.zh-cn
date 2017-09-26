---
title: "搜索报表和其他项 （报表生成器和 SSRS） |Microsoft 文档"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a586659-5c2b-453b-8f40-a3a469277b17
caps.latest.revision: 7
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: a6aeda8e785fcaabef253a8256b5f6f7a842a324
ms.openlocfilehash: 91286fbfea763ffd8058524ff2e5274179305d8d
ms.contentlocale: zh-cn
ms.lasthandoff: 09/21/2017

---
# <a name="searching-for-reports-and-other-items-report-builder--and-ssrs"></a>搜索报表和其他项（报表生成器和 SSRS）
  您可以使用报表管理器在报表服务器中按名称或说明搜索特定的项。 可以搜索发布的报表、报表模型、文件夹、共享数据源和资源。 无法搜索计划、所有者、角色分配、订阅或者报表历史记录中的特定快照。 搜索是在存储项的报表服务器数据库上执行的。  
  
> [!NOTE]  
>  对于由报表服务器管理的项，执行文件系统搜索不会为其返回搜索结果。  
  
-   若要在报表管理器中搜索项，请在页面顶部的 **“搜索”** 文本框中键入搜索字符串。 搜索将从文件夹层次结构的顶部节点开始，然后逐渐涉及每一个分支。 如果您无权访问特定分支，就会将其跳过。 这一点适用于其他用户的“我的报表”文件夹以及一般情况下不可用的其他文件夹。 搜索结果中将只包含您有权查看的报表和项。  
  
-   若要按名称或说明搜索项，请指定希望匹配的全部或部分文本。 搜索字符串不区分大小写。 您不能使用搜索运算符来规定或排除搜索条件，如加号 (+) 或减号 (–)。  
  
-   若要在报表中搜索特定文本，请使用报表顶部的工具栏。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [查找和查看报表在报表管理器 &#40;报表生成器和 SSRS &#41;](/sql-docs/docs/reporting-services/report-builder/finding-and-viewing-reports-with-a-browser-report-builder-and-ssrs)   
 [使用我的报表 &#40;报表生成器和 SSRS &#41;](../../reporting-services/report-builder/using-my-reports-report-builder-and-ssrs.md)   
 [查找、查看和管理报表（报表生成器和 SSRS）](../../reporting-services/report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)   
 [打开和关闭报表 &#40;报表管理器 &#41;](../../reporting-services/reports/open-and-close-a-report-report-manager.md)  
  
  