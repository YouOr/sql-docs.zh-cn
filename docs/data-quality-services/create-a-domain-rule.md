---
title: "创建域规则 | Microsoft Docs"
ms.custom: ""
ms.date: "11/08/2011"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "data-quality-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dqs.dm.testdomainrule.f1"
  - "sql13.dqs.dm.rules.f1"
ms.assetid: 339fa10d-e22c-4468-b366-080c33f1a23f
caps.latest.revision: 28
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 28
---
# 创建域规则
  本主题介绍如何在 [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) 中创建域规则。 域规则是用于验证、更正和标准化域值的条件。 域规则必须在域中保持正确，这样才能认为域值是准确的并且符合业务要求。 域规则可以包含用于验证域值、但不用于更正数据质量项目中的数据的验证规则。 规则还包含应用于有效数据并用于数据更正的标准化规则。  
  
##  <a name="BeforeYouBegin"></a> 开始之前  
  
###  <a name="Prerequisites"></a> 先决条件  
 若要创建一个域规则，您必须具有知识库以及在域管理活动中打开的域。  
  
###  <a name="Security"></a> 安全性  
  
####  <a name="Permissions"></a> 权限  
 您必须对 DQS_MAIN 数据库具有 dqs_kb_editor 或 dqs_administrator 角色，才能创建域规则。  
  
##  <a name="Build"></a> 生成域规则  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)] [运行数据质量客户端应用程序](../data-quality-services/run-the-data-quality-client-application.md)。  
  
2.  在 [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] 的主屏幕中，打开或创建一个知识库。 选择 **“域管理”** 作为活动，然后单击 **“打开”** 或 **“创建”**。 有关详细信息，请参阅 [Create a Knowledge Base](../data-quality-services/create-a-knowledge-base.md) 或 [Open a Knowledge Base](../data-quality-services/open-a-knowledge-base.md)。  
  
    > [!NOTE]  
    >  域管理在 Data Quality Service 客户端页面中执行，该页面包含用于单独域管理操作的五个选项卡。 它不是一个向导驱动的过程；任何管理操作都可以单独执行。  
  
3.  从 **“域管理”** 页上的 **“域列表”** 中，选择您要为其创建域规则的域，或者创建一个新的域。 如果您必须创建新域，请参阅 [Create a Domain](../data-quality-services/create-a-domain.md)。  
  
4.  单击 **“域规则”** 选项卡。  
  
5.  单击 **“添加新的域规则”**，然后输入在知识库中唯一的名称并且为该规则输入说明。  
  
6.  选择 **Active** 来指定该规则将运行 （默认值），或取消选中则可以阻止规则运行。  
  
7.  在 **生成规则** 窗格中，选择一个条件，从下拉列表中规则的条件框。  
  
8.  如果该条件需要某个值，则在关联的文本框中输入该值。  
  
9. 如果要求其他条件，则单击 **“向所选子句添加新的条件”** 。  
  
10. 选择 **AND** 或 **OR** 作为运算符。  
  
11. 从下拉列表中选择某个条件，然后为操作数输入一个值（如果需要）。  
  
12. 若要更改子句在该列表中出现的顺序，请选择某个子句，然后单击向上或向下箭头。 这将更改执行这些子句的顺序，因此可能会影响结果。  
  
13. 根据需要添加更多子句。 如果需要，则通过选择某一条件并单击 **“删除所选子句”**，删除该条件。  
  
14. 重复上述操作以便根据需要添加新规则。  
  
15. 若要查看某个验证规则在实施后对值的影响，请单击 **“分析该域规则对域值的影响”** 图标。  
  
16. 继续执行下面的测试过程。  
  
##  <a name="Test"></a> 测试域规则  
  
1.  在选定一条规则后，单击 **“对测试数据运行所选域规则”** 图标。  
  
2.  在“测试域规则”对话框中，单击 **“为域规则添加新的测试字词”** 图标。 输入要测试的值。 根据需要输入其他值。 选择一个值，然后根据需要单击 **“删除所选测试字词”** 图标。  
  
3.  单击 **“对所有字词测试域规则”** 图标。  
  
4.  检查每个字词的有效性。 对勾意味着“正确”、叉号意味着“错误”、三角形意味着“无效”。  
  
5.  在完成后在测试对话框中单击 **“关闭”** 。  
  
6.  根据需要对其他规则重复上述操作。  
  
7.  继续执行下面的应用过程。  
  
##  <a name="Apply"></a> 应用域规则  
  
1.  单击 **“应用所有规则”** 可将规则应用于域中的值。 在您单击 **“应用所有规则”**后，将显示一个弹出窗口，指示该规则在某些状态下会影响多少个值。 如果您仍想要应用该规则，则单击 **“是”** ；否则单击 **“否”** 。 如果您单击 **“是”**，则单击 **确定** 可关闭结果弹出窗口。  
  
    > [!NOTE]  
    >  在您创建或更改某一规则时，无需保存更改。 但是，您必须应用规则，更改才能生效。  
  
2.  单击 **“放弃所有更改”** 可取消对域规则进行的所有更改，并且还原为以前应用的规则，具有在规则的上次应用不再适用后任何更改产生的结果。 域中每个规则的有效性将按照以前应用的规则而非放弃的更改进行更新。  
  
3.  单击 **“完成”** 以完成域管理活动，如 [End the Domain Management Activity](../Topic/End%20the%20Domain%20Management%20Activity.md)中所述。  
  
##  <a name="FollowUp"></a> 跟进：创建域规则后  
 在创建域规则后，您可以对域执行其他域管理任务，可以执行知识发现以便向域添加知识，或者可以向域添加匹配策略。 有关详细信息，请参阅 [执行知识发现](../data-quality-services/perform-knowledge-discovery.md), ，[管理域](../data-quality-services/managing-a-domain.md), ，或 [创建匹配策略](../data-quality-services/create-a-matching-policy.md)。  
  
##  <a name="Conditions"></a> 域规则条件  
 下表介绍可在域规则中应用的条件，并且提供说明如何应用条件的示例。  
  
 在应用某一域规则并且域值未能通过该规则时，该值将被指定为“无效”。 如果导致该值无效的规则被删除、停用或者规则已更改以致该值可通过该规则后，指定为“无效”的值将更改为“正确”。 如果您手动将某个值指定为“无效”（在域管理活动的“域值”选项卡中），并且删除、停用或更改了该值未能通过的规则，则根据手动指定的内容，该值仍将被指定为“无效”。  
  
 具有可定义条件的域规则将规则逻辑应用于条件中的值的同义词以及这些值本身。 可定义条件是值等于、值不等于、值处于和值不处于。 例如，假设您有以下域规则：“For ‘City’, Value is equal to ‘Los Angeles’”。 如果“Los Angeles”和“LA”是同义词，则两者均正确。 另一方面，如果您的规则不包含可定义条件，例如“For City, Value ends with‘City’”，则“Los Angeles” 将是正确的，但其同义词“LA”则不正确。  
  
 您还可以选择创建一个域值。 例如，若要验证值是否以字母 A、B 或 C 开头，则您可以创建一个具有复杂条件的简单规则（例如，具有竖线字符的正则表达式），或者可以创建包含若干简单条件的复杂规则。 第一个规则的一个例子是“Value contains regular expression (^A|^B|^C)”。 第二个规则的一个例子是“’Value begins with A’ OR ‘Value begins with B’ OR ‘Value begins with C’”。  
  
|条件|说明|示例|  
|---------------|-----------------|-------------|  
|长度等于|只有包含由操作数指定的字符数的值才有效。|示例操作数：3<br /><br /> 有效值：BB1<br /><br /> 无效值：AA|  
|长度大于或等于|只有包含由操作数指定的字符数或更多字符数的值才有效。|示例操作数：3<br /><br /> 有效值：BB1、BBAA<br /><br /> 无效值：AA|  
|长度小于或等于|只有包含由操作数指定的字符数或更少字符数的值才有效。|示例操作数：3<br /><br /> 有效值：BB1、AA<br /><br /> 无效值：BBAA|  
|值等于|只有与操作数完全相同的值才有效。|示例操作数：BB1<br /><br /> 有效值：BB1<br /><br /> 无效值︰ BB、 BB1#|  
|值不等于|只有与操作数不完全相同的值才有效。|示例操作数：BB1<br /><br /> 有效值︰ BB、 BB1#<br /><br /> 无效值：BB1|  
|值包含|只有其全部字符以任何顺序包含在操作数内的值才有效。|示例操作数：A1<br /><br /> 有效值：A1、AA1<br /><br /> 无效值：1A、AA|  
|值不包含|只有不包含在操作数内的值才有效。|示例操作数：A1<br /><br /> 有效值：1A、AA<br /><br /> 无效值：A1、AA1|  
|值开头为|只有以操作数中的字符开头的值才有效。|示例操作数：AA<br /><br /> 有效值：AA1<br /><br /> 无效值：1AAB|  
|值结尾为|只有以操作数中的字符结尾的值才有效。|示例操作数：AA<br /><br /> 有效值：1AA<br /><br /> 无效值：1AAB|  
|值为数字|只有具有 SQL Server 数字数据类型的值才有效。 这包括 int、decimal、float 等。|示例操作数：无<br /><br /> 有效值：1、25、345.1234<br /><br /> 无效值：2b、bcdef|  
|值为日期/时间|只有具有 SQL Server 日期/时间数据类型的值才有效。 这包括 datetime、time、date 等。|示例操作数：无<br /><br /> 有效值：1916-06-04；1916-06-04 18:24:24；March 21, 2001；5/18/2011；18:24:24<br /><br /> 无效值：March 213, 2006|  
|值处于|只有在操作数集中的值才有效。<br /><br /> 若要在集中输入值，请单击操作数文本框，输入第一个值，按下 Enter，输入第二个值，对于要在集中输入的任何数目的值重复上述步骤，然后再次在操作数文本框中单击。 DQS 将在集中的各个值之间添加逗号。 如果您输入含逗号的单个字符串并且没有输入回车符（例如“A1, B1”），则 DQS 会将该字符串视作集中的单个值。|示例操作数：[A1, B1]<br /><br /> 有效值：A1、B1<br /><br /> 无效值：AA、11|  
|值不处于|只有不在操作数集中的值才有效。|示例操作数：[A1, B1]<br /><br /> 有效值：AA、11<br /><br /> 无效值：A1、B1|  
|值匹配模式|只有与操作数中的字符、数字和特殊字符的模式相匹配的值才有效。<br /><br /> 任何字母 (A…Z) 均可用作任何字母的模式；不区分大小写。 任何数字 (0…9) 均可用作任何数字的模式。 任何特殊字符（字母或数字除外）均可用作其自身的模式。 方括号 [] 定义可选匹配。|示例操作数︰ AA:000 (一种模式的 *任何* 两个字符后, 跟一个冒号 （:），再跟 *任何* 三位数字。<br /><br /> 有效值：AB:012、df:257<br /><br /> 无效值：abc:123、FJ-369<br /><br /> 有关 DQS 中的模式规则和示例的详细信息，请参阅 [DQS 域规则中的模式匹配](http://blogs.msdn.com/b/dqs/archive/2012/10/08/pattern-matching-in-dqs-domain-rules.aspx)。|  
|值不匹配模式|只有与操作数中的字符、数字和特殊字符的模式不匹配的值才有效。|示例操作数︰ A1 (值不得匹配的模式 *任何* 一个字符后跟 *任何* 有一个数字。)<br /><br /> 有效值：AB1、A、A:5<br /><br /> 无效值：B7、c9|  
|值包含模式|只有包含操作数中的字符、数字和特殊字符的模式的值才有效。|示例操作数︰ aa-12 (值包含以下模式 *任何* 两个字符后跟再跟一个连字符 （-）， *任何* 两位数字。)<br /><br /> 有效值：AAA-01、ab-975<br /><br /> 无效值：A7、AA-6、C-45、aa;98|  
|值不包含模式|只有不包含操作数中字符模式的值才有效。|示例操作数︰ ab-12 (值不得包含的模式 *任何* 两个字符后跟再跟一个连字符 （-）， *任何* 两位数字。)<br /><br /> 有效值：A7、AA-6、C-45、aa;98<br /><br /> 无效值：AAA-01、ab-975|  
|值匹配正则表达式|只有等于操作数中正则表达式的值才被认为有效。<br /><br /> 不包含针对正则表达式的“^”定位点或“$”定位点，因为 DQS 自动将这些定位点添加到包含“值等于”正则表达式的子句。 （或者，您可以用小括号将包含“^”和“$”定位点的正则表达式括起来。）有关正则表达式的详细信息，请参阅 [正则表达式语言元素](http://go.microsoft.com/fwlink/?LinkId=225561)。|示例操作数：[1-5]+（每个字符必须是从 1 到 5 并且出现一次或多次的数字）<br /><br /> 有效值：123、12345、14352<br /><br /> 无效值：456、ABC|  
|值不匹配正则表达式|只有不匹配操作数中正则表达式的值才被认为有效。|示例操作数：[1-5]+（字符串不得是仅限从 1 到 5 的数字）<br /><br /> 有效值：456、ABC<br /><br /> 无效值：123、123456、14352|  
  
  