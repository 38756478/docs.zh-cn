---
title: 类型 &#39;&lt;typename&gt;&#39; 未定义
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 68eb37f43600c51dc9117c3785a12e3c8ede1965
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="type-39lttypenamegt39-is-not-defined"></a>类型 &#39;&lt;typename&gt;&#39; 未定义
该语句已对尚未定义的类型引用。 你可以定义一种类型的声明语句中诸如`Enum`， `Structure`， `Class`，或`Interface`。  
  
 **错误 ID:** BC30002  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   请确保类型定义和它的引用都使用相同的拼写。  
  
-   请确保类型定义为引用可访问。 例如，如果类型是另一个模块中并已被声明为`Private`、 将类型定义移到引用的模块或将其声明`Public`。  
  
-   请确保类型的命名空间不会重新定义您的项目中。 如果是，使用`Global`关键字用于完全限定类型名称。 例如，如果一个项目定义的命名空间名为`System`、<xref:System.Object?displayProperty=nameWithType>无法访问类型，除非它是使用完全限定`Global`关键字： `Global.System.Object`。  
  
-   如果定义的类型，但未注册的对象库或在其中定义的类型库[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]，单击**添加引用**上**项目**菜单，然后选择适当的对象库或类型库。  
  
-   请确保该类型所在的目标.NET Framework 配置文件一部分的程序集中。 有关详细信息，请参阅 [.NET Framework 目标错误疑难解答](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors)。  
  
## <a name="see-also"></a>另请参阅  
 [在 Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [管理项目中的引用](/visualstudio/ide/managing-references-in-a-project)
