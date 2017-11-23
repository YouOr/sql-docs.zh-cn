---
title: "sysmail_allitems (TRANSACT-SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sysmail_allitems_TSQL
- sysmail_allitems
dev_langs: TSQL
helpviewer_keywords: sysmail_allitems database mail view
ms.assetid: 21fb8432-7677-4435-902f-64a58bba4cbb
caps.latest.revision: "17"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 0abb8eb792b85eed60df52f70a2c13c2e3f920d8
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2017
---
# <a name="sysmailallitems-transact-sql"></a>sysmail_allitems (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  数据库邮件处理的每个消息都在视图中占一行。 如果要查看所有消息的状态，则请使用该视图。  
  
 若要查看仅具有失败的状态消息，使用[sysmail_faileditems &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sysmail-faileditems-transact-sql.md). 若要查看未发送的邮件，使用[sysmail_unsentitems &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sysmail-unsentitems-transact-sql.md). 若要查看已发送的消息，使用[sysmail_sentitems &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sysmail-sentitems-transact-sql.md).  
  
||  
|-|  
|**适用范围**： [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] （[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] 到 [当前版本](http://go.microsoft.com/fwlink/p/?LinkId=299658)）。|  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**mailitem_id**|**int**|邮件队列中邮件项的标识符。|  
|**profile_id**|**int**|发送消息所用配置文件的标识符。|  
|**收件人**|**varchar(max)**|消息收件人的电子邮件地址。|  
|**copy_recipients**|**varchar(max)**|接收消息副本的用户的电子邮件地址。|  
|**blind_copy_recipients**|**varchar(max)**|接收消息副本但其姓名未出现在消息标头中的用户的电子邮件地址。|  
|**主题**|**nvarchar(510)**|消息的主题行。|  
|**正文**|**varchar(max)**|消息的正文。|  
|**body_format**|**varchar （20)**|消息正文的格式。 可能值为 TEXT 和 HTML。|  
|**重要性**|**varchar(6)**|**重要性**消息参数。|  
|**敏感度**|**varchar(12)**|**敏感度**消息参数。|  
|**file_attachments**|**varchar(max)**|附加到电子邮件中的文件名列表，以分号分隔。|  
|**attachment_encoding**|**varchar （20)**|邮件附件的类型。|  
|**查询**|**varchar(max)**|邮件程序所执行的查询。|  
|**execute_query_database**|**sysname**|邮件程序在其中执行查询的数据库上下文。|  
|**attach_query_result_as_file**|**bit**|如果该值为 0，则查询结果包含在电子邮件的正文中，在正文的内容之后。 如果该值为 1，则结果作为附件返回。|  
|**query_result_header**|**bit**|值为 1 时，查询结果将包含列标题。 0 值时，查询结果未包含列标题。|  
|**query_result_width**|**int**|**Query_result_width**消息参数。|  
|**query_result_separator**|**char （1)**|用于分隔查询输出中的各列的字符。|  
|**exclude_query_output**|**bit**|**Exclude_query_output**消息参数。 有关详细信息，请参阅[sp_send_dbmail &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-send-dbmail-transact-sql.md).|  
|**append_query_error**|**bit**|**Append_query_error**消息参数。 0 指示如果查询中存在错误，则数据库邮件不应发送电子邮件。|  
|**send_request_date**|**datetime**|将消息放在邮件队列中的日期和时间。|  
|**send_request_user**|**sysname**|提交消息的用户。 这是数据库邮件过程的用户上下文，不是邮件的“发件人:”字段。|  
|**sent_account_id**|**int**|发送消息所用数据库邮件帐户的标识符。|  
|**sent_status**|**varchar(8)**|邮件的状态。 可能的值有：<br /><br /> **发送**-已发送邮件。<br /><br /> **未发送**-数据库邮件仍在尝试将消息发送。<br /><br /> **重试**-数据库邮件无法发送消息，而尝试重新发送它。<br /><br /> **失败**-数据库邮件无法发送消息。|  
|**sent_date**|**datetime**|发送消息的日期和时间。|  
|**last_mod_date**|**datetime**|上次修改行的日期和时间。|  
|**last_mod_user**|**sysname**|上次修改行的用户。|  
  
## <a name="remarks"></a>注释  
 使用**sysmail_allitems**视图以查看所有消息的状态处理的数据库邮件。 排除数据库邮件故障时，该视图通过向您显示已发送的消息的属性（与未发送的消息的属性进行比较），可帮助您确定问题的本质。  
  
 此视图所公开的系统表包含所有消息，并且可能导致**msdb**数据库增长。 应定期从视图中删除旧的消息，以减小表的大小。 有关详细信息，请参阅[创建一个 SQL Server 代理作业以存档数据库邮件和事件日志](../../relational-databases/database-mail/create-a-sql-server-agent-job-to-archive-database-mail-messages-and-event-logs.md)。  
  
## <a name="permissions"></a>Permissions  
 授予**sysadmin**固定的服务器角色和**DatabaseMailUserRole**数据库角色。 由的成员执行时**sysadmin**固定服务器角色，此视图显示所有消息。 所有其他用户仅可查看他们已提交的消息。  
  
  