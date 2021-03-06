---
title: SQL Server Express LocalDB 实例 API 参考 |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: faec46da-0536-4de3-96f3-83e607c8a8b6
caps.latest.revision: 11
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 211e7a076cae09b3fef7ef40a23cca9c60910e47
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37154299"
---
# <a name="sql-server-express-localdb-instance-api-reference"></a>SQL Server Express LocalDB 实例 API 参考
  在传统的、基于服务的 SQL Server 世界里，安装在单台计算机上的各 SQL Server 实例是物理分隔的；也就是说，每个实例都必须单独进行安装和删除，具有单独的一组二进制代码，并且在单独的服务进程下运行。 SQL Server 实例名称用于指定用户要连接的 SQL Server 实例。  
  
 SQL Server Express LocalDB 实例 API 使用简化的“轻型”实例模型。 尽管各个 LocalDB 实例在磁盘和注册表中是单独分开的，但它们使用同一组共享 LocalDB 二进制代码。 此外，LocalDB 不使用服务；LocalDB 实例是通过 LocalDB 实例 API 调用按需启动的。 在 LocalDB 中，实例名称用于指定用户要使用的 LocalDB 实例。  
  
 LocalDB 实例始终由单个用户拥有，并且仅可从该用户的上下文中看到和访问，除非启用实例共享。  
  
 尽管从技术上说 LocalDB 实例与传统 SQL Server 实例不同，但它们的目标用途是类似的。 它们被称为*实例*强调这一相似性，使其更加直观 SQL Server 用户。  
  
 LocalDB 支持两种类型的实例：自动实例 (AI) 和命名实例 (NI)。 LocalDB 实例的标识符为实例名称。  
  
## <a name="automatic-localdb-instances"></a>自动 LocalDB 实例  
 自动 LocalDB 实例是“公共的”；系统自动为用户创建和管理此类实例，并可由任何应用程序使用。 安装在用户计算机上的每个 LocalDB 版本都存在一个自动 LocalDB 实例。  
  
 自动 LocalDB 实例提供无缝的实例管理。 用户不需要创建该实例。 这使用户能够轻松地安装应用程序，并迁移到不同的计算机。 如果目标计算机已安装指定版本的 LocalDB，则该计算机也提供此版本的自动 LocalDB 实例。  
  
### <a name="automatic-instance-management"></a>自动实例管理  
 用户无需创建自动 LocalDB 实例。 在第一次使用此实例时将以惰性方式创建此实例，前提是用户计算机上提供了指定版本的 LocalDB。 从用户的角度来说，只要 LocalDB 存在，则自动实例始终存在。  
  
 其他实例管理操作（如删除、共享和取消共享）也适应于自动实例。 尤其是，删除自动实例可以高效地重置实例，这样，在下一个启动操作时将重新创建此实例。 如果系统数据库已损坏，则可能需要删除自动实例。  
  
### <a name="automatic-instance-naming-rules"></a>自动实例命名规则  
 自动 LocalDB 实例具有属于保留命名空间的特殊实例名称模式。 这对于防止名称与命名 LocalDB 实例发生冲突至关重要。  
  
 自动实例名称是以单个“v”字符为前缀的 LocalDB 基准版本号。 这看起来就是“v”加上两个数字且在两个数字之间有一个句点；例如，v11.0 或 V12.00。  
  
 非法自动实例名称的示例如下：  
  
-   11.0（开头缺少“v”字符）  
  
-   v11（缺少句点和版本的第二个数字）  
  
-   v11. （缺少版本的第二个数字）  
  
-   v11.0.1.2（版本号超出两个部分）  
  
## <a name="named-localdb-instances"></a>命名的 LocalDB 实例  
 命名的 LocalDB 实例是“私有的”；实例由负责创建和管理该实例的单个应用程序所拥有。 命名的 LocalDB 实例提供隔离并改进性能。  
  
### <a name="named-instance-creation"></a>创建命名实例  
 用户必须通过 LocalDB 管理 API 显式创建命名实例，或通过托管应用程序的 app.config 文件隐式创建命名实例。 托管应用程序也可以使用 API。  
  
 每个命名实例都具有关联的 LocalDB 版本；也就是说，它指向指定的一组 LocalDB 二进制代码。 命名实例的版本是在实例创建过程中设置的。  
  
### <a name="named-instance-naming-rules"></a>命名实例命名规则  
 LocalDB 实例名称最多可包含 128 个字符（该限制由 `sysname` 数据类型指定）。 这与传统 SQL Server 实例名称相比有显著差异，后者限制为 16 个 ASCII 字符的 NetBIOS 名称。 存在此差异的原因是 LocalDB 将数据库视为文件，因此，这意味着基于文件的语义，这样，它对于用户是直观的，可以更自由地选择实例名称。  
  
 LocalDB 实例名称可包含在文件名组分内合法的任何 Unicode 字符。 文件名组件中的有非法字符通常包括以下字符： ASCII/Unicode 字符 1 到 31，以及引号 （"）、 小于 (\<)、 大于号 (>)、 竖线 (|)、 退格符 (\b)、 制表符 (\t)、 冒号 （:）、 星号 （*）问号 （？）、 反斜杠 (\\)，和正斜杠 （/）。 请注意，允许使用 Null 字符 (\ 0)，因为它用于终止字符串；第一个 Null 字符之后的任何字符都将忽略。  
  
> [!NOTE]  
>  非法字符列表取决于操作系统，并且可能在将来的版本中更改。  
  
 实例名称中的前导和尾随空格都将被忽略，并将进行修整。  
  
 若要避免命名冲突，命名 LocalDB 实例不能遵循自动实例命名模式的名称在"自动实例命名规则。"的前面部分中所述 尝试使用有效地遵循自动实例命名模式的名称创建命名的实例创建一个默认实例。  
  
## <a name="sql-server-express-localdb-reference-topics"></a>SQL Server Express LocalDB 参考主题  
 [SQL Server Express LocalDB 标头信息和版本信息](sql-server-express-localdb-header-and-version-information.md)  
 提供用于查找 LocalDB 实例 API 的头文件信息和注册表项。  
  
 [命令行管理工具：SqlLocalDB.exe](command-line-management-tool-sqllocaldb-exe.md)  
 介绍 SqlLocalDB.exe，这是一个从命令行管理 LocalDB 实例的工具。  
  
 [LocalDBCreateInstance 函数](localdbcreateinstance-function.md)  
 描述创建新的 LocalDB 实例的函数。  
  
 [LocalDBDeleteInstance 函数](localdbdeleteinstance-function.md)  
 描述删除 LocalDB 实例的函数。  
  
 [LocalDBFormatMessage 函数](localdbformatmessage-function.md)  
 描述返回 LocalDB 错误的本地化说明的函数。  
  
 [LocalDBGetInstanceInfo 函数](localdbgetinstanceinfo-function.md)  
 描述获取有关 LocalDB 实例的信息的函数，如该实例是否存在、版本信息、是否正在运行等。  
  
 [LocalDBGetInstances 函数](localdbgetinstances-function.md)  
 描述返回具有指定版本的所有 LocalDB 实例的函数。  
  
 [LocalDBGetVersionInfo 函数](localdbgetversioninfo-function.md)  
 描述返回指定的 LocalDB 版本的信息的函数。  
  
 [LocalDBGetVersions 函数](localdbgetversions-function.md)  
 描述返回计算机上可用的所有 LocalDB 版本的函数。  
  
 [LocalDBShareInstance 函数](localdbshareinstance-function.md)  
 描述共享指定的 LocalDB 实例的函数。  
  
 [LocalDBStartInstance 函数](localdbstartinstance-function.md)  
 描述启动指定的 LocalDB 实例的函数。  
  
 [LocalDBStartTracing 函数](localdbstarttracing-function.md)  
 描述为用户启用 API 跟踪的函数。  
  
 [LocalDBStopInstance 函数](localdbstopinstance-function.md)  
 描述停止指定的 LocalDB 实例运行的函数。  
  
 [LocalDBStopTracing 函数](localdbstoptracing-function.md)  
 描述为用户禁用 API 跟踪的函数。  
  
 [LocalDBUnshareInstance 函数](localdbunshareinstance-function.md)  
 描述停止共享指定的 LocalDB 实例的函数。  
  
  
