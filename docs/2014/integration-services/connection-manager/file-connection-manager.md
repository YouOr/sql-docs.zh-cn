---
title: 文件连接管理器 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- folders [Integration Services], connections
- files [Integration Services], connections
- files [Integration Services]
- connection managers [Integration Services], File
- connections [Integration Services], files
- File connection manager
ms.assetid: 019078bc-44ee-4975-9169-0f9a89e3f3be
caps.latest.revision: 50
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 33e9bb0dbb4030d09be6db95dda2a33245cd7288
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37252689"
---
# <a name="file-connection-manager"></a>文件连接管理器
  文件连接管理器使包可以在运行时引用现有的文件或文件夹，或者创建文件或文件夹。 例如，您可以引用 Excel 文件。  [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 中的某些组件使用文件中的信息来执行其工作。 例如，执行 SQL 任务可以引用包含该任务执行的 SQL 语句的文件。 其他组件对文件执行操作。 例如，文件系统任务可以引用一个文件，以便将其复制到新的位置。  
  
## <a name="usage-types-of-the-file-connection-manager"></a>文件连接管理器的使用类型  
 `FileUsageType`文件连接管理器的属性指定如何使用文件连接。 文件连接管理器可以创建文件、创建文件夹、使用现有文件或使用现有文件夹。  
  
 下表列出了值的`FileUsageType`。  
  
|ReplTest1|Description|  
|-----------|-----------------|  
|`0`|文件连接管理器使用现有文件。|  
|`1`|文件连接管理器创建文件。|  
|`2`|文件连接管理器使用现有文件夹。|  
|`3`|文件连接管理器创建文件夹。|  
  
## <a name="multiple-file-or-folder-connections"></a>多个文件或文件夹连接  
 文件连接管理器只能引用一个文件或文件夹。 若要引用多个文件或文件夹，请使用多文件连接管理器，而不是文件连接管理器。 有关详细信息，请参阅 [Multiple Files Connection Manager](multiple-files-connection-manager.md)。  
  
## <a name="configuration-of-the-file-connection-manager"></a>文件连接管理器的配置  
 在将文件连接管理器添加到包中，[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]创建的连接管理器将解析为在运行时的文件连接，设置文件连接属性，并将该文件连接到`Connections`包的集合。  
  
 `ConnectionManagerType`连接管理器属性设置为`FILE`。  
  
 可以用下列方式配置文件连接管理器：  
  
-   指定使用类型。  
  
-   指定文件或文件夹。  
  
 通过在 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] 的“属性”窗口中指定表达式，可以设置文件连接管理器的 ConnectionString 属性。 但为了避免在使用表达式指定文件或文件夹时出现验证错误，请在“文件连接管理器编辑器”中，为“文件/文件夹”添加文件或文件夹路径。  
  
 可以通过 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 设计器或以编程方式设置属性。  
  
 有关可以在 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 设计器中设置的属性的详细信息，请参阅 [文件连接管理器编辑器](../file-connection-manager-editor.md)。  
  
 有关以编程方式配置连接管理器的信息，请参阅<xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>并[连接以编程方式添加](../building-packages-programmatically/adding-connections-programmatically.md)。  
  
  
