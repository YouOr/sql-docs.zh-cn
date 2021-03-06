---
title: 运行测试用例 (SybaseToSQL) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: ssma
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Azure SQL Database
- SQL Server
helpviewer_keywords:
- Tester Component,Execution Steps
ms.assetid: 195ffdef-cfde-4bf4-a3ae-e7402bb07972
caps.latest.revision: 6
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: e74fe0d569c627df15b4a75200b6821a236404ef
ms.sourcegitcommit: 603d2e588ac7b36060fa0cc9c8621ff2a6c0fcc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2018
ms.locfileid: "40392462"
---
# <a name="running-test-cases-sybasetosql"></a>运行测试用例 (SybaseToSQL)
SSMA 测试人员运行时测试用例，它执行所选测试对象，并创建有关验证结果的报告。 如果结果为在这两个平台上完全相同，测试成功。 Sybase 之间的对象的对应关系和[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]根据当前的 SSMA 项目的架构映射设置确定。  
  
成功的测试的一个必要要求是所有 Sybase 对象将转换并加载到目标数据库。 此外，应该迁移表数据，以便同步这两个平台上的表的内容。  
  
## <a name="run-test-case"></a>运行测试用例  
运行已准备好的测试用例：  
  
1.  单击**运行**按钮。  
  
2.  在中**连接到 Sybase**对话框中，输入连接信息，然后单击**Connect**。  
  
测试完成后，创建测试用例报表。 单击**报表**按钮，以查看[查看测试用例报表&#40;SybaseToSQL&#41;](../../ssma/sybase/viewing-test-case-reports-sybasetosql.md)。 测试 （测试用例报表） 的结果会自动存储在[使用测试存储库&#40;SybaseToSQL&#41; ](../../ssma/sybase/using-test-repositories-sybasetosql.md)以供将来使用。  
  
## <a name="test-case-execution-steps"></a>测试用例执行步骤  
  
### <a name="prerequisites"></a>必要條件  
SSMA 测试人员会检查测试的测试执行开始前是否满足所有先决条件。 如果不满足某些条件时，会显示一条错误消息。  
  
### <a name="initialization"></a>初始化  
在此步骤中，SSMA 测试人员创建辅助对象 （表、 触发器和视图） 这两个在 Sybase 和[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]。 它们允许选择进行验证，如果表的比较模式为受影响的表中所做的跟踪更改**只更改**。  
  
假定已验证的表名为 USER_TABLE。 对于此类表，在 Sybase 中创建以下辅助对象。  
  
以下对象创建在 Sybase SSMATESTER2005db 或 SSMATESTER2008db 数据库中并在[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ssmatesterdb_syb 数据库中。  
  
|“属性”|类型|Description|  
|--------|--------|---------------|  
|USER_TABLE$ /{trg|触发器|审核已验证的表中的更改的触发器。|  
|USER_TABLE$ 澳大利亚元|表|保存已删除和覆盖的行的表。|  
|USER_TABLE$ AudID|表|保存新的和已更改行的表。|  
|USER_TABLE|“查看”|表修改简化表示形式。|  
|USER_TABLE $ 新|“查看”|简化表示形式插入和覆盖的行。|  
|USER_TABLE$ new_id|“查看”|插入和已更改的行的标识。|  
|USER_TABLE $ 旧|“查看”|已删除和覆盖的行的简化表示形式。|  
  
已验证表在 Sybase 数据库中创建以下对象和[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]。  
  
|“属性”|类型|Description|  
|--------|--------|---------------|  
|USER_TABLE$ /{trg|触发器|审核已验证的表中的更改的触发器。|  
  
### <a name="test-object-calls"></a>测试对象调用  
在此步骤中，SSMA 测试人员调用所选测试每个对象、 比较结果，并显示的报表。  
  
### <a name="finalization"></a>终止  
在终止期间 SSMA 测试人员会清理在创建的辅助对象**初始化**步骤。  
  
## <a name="next-step"></a>下一步  
[查看测试用例报表&#40;SybaseToSQL&#41;](../../ssma/sybase/viewing-test-case-reports-sybasetosql.md)  
  
## <a name="see-also"></a>请参阅  
[选择并配置测试的对象&#40;SybaseToSQL&#41;](../../ssma/sybase/selecting-and-configuring-objects-to-test-sybasetosql.md)  
[选择并配置受影响的对象&#40;SybaseToSQL&#41;](../../ssma/sybase/selecting-and-configuring-affected-objects-sybasetosql.md)  
[测试迁移的数据库对象&#40;SybaseToSQL&#41;](../../ssma/sybase/testing-migrated-database-objects-sybasetosql.md)  
  
