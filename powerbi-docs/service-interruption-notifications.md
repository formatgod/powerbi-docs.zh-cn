---
title: 服务中断通知
description: 了解如何在出现 Power BI 服务中断或降级时接收电子邮件通知。
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/17/2020
ms.author: kfollis
ms.openlocfilehash: 85b26b68c4943e0bc100be7a298730cec34cfc78
ms.sourcegitcommit: d43761104f7daf4b2f297648855bb573b53e6d8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2020
ms.locfileid: "81637756"
---
# <a name="service-interruption-notifications"></a>服务中断通知

深入了解关键业务应用程序的可用性至关重要。 Power BI 提供事件通知，因此，你可以选择在出现服务中断或降级时接收电子邮件。 Power BI 99.9% 的服务级别协议 (SLA) 使得此类事件发生的概率极低，但万一发生，我们希望确保你能及时了解情况。 以下屏幕截图显示了你在启用通知时将收到的电子邮件类型：

![刷新通知电子邮件](media/service-interruption-notifications/refresh-notification-email.png)

目前，我们会针对以下可靠性场景发送电子邮件  ：

- 打开报表可靠性
- 模型刷新可靠性
- 查询刷新可靠性

在打开报表、刷新数据集或执行查询等操作中出现_较长延迟_的情况，则会发送通知。 事件解决后，你将收到跟进电子邮件。

> [!NOTE]
> 此功能目前仅适用于 Power BI Premium 中的专用容量。 不适用于共享容量或嵌入容量。





## <a name="enable-notifications"></a>启用通知

Power BI 租户管理员在管理门户中启用通知：

1. 标识或创建已启用电子邮件的安全组，该安全组将接收通知。

1. 在管理员门户中，选择“租户设置”  。 在“帮助和支持设置”下，展开“接收服务中断或突发事件相关电子邮件通知”   。

1. 启用通知，输入安全组，并选择“应用”  。

    ![启用服务通知](media/service-interruption-notifications/enable-notifications.png)

> [!NOTE]
> Power BI 将通过帐户 no-reply-powerbi@microsoft.com 发送通知。 确保此帐户已列入允许列表，以防止通知被发送到垃圾邮件文件夹中。

## <a name="next-steps"></a>后续步骤

[Power BI Pro 和 Power BI Premium 支持选项](service-support-options.md)

更多问题？ [尝试参与 Power BI 社区](https://community.powerbi.com/)
