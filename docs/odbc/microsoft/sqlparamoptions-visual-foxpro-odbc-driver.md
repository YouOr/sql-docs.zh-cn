---
title: SQLParamOptions （Visual FoxPro ODBC 驱动程序） |Microsoft 文档
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
- SQLParamOptions function [ODBC], Visual FoxPro ODBC Driver
ms.assetid: 7f94a6e2-9c34-405c-b2b0-304d94269715
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: bdced0993d2efc27a2fb40091576c47b931e892a
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32902912"
---
# <a name="sqlparamoptions-visual-foxpro-odbc-driver"></a>SQLParamOptions （Visual FoxPro ODBC 驱动程序）
> [!NOTE]  
>  本主题包含 Visual FoxPro ODBC 驱动程序相关的信息。 有关此函数的常规信息，请参阅下的相应主题[ODBC API 参考](../../odbc/reference/syntax/odbc-api-reference.md)。  
  
 支持： 完整  
  
 ODBC API 一致性： 级别 1  
  
 允许应用程序指定的分配的参数集的多个值[SQLBindParameter](../../odbc/microsoft/sqlbindparameter-visual-foxpro-odbc-driver.md)。 指定一组参数的多个值的功能可用于大容量插入和其他工作，要求数据源处理对各种参数值多次相同的 SQL 语句。 例如，应用程序可以指定三个组值的参数与关联集**插入**语句，然后执行**插入**语句一次执行三个插入操作。  
  
 有关详细信息，请参阅[SQLParamOptions](../../odbc/reference/syntax/sqlparamoptions-function.md)中*ODBC 程序员参考*。
