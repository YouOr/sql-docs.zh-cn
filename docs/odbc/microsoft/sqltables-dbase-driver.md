---
title: SQLTables (dBASE 驱动程序) |Microsoft 文档
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
- DBase driver [ODBC], SQLTables
- SQLTables function [ODBC], dBASE Driver
ms.assetid: 45938efb-b678-47d8-9345-644fa26ad679
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 21b99888f7fad3e80fa6e4ae6933a3c0deaef770
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32903212"
---
# <a name="sqltables-dbase-driver"></a>SQLTables (dBASE 驱动程序)
> [!NOTE]  
>  本主题提供 dBASE 特定于驱动程序的信息。 有关此函数的常规信息，请参阅下的相应主题[ODBC API 参考](../../odbc/reference/syntax/odbc-api-reference.md)。  
  
|参数|注释|  
|--------------|--------------|  
|*szTableOwner*|唯一有效参数*szTableOwner*为 NULL，因为无驱动程序支持所有者名称。 与*szTableOwner*设置为 NULL，返回所有表。 TABLE_OWNER 列中返回 NULL。|  
|*szTableQualifier*|在 TABLE_QUALIFIER 列中， **SQLTables**将返回目录的路径。|  
|*SzTableType*|对于 dBASE 文件，"表"是唯一支持的表类型。|
