---
title: 刷新不支持的数据源故障排除
description: 刷新不支持的数据源故障排除
author: maggiesMSFT
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 12/06/2017
ms.author: maggies
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: e3fe8626001972acc0b7555f37844b5abb62753b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "74791997"
---
# <a name="troubleshooting-unsupported-data-source-for-refresh"></a>刷新不支持的数据源故障排除
尝试为计划的刷新配置数据集时，你可能会遇到错误。

        You cannot schedule refresh for this dataset because it gets data from sources that currently don’t support refresh.

刷新不支持在 Power BI Desktop 中使用的数据源时，会发生这种情况。 你需要查找所使用的数据源并将它与[在 Power BI 中刷新数据](refresh-data.md)处的不支持数据源列表进行比较。 

## <a name="find-the-data-source"></a>查找数据源
如果你不确定所使用的数据源，则可以在 Power BI Desktop 中使用以下步骤来查找该数据源。  

1. 在 Power BI Desktop 中，请确保你处于**报表**窗格上。  
   ![Desktop 报表窗格](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-report-pane.png)
2. 从功能区栏中选择**编辑查询**。  
   ![编辑查询](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-edit-queries.png)
3. 选择**高级编辑器**。  
   ![高级编辑器](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-advanced-editor.png)
4. 记下为源列出的提供程序。  在此示例中，提供程序是 ActiveDirectory。  
   ![数据源提供程序](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-provider.png)
5. 将提供程序与在 [Power BI 数据源](power-bi-data-sources.md)中不支持的数据源列表进行比较。

## <a name="next-steps"></a>后续步骤
[数据刷新](refresh-data.md)  
[Power BI Gateway - Personal](service-gateway-personal-mode.md)  
[On-premises data gateway (本地数据网关)](service-gateway-onprem.md)  
[本地数据网关故障排除](service-gateway-onprem-tshoot.md)  
[Power BI Gateway - Personal 故障排除](service-admin-troubleshooting-power-bi-personal-gateway.md)  

更多问题？ [尝试咨询 Power BI 社区](https://community.powerbi.com/)

