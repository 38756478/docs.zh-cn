---
title: '&lt;&lt;= 运算符（C# 参考）'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b5c2a177182561075442afc3f1b76603c6646bd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-c-reference"></a>&lt;&lt;= 运算符（C# 参考）
左移赋值运算符。  
  
## <a name="remarks"></a>备注  
 形式如下的表达式  
  
```  
x <<= y  
```  
  
 计算结果为  
  
```  
x = x << y  
```  
  
 不同的是 `x` 只计算一次。 [<< 运算符](../../../csharp/language-reference/operators/left-shift-operator.md) 将 `x` 向左移动 `y` 指定的位数。  
  
 不能直接重载 `<<=` 运算符，但用户定义的类型可重载 [<< 运算符](../../../csharp/language-reference/operators/left-shift-operator.md)（参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
