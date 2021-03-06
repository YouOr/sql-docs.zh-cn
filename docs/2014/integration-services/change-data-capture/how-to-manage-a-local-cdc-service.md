---
title: 如何管理本地 CDC 服务 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 7f9be649-cd93-40c1-bc48-0480106f207c
caps.latest.revision: 5
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 1d913d41b9a94e0dbc407b64f23c382bdbded6c1
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37187166"
---
# <a name="how-to-manage-a-local-cdc-service"></a>如何管理本地 CDC 服务
  本过程介绍如何使用 CDC 服务配置控制台来管理特定的 CDC 服务。  
  
### <a name="to-manage-a-specific-cdc-service"></a>管理特定的 CDC 服务  
  
1.  从 **“开始”** 菜单上，选择 **“Oracle CDC 服务配置”**。  
  
2.  从 CDC 服务配置控制台的左侧窗格中，展开 **“本地 CDC 服务”**。  
  
3.  选择要使用的 CDC 服务。  
  
     也可以右键单击要使用的 CDC 服务，然后选择所需操作。  
  
     **或**  
  
     从 CDC 服务配置控制台的左侧窗格中选择 **“本地 CDC 服务”** ，然后从 CDC 服务配置控制台的中部选择要使用的服务。  
  
     也可以右键单击要使用的 CDC 服务，然后选择所需操作。  
  
4.  您可在使用 CDC 服务时执行以下任务。  
  
    -   **删除服务**  
  
         从 CDC 服务配置控制台右侧的 **“操作”** 窗格，单击 **“删除”** 以便删除服务。  
  
         也可以右键单击要删除的 CDC 服务，然后选择“删除”。  
  
         **注意**：如果在删除服务时该服务正在运行，则该服务将在被删除前停止。  
  
         若要删除 Oracle CDC Windows 服务定义，程序需要对关联的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例中的 MSXDBCDC 数据库具有更新访问权限。 在您单击 **“确定”** 删除该服务后，程序将尝试在 MSXDBCDC 数据库中删除 Oracle CDC 服务注册。 如果由于权限不足而失败，将显示一个对话框，提示用户输入具有对 MSXDBCDC 数据库的更新访问权限的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 登录名。  
  
         有关必须在“连接到 SQL Server”对话框中输入的数据的信息，请参阅 [Manage an Oracle CDC Service](manage-an-oracle-cdc-service.md) 和 [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md)。  
  
    -   **编辑 CDC 服务属性**  
  
         从 CDC 服务配置控制台右侧的 **“操作”** 窗格中，单击 **“属性”**。  
  
         也可以右键单击要编辑其属性的 CDC 服务，然后选择“属性”。  
  
## <a name="see-also"></a>请参阅  
 [管理 Oracle CDC 服务](manage-an-oracle-cdc-service.md)  
  
  
