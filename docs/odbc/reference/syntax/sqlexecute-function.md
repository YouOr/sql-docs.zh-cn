---
title: SQLExecute 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
apiname:
- SQLExecute
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLExecute
helpviewer_keywords:
- SQLExecute function [ODBC]
ms.assetid: 9286a01d-cde2-4b90-af94-9fd7f8da48bf
caps.latest.revision: 22
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: e7a64d4e3cf265b8a53fc975b33e908bb2eb9248
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32922974"
---
# <a name="sqlexecute-function"></a>SQLExecute 函数
**一致性**  
 版本引入了： ODBC 1.0 标准合规性： ISO 92  
  
 **摘要**  
 **SQLExecute**执行已准备的语句，如果任何参数标记存在语句中使用的参数标记变量的当前值。  
  
## <a name="syntax"></a>语法  
  
```  
  
SQLRETURN SQLExecute(  
     SQLHSTMT     StatementHandle);  
```  
  
## <a name="arguments"></a>参数  
 *StatementHandle*  
 [输入]语句句柄。  
  
## <a name="returns"></a>返回  
 SQL_SUCCESS、 SQL_SUCCESS_WITH_INFO、 SQL_NEED_DATA、 SQL_STILL_EXECUTING、 SQL_ERROR、 SQL_NO_DATA、 SQL_INVALID_HANDLE 或 SQL_PARAM_DATA_AVAILABLE。  
  
## <a name="diagnostics"></a>诊断  
 当**SQLExecute**返回 SQL_ERROR 或 SQL_SUCCESS_WITH_INFO，可通过调用获取关联的 SQLSTATE 值**SQLGetDiagRec**与*HandleType*的SQL_HANDLE_STMT 和*处理*的*StatementHandle*。 下表列出了通常返回的 SQLSTATE 值**SQLExecute**并说明的上下文中的此函数; 每个表示法"(DM)"之前 SQLSTATEs 返回由驱动程序管理器中的说明。 与每个 SQLSTATE 值关联的返回代码是 SQL_ERROR，除非另外说明。  
  
|SQLSTATE|错误|Description|  
|--------------|-----------|-----------------|  
|01000|常规警告|特定于驱动程序的信息性消息。 （函数返回 SQL_SUCCESS_WITH_INFO。）|  
|01001|游标操作冲突|已准备的语句与关联*StatementHandle*包含定位的更新或删除语句，并且任何行或多个行未更新或删除。 (有关更新多个行的详细信息，请参阅 SQL_ATTR_SIMULATE_CURSOR 说明*属性*中**SQLSetStmtAttr**。)<br /><br /> （函数返回 SQL_SUCCESS_WITH_INFO。）|  
|01003|Set 函数中消除了空值|已准备的语句与关联*StatementHandle*包含 set 函数 (如**AVG**，**最大**， **MIN**，依次类推)，但不是**计数**设置函数和 NULL 值而清除之前应用了函数的自变量。 （函数返回 SQL_SUCCESS_WITH_INFO。）|  
|01004|字符串数据，右截断|字符串或为输出参数返回的二进制数据导致的非空白字符或非 NULL 二进制数据截断。 如果它是一个字符串值，它是右侧被截断。 （函数返回 SQL_SUCCESS_WITH_INFO。）|  
|01006|未撤消特权|已准备的语句与关联*StatementHandle*已**撤消**语句，然后用户没有指定的特权。 （函数返回 SQL_SUCCESS_WITH_INFO。）|  
|01007|未授予的权限|已准备的语句与关联*StatementHandle*已**授予**语句，然后用户无法授予 %1 指定的特权。|  
|01S02|选项值已更改|指定的语句属性由于实现工作条件无效，因此暂时替换类似的值。 (**SQLGetStmtAttr**可以调用以确定暂时被替换的值是什么。)替换值可用于*StatementHandle*直到游标关闭，此时语句属性将恢复为以前的值。 可以更改这些语句属性包括： SQL_ATTR_CONCURRENCY、 SQL_ATTR_CURSOR_TYPE、 SQL_ATTR_KEYSET_SIZE、 SQL_ATTR_MAX_LENGTH、 SQL_ATTR_MAX_ROWS、 SQL_ATTR_QUERY_TIMEOUT 和 SQL_ATTR_SIMULATE_CURSOR。 （函数返回 SQL_SUCCESS_WITH_INFO。）|  
|01S07|小数部分组成的截断|输入/输出返回的数据或输出参数中的内容已被截断，以便数值数据类型的小数部分被截断，或者时间组成部分的时间、 时间戳，还是间隔的数据类型的小数部分被截断。<br /><br /> （函数返回 SQL_SUCCESS_WITH_INFO。）|  
|07002|计数字段不正确|在指定的参数数目**SQLBindParameter**中包含的 SQL 语句中的参数数目少于\* *StatementText*。<br /><br /> **SQLBindParameter**调用时使用*ParameterValuePtr*设置为 null 指针， *StrLen_or_IndPtr*未设置为 SQL_NULL_DATA 或 SQL_DATA_AT_EXEC，和*InputOutputType*到 SQL_PARAM_OUTPUT，未设置，以便在指定的参数数目**SQLBindParameter**大于中包含的 SQL 语句中的参数数目 **StatementText*.|  
|07006|受限制的数据类型属性冲突|由标识的数据值*ValueType*中的参数**SQLBindParameter**对于无法转换的绑定的参数，标识的数据类型为*ParameterType*中的参数**SQLBindParameter**。<br /><br /> 绑定 SQL_PARAM_INPUT_OUTPUT 或 SQL_PARAM_OUTPUT 不无法转换为标识的数据类型的参数返回的数据值*ValueType*中的参数**SQLBindParameter**。<br /><br /> （如果无法转换一个或多个行的数据值，但没有成功返回一个或多个行，此函数返回 SQL_SUCCESS_WITH_INFO。）|  
|07007|Restricted 的参数值冲突|参数类型 SQL_PARAM_INPUT_OUTPUT_STREAM 仅用于发送和接收数据部分中的参数。 此参数类型不允许输入绑定的缓冲区。<br /><br /> 当参数类型为 SQL_PARAM_INPUT_OUTPUT，和时，将出现此错误\* *StrLen_or_IndPtr*中指定**SQLBindParameter**是否不等于 SQL_NULL_DATA，SQL_DEFAULT_PARAM、 SQL_LEN_DATA_AT_EXEC(len) 或 SQL_DATA_AT_EXEC。|  
|07S01|不允许使用默认参数|参数值，设置**SQLBindParameter**、 SQL_DEFAULT_PARAM，以及相应的参数不是 ODBC 规范过程调用的参数。|  
|08S01|通讯链接失败|在函数完成处理之前失败的驱动程序和驱动程序已连接到数据源之间的通信链接。|  
|21S02|派生表的等级与列列表不匹配|已准备的语句与关联*StatementHandle*包含**CREATE VIEW**语句和未限定的列列表 (中的视图为指定的列数*列标识符*SQL 语句的参数) 包含多个名称中定义的派生表的列数比*查询规范*的 SQL 语句的自变量。|  
|22001|字符串数据，右截断|字符或二进制值的列分配导致非空白 （字符） 或非 null （二进制） 字符或字节数的截断。|  
|22002|需要指示器变量，但未提供|NULL 数据被绑定到一个输出参数其*StrLen_or_IndPtr*设置**SQLBindParameter**是空指针。|  
|22003|数值超出范围|已准备的语句与关联*StatementHandle*包含绑定的数值参数，并且参数值导致整个 （而不是小数部分组成） 的部分将被截断时分配给关联表的列。<br /><br /> 返回一个或多个输入/输出参数或输出参数的数字值 （为数字或字符串） 可能会导致整个 （而不是小数部分组成） 的部分将被截断。|  
|22007|无效的日期时间格式|已准备的语句与关联*StatementHandle*包含 SQL 语句包含日期、 时间戳结构作为绑定参数，并且参数是，分别、 无效的日期、 时间，或时间戳。<br /><br /> 一个输入/输出或输出参数绑定到日期、 时间或时间戳 C 结构中返回的参数, 的值，分别无效的日期、 时间戳。 （函数返回 SQL_SUCCESS_WITH_INFO。）|  
|22008|Datetime 字段溢出|已准备的语句与关联*StatementHandle*包含 SQL 语句包含，当计算，产生的日期时间戳结构的日期时间表达式无效。<br /><br /> 日期时间表达式计算的输入/输出或输出参数导致日期、 时间或时间戳 C 结构无效。|  
|22012|被零除|已准备的语句与关联*StatementHandle*包含导致被零除的算术表达式。<br /><br /> 输出参数导致被零的除法或算术表达式计算的输入/输出。|  
|22015|间隔字段溢出|*\*StatementText*包含准确的数值或间隔参数，当转换到 SQL 数据类型的时间间隔，导致重要数字丢失。<br /><br /> *\*StatementText*包含多个字段间隔参数，当转换为数值数据类型列中，没有表示形式具有数值数据类型。<br /><br /> *\*StatementText*包含已分配至间隔为 SQL 类型的参数数据，并且存在间隔 SQL 类型的 C 类型的值没有表示形式。<br /><br /> 分配为精确数字或时间间隔为间隔 C 类型导致重要数字丢失的 SQL 类型的输入/输出或输出参数。<br /><br /> 如果参数为输入/输出或输出已分配给间隔 C 结构中，没有间隔数据结构中的数据的表示形式。|  
|22018|转换指定的的无效字符值|*\*StatementText*包含 C 类型，是准确或近似数字、 日期时间或间隔数据类型; 的 SQL 类型的列是字符数据类型; 并且列中的值不是有效的文本的绑定的 C 类型。<br /><br /> SQL 类型返回一个输入/输出或输出参数，如果未准确或近似数字、 日期时间或间隔数据类型;C 类型为 SQL_C_CHAR;并且列中的值不是有效的文本的绑定的 SQL 类型。|  
|22019|无效的转义字符|已准备的语句与关联*StatementHandle*包含**如**谓词和**转义**中**其中**子句，并之后的转义字符的长度**转义**未等于 1。|  
|22025|无效的转义序列|已准备的语句与关联*StatementHandle*包含"**如***模式值***转义***转义字符*"中**其中**子句，并且后面模式值中的转义字符的字符不是之一"%"或"_"。|  
|23000|完整性约束冲突|已准备的语句与关联*StatementHandle*包含参数。 参数值定义为 NOT NULL 关联的表列中的列为 NULL、 重复的值提供约束为仅包含唯一值，某一列或违反某些其他完整性约束。|  
|24000|无效的游标状态|在光标*StatementHandle*通过**SQLFetch**或**SQLFetchScroll**。 此错误返回由驱动程序管理器中，如果**SQLFetch**或**SQLFetchScroll**未返回 SQL_NO_DATA，并且如果由驱动程序返回**SQLFetch**或**SQLFetchScroll**已返回 SQL_NO_DATA。<br /><br /> 在打开游标的*StatementHandle*。<br /><br /> 已准备的语句与关联*StatementHandle*包含定位的更新或删除 statemen、 t 和光标所处早于开始日期的结果集或结果集的结尾之后。|  
|40001|序列化失败|事务已回滚，因为资源死锁与另一个事务。|  
|40003|未知的语句结束|此函数在执行期间失败关联的连接，无法确定事务的状态。|  
|42000|语法错误或访问冲突|用户没有执行已准备的语句与关联的权限*StatementHandle*。|  
|44000|WITH CHECK OPTION 冲突|已准备的语句与关联*StatementHandle*包含**插入**上查看的表执行的语句或派生自创建通过指定查看表的表**WITH CHECK OPTION**，以便影响的一个或多个行**插入**语句将不再存在于查看的表。<br /><br /> 已准备的语句与关联*StatementHandle*包含**更新**上查看的表执行的语句或派生自创建通过指定查看表的表**WITH CHECK OPTION**，以便影响的一个或多个行**更新**语句将不再存在于查看的表。|  
|HY000|常规错误|有关其中没有任何特定的 SQLSTATE 和为其定义没有特定于实现的 SQLSTATE 出错。 返回的错误消息**SQLGetDiagRec**中 *\*MessageText*缓冲区描述错误以及其可能的原因。|  
|HY001|内存分配错误|该驱动程序无法分配支持执行或函数完成所需的内存。|  
|HY008|已取消操作|为启用了异步处理*StatementHandle*。 已调用函数，和它之前完成执行， **SQLCancel**或**SQLCancelHandle**上调用了*StatementHandle*。 然后在再次调用该函数*StatementHandle*。<br /><br /> 已调用函数，和它之前完成执行， **SQLCancel**或**SQLCancelHandle**上调用了*StatementHandle*来自中的不同线程多线程应用程序。|  
|HY010|函数序列错误|(DM) 为与关联的连接句柄调用以异步方式执行的函数*StatementHandle*。 此异步函数仍在执行时**SQLExecute**调用函数。<br /><br /> (DM) **SQLExecute**， **SQLExecDirect**，或**SQLMoreResults**曾为*StatementHandle*并返回 SQL_PARAM_DATA_可用。 数据已检索到的所有经过流处理参数之前调用此函数。<br /><br /> (DM) 以异步方式执行的函数 （而不是此的一个） 曾为*StatementHandle*和仍在执行时调用此函数。<br /><br /> (DM) **SQLExecute**， **SQLExecDirect**， **SQLBulkOperations**，或**SQLSetPos**曾为*StatementHandle*并返回 SQL_NEED_DATA。 数据已发送的所有数据在执行参数或列之前调用此函数。<br /><br /> (DM) *StatementHandle*未准备好。|  
|HY013|内存管理错误|无法处理函数调用，因为基础内存对象无法访问，可能是由于内存不足的情况。|  
|HY090|字符串或缓冲区长度无效|参数值，设置**SQLBindParameter**、 null 指针，以及参数长度值不是 0、 SQL_NULL_DATA、 SQL_DATA_AT_EXEC、 SQL_DEFAULT_PARAM，或小于或等于 SQL_LEN_DATA_AT_EXEC_OFFSET。<br /><br /> 参数值，设置**SQLBindParameter**、 不是空指针; C 数据类型不 SQL_C_BINARY 或 SQL_C_CHAR; 和参数长度值是小于 0，但不是 sql_nts 以、 SQL_NULL_DATA、 SQL_DEFAULT_PARAM 或 SQL_DATA_AT_EXEC，或小于或等于 SQL_LEN_DATA_AT_EXEC_OFFSET。<br /><br /> 通过参数长度值绑定**SQLBindParameter**为设置为 SQL_DATA_AT_EXEC; SQL 类型为 SQL_LONGVARCHAR、 SQL_LONGVARBINARY、 或 long 数据源 – 特定数据类型; 以及 SQL_NEED_LONG_DATA_LEN 信息键入**SQLGetInfo**已"Y"。|  
|HY105|无效的参数类型|为参数指定的值*InputOutputType*中**SQLBindParameter** SQL_PARAM_OUTPUT，且该参数为输入的参数。|  
|HY109|无效的光标位置|已准备的语句已定位的 update 或 delete 语句和光标 (通过**SQLSetPos**或**SQLFetchScroll**) 上已被删除，或者无法获取的行。|  
|HY117|连接是由于未知的事务状态挂起。 仅断开连接，允许使用只读的函数。|(DM) 有关挂起状态的详细信息，请参阅[SQLEndTran 函数](../../../odbc/reference/syntax/sqlendtran-function.md)。|  
|HYC00|未实现的可选功能|驱动程序或数据源不支持 SQL_ATTR_CONCURRENCY 和 SQL_ATTR_CURSOR_TYPE 语句属性的当前设置的组合。<br /><br /> SQL_ATTR_USE_BOOKMARKS 语句属性已设置为 SQL_UB_VARIABLE，且 SQL_ATTR_CURSOR_TYPE 语句属性被设置为该驱动程序不支持书签游标类型。|  
|HYT00|超时时间已到|查询超时期限过期之前的数据源返回了结果集。 通过设置的超时期限**SQLSetStmtAttr**，SQL_ATTR_QUERY_TIMEOUT。|  
|HYT01|连接超时过期|连接超时期限过期之前的数据源响应此请求。 通过设置连接超时期限**SQLSetConnectAttr**，SQL_ATTR_CONNECTION_TIMEOUT。|  
|IM001|驱动程序不支持此函数|(DM) 驱动程序与*StatementHandle*不支持该函数。|  
|IM017|在异步通知模式中禁用轮询|使用通知模型，则每当轮询处于禁用状态。|  
|IM018|**SQLCompleteAsync**尚未调用以完成此句柄上的上一个异步操作。|如果句柄上的上一个函数调用返回 SQL_STILL_EXECUTING，如果启用了通知模式， **SQLCompleteAsync**必须在要执行的后处理工作并完成该操作的句柄上调用。|  
  
 **SQLExecute**可以返回可以由任何 SQLSTATE **SQLPrepare**，具体取决当数据源的计算结果与语句关联的 SQL 语句。  
  
## <a name="comments"></a>注释  
 **SQLExecute**执行准备的语句**SQLPrepare**。 应用程序处理或放弃对的调用的结果后**SQLExecute**，应用程序可以调用**SQLExecute**再次使用新的参数值。 准备好的执行有关的详细信息，请参阅[已准备的执行](../../../odbc/reference/develop-app/prepared-execution-odbc.md)。  
  
 若要执行**选择**语句不止一次，应用程序必须调用**SQLCloseCursor**之前 reexecuting**选择**语句。  
  
 如果数据源在手动提交模式 （需要显式事务启动），并且尚未启动事务，该驱动程序将启动事务，再将发送的 SQL 语句。 有关详细信息，请参阅[事务](../../../odbc/reference/develop-app/transactions-odbc.md)。  
  
 如果应用程序使用**SQLPrepare**准备和**SQLExecute**提交**提交**或**回滚**语句，它不是DBMS 产品之间互操作。 若要提交或回滚事务，调用**SQLEndTran**。  
  
 如果**SQLExecute**遇到数据在执行参数，它将返回 SQL_NEED_DATA。 应用程序发送数据使用**SQLParamData**和**SQLPutData**。 请参阅[SQLBindParameter](../../../odbc/reference/syntax/sqlbindparameter-function.md)， [SQLParamData](../../../odbc/reference/syntax/sqlparamdata-function.md)， [SQLPutData](../../../odbc/reference/syntax/sqlputdata-function.md)，和[发送的长整型数据](../../../odbc/reference/develop-app/sending-long-data.md)。  
  
 如果**SQLExecute**执行搜索的 update、 insert 或 delete 语句，但不影响数据源，对的调用中的任何行**SQLExecute**返回 SQL_NO_DATA。  
  
 如果 SQL_ATTR_PARAMSET_SIZE 语句属性的值大于 1，并且 SQL 语句包含至少一个参数标记， **SQLExecute**数组中执行的每组参数值一次的 SQL 语句指向 *\*ParameterValuePtr*调用中的自变量**SQLBindParameter**。 有关详细信息，请参阅[参数值的数组](../../../odbc/reference/develop-app/arrays-of-parameter-values.md)。  
  
 如果启用了书签并执行一个查询时，无法支持书签，驱动程序应尝试强制转换为支持通过更改属性值并返回 SQLSTATE 01s02 的警告的书签的环境 （选项值已更改）。 如果该属性不能更改，该驱动程序应返回 SQLSTATE HY024 （无效的属性值）。  
  
> [!NOTE]  
>  当使用连接池时，应用程序不能执行 SQL 语句，如更改数据库或数据库，上下文**使用***数据库*更改的 SQL Server 中的语句数据源使用的目录。  
  
## <a name="code-example"></a>代码示例  
 请参阅[SQLBindParameter](../../../odbc/reference/syntax/sqlbindparameter-function.md)， [SQLBulkOperations](../../../odbc/reference/syntax/sqlbulkoperations-function.md)， [SQLPutData](../../../odbc/reference/syntax/sqlputdata-function.md)，和[SQLSetPos](../../../odbc/reference/syntax/sqlsetpos-function.md)。  
  
## <a name="related-functions"></a>相关函数  
  
|有关信息|请参阅|  
|---------------------------|---------|  
|绑定到结果集中的列的缓冲区|[SQLBindCol 函数](../../../odbc/reference/syntax/sqlbindcol-function.md)|  
|取消语句处理|[SQLCancel 函数](../../../odbc/reference/syntax/sqlcancel-function.md)|  
|关闭游标|[SQLCloseCursor 函数](../../../odbc/reference/syntax/sqlclosecursor-function.md)|  
|执行提交或回滚操作|[SQLEndTran 函数](../../../odbc/reference/syntax/sqlendtran-function.md)|  
|执行 SQL 语句|[SQLExecDirect 函数](../../../odbc/reference/syntax/sqlexecdirect-function.md)|  
|提取数据的多个的行|[SQLFetch 函数](../../../odbc/reference/syntax/sqlfetch-function.md)|  
|提取的数据块，或通过结果滚动设置|[SQLFetchScroll 函数](../../../odbc/reference/syntax/sqlfetchscroll-function.md)|  
|释放语句句柄|[SQLFreeStmt 函数](../../../odbc/reference/syntax/sqlfreestmt-function.md)|  
|返回游标名称|[SQLGetCursorName 函数](../../../odbc/reference/syntax/sqlgetcursorname-function.md)|  
|提取部分或全部数据列|[SQLGetData 函数](../../../odbc/reference/syntax/sqlgetdata-function.md)|  
|返回下一个参数发送数据|[SQLParamData 函数](../../../odbc/reference/syntax/sqlparamdata-function.md)|  
|准备执行的语句|[SQLPrepare 函数](../../../odbc/reference/syntax/sqlprepare-function.md)|  
|在执行时发送的参数数据|[SQLPutData 函数](../../../odbc/reference/syntax/sqlputdata-function.md)|  
|设置游标名称|[SQLSetCursorName 函数](../../../odbc/reference/syntax/sqlsetcursorname-function.md)|  
|设置语句属性|[SQLSetStmtAttr 函数](../../../odbc/reference/syntax/sqlsetstmtattr-function.md)|  
  
## <a name="see-also"></a>另请参阅  
 [ODBC API 参考](../../../odbc/reference/syntax/odbc-api-reference.md)   
 [ODBC 头文件](../../../odbc/reference/install/odbc-header-files.md)
