---
title: 升级数据库引擎 | Microsoft Docs
ms.custom: ''
ms.date: 07/18/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: install
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- compatibility [SQL Server], databases
- compatibility levels [SQL Server], after upgrade
- Database Engine [SQL Server], upgrading
ms.assetid: 3c036813-36cf-4415-a0c9-248d0a433859
caps.latest.revision: 62
author: MashaMSFT
ms.author: mathoma
monikerRange: '>=sql-server-2016||=sqlallproducts-allversions'
manager: craigg
ms.openlocfilehash: f45a13e8a49f7d245ea67d00f966118fd421bf45
ms.sourcegitcommit: 79d4dc820767f7836720ce26a61097ba5a5f23f2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2018
ms.locfileid: "40175082"
---
# <a name="upgrade-database-engine"></a>升级数据库引擎

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]
  
  本部分中的文章可帮助将 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 数据库引擎从先前的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 版本升级到 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]。  
  
1.  [选择数据库引擎升级方法](../../database-engine/install-windows/choose-a-database-engine-upgrade-method.md) 开始升级之前，你需要了解各种不同的升级方法。 本文讨论升级方法和每个升级方法所涉及的步骤。  
  
2.  [计划并测试数据库引擎升级计划](../../database-engine/install-windows/plan-and-test-the-database-engine-upgrade-plan.md) 查看升级方法后，便可开始为你的环境制定合适的升级方法，然后在升级现有环境之前对该升级方法进行测试。 本文讨论如何制定升级方法并对其进行测试。  
  
3.  [完成数据库引擎升级](../../database-engine/install-windows/complete-the-database-engine-upgrade.md) 在数据库升级到 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 后，还需要完成一些步骤，包括进行新备份、启用新功能和重新填充全文目录。 本文讨论了这些步骤。  
  
4.  [更改数据库兼容性模式和使用 Query Store](../../database-engine/install-windows/change-the-database-compatibility-mode-and-use-the-query-store.md) 数据库升级到 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 后，你要采取的一个步骤是通过更改数据库兼容性模式，然后使用查询存储以监视性能来启用新功能。 本文讨论了此过程，并提供建议的工作流。  
  
5.  [利用新的 SQL Server 功能](http://www.microsoft.com/sql-server/sql-server-2017) 最后，完成前面的步骤后，你就可以探索利用特定的新数据库引擎增强功能。 本文推荐了这些增强功能中的几个，并提供了获取详细信息的链接。  
  
  
