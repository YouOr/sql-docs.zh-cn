---
title: "更新内容 - 数据库引擎文档| Microsoft Docs"
description: "显示数据库引擎的文档中最近更改的更新内容片段。"
services: na
documentationcenter: 
author: MightyPen
manager: jhubbard
editor: barbkess
ms.service: na
ms.topic: updart-autogen
ms.technology: database-engine
ms.custom: UpdArt.exe
ms.workload: database-engine
ms.tgt_pltfrm: na
ms.devlang: na
ms.date: 09/11/2017
ms.author: genemi
ms.translationtype: HT
ms.sourcegitcommit: 15080827744c19120a8474f3142004c4af7a4064
ms.openlocfilehash: ce80496cdf82c2bc2df2447ed043216e6c78ad7e
ms.contentlocale: zh-cn
ms.lasthandoff: 09/13/2017

---
# <a name="new-and-recently-updated-database-engine-docs"></a>新增内容和最近更新内容：数据库引擎文档



Microsoft 几乎每天都会更新其 [Docs.Microsoft.com](http://docs.microsoft.com/) 文档网站上的一些现有文章。 本文显示从最近更新的文章中摘录的内容。 可能还会列出新文章的链接。

本文由定期重新运行的程序生成。 摘录内容偶尔会有格式问题，还可能以源文的 markdown 格式显示。 此处不会显示任何图像。

最新的更新报告涵盖以下日期范围和主题：



- 更新日期范围：从 2017-07-18 到 2017-09-11
- 主题区域：&nbsp;数据库引擎。




&nbsp;

## <a name="new-articles-created-recently"></a>最近创建的新文章

单击以下链接可跳转到最近添加的新文章。


1. [SQL Server 安装](install-windows/installation-for-sql-server.md)
2. [SQL Server 2017 支持的版本和版本升级](install-windows/supported-version-and-edition-upgrades-2017.md)
3. [SQL Server 数据库引擎](sql-server-database-engine-overview.md)
4. [数据库引擎中的新增功能 - SQL Server 2016](whats-new-in-sql-server-2016.md)
5. [数据库引擎中的新增功能 - SQL Server 2017](whats-new-in-sql-server-2017.md)



&nbsp;

## <a name="updated-articles-with-excerpts"></a>包含摘录内容的已更新文章

此部分显示从最近大幅更新的文章中收集到的更新的摘录内容。

此处显示的摘录与其对应的语义上下文脱离。 此外，有时摘录会与实际文章中此摘录周围的重要 markdown 语法元素脱离。 因此，这些摘录仅可用于一般指导。 摘录只是帮助你确定自己是否有兴趣花时间点击并访问实际文章。

鉴于以上原因及其他原因，请不要复制这些摘录中的代码，也不要将摘录当作确切事实。 请转而访问实际文章。





&nbsp;

<a name="compactupdatedlist"/>

## <a name="compact-list-of-articles-updated-recently"></a>最近更新的文章的紧凑列表

此紧凑列表提供了在摘要部分列出的所有更新文章的链接。

1. [次要副本的自动种子设定](#TitleNum_1)




&nbsp;

&nbsp;

<a name="TitleNum_1"/>

### <a name="1-nbsp-automatic-seeding-for-secondary-replicasavailability-groupswindowsautomatic-seeding-secondary-replicasmd"></a>1.&nbsp;[次要副本的自动种子设定](availability-groups/windows/automatic-seeding-secondary-replicas.md)

更新日期：2017-08-21 

<!-- Source markdown line 55.  ms.author= "mikeray".  -->

&nbsp;


<!-- git diff --ignore-all-space --unified=0 0b7b6a23f38bfe5959ccd170527a9bbdb308dc4b dc51fdf69649ed6cae03584cff7bc900d5b72149  (PR=2896  ,  Filename=automatic-seeding-secondary-replicas.md  ,  Dirpath=docs\database-engine\availability-groups\windows\  ,  MergeCommitSha40=80642503480add90fc75573338760ab86139694c) -->



在 SQL Server 2016 及之前版本中，自动种子设定将在其中创建数据库的文件夹必须已经存在，并且与主要副本上的路径相同。

在 SQL Server 2017 中，Microsoft 建议对参与可用性组的所有副本使用相同的数据和日志文件路径，但如有必要，可使用其他路径。 例如，在跨平台可用性组中，SQL Server 的一个实例适用于 Windows，而 SQL Server 的另一实例适用于 Linux。 不同平台的默认路径不同。 SQL Server 2017 支持具有不同默认路径的 SQL Server 实例的可用性组副本。

下表列出了关于可支持自动种子设定的受支持的数据磁盘布局的示例：

|主实例</br>默认数据路径|辅助实例</br>默认数据路径|主实例</br>源文件位置|辅助实例</br> 目标文件位置
|:------|:------|:------|:------
|c:\\data\\ |/var/opt/mssql/data/ |c:\\data\\ |/var/opt/mssql/data/|
|c:\\data\\ |/var/opt/mssql/data/ |c:\\data\\group1\\ |/var/opt/mssql/data/group1/|
|c:\\data\\ |d:\\data\\ |c:\\data\\ |d:\\data\\
|c:\\data\\ |d:\\data\\ |c:\\data\\group1\\ |d:\\data\\group1\

其中主要和辅助副本数据库位置不是实例的默认路径的方案不受此更改影响。 对用于匹配主副本文件路径的辅助副本文件路径的要求保持不变。

|主实例</br>默认数据路径|辅助实例</br>默认数据路径|主实例</br>文件位置|辅助实例</br> 文件位置
|:------|:------|:------|:------
|c:\\data\\ |c:\\data\\ |d:\\group1\\ |d:\\group1\\
|c:\\data\\ |c:\\data\\ |d:\\data\\ |d:\\data\\
|c:\\data\\ |c:\\data\\ |d:\\data\\group1\\ |d:\\data\\group1\\

如果混合使用主要和辅助副本上的默认和非默认路径，SQL Server 2017 的行为将不同于之前的版本。 下表显示了 SQL Server 2017 的行为。







## <a name="similar-articles"></a>类似文章

<!--  HOW TO:
    Refresh this file's line items with the latest 'Count-in-Similars*' content.
    Then run Run-533-*.BAT
-->

本节列出了 GitHub.com 公共存储库 ([MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs/)) 内其他主题区域中与最近更新的文章非常相似的文章。

#### <a name="subject-areas-which-do-have-new-or-recently-updated-articles"></a>主题区域具有新的或最近更新的文章

- [新文章和更新的文章 (3+12)：SQL 高级分析 文档](../advanced-analytics/new-updated-advanced-analytics.md)
- [新文章和更新的文章 (5+0)：连接到 SQL 文档](../connect/new-updated-connect.md)
- [新文章和更新的文章 (5+1)：SQL 数据库引擎文档](../database-engine/new-updated-database-engine.md)
- [新文章和更新的文章 (19+82)：SQL Integration Services 文档](../integration-services/new-updated-integration-services.md)
- [新文章和更新的文章 (1+8)：Linux for SQL 文档](../linux/new-updated-linux.md)
- [新文章和更新的文章 (12+1)：SQL 关系数据库文档](../relational-databases/new-updated-relational-databases.md)
- [新文章和更新的文章 (0+1)：SQL Reporting Services 文档](../reporting-services/new-updated-reporting-services.md)
- [新文章和更新的文章 (7+1)：Microsoft SQL Server 文档](../sql-server/new-updated-sql-server.md)
- [新文章和更新的文章 (1+1)：SQL Server Data Tools (SSDT) 文档](../ssdt/new-updated-ssdt.md)
- [新文章和更新的文章 (0+2)：SQL Server Migration Assistant (SSMA) 文档](../ssma/new-updated-ssma.md)
- [新文章和更新的文章 (1+4)：SQL Server Management Studio (SSMS) 文档](../ssms/new-updated-ssms.md)
- [新文章和更新的文章 (4+1)：Transact-SQL 文档](../t-sql/new-updated-t-sql.md)
- [新文章和更新的文章 (0+1)：Tools for SQL 文档](../tools/new-updated-tools.md)

#### <a name="subject-areas-which-have-no-new-or-recently-updated-articles"></a>没有新的或最近更新文章的主题区域

- [新的和更新的文章 (0+0)：ActiveX Data Objects (ADO) for SQL 文档](../ado/new-updated-ado.md)
- [新文章和更新的文章 (0+0)：SQL Analysis Services 文档](../analysis-services/new-updated-analysis-services.md)
- [新的和更新的文章 (0+0)：Data Quality Services for SQL 文档](../data-quality-services/new-updated-data-quality-services.md)
- [新的和更新的文章 (0+0)：SQL 数据挖掘扩展插件 (DMX) 文档](../dmx/new-updated-dmx.md)
- [新文章和更新的文章 (0+0)：Master Data Services (MDS) for SQL 文档](../master-data-services/new-updated-master-data-services.md)
- [新的和更新的文章 (0+0)：SQL 多维表达式 (MDX) 文档](../mdx/new-updated-mdx.md)
- [新的和更新的文章 (0+0)：SQL 开放式数据库连接 (ODBC) 文档](../odbc/new-updated-odbc.md)
- [新的和更新的文章 (0+0)：PowerShell for SQL 文档](../powershell/new-updated-powershell.md)
- [新的和更新的文章 (0+0)：SQL 示例文档](../sample/new-updated-sample.md)
- [新的和更新的文章 (0+0)：XQuery for SQL 文档](../xquery/new-updated-xquery.md)


