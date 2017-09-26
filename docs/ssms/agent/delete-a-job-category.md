---
title: "删除作业类别 | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server Agent jobs, categories
- deleting job category
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- removing job category
ms.assetid: 47a7640b-20b3-4639-ab37-b6fc73575e6c
caps.latest.revision: 5
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 044f52ffbf373622b820014862497361316afc3f
ms.contentlocale: zh-cn
ms.lasthandoff: 06/22/2017

---
# <a name="delete-a-job-category"></a>删除作业类别
本主题说明如何通过使用 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)]、[!INCLUDE[tsql](../../includes/tsql_md.md)] 或 SQL Server 管理对象在 [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] 中删除 [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 代理作业类别。  
  
作业类别有助于您组织作业，从而更容易筛选和分组。 例如，可以将所有数据库备份作业组织到“数据库维护”类别中。  
  
**本主题内容**  
  
-   **开始之前：**  
  
    [限制和局限](#Restrictions)  
  
    [Security](#Security)  
  
-   **若要删除作业类别，请使用：**  
  
    [SQL Server Management Studio](#SSMS)  
  
    [Transact-SQL](#TSQL)  
  
    [SQL Server 管理对象](#SMO)  
  
## <a name="BeforeYouBegin"></a>开始之前  
  
### <a name="Restrictions"></a>限制和局限  
在删除用户定义的作业类别时， [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 代理将提示您，将分配给它的作业重新分配给其他作业类别。 仅可以删除用户定义的作业类别。  
  
### <a name="Security"></a>Security  
有关详细信息，请参阅 [Implement SQL Server Agent Security](../../ssms/agent/implement-sql-server-agent-security.md)。  
  
## <a name="SSMS"></a>使用 SQL Server Management Studio  
  
#### <a name="to-delete-a-job-category"></a>删除作业类别  
  
1.  在 **“对象资源管理器”**中，单击加号以展开您想要在其中删除作业类别的服务器。  
  
2.  单击加号以展开 **“SQL Server 代理”**。  
  
3.  右键单击 **“作业”** 文件夹，然后选择 **“管理作业类别”**。  
  
4.  在“管理作业类别” *server_name* 对话框中，选择要删除的作业类别。  
  
5.  单击 **“删除”**。  
  
6.  在 **“作业类别”** 对话框中，单击 **“是”**。  
  
7.  关闭“管理作业类别” *server_name* 对话框。  
  
## <a name="TSQL"></a>使用 Transact-SQL  
  
#### <a name="to-delete-a-job-category"></a>删除作业类别  
  
1.  在 **“对象资源管理器”**中，连接到 [!INCLUDE[ssDE](../../includes/ssde_md.md)]的实例。  
  
2.  在标准菜单栏上，单击 **“新建查询”**。  
  
3.  将以下示例复制并粘贴到查询窗口中，然后单击 **“执行”**。  
  
    ```  
    -- deletes the job category named AdminJobs.  
    USE msdb ;  
    GO   
    EXEC dbo.sp_delete_category  
        @name = N'AdminJobs',  
        @class = N'JOB' ;  
    GO  
    ```  
  
有关详细信息，请参阅 [sp_delete_category (Transact-SQL)](http://msdn.microsoft.com/en-us/63ea7d0d-a567-456e-a778-bee99e21d16c)。  
  
## <a name="SMO"></a>使用 SQL Server 管理对象  
**删除作业类别**  
  
通过使用所选编程语言（如 Visual Basic、Visual C# 或 PowerShell）来调用 **JobCategory** 类。  
  
