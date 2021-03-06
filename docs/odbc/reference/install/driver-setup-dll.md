---
title: 驱动程序安装程序 DLL |Microsoft 文档
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
- installing ODBC components [ODBC], driver setup DLL
- ODBC drivers [ODBC], driver setup DLL
- driver setup DLL [ODBC]
ms.assetid: 49bab021-81fa-402e-b7a4-a5214f1fadc4
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 02a9565f5417a0e18275aa21b87a8511ae31ff6e
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32915752"
---
# <a name="driver-setup-dll"></a>驱动程序安装程序 DLL
> [!NOTE]  
>  从 Windows XP 和 Windows Server 2003 开始，在 Windows 操作系统中包含 ODBC。 在早期版本的 Windows 上，应仅显式安装 ODBC。  
  
 DLL 包含驱动程序安装程序**ConfigDriver**和**ConfigDSN**函数。 **ConfigDriver**执行特定于驱动程序的安装任务，如注册表中输入特定于驱动程序的信息。 **ConfigDSN**会维护有关在注册表中的数据源的特定于驱动程序的信息。 有关这些函数的完整说明，请参阅[安装 DLL API 参考](../../../odbc/reference/syntax/setup-dll-api-reference.md)。  
  
 **ConfigDSN**在安装程序来维护注册表中的数据源信息的 DLL 调用以下函数：  
  
-   **SQLWriteDSNToIni**。 添加数据源。  
  
-   **SQLRemoveDSNFromIni**。 删除数据源。  
  
-   **SQLWritePrivateProfileString**。 写入数据源规范子项下的特定于驱动程序的值。  
  
-   **SQLGetPrivateProfileString**。 从数据源规范子项读取特定于驱动程序的值。  
  
-   **SQLGetTranslator**。 提示用户输入转换器名称和选项。 此函数将调用**ConfigTranslator**在转换程序安装程序 DLL。  
  
 驱动程序安装程序 DLL 是由驱动程序开发人员编写的。 也可以是驱动程序的一部分的 DLL 或单独的 DLL。
