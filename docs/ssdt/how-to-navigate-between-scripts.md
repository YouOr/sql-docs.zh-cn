---
title: 如何：在脚本之间导航 | Microsoft Docs
ms.custom:
- SSDT
ms.date: 02/09/2017
ms.prod: sql
ms.technology: ssdt
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql.data.tools.editor.howto.navigate
ms.assetid: 8664bde5-86ff-4e8b-b5a6-af003316f6ad
caps.latest.revision: 11
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: b06fbf69aa5a9d1c9354907f953d0fa98e8f9d40
ms.sourcegitcommit: c8f7e9f05043ac10af8a742153e81ab81aa6a3c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2018
ms.locfileid: "39085669"
---
# <a name="how-to-navigate-between-scripts"></a>如何在脚本之间导航
用于脱机部署的 Transact\-SQL 编辑器提供两种 Visual Studio 用户所熟悉的有用的导航工具：“转到定义”和“查找所有引用”。 例如，您可以右键单击某个表名称，然后使用“查找所有引用”来列出项目中对该表的所有引用。 您可以双击某一搜索结果以转到特定的代码文件。 在此文件中，您可以再次右键单击表名称，然后选择“转到定义”以返回到表定义。  
  
> [!WARNING]  
> 以下过程利用在[连接的数据库开发](../ssdt/connected-database-development.md)和[面向项目的脱机数据库开发](../ssdt/project-oriented-offline-database-development.md)部分中的之前过程中创建的实体。  
  
### <a name="to-navigate-between-scripts"></a>在脚本之间导航  
  
1.  在“解决方案资源管理器”中展开“函数”文件夹，然后双击“GetProductsBySupplier.sql”。  
  
2.  在此行代码中右键单击 `Products`，然后选择“转到定义”  
  
    ```  
    SELECT * from Products p  
    ```  
  
3.  Products.sql 将自动打开，并且显示定义 `Products` 类型的位置。  
  
4.  返回到 GetProductsBySupplier.sql。 这次在 `Products` 的上下文菜单中选择“查找所有引用”。 在“查找符号结果”窗格中，你将看到引用了 `Products` 表的位置的列表。 双击任何搜索结果将转到该引用的位置。  
  
