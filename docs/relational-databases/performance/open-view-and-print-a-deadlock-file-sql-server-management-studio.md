---
title: 打开、查看和打印死锁文件 (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: performance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- deadlocks [SQL Server], printing files
- deadlocks [SQL Server], opening files
- opening deadlock files
- printing deadlock files
ms.assetid: 5061b13f-2cb7-457a-b8d0-fbd437b510ab
caps.latest.revision: 14
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: b89c44ca71dcac588dea2c364f8fef7220331b3f
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "39560767"
---
# <a name="open-view-and-print-a-deadlock-file-sql-server-management-studio"></a>打开、查看和打印死锁文件 (SQL Server Management Studio)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] 生成死锁时，您可以捕获死锁信息并将死锁信息保存到文件。 保存死锁文件后，可以在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 中将其打开以进行查看或打印。  
  
## <a name="open-and-view-a-deadlock-file"></a>打开和查看死锁文件  
  
1. 在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 中的“文件”菜单上，指向“打开”，然后选择“文件”。  
  
2. 在 **“打开文件”** 对话框的 **“文件类型”** 框中选择 .xdl 文件类型。 现在就获得了一个筛选为只包含死锁文件的列表。  
  
## <a name="print-a-deadlock-file"></a>打印死锁文件  
  
1. 在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 中的“文件”菜单上，指向“打开”，然后选择“文件”。  
  
2. 在 **“打开文件”** 对话框的 **“文件类型”** 框中选择 .xdl 文件类型。 现在就获得了一个筛选为只包含死锁文件的列表。  
  
3. 选择要打印的死锁文件，然后选择“打开”。  
  
4. 在“文件”菜单上，选择“打印”。  
  
## <a name="see-also"></a>另请参阅  
 [保存死锁图形 (SQL Server Profiler)](../../relational-databases/performance/save-deadlock-graphs-sql-server-profiler.md)  
  
  
