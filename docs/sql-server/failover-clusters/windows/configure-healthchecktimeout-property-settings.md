---
title: 配置 HealthCheckTimeout 属性设置 | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: high-availability
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 3bbeb979-e6fc-4184-ad6e-cca62108de74
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: c2ba9869ec0cb5760c3c4aff4e055c11a61a78a8
ms.sourcegitcommit: 8aa151e3280eb6372bf95fab63ecbab9dd3f2e5e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34772313"
---
# <a name="configure-healthchecktimeout-property-settings"></a>配置 HealthCheckTimeout 属性设置
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  HealthCheckTimeout 设置用于指定以毫秒表示的一段时间，在这段时间内 SQL Server 资源 DLL 应等待 [sp_server_diagnostics](../../../relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql.md) 存储过程返回的信息，之后才能将 Always On 故障转移群集实例 (FCI) 报告为不响应。 对超时设置所做的更改会立即生效，不需要重新启动 SQL Server 资源。  
  
-   **准备工作：**[限制和局限](#Limits)、[安全性](#Security)  
  
-   **要配置 HeathCheckTimeout 设置，请使用：**[PowerShell](#PowerShellProcedure)、[故障转移群集管理器](#WSFC)、[Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> 开始之前  
  
###  <a name="Limits"></a> 限制和局限  
 此属性的默认值为 30,000 毫秒（30 秒）。 最小值为 15,000 毫秒（15 秒）。  
  
###  <a name="Security"></a> 安全性  
  
####  <a name="Permissions"></a> Permissions  
 需要 ALTER SETTINGS 和 VIEW SERVER STATE 权限。  
  
##  <a name="PowerShellProcedure"></a> 使用 PowerShell  
  
##### <a name="to-configure-healthchecktimeout-settings"></a>配置 HealthCheckTimeout 设置  
  
1.  通过 **“以管理员身份运行”** 启动提升的 Windows PowerShell。  
  
2.  导入 **FailoverClusters** 模块以启用群集 cmdlet。  
  
3.  使用 **Get-ClusterResource** cmdlet 查找 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 资源，然后使用 **Set-ClusterParameter** cmdlet 为故障转移群集实例设置 **HealthCheckTimeout** 属性。  
  
> [!TIP]  
>  每次打开新的 PowerShell 窗口时，都需要导入 **FailoverClusters** 模块。  
  
### <a name="example-powershell"></a>示例 (PowerShell)  
 下面的示例将 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 资源“`SQL Server (INST1)`”上的 HealthCheckTimeout 设置更改为 60000 毫秒。  
  
```powershell  
Import-Module FailoverClusters  
  
$fci = "SQL Server (INST1)"  
Get-ClusterResource $fci | Set-ClusterParameter HealthCheckTimeout 60000  
  
```  
  
### <a name="related-content-powershell"></a>相关内容 (PowerShell)  
  
-   [群集和高可用性](http://blogs.msdn.com/b/clustering/archive/2009/05/23/9636665.aspx) （故障转移群集和网络负载平衡团队博客）  
  
-   [故障转移群集上的 Windows PowerShell 入门](http://technet.microsoft.com/library/ee619762\(WS.10\).aspx)  
  
-   [群集资源命令和等效的 Windows PowerShell cmdlet](http://msdn.microsoft.com/library/ee619744.aspx#BKMK_resource)  
  
##  <a name="WSFC"></a> 使用故障转移群集管理器管理单元  
 **配置 HealthCheckTimeout 设置**  
  
1.  打开故障转移群集管理器管理单元。  
  
2.  展开 **“服务和应用程序”** ，然后选择 FCI。  
  
3.  右键单击“其他资源”下的“SQL Server 资源”，然后从右键菜单中选择“属性”。 此时将打开 SQL Server 资源 **“属性”** 对话框。  
  
4.  选择 **“属性”** 选项卡，为 **HealthCheckTimeout** 属性输入所需的值，然后单击 **“确定”** 以应用更改。  
  
##  <a name="TsqlProcedure"></a> 使用 Transact-SQL  
 使用 [ALTER SERVER CONFIGURATION](../../../t-sql/statements/alter-server-configuration-transact-sql.md)[!INCLUDE[tsql](../../../includes/tsql-md.md)] 语句，你可以指定 HealthCheckTimeOut 属性值。  
  
###  <a name="TsqlExample"></a> 示例 (Transact-SQL)  
 下面的示例将 HealthCheckTimeout 选项设置为 15,000 毫秒（15 秒）。  
  
```  
ALTER SERVER CONFIGURATION   
SET FAILOVER CLUSTER PROPERTY HealthCheckTimeout = 15000;  
```  
  
## <a name="see-also"></a>另请参阅  
 [故障转移群集实例的故障转移策略](../../../sql-server/failover-clusters/windows/failover-policy-for-failover-cluster-instances.md)  
  
  
