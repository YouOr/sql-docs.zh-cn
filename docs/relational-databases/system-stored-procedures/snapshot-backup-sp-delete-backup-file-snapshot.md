---
title: "sp_delete_backup_file_snapshot (TRANSACT-SQL) |Microsoft 文档"
ms.date: 08/09/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.custom: 
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: TSQL
ms.assetid: 5afe5530-a404-4fa5-af3c-bc7c3ca43ce6
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 4cf8bf8484e77c15c951ca548ce00baccfaf5b38
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2017
---
# <a name="snapshot-backup---spdeletebackupfilesnapshot"></a>快照备份-sp_delete_backup_file_snapshot
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  从指定的数据库中删除指定的备份快照。 使用此系统存储过程结合**sys.fn_db_backup_file_snapshots**系统函数来标识和删除孤立的备份快照。 有关详细信息，请参阅 [Azure 中数据库文件的文件快照备份](../../relational-databases/backup-restore/file-snapshot-backups-for-database-files-in-azure.md)。  

  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sys.sp_delete_backup_file_snapshot  
    [ @db_name = ] N’<database_name>  
    , [ @snapshot_url = ] N’<snapshot_url>  
```  
  
## <a name="arguments"></a>参数  
 *[ @db_name =] database_name*  
 包含要删除、 提供为 Unicode 字符串的快照的数据库名称。  
  
 *[ @snapshot_url =] snapshot_url*  
 若要删除，作为 Unicode 字符串提供快照的 URL。  
  
## <a name="permissions"></a>Permissions  
 需要 ALTER ANY DATABASE 权限。  
  
## <a name="see-also"></a>另请参阅  
 [sys.fn_db_backup_file_snapshots &#40;Transact SQL &#41;](../../relational-databases/system-functions/sys-fn-db-backup-file-snapshots-transact-sql.md)   
 [sp_delete_backup (Transact-SQL)](../../relational-databases/system-stored-procedures/snapshot-backup-sp-delete-backup.md)  
  
  