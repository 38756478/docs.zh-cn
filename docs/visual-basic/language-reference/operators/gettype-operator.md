---
title: GetType 运算符 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38a984dce44133936f7f163e6afb20f0f336377c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="gettype-operator-visual-basic"></a>GetType 运算符 (Visual Basic)
返回<xref:System.Type>指定类型的对象。 <xref:System.Type>对象提供了有关如其属性、 方法和事件类型的信息。  
  
## <a name="syntax"></a>语法  
  
```  
GetType(typename)  
```  
  
#### <a name="parameters"></a>参数  
  
|参数|描述|  
|---|---|  
|`typename`|为其所需信息的类型的名称。|  
  
## <a name="remarks"></a>备注  
 `GetType`运算符返回<xref:System.Type>的指定对象的`typename`。 可以将在任何定义的类型名称传递给`typename`。 这包括：  
  
-   任何 Visual Basic 数据类型，如`Boolean`或`Date`。  
  
-   任何.NET Framework 类、 结构、 模块或接口，如<xref:System.ArgumentException?displayProperty=nameWithType>或<xref:System.Double?displayProperty=nameWithType>。  
  
-   任何类、 结构、 模块或接口定义应用程序。  
  
-   应用程序定义的任何数组。  
  
-   应用程序定义的任何委托。  
  
-   任何由 Visual Basic、.NET Framework 中或你的应用程序定义的枚举。  
  
 如果你想要获取的对象变量的类型对象，使用<xref:System.Type.GetType%2A?displayProperty=nameWithType>方法。  
  
 `GetType`运算符可以在以下情况下有用：  
  
-   必须在运行时访问类型的元数据。 <xref:System.Type>对象提供元数据，例如类型成员和部署信息。 您需要它，例如，在程序集上进行反射。 有关详细信息，请参阅<xref:System.Reflection?displayProperty=nameWithType>。  
  
-   你想要比较两个对象引用，以了解它们是否引用相同类型的实例。 如果他们这样做，`GetType`返回对相同的引用<xref:System.Type>对象。  
  
## <a name="example"></a>示例  
 下面的示例演示`GetType`中使用的运算符。  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/gettype-operator_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
