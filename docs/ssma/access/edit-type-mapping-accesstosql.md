---
title: "编辑类型映射 (AccessToSQL) |Microsoft 文档"
ms.prod: sql-non-specified
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 7f9d9530-6c04-41d9-bbe7-d91820a30066
caps.latest.revision: 4
author: Shamikg
ms.author: Shamikg
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 2cfe289d367eee5d33177f8170e4be2919870ada
ms.contentlocale: zh-cn
ms.lasthandoff: 08/02/2017

---
# <a name="edit-type-mapping-accesstosql"></a>编辑类型映射 (AccessToSQL)
**编辑类型映射**对话框中，可以指定类型的源和目标的数据库对象对象之间的映射方式。  
  
你可以访问此对话框中，在多个位置：  
  
-   当你选择源数据库或数据库对象**类型映射**选项卡上显示的元数据资源管理器的右侧。 单击**添加**以添加新的类型映射，或单击**编辑**若要更改现有的类型映射。  
  
-   上**工具**菜单上，选择**项目设置**或**默认项目设置**。 在生成的对话框中，选择**类型映射**。 单击**添加**以添加新的类型映射，或单击**编辑**若要更改现有的类型映射。  
  
特定于表的类型映射重写数据库和项目类型映射。 特定于数据库的映射覆盖项目映射。  
  
## <a name="options"></a>选项  
**源类型**  
选择要映射到的源数据类型[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]数据类型。  
  
以下字段的可变长度数据类型时，将出现在**源类型**:  
  
**从**  
指定此映射的最短长度。 例如，对于**文本**数据类型，你可以输入 10 来指定此映射的范围开始**text(10)**。  
  
**若要**  
指定此映射的最大长度。 例如，对于**文本**数据类型，你可以输入 20，若要指定此映射的结束时间范围**text(20)**。  
  
**目标类型**  
选择[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]源数据类型映射到的数据类型。 SSMA 时创建的表或存储的过程在[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]，源数据类型将更改为此数据类型。  
  
以下字段的可变长度数据类型时，将出现在**目标类型**:  
  
**Replace with**  
指定此映射的目标长度。 例如，对于**nvarchar**数据类型，你可以输入 20 指定指定的源数据类型应映射到**nvarchar(20)**。  
  
