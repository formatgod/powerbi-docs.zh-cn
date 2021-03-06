---
title: 在 Power BI 中使用相对时间切片器或筛选器
description: 了解如何使用切片器或筛选器在 Power BI 中约束相对时间范围。
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/22/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 31563e5bb5b91468b8913c3204e9d27607716c77
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83279195"
---
# <a name="use-a-relative-time-slicer-and-filter-in-power-bi"></a>在 Power BI 中使用相对时间切片器和筛选器

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

随着快速刷新方案的出现，筛选到较小时段的功能可能非常有用。 借助相对时间切片器或筛选器，可以向数据模型中的任意日期或时间列应用时间筛选器。 例如，可以使用相对时间切片器来只显示最后一分钟或一小时的视频视图。 

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time.gif" alt-text="相对时间示例":::

你不必将此功能与[自动页刷新](../create-reports/desktop-automatic-page-refresh.md)功能结合使用。 不过，很多相对时间方案都能与自动页面刷新功能搭配使用。  

> [!NOTE]
> 在页面或报表级别应用相对时间筛选器或切片器时，将使用共享锚点时间，将该页面或报表中的所有视觉对象筛选为完全相同的时间范围  。 由于视觉对象的执行时间可能略有不同，因此，此共享的锚点时间可确保在页面或报表之间同步视觉对象。 有关详细信息，请参阅本文中的[锚点时间](#understanding-anchor-time)。

## <a name="turn-on-relative-time-preview"></a>打开相对时间预览

相对时间筛选器处于预览阶段，因此需要打开此功能开关。 转到“文件” > “选项和设置” > 选项”    。 在“全局设置” > “预览功能”中，确保选中“相对时间筛选器”    。

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-set-preview.png" alt-text="设置相对时间预览选项":::

## <a name="create-a-relative-time-slicer-or-filter"></a>创建相对时间切片器或筛选器

启用该功能后，可将“日期”或“时间”字段拖放到切片器字段框或“筛选器”窗格中的放置区域中。 

### <a name="create-a-slicer"></a>创建切片器

1. 将“日期”或“时间”字段拖放到画布

2. 选择“切片器”可视化效果类型  。

    :::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-create-slicer.png" alt-text="创建时间切片器":::

### <a name="create-a-filter"></a>创建筛选器
 
- 对于“此视觉对象”、“此页面”或“所有页面”，请将“日期”或“时间”字段拖放到“筛选器”窗格中    。

### <a name="set-relative-time"></a>设置相对时间 

接下来，将筛选器类型更改为“相对时间”  。

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-set.png" alt-text="更改为“相对时间”":::
 
在切片器中的显示方式如下所示：

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-slicer.png" alt-text="切片器中的相对时间":::

筛选器卡片中的显示方式如下所示： 

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-filter.png" alt-text="筛选器中的相对时间":::
 
使用此新的筛选器类型，可根据“上一次”、“下一次”或“此时间段”进行筛选    ： 

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-last-next.png" alt-text="选择“上一次”、“下一次”或“此时间段”":::
 
使用整数和时间单位指定时间范围：分钟或小时   。
 
:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-minutes-hours.png" alt-text="选择分钟数或小时数":::

如果需要在画布上保存空间，还可以在“筛选器”窗格中创建相对时间筛选器作为筛选器卡片。

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-set-filter.png" alt-text="改为在筛选器中设置相对时间":::
 
## <a name="understanding-anchor-time"></a>了解锚点时间

当筛选器应用于页面或报表级别时，该页面或报表上的所有视觉对象都将同步到相同的时间范围。 这些查询都是相对于称为“锚点时间”的时间发出的  。 锚点时间在以下条件下自动刷新：

- 初始页面加载。
- 手动刷新。
- 自动或更改检测页刷新。
- 对模型进行更改。

### <a name="anchor-time-exceptions"></a>锚点时间异常

- 使用问答视觉对象的相对时间筛选与此锚点时间无关，除非将问答视觉对象转换为标准视觉对象。 但其他 AI 视觉对象（如关键影响因素和分解树）将与锚点时间进行同步。 
- 此外，相对日期筛选器或切片器不是相对于锚点时间，除非存在相对时间筛选器。 如果相对日期和相对时间筛选器位于同一页上，则相对日期筛选器将遵循锚点时间。

## <a name="limitations-and-considerations"></a>限制和注意事项

目前，使用相对日期切片器和筛选器时，需要遵循以下限制和注意事项。

- **时区注意事项**Power BI 中的数据模型不包含时区信息。 模型可以存储时间，但并不指明所在时区。 切片器和筛选器始终基于 UTC 的时间。 如果在报表中设置筛选器并将其发送给位于其他时区的同事，你们将看到相同的数据。 除非你或你的同事处于 UTC 时区，否则你们都必须考虑将会遇到的时间偏移量。 可使用查询编辑器将在本地时区捕获的数据转换为 UTC。
- Power BI Desktop、Power BI 服务、Power BI Embedded 和 Power BI 移动应用支持这种新的筛选器类型。 但存在以下几个已知的支持限制：

    - 不支持嵌入 API。
    - 不支持发布到 Web。

- **查询缓存**：我们使用客户端缓存。 因此，假设指定“过去 1 分钟”，再指定“过去 5 分钟”，则会返回到“过去 1 分钟”。 此时，你看到的结果与首次运行时的结果相同，除非你刷新页面或页面自动刷新。

## <a name="next-steps"></a>后续步骤

- [在 Power BI 中使用相对日期切片器和筛选器](../visuals/desktop-slicer-filter-date-range.md)
- [Power BI 中的切片器](../visuals/power-bi-visualization-slicers.md)
