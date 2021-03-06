---
title: SQL Server 故障转移群集安装 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: c0e75a7c-85c5-423c-a218-77247bf071aa
caps.latest.revision: 7
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 9b11a175ddf9a7a12610c2f3588e4bbf42ac7802
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37317837"
---
# <a name="sql-server-failover-cluster-installation"></a>SQL Server 故障转移群集安装
  若要安装 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 故障转移群集，您必须通过运行 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 安装程序来创建并配置一个故障转移群集实例。  
  
## <a name="installing-a-failover-cluster"></a>安装故障转移群集  
 若要安装故障转移群集，您必须使用具有本地管理员权限的域帐户，拥有作为服务登录的权限，并且拥有在故障转移群集的所有节点上作为操作系统的一部分进行操作的权限。 若要通过使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 安装程序来安装故障转移群集，请执行以下步骤：  
  
1.  若要安装、配置和维护 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 故障转移群集，请使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 安装程序。  
  
    -   确定创建故障转移群集实例（如群集磁盘资源、IP 地址和网络名称）和可用于故障转移的节点所需的信息。 详细信息：    
  
        -   [安装故障转移群集前的准备工作](before-installing-failover-clustering.md)  
  
        -   [安装 SQL Server 的安全注意事项](../../install/security-considerations-for-a-sql-server-installation.md)  
  
    -   必须在运行 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 安装程序之前完成这些配置步骤，可使用 Windows 群集管理器来执行操作。必须为要配置的各个故障转移群集实例设置一个 WSFC 组。  
  
    -   您必须确保您的系统满足最低要求。 有关 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 故障转移群集的具体要求的详细信息，请参阅 [安装故障转移群集前的准备工作](before-installing-failover-clustering.md)。  
  
2.  在故障转移群集配置中添加或删除节点而不影响其他群集节点。 有关详细信息，请参阅[在 SQL Server 故障转移群集中添加或删除节点（安装程序）](add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)。  
  
    -   故障转移群集中的所有节点都必须属于同一平台（可以是 32 位或 64 位平台），并且必须运行相同版本的操作系统。 而且，64 位 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 版本必须安装在运行 64 位版本的 Windows 操作系统的 64 位硬件上。 此版本中不对故障转移群集提供 WOW64 支持。  
  
3.  为每个故障转移群集实例指定多个 IP 地址。 您可以为每个子网指定多个 IP 地址。 如果多个 IP 地址在同一子网上， [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 安装程序会将依赖关系设置为 AND。 如果您正在创建跨多个子网的群集节点，则 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 安装程序将依赖关系设置为 OR。  
  
## <a name="includessnoversionincludesssnoversion-mdmd-failover-cluster-installation-options"></a>[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 故障转移群集安装选项  
  
##### <a name="option-1-integrated-installation-with-add-node"></a>选项 1：带“添加节点”功能的集成安装  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 集成故障转移群集安装包括两个步骤：  
  
1.  创建并配置单节点 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 故障转移群集实例。 在成功配置完该节点时，您将拥有一个功能齐全的故障转移群集实例。 此时，由于故障转移群集内仅有一个节点，因此它不具备高可用性。  
  
2.  在要添加到 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 故障转移群集中的每个节点上，运行带“添加节点”功能的安装程序以添加该节点。  
  
##### <a name="option-2-advancedenterprise-installation"></a>选项 2：高级/企业安装  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 高级/企业故障转移群集安装包括两个步骤：  
  
1.  在将要成为 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 故障转移群集一部分的每个节点上，运行带“准备故障转移群集”功能的安装程序。 此步骤将准备好节点使其可以加入群集，但在此步骤结束时不会有可工作的 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 实例。  
  
2.  在准备好节点以便加入群集后，使用“完成故障转移群集”功能在拥有共享磁盘的节点上运行安装程序。 此步骤将配置并完成故障转移群集实例。 此步骤结束时，您将有一个可以工作的 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 故障转移群集实例。  
  
    > [!NOTE]  
    >  两种安装选项都允许多节点 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 故障转移群集安装。 在创建了 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 故障转移群集后，“添加节点”功能可用于在任一安装选项下添加更多节点。  
  
    > [!IMPORTANT]  
    >  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 安装位置的操作系统驱动器号在添加到 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 故障转移群集的所有节点上必须匹配。  
  
#### <a name="ip-address-configuration-during-setup"></a>在安装过程中配置 IP 地址  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 安装程序在以下操作期间允许您设置或更改 IP 资源依赖关系设置：  
  
-   集成安装 - [创建新的 SQL Server 故障转移群集（安装程序）](create-a-new-sql-server-failover-cluster-setup.md)  
  
-   CompleteFailoverCluster（高级安装） - [创建新的 SQL Server 故障转移群集（安装程序）](create-a-new-sql-server-failover-cluster-setup.md)  
  
-   添加节点 - [在 SQL Server 故障转移群集中添加或删除节点（安装程序）](add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)  
  
-   删除节点 - [在 SQL Server 故障转移群集中添加或删除节点（安装程序）](add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)  
  
 **注意** 支持 IPV6 IP 地址。  如果您同时配置 IPV4 和 IPV6，将像对待不同的子网那样处理它们，IPV6 首先联机。  
  
##### <a name="includessnoversionincludesssnoversion-mdmd-multi-subnet-failover-cluster"></a>[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 多子网故障转移群集  
 当群集上的节点位于不同子网时，您可以设置 OR 依赖关系。 但是， [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 多子网故障转移群集中的每个节点必须是至少一个指定的 IP 地址的可能所有者。  
  
## <a name="see-also"></a>请参阅  
 [安装故障转移群集前的准备工作](before-installing-failover-clustering.md)   
 [创建新的 SQL Server 故障转移群集（安装程序）](create-a-new-sql-server-failover-cluster-setup.md)   
 [从命令提示符安装 SQL Server 2014](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md)   
 [升级 SQL Server 故障转移群集](../windows/upgrade-a-sql-server-failover-cluster-instance.md)  
  
  
