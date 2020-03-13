---
title: 在 Power BI 报表生成器中预览报表
description: 在创建报表生成器分页报表时，一个很有用的做法是经常预览报表以验证报表是否显示所需内容。
ms.date: 06/06/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: ba6b5bdd-d8c6-4aa8-ba32-3a10b11969d4
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: afbc31e3ece8bc72ad52bb2fe7c3d871b2f68e1b
ms.sourcegitcommit: ced8c9d6c365cab6f63fbe8367fb33e6d827cb97
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "78922933"
---
# <a name="previewing-reports-in-power-bi-report-builder"></a>在 Power BI 报表生成器中预览报表
  在创建报表生成器分页报表时，一个很有用的做法是经常预览报表以验证报表是否显示所需内容。 要预览报表，请单击“运行”  。 在预览模式下呈现报表。  
  
 报表生成器通过在连接到报表服务器时使用编辑会话来改善预览体验。 编辑会话会创建数据缓存，并使缓存中的数据集可用于反复预览报表。 编辑会话不是一项直接与用户交互的功能，但了解何时刷新缓存数据集将有助于在预览报表时提高性能并了解报表呈现速度变快或变慢的原因。  

  
> [!NOTE]  
> 在报表生成器中预览与在浏览器中查看，二者之间存在一些差异。 例如，指定日期/时间类型参数时添加到报表中的日历控件在报表生成器中和在浏览器中有所不同。 
  
## <a name="improving-preview-performance"></a>改进预览性能  
 创建和更新报表的方式会影响报表在预览中呈现的速度。 首次预览一个依赖于服务器引用的报表时，会创建编辑会话，并会将报表运行时所使用的数据添加到存储的数据缓存中。 更改一个不影响数据的报表时，报表会使用缓存的数据副本。 这意味着每次预览报表时都不会看到数据更改。 如果要查看新数据，请单击功能区上的“刷新”按钮  。  
  
 以下操作会导致缓存刷新，并且在下次预览报表时减慢报表呈现速度：  
  
-   添加、更改或删除数据集。 缓存的数据集包含报表使用的所有数据集，并且修改任何数据集都会导致缓存的数据集无效。 包括更改名称、查询或数据集中的字段。  
  
    > [!NOTE]  
    >  如果数据集包含大量用不到的字段，应考虑更新数据集，省略这些字段。 虽然这会创建新的编辑会话，并且报表的首次预览速度会较慢，但较小的缓存数据集总体上有利于提高报表服务器的性能。  
  
-   添加、更改或删除数据源。 这包括更改数据源的名称或属性、数据源的数据扩展名或数据源的连接属性。  
  
-   将报表使用的数据源更改为其他数据源。  
  
-   更改报表语言。  
  
-   更改报表使用的程序集或自定义代码。  
  
-   添加、更改或删除报表中的查询参数或参数值。  
  
 对报表布局和数据格式的更改不影响缓存的数据集。 无需刷新缓存的数据集，即可执行以下操作：  
  
-   添加或删除数据区域（如表、矩阵或图表）。  
  
-   添加或删除报表中的列。 数据集中的所有字段都可在报表中使用。 在报表中添加或删除字段不影响数据集。  
  
-   更改表和矩阵中的字段顺序。  
  
-   添加、更改或删除行和列组。  
  
-   添加、更改或删除字段中数据值的格式。  
  
-   添加、更改或删除图像、线条或文本框。  
  
-   更改分页符。  
  
第一次预览报表时将创建编辑会话。 编辑会话默认持续 7200 秒（2 个小时）。 每次运行报表时，会话都会重置为两个小时。 编辑会话过期时，将删除数据缓存。 如果编辑会话过期，下次预览报表时会自动再创建一个。
  
数据缓存默认最多可容纳五个数据集。 如果使用多个不同的参数值组合，报表可能需要更多数据。 这样就需要刷新缓存，且下次预览报表时报表呈现速度会变慢。 
  
## <a name="concurrency-of-report-updates"></a>并发的报表更新  
通常会频繁地在更新报表并将其保存到 Power BI 服务的过程中预览报表。 更新报表时，其他人也可能同时在更新并保存报表。 最后保存的报表是将来查看和更新报表时所使用的版本。 这意味着预览的报表版本可能不是重新打开时的版本。 可使用“报表生成器”菜单上的“另存为”选项，使用新名称保存报表  。  
  
## <a name="external-report-items"></a>外部报表项  
 报表可能包含与报表分开存储的外部图像等项。 由于这些项是单独存储的，因此可能会被移至其他位置或被删除。 如果发生这种情况，可能无法预览报表。 可以更新报表以指示更新的项位置，或如果项已被删除，可将其替换为现有项，或者从报表中删除对该项的引用。  
  
## <a name="next-steps"></a>后续步骤

- [Power BI Premium 中的分页报表是什么？](paginated-reports-report-builder-power-bi.md)
  