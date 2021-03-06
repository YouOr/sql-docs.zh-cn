---
title: 检查支持的功能和变化参数 |Microsoft 文档
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- interoperability [ODBC], feature support and variability
- interoperability [ODBC], writing interoperable applications
- feature support in interoperable applications [ODBC]
- feature variability in interoperable applications [ODBC]
ms.assetid: ff45f220-9b8b-4c44-82f8-a8e9913fffea
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: a2dfea013336a98ab4e69adf79198692e336acfd
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32909322"
---
# <a name="checking-feature-support-and-variability"></a>检查支持的功能和变化参数
若要检查支持的功能和变化，应用程序通常调用**SQLGetInfo**， **SQLGetFunctions**，和**SQLGetTypeInfo**。 良好的起点是驱动程序的 API 和 SQL 语法一致性级别。 这些过程描述广泛级别的功能支持。 然后，应用程序可以调用**SQLGetInfo**与其他选项来确定的支持的功能需要可变性**SQLGetFunctions**以确定是否在超出返回需要函数它支持一致性级别，和**SQLGetTypeInfo**以确定支持哪些 SQL 数据类型。  
  
 应用程序可以确定是否通过调用支持一个语句或连接特性**SQLSetStmtAttr**或**SQLSetConnectAttr**与该属性。 如果该函数将返回 SQL_SUCCESS 或 SQL_SUCCESS_WITH_INFO，则支持该属性;如果它返回 SQL_ERROR 和 SQLSTATE HYC00 （可选未实现的功能），不支持属性。  
  
 应用程序还可以确定一个有限的信息，然后再连接到该驱动程序通过调用**SQLDrivers**。
