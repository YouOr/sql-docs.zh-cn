---
title: "sp_defaultlanguage (TRANSACT-SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_defaultlanguage
- sp_defaultlanguage_TSQL
dev_langs: TSQL
helpviewer_keywords: sp_defaultlanguage
ms.assetid: 908d01cc-e704-45d9-9e85-d2df6da3e6f5
caps.latest.revision: "15"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 4428c73d462f8fe950d5fef2be8698f096419f70
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="spdefaultlanguage-transact-sql"></a>sp_defaultlanguage (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  更改 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 登录的默认语言。  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]使用[ALTER LOGIN](../../t-sql/statements/alter-login-transact-sql.md)相反。  
  
||  
|-|  
|**适用范围**： [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] （[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] 到 [当前版本](http://go.microsoft.com/fwlink/p/?LinkId=299658)）。|  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_defaultlanguage [ @loginame = ] 'login'   
     [ , [ @language = ] 'language' ]   
```  
  
## <a name="arguments"></a>参数  
 [  **@loginame =** ] *登录*  
 登录名。 *登录名*是**sysname**，无默认值。 *登录名*可以是现有[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]登录或 Windows 用户或组。  
  
 [  **@language =** ] *语言*  
 登录的默认语言。 *语言*是**sysname**，默认值为 NULL。 *语言*必须是有效的语言，在服务器上。 如果*语言*未指定，*语言*设置为服务器的默认语言; 由默认语言**sp_configure**配置变量**默认语言**。 更改服务器默认语言不会更改现有登录的默认语言。  
  
## <a name="return-code-values"></a>返回代码值  
 0（成功）或 1（失败）  
  
## <a name="remarks"></a>注释  
 **sp_defaultlanguage**调用 ALTER LOGIN，支持其他选项。 有关更改其他登录名默认值的信息，请参阅[ALTER LOGIN &#40;Transact SQL &#41;](../../t-sql/statements/alter-login-transact-sql.md).  
  
 使用 SET LANGUAGE 语句更改当前会话的语言。 使用 @@LANGUAGE函数以显示的当前语言设置。  
  
 如果从服务器中删除登录的默认语言，则登录将获取服务器的默认语言。 **sp_defaultlanguage**不能在用户定义的事务内执行。  
  
 有关在服务器上安装的语言的信息会显示在**sys.syslanguages**目录视图。  
  
## <a name="permissions"></a>Permissions  
 需要 ALTER ANY LOGIN 权限。  
  
## <a name="examples"></a>示例  
 以下示例使用 `ALTER LOGIN` 将登录 `Fathima` 的默认语言更改为阿拉伯语。 这是首选方法。  
  
```  
ALTER LOGIN Fathima WITH DEFAULT_LANGUAGE = Arabic;  
GO  
```  
  
## <a name="see-also"></a>另请参阅  
 [安全存储过程 &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [ALTER LOGIN &#40;Transact-SQL&#41;](../../t-sql/statements/alter-login-transact-sql.md)   
 [@@LANGUAGE (Transact-SQL)](../../t-sql/functions/language-transact-sql.md)   
 [SET 语句 (Transact-SQL)](../../t-sql/statements/set-statements-transact-sql.md)   
 [sys.syslanguages &#40;Transact SQL &#41;](../../relational-databases/system-compatibility-views/sys-syslanguages-transact-sql.md)   
 [系统存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  