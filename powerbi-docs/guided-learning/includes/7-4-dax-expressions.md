---
ms.openlocfilehash: f22c12ec0ad5bd413f3658704132143c878df1aa
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "73799701"
---
使用**变量**是 DAX 表达式的功能非常强大的组成部分。

![](media/7-4-dax-expressions/dax-variables_1.png)

你可以使用以下语法在 DAX 表达式的任意位置定义一个变量：

    VARNAME = RETURNEDVALUE

变量可以是任何数据类型，包括整个表。

请记住，每次在 DAX 表达式中引用变量时，Power BI 必须根据定义重新计算它的值。 因此，在函数中避免使用重复变量是一个好做法。

> 视频内容由 [Alberto Ferrari, SQLBI](https://www.sqlbi.com/learning-dax) 提供
> 
> 

