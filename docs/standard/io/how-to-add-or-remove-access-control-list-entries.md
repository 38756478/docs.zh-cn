---
title: "如何：添加或移除访问控制列表项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ACEs [.NET Framework]
- ACLs [.NET Framework]
- access control entries [.NET Framework]
- I/O [.NET Framework], access control list entries
- access control lists [.NET Framework]
ms.assetid: 53758b39-bd9b-4640-bb04-cad5ed8d0abf
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 988fd354caa5fcc716107087242ead113c9a9939
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-add-or-remove-access-control-list-entries"></a>如何：添加或移除访问控制列表项
若要向文件添加或从文件删除访问控制列表 (ACL) 条目，则必须从文件或目录获取 <xref:System.Security.AccessControl.FileSecurity> 或 <xref:System.Security.AccessControl.DirectorySecurity> 对象并对其进行修改，然后应用回文件或目录。  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-file"></a>若要添加或从文件中删除 ACL 条目  
  
1.  调用 <xref:System.IO.File.GetAccessControl%2A> 方法以获取 <xref:System.Security.AccessControl.FileSecurity> 对象，该对象包含文件的当前 ACL 条目。  
  
2.  添加或从步骤 1 返回的 <xref:System.Security.AccessControl.FileSecurity> 对象中删除 ACL 条目。  
  
3.  将 <xref:System.Security.AccessControl.FileSecurity> 对象传递给 <xref:System.IO.File.SetAccessControl%2A> 方法以应用更改。  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-directory"></a>若要添加或从目录中删除 ACL 条目  
  
1.  调用 <xref:System.IO.Directory.GetAccessControl%2A> 方法以获取 <xref:System.Security.AccessControl.DirectorySecurity> 对象，该对象包含目录的当前 ACL 条目。  
  
2.  添加或从步骤 1 返回的 <xref:System.Security.AccessControl.DirectorySecurity> 对象中删除 ACL 条目。  
  
3.  将 <xref:System.Security.AccessControl.DirectorySecurity> 对象传递给 <xref:System.IO.Directory.SetAccessControl%2A> 方法以应用更改。  
  
## <a name="example"></a>示例  
 [!code-cpp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/cpp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/cpp/sample.cpp#1)]
 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 你必须提供有效的用户或组帐户以运行此示例。 此示例使用 <xref:System.IO.File> 对象；但是，对于 <xref:System.IO.FileInfo>、<xref:System.IO.Directory> 和 <xref:System.IO.DirectoryInfo> 类使用相同的过程。
