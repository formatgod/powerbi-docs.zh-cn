---
title: 在 Excel 中分析 Power BI
description: 了解如何在 Excel 中分析 Power BI 数据集
author: davidiseminger
ms.reviewer: ''
ms.custom: contperfq4
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/06/2020
ms.author: davidi
LocalizationGroup: Reports
ms.openlocfilehash: afc1b7127fa20cb095bb441923bf29533f2a8b8f
ms.sourcegitcommit: 008467dc9d4f88f91728c59caeb68b7db94f267c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82884042"
---
# <a name="analyze-in-excel"></a>在 Excel 中分析
有时，你可能希望使用 Excel 查看 Power BI 中的数据集并与之交互。 借助**在 Excel 中分析**，不仅可以做到这一点，还可以基于 Power BI 中存在的数据集访问 Excel 中的数据透视表、图表和切片器功能。

## <a name="two-ways-to-get-started"></a>可使用两种方法开始此操作
可通过两种不同的方法在 Excel 中浏览 Power BI 数据集 - 如果从 Power BI 开始，则需按照本文档中所述的步骤进行操作。  现在，使用特定 Office SKU 的用户还可以直接从 Excel 工作簿内的“获取数据”体验中访问其数据集。  他们可以浏览有权访问的数据集，了解数据集是否经过验证或升级，以及是否已应用数据保护标签。  若要了解有关此体验的详细信息，请参阅 Excel 文档中的[使用 Power BI 数据集创建数据透视表](https://support.office.com/article/31444a04-9c38-4dd7-9a45-22848c666884)。

## <a name="requirements"></a>要求
使用**在 Excel 中分析**时有以下几点要求：

* Microsoft Excel 2010 SP1 和更高版本支持**在 Excel 中分析**。

* Excel 数据透视表不支持对数值字段进行拖放聚合。 你在 Power BI 中的数据集 *必须具有预定义的度量值* 。 阅读有关[创建度量值](desktop-measures.md)的信息。
* 某些组织可能有组策略规则，导致无法对 Excel 安装所需的**在 Excel 中分析**更新。 如果无法安装更新，请与管理员联系。
* “在 Excel 中分析”功能要求数据库位于 Power BI Premium 中或者用户具有 Power BI Pro 许可证。 若要详细了解许可证类型之间的功能差异，请参阅 [Power BI 定价](https://powerbi.microsoft.com/pricing/)的“Power BI 功能比较”部分。
* 如果用户具有基本数据集的权限，则可通过“在 Excel 中分析”功能连接到数据集。  用户可通过多种方式获取此权限，例如成为包含此数据集的工作区的成员、具有他人向其共享了使用该数据集的报表或仪表板，或者在包含该数据集的应用或工作区中具有该数据集的生成权限。 详细了解数据集的[“生成”权限](service-datasets-build-permissions.md)。
* 来宾用户无法将“在 Excel 中分析”用于从另一个租户发送的数据集。 
* “在 Excel 中分析”是一项 Power BI 服务功能，该功能在 Power BI 报表服务器或 Power BI Embedded 中不可用。 
* “在 Excel 中分析”仅在运行 Microsoft Windows 的计算机上受到支持。

## <a name="how-does-it-work"></a>工作原理
从与 Power BI 中的数据集或报表关联的“更多选项”菜单 (…) 中选择“在 Excel 中分析”之后，Power BI 会创建一个 .ODC 文件并将其从浏览器下载到你的计算机  。

![在 Excel 中分析](media/service-analyze-in-excel/power-bi-analyze-in-excel.png)

在 Excel 中打开该文件后，将显示空的**数据透视表**和**字段**列表以及来自 Power BI 数据集的表、字段和度量值。 你可以创建数据透视表和图表，并分析该数据集，就像在 Excel 中处理本地数据集一样。

.ODC 文件有一个 MSOLAP 连接字符串，该字符串连接到 Power BI 中的数据集。 当你分析或处理数据时，Excel 会在 Power BI 中查询该数据集，并将结果返回到 Excel。 如果该数据集使用 DirectQuery 连接到实时数据源，Power BI 会查询该数据源，并将结果返回到 Excel。

“在 Excel 中分析” 对以下数据集和报表非常有用：连接 *Analysis Services 表格* 或 *多维* 数据库的数据集和报表，或者来自包含数据模型（模型度量值是使用数据分析表达式 (DAX) 创建而成）的 Power BI Desktop 文件或 Excel 工作簿的数据集和报表。

## <a name="get-started-with-analyze-in-excel-in-power-bi"></a>Power BI 中的“在 Excel 中分析”入门
在 Power BI 中，选择报表或数据集旁边的“更多选项”菜单（报表或数据集名称旁边的 …），然后从出现的菜单中选择“在 Excel 中分析” 。

![在 Excel 中分析](media/service-analyze-in-excel/power-bi-analyze-menu.png)

### <a name="install-excel-updates"></a>安装 Excel 更新
首次使用**在 Excel 中分析**时，需要对 Excel 库安装更新。 系统会提示你下载并运行 Excel 更新（这将启动 *SQL_AS_OLEDDB.msi* Windows Installer 程序包的安装）。 此程序包将安装 **Microsoft AS OLE DB Provider for SQL Server 2016 RC0（预览版）** 。

> [!NOTE]
> 务必选中“安装 Excel 更新”对话框中的“不再显示此信息” 。 此更新只需安装一次。
> 
> 

![不再显示复选框](media/service-analyze-in-excel/pbi_anlz_excel_dontshow.png)

如果需要为**在 Excel 中分析**再次安装 Excel 更新，可以通过 Power BI 中的**下载**图标下载更新，如下图所示。

![安装 更新](media/service-analyze-in-excel/pbi_anlz_excel_download_again.png)

### <a name="sign-in-to-power-bi"></a>登录到 Power BI
即便你已经在浏览器中登录 Power BI，在 Excel 中首次打开新的 .ODC 文件时，也会看到使用 Power BI 帐户登录 Power BI 的提示。 这会对 Excel 到 Power BI 的连接进行身份验证。

### <a name="users-with-multiple-power-bi-accounts"></a>拥有多个 Power BI 帐户的用户
某些用户拥有多个 Power BI 帐户，这些用户可能会遇到这种情况：他们使用某个帐户登录到 Power BI，但有权访问“在 Excel 中分析”中所用数据集的帐户是不同的帐户。 在这些情况下，如果尝试访问“在 Excel 工作簿中分析”中所用的数据集，你可能会遇到**禁止**错误或登录失败。

你有机会再次登录，届时你可以使用有权访问“在 Excel 中分析”所访问的数据集的 Power BI 帐户登录。 你还可以在 Excel 的顶部功能区选择你的名称，该功能区可标识当前登录的帐户。 注销并使用其他帐户登录。

### <a name="enable-data-connections"></a>启用数据连接
若要在 Excel 中分析 Power BI 数据，系统会提示你验证 .odc 文件的文件名和路径，验证后请选择**启用**。

![启用数据连接](media/service-analyze-in-excel/pbi_anlz_excel_enable.png)

> [!NOTE]
> 本地数据集托管在 Analysis Services (AS) 数据库中的情况下，Power BI 租户的管理员可以使用“Power BI 管理门户”禁用“在 Excel 中分析”。 禁用该选项时，会对 AS 数据库禁用**在 Excel 中分析**，但它仍可用于其他数据集。
> 
> 

## <a name="analyze-away"></a>开始分析
Excel 已打开并且你有一个空数据透视表，现在可以对 Power BI 数据集执行各种分析。 借助“在 Excel 中分析”，你可以创建数据透视表、图表、添加来自其他源的数据等等，就像使用其他本地工作簿一样。 当然，你也可以创建包含各种数据视图的不同工作表。

![Excel 中的数据透视表和数据透视图](media/service-analyze-in-excel/pbi_anlz_excel_chart.png)

> [!NOTE]
> 请务必了解，使用“在 Excel 中分析”会向具有数据集访问权限的任何用户公开所有详细信息级别的数据。
> 
> 

## <a name="save"></a>保存
你可以保存此 Power BI 数据集连接工作簿，就像保存任何其他工作簿一样。 但是，你不能将该工作簿发布或导回到 Power BI，因为你只能将表中有数据或具有数据模型的工作簿发布或导入到 Power BI。 因为新工作簿与 Power BI 中的数据集建立了连接，所以将其发布或导入到 Power BI 无疑是在兜圈子！

## <a name="share"></a>共享
保存工作簿后，可以将它与组织中的其他 Power BI 用户共享。

当你与某位用户共享了你的工作簿，而该用户打开该工作簿时，他将看到你在上一次保存该工作簿时显示的数据透视表和数据，但这些可能不是最新版本的数据。 若要获取最新数据，用户必须使用**数据**功能区上的**刷新**按钮。 由于工作簿连接到 Power BI 中的数据集，因此，尝试刷新工作簿的用户在首次尝试使用此方法更新时，必须登录 Power BI 并安装 Excel 更新。

由于用户需要刷新数据集，但 Excel Online 不支持刷新外部连接，因此，建议用户在其计算机上的桌面版 Excel 中打开工作簿。

## <a name="troubleshooting"></a>故障排除
有时，在使用 Analyze in Excel 期间可会能收意外的结果，或功能未按预期工作。 [此页提供针对 Analyze in Excel 常见问题的解决方案](desktop-troubleshooting-analyze-in-excel.md)

## <a name="next-steps"></a>后续步骤

你可能还会对以下文章感兴趣：

* [在 Power BI Desktop 中使用跨报表钻取](desktop-cross-report-drill-through.md)
* [在 Power BI Desktop 中使用切片器](visuals/power-bi-visualization-slicers.md)
