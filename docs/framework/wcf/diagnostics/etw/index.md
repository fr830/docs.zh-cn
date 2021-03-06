---
title: 使用 ETW 进行分析跟踪
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: cff13439995d8a90da15b7afa15723f21574e35e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193709"
---
# <a name="analytic-tracing-with-etw"></a>使用 ETW 进行分析跟踪
Windows Communication Foundation (WCF) 分析跟踪提供了一种方法来执行 WCF 服务期间捕获诊断信息。 WCF 分析跟踪事件发出的 WCF 堆栈，以允许在生产环境中的 WCF 服务的故障排除中的关键点。 分析跟踪 WCF 服务的最小对性能产生影响的产品服务器承载[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]WCF 服务，因为这些事件非常高效地发送到 Windows 事件跟踪 (ETW) 会话。  
  
## <a name="in-this-section"></a>本节内容  
 [分析跟踪概述](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 讨论 WCF 分析跟踪中的工作方式[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]。  
  
 [动态启用分析跟踪](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 讨论如何使用 ETW 动态启用或禁用跟踪。  
  
 [配置消息流跟踪](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 描述如何配置消息流跟踪。  
  
 [分析跟踪事件参考](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 显示一张表，其中包括事件 ID 及其事件级别、事件消息和关键字。  
  
## <a name="see-also"></a>请参阅

- [针对 Windows 的 WCF 服务和事件跟踪](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
- [在 Windows 事件跟踪中跟踪事件](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
