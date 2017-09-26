---
title: "只读状态 （Excel 驱动程序） |Microsoft 文档"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- read-only status for Excel driver [ODBC]
- Excel driver [ODBC], read-only status
ms.assetid: ef5d773b-4f8f-4005-b985-84b53d8e9f9b
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 641c6b6324ccb0f12cb5b28bd25b06dc0fcc5029
ms.contentlocale: zh-cn
ms.lasthandoff: 09/09/2017

---
# <a name="read-only-status-excel-driver"></a>只读状态 （Excel 驱动程序）
当使用 Microsoft Excel 驱动程序时，默认情况下，情况下以只读方式打开数据源表和源一次只能有一个用户可以打开。 即使表具有只读状态，但是，应用程序可以执行插入和更新 Microsoft Excel 表。  
  
 当应用程序通过 Microsoft Excel 驱动程序的 Microsoft Excel 数据上执行的另存为命令时，应用程序应创建一个新表和插入数据以保存到新表。 插入导致追加到表。 可以对表不执行任何其他操作，直到关闭并重新打开。 一旦关闭表，可以不执行任何后续插入，因为表然后是只读的表。  
  
 可以更新值时使用 Microsoft Excel 驱动程序，但无法从基于 Microsoft Excel 电子表格，因此不正式支持的 Microsoft Excel 驱动程序考虑更新表中删除行。