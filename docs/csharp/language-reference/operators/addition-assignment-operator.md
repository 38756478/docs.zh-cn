---
title: += 运算符（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: de83f48fc644d8b232d9ef9e1698272f20a27d65
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="-operator-c-reference"></a>+= 运算符（C# 参考）
加法赋值运算符。  
  
## <a name="remarks"></a>备注  
 使用 `+=` 赋值运算符的表达式，如  
  
```  
x += y  
```  
  
 等效于  
  
```  
x = x + y  
```  
  
 不同的是 `x` 只计算一次。 [+ 运算符](../../../csharp/language-reference/operators/addition-operator.md)的含义取决于 `x` 和 `y` 的类型（数值操作数表示加法、字符串操作数表示串联等等）。  
  
 不能直接重载 `+=` 运算符，但用户定义的类型可重载 [+ 运算符](../../../csharp/language-reference/operators/addition-operator.md)（参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。  
  
 `+=` 运算符还用于指定事件响应中要调用的方法；此类方法称为事件处理程序。 在此上下文中使用 `+=` 运算符被称为订阅事件。 有关详细信息，请参阅[如何：订阅和取消订阅事件](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)和[委托](../../../csharp/programming-guide/delegates/index.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
