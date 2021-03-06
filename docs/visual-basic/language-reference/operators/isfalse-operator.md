---
title: IsFalse 运算符 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d85fc51a75f82c65cf226b8239a8eee6585bd18a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse 运算符 (Visual Basic)
确定表达式是否为`False`。  
  
 不能调用`IsFalse`显式中你的代码，而 Visual Basic 编译器可以用它来生成代码从`AndAlso`子句。 如果你定义的类或结构，然后使用在该类型的变量的`AndAlso`子句中，你必须定义`IsFalse`在类或结构上。  
  
 编译器认为`IsFalse`和`IsTrue`与运算符*匹配对*。 这意味着，如果其中一个定义，你必须还定义另一个。  
  
> [!NOTE]
>  `IsFalse`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，其操作数的类或结构的类型。 如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的代码示例定义的结构，其中包含定义大纲`IsFalse`和`IsTrue`运算符。  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isfalse-operator_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [IsTrue 运算符](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [如何：定义运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [AndAlso 运算符](../../../visual-basic/language-reference/operators/andalso-operator.md)
