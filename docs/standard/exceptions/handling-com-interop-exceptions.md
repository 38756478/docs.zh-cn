---
title: "处理 COM 互操作异常"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: error-reference
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- HRESULTs
- exceptions, COM interop
- COM interop, exceptions
ms.assetid: e6104aa8-8e5f-4069-b864-def85579c96c
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e894d07e77b929b1ea22df2d34e542544ec3b1f3
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="handling-com-interop-exceptions"></a>处理 COM 互操作异常
托管和非托管代码可协同工作来处理异常。 如果方法在托管代码中引发异常，公共语言运行时可将 HRESULT 传递至 COM 对象。 如果方法因返回失败 HRESULT 而在非托管代码中失败，运行时会引发可由托管代码捕获的异常。  
  
 运行时自动将 HRESULT 从 COM 互操作映射到更具体的异常。 例如，E_ACCESSDENIED 成为 <xref:System.UnauthorizedAccessException>、E_OUTOFMEMORY 成为 <xref:System.OutOfMemoryException>，依次类推。  
  
 如果 HRESULT 为自定义结果或运行时不知道它，运行时会将泛型 <xref:System.Runtime.InteropServices.COMException> 传递到客户端。 COMException 的 ErrorCode 属性包含 HRESULT 值。  
  
## <a name="working-with-ierrorinfo"></a>处理 IErrorInfo  
 当错误从 COM 传递至托管代码时，运行时会将错误信息填充至异常对象。 支持 IErrorInfo 并返回 HRESULT 的 COM 对象将向托管代码异常提供此信息。 例如，运行时将“说明”从 COM 错误映射至异常的 <xref:System.Exception.Message%2A> 属性。 如果 HRESULT 未提供任何其他错误信息，运行时将对很多异常的属性填充默认值。  
  
 如果方法在非托管代码中失败，则异常可以传递至托管代码段中。 主题 [HRESULTS 和异常](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)中的表展示了如何将 HRESULTS 映射到运行时异常对象。  

## <a name="see-also"></a>请参阅
[异常](index.md) 
