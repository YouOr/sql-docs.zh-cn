---
title: “选择数据库”页（新建可用性组向导和添加数据库向导）| Microsoft Docs
ms.custom: ''
ms.date: 05/17/2016
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: high-availability
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.swb.adddatabasewizard.selectdatabases.f1
- sql13.swb.newagwizard.selectdatabases.f1
ms.assetid: 929c5e15-d087-438d-b1f2-aa97c5f8bff8
caps.latest.revision: 16
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 7235f453c1476cea469aedaeca2cafa794dc483a
ms.sourcegitcommit: 8aa151e3280eb6372bf95fab63ecbab9dd3f2e5e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34769053"
---
# <a name="select-databases-page-new-availability-group-wizard-and-add-database-wizard"></a>Select Databases Page (New Availability Group Wizard and Add Database Wizard)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  本帮助主题说明 **“指定数据库”** 页的选项。 本主题适用于 [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] 的 [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] 和 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]。  
  
##  <a name="PageOptions"></a> 选择数据库选项  
 **“此 SQL Server 实例上的用户数据库”** 网格列出每个本地用户数据库。 这些列如下所示：  
  
 **名称**  
 显示本地用户数据库的名称。  

 **大小**  
 显示数据库大小（如果在该向导中提供）。  
  
 **“状态”**  
 显示超链接，其中的文本指示给定的数据库是否满足添加到可用性组的先决条件。 如果状态为 **“满足先决条件”**，则可以将该数据库添加到可用性组。 如果数据库不满足所有先决条件， **“状态”** 超链接将提供关于该数据库为何不符合要求的简短解释。 有关详细信息，请单击该超链接。  
  
 在对数据库采取操作以满足先决条件的过程中，您可以在 **“选择数据库”** 页上离开该向导。 当您返回 **“选择数据库”** 页时，请单击 **“刷新”** 更新该网格。  
  
 **密码**  
 如果数据库包含数据库主密钥，则请输入数据库主密钥的密码。  
  
 **“刷新”**  
 单击以刷新该网格。 对数据库采取操作以满足先决条件后，这样做非常有用。  
  
##  <a name="RelatedTasks"></a> 相关任务  
  
-   [使用“新建可用性组”对话框 (SQL Server Management Studio)](../../../database-engine/availability-groups/windows/use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [使用“将数据库添加到可用性组向导”(SQL Server Management Studio)](../../../database-engine/availability-groups/windows/availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a>另请参阅  
 [AlwaysOn 可用性组概述 (SQL Server)](../../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [针对 AlwaysOn 可用性组的先决条件、限制和建议 (SQL Server)](../../../database-engine/availability-groups/windows/prereqs-restrictions-recommendations-always-on-availability.md)  
  
  
