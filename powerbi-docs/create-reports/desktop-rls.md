---
title: 使用 Power BI Desktop 行级安全性 (RLS) 限制数据访问
description: 如何为导入的数据集和 Power BI Desktop 内的 DirectQuery 配置行级别安全性。
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.custom: ''
ms.date: 01/31/2020
LocalizationGroup: Create reports
ms.openlocfilehash: 89c33de2ef7319c6dcbeace0df79786128e16cd9
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83334306"
---
# <a name="restrict-data-access-with-row-level-security-rls-for-power-bi-desktop"></a>使用 Power BI Desktop 行级安全性 (RLS) 限制数据访问

可以结合使用行级别安全性 (RLS) 和 Power BI Desktop，以限制给定用户的数据访问。 筛选器可限制行级别上的数据。 你可以定义角色中的筛选器。

现在，你可以使用 Power BI Desktop 为导入到 Power BI 的数据模型配置 RLS。 还可以在使用 [DirectQuery](../connect-data/desktop-use-directquery.md)（如 SQL Server）的数据集上配置 RLS。 在此之前，只能在 Power BI 外的本地 Analysis Services 模型中实现 RLS。 对于 Analysis Services 的实时连接，你可以在本地模型上配置行级别安全性。 实时连接数据集不会显示安全选项。

> [!IMPORTANT]
> 如果在 Power BI 服务中定义了角色和规则，则需要在 Power BI Desktop 中重新创建这些角色，然后将报表发布到服务。 了解有关 [Power BI 服务中的 RLS](../admin/service-admin-rls.md) 选项的详细信息。

[!INCLUDE [include-short-name](../includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](../includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](../includes/rls-limitations.md)]

[!INCLUDE [include-short-name](../includes/rls-faq.md)]

## <a name="next-steps"></a>后续步骤

[Power BI 服务行级别安全性 (RLS)](../admin/service-admin-rls.md)  

更多问题？ [尝试咨询 Power BI 社区](https://community.powerbi.com/)。