---
title: 为在 ODBC 中的行加书签 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], fetching rows
- ODBC cursors, fetching rows
- cursors [ODBC], scrolling rows
- ODBC cursors, scrolling rows
- bookmarks [ODBC]
ms.assetid: 9cfcd243-c9d4-4c2a-abc4-399dbabe5f6b
caps.latest.revision: 30
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: fb9f3284ab180ed05acc2a199c3b8cece8a1e40b
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37430696"
---
# <a name="bookmarking-rows-in-odbc"></a>在 ODBC 中为行加书签
  书签是用于标识数据行的值。 只有驱动程序或数据源才知道书签值的含义。 例如，书签可能与行号一样简单，也可能与磁盘地址一样复杂。 在 ODBC 中，应用程序为特定行请求书签，存储该书签，并将其传回到游标以返回到该行。  
  
 提取的行时[SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md)，应用程序可以用于选择开始行作为基础使用书签。 这是一种绝对寻址的格式，因为它不依赖于当前游标位置。 若要滚动到带书签的行，应用程序调用**SQLFetchScroll**与*FetchOrientation*的 SQL_FETCH_BOOKMARK。 此操作使用 SQL_ATTR_FETCH_BOOKMARK_PTR 选项属性所指向的书签。 它将返回以该书签标识的行开始的行集。 应用程序可以指定在此操作的偏移量*FetchOffset*的调用的参数**SQLFetchScroll**。 指定偏移量后，会通过将 FetchOffset 参数中的数字与由书签标识的这一行的编号相加来确定所返回行集的第一行。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC 驱动程序只对于静态游标和键集游标支持书签。 如果在设置书签时要求动态游标，则转而打开键集游标。  
  
 书签还可用于**SQLBulkOperations**函数对一组从书签处开始的行执行操作。  
  
## <a name="see-also"></a>请参阅  
 [滚动和提取行](../native-client-ole-db-rowsets/fetching-rows.md)  
  
  
