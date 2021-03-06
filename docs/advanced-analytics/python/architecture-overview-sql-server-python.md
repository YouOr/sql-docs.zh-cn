---
title: SQL Server 计算机学习 Services 与 Python 一起的体系结构概述 |Microsoft 文档
ms.prod: sql
ms.technology: machine-learning
ms.date: 04/15/2018
ms.topic: conceptual
author: HeidiSteen
ms.author: heidist
manager: cgronlun
ms.openlocfilehash: 9876e54ed0b45bda48f76c3b1d764b1312313348
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31201600"
---
# <a name="architecture-overview-for-machine-learning-services-with-python"></a>具有 Python 的机器学习服务的体系结构概述
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

本文概述如何与 SQL Server，包括支持外部脚本执行的数据库引擎和启用与 SQL Server 的 Python 的互操作性的新组件中的安全模型，组件集成 Python。 有关详细信息，请参阅链接的文章。

> [!IMPORTANT]
> Python 支持的 SQL Server 自 2017 年 1 CTP 2.0 开始提供。 此预发行功能进行更改。

## <a name="python-interoperability"></a>Python 互操作性

SQL Server 计算机学习 Services （数据库中） 安装 Python，Anaconda 分发和 Python 3.5 运行时和解释器。 这可确保几乎完全与标准 Python 解决方案的兼容性。 从 SQL Server，若要确保数据库操作不会危及安全中在单独的进程中运行 Python。

有关使用 Python 的 SQL Server 的交互的详细信息，请参阅[Python 互操作性](../../advanced-analytics/python/python-interoperability.md)

## <a name="components-that-support-python-integration"></a>支持 Python 集成的组件

现在在 SQL Server 2016 中引入的 extensibility framework 支持执行 Python 脚本，通过添加新的特定于语言的组件。 这些组件提高数据 exchange 速度和压缩，同时提供用于在运行外部脚本的一个安全、 高性能的平台。

有关支持 Python，如的组件的详细说明[!INCLUDE[rsql_launchpad_md](../../includes/rsql-launchpad-md.md)]和 PythonLauncher，请参阅[新组件](../../advanced-analytics/python/new-components-in-sql-server-to-support-python-integration.md)。

## <a name="security"></a>Security

Python 任务执行外部 SQL Server 过程中，以提供安全和更高版本的可管理性。

所有任务都受 Windows 作业对象或 SQL Server 安全机制。 通过强制在表、 数据库和实例级别的 SQL Server 安全情况下，数据保留在法规遵从性边界内。 数据库管理员可以控制谁有运行 Python 作业、 监视的用户、 Python 脚本的使用和查看占用的资源的能力。

有关详细信息，请参阅[for Python 的安全](../../advanced-analytics/python/security-overview-sql-server-python-services.md)

## <a name="resource-governance"></a>资源调控

在 SQL Server Enterprise Edition，你可以使用资源调控器来管理和监视资源使用的外部脚本操作，包括 R 脚本和 Python 脚本。

有关详细信息，请参阅[R 的资源调控](../../advanced-analytics/r/resource-governance-for-r-services.md)。

## <a name="next-steps"></a>后续步骤

[运行 Python 使用 T-SQL](../tutorials/run-python-using-t-sql.md)
