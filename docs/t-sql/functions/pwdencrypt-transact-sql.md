---
title: PWDENCRYPT (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- PWDENCRYPT
- PWDENCRYPT_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- PWDENCRYPT function [Transact-SQL]
ms.assetid: 333e9a43-1099-4b9b-b941-4b0b016f47f3
caps.latest.revision: 9
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: f7efafcbc18e0be56a4941076f93b63837be3db1
ms.sourcegitcommit: 05e18a1e80e61d9ffe28b14fb070728b67b98c7d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/04/2018
ms.locfileid: "37780968"
---
# <a name="pwdencrypt-transact-sql"></a>PWDENCRYPT (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  返回使用密码哈希算法的当前版本的输入值的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 密码哈希。  
  
 PWDENCRYPT 是一个比较旧的函数，在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的将来版本中可能不再支持。 改用 [HASHBYTES](../../t-sql/functions/hashbytes-transact-sql.md)。 HASHBYTES 提供更多的哈希算法。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
PWDENCRYPT ( 'password' )  
```  
  
## <a name="arguments"></a>参数  
 password  
 要加密的密码。 password 的数据类型为 sysname。  
  
## <a name="return-types"></a>返回类型  
 **varbinary(128)**  
  
## <a name="permissions"></a>权限  
 PWDENCRYPT 向用户开放使用。  
  
## <a name="see-also"></a>另请参阅  
 [安全函数 (Transact-SQL)](../../t-sql/functions/security-functions-transact-sql.md)   
 [PWDCOMPARE (Transact-SQL)](../../t-sql/functions/pwdcompare-transact-sql.md)  
  
  
