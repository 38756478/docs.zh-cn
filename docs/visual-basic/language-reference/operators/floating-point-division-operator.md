---
title: / 运算符 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f221e863725b9aeb0b3fa3219b3a881541e2be0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>/ 运算符 (Visual Basic)
使两个数字相除，返回浮点结果。  
  
## <a name="syntax"></a>语法  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a>部件  
 `expression1`  
 必需。 任何数值表达式。  
  
 `expression2`  
 必需。 任何数值表达式。  
  
## <a name="supported-types"></a>支持的类型  
 所有数值类型，包括未签名和浮点类型和`Decimal`。  
  
## <a name="result"></a>结果  
 结果为完整的商`expression1`除以`expression2`，包括所有余数。  
  
 [\ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)返回的整数的商，这会导致断开其余部分。  
  
## <a name="remarks"></a>备注  
 结果的数据类型取决于操作数的类型。 下表显示如何确定结果的数据类型。  
  
|操作数数据类型|结果数据类型|  
|------------------------|----------------------|  
|两个表达式均整数数据类型 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)，[字节](../../../visual-basic/language-reference/data-types/byte-data-type.md)，[短](../../../visual-basic/language-reference/data-types/short-data-type.md)， [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)，[整数](../../../visual-basic/language-reference/data-types/integer-data-type.md)，[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)，[长](../../../visual-basic/language-reference/data-types/long-data-type.md)， [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|`Double`|  
|一个表达式是[单个](../../../visual-basic/language-reference/data-types/single-data-type.md)数据类型和其他不是[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Single`|  
|一个表达式是[十进制](../../../visual-basic/language-reference/data-types/decimal-data-type.md)数据类型和其他不是[单个](../../../visual-basic/language-reference/data-types/single-data-type.md)或[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Decimal`|  
|其中任何一个表达式是[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)数据类型|`Double`|  
  
 执行除法运算之前，任何整型的数值表达式都将加宽到`Double`。 如果你将结果赋给整型数据类型时，Visual Basic 将尝试将转换的结果`Double`为该类型。 如果结果不符合该类型，这可以引发异常。 具体而言，此帮助页上看到"尝试用零作除数"。  
  
 如果`expression1`或`expression2`计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)，它将被视为零。  
  
## <a name="attempted-division-by-zero"></a>尝试的除数为零  
 如果`expression2`计算结果为零，`/`运算符的操作数数据类型不同的行为有所不同。 下表显示可能的行为。  
  
|操作数数据类型|行为如果`expression2`为零|  
|------------------------|---------------------------------------|  
|浮点 (`Single`或`Double`)|返回无穷大 (<xref:System.Double.PositiveInfinity>或<xref:System.Double.NegativeInfinity>)，或<xref:System.Double.NaN>（而不是数字） 如果`expression1`也为零|  
|`Decimal`|引发<xref:System.DivideByZeroException>|  
|整数 （有符号或无符号）|尝试转换回整数类型会引发<xref:System.OverflowException>因为整数类型不能接受<xref:System.Double.PositiveInfinity>， <xref:System.Double.NegativeInfinity>，或<xref:System.Double.NaN>|  
  
> [!NOTE]
>  `/`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。 如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 此示例使用`/`执行浮点除法运算的运算符。 结果是两个操作数的商。  
  
 [!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]  
  
 在前面的示例表达式返回 2.5 和 3.333333 的值。 请注意结果始终是浮点 (`Double`)，即使这两个操作数都是整数常量。  
  
## <a name="see-also"></a>另请参阅  
 [/ = 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [\ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)  
 [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [在 Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
