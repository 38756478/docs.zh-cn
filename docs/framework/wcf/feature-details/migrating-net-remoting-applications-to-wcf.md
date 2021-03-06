---
title: "将 .NET 远程处理应用程序迁移到 WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b7d305adf1810832016cdafbb60fc025f17e0786
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>将 .NET 远程处理应用程序迁移到 WCF
**本主题介绍一项传统技术，保留该技术是为了向后兼容现有的应用程序，不建议对新的开发使用该技术。现在应该使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 来开发分布式应用程序。**  
  
 通过现有的 .NET Remoting 应用程序来利用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 有两种方法：集成和迁移。 通过集成可以并行运行 .Net Remoting 2.0 和 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]，从而可以同时通过两种技术公开相同的业务对象，而不必修改现有的 .Net Remoting 2.0 代码。 集成要求运行 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 或更高版本。 如果您想要利用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的功能而不需要与 Remoting 2.0 系统具有网络兼容性，则可以将整个服务迁移到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]。 从 .NET Remoting 2.0 迁移到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 要求更改远程对象接口及其配置设置。 中介绍了这两这些主题[从远程处理与 Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403)。  
  
## <a name="see-also"></a>请参阅  
 [概念性概述](../../../../docs/framework/wcf/conceptual-overview.md)
