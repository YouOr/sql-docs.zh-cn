---
title: 默认数据源 |Microsoft 文档
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
- data sources [ODBC], connection functions
- connecting to data source [ODBC], default data source
- functions [ODBC], data source or driver connections
- data sources [ODBC], default
- default data source [ODBC]
- connecting to data source [ODBC], functions
- connecting to driver [ODBC], default data source
- connecting to driver [ODBC], functions
- connection functions [ODBC]
- ODBC drivers [ODBC], connection functions
ms.assetid: dd473cc6-f051-4aa0-ab14-3dd1b37fe99e
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 8b756f9b553c622028266d1fc591596bf58ddf45
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32908132"
---
# <a name="default-data-source"></a>默认数据源
该驱动程序可能选择名的默认数据源，在某些情况下，其中应用程序未显式指定一个数据源：  
  
-   对的调用中**SQLConnect**其中*ServerName*自变量是零长度字符串、 null 指针或 DEFAULT。  
  
-   对的调用中**SQLDriverConnect**其中*InConnectionString*或者指定**DSN**= 默认值或指定与**DSN**关键字未包含在系统信息的数据源。  
  
 它是驱动程序定义的指定的默认数据源的方式。 这可能涉及到的管理操作，并可能依赖于用户。
