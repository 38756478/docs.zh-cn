---
title: "ICorProfilerCallback::ModuleLoadStarted 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleLoadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ad525b44169a85e61140c9e2a8d83c967945b2f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="d9e13-102">ICorProfilerCallback::ModuleLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="d9e13-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="d9e13-103">通知探查器加载模块。</span><span class="sxs-lookup"><span data-stu-id="d9e13-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9e13-104">语法</span><span class="sxs-lookup"><span data-stu-id="d9e13-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9e13-105">参数</span><span class="sxs-lookup"><span data-stu-id="d9e13-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="d9e13-106">[in]正在加载的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="d9e13-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9e13-107">备注</span><span class="sxs-lookup"><span data-stu-id="d9e13-107">Remarks</span></span>  
 <span data-ttu-id="d9e13-108">值`moduleId`无效的信息请求之前，不能[icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)调用方法。</span><span class="sxs-lookup"><span data-stu-id="d9e13-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9e13-109">要求</span><span class="sxs-lookup"><span data-stu-id="d9e13-109">Requirements</span></span>  
 <span data-ttu-id="d9e13-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d9e13-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9e13-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d9e13-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d9e13-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9e13-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9e13-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9e13-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e13-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9e13-114">See Also</span></span>  
 [<span data-ttu-id="d9e13-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="d9e13-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)