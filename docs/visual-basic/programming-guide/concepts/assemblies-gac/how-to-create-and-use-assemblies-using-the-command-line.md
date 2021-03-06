---
title: 如何： 创建和使用程序集使用命令行 (Visual Basic)
ms.custom: ''
ms.date: 03/14/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b39648107697cdbaa8856705f44df605efda11fa
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a>如何： 创建和使用程序集使用命令行 (Visual Basic)
程序集或动态链接库 (DLL) 会在运行时链接到程序。 为了演示如何生成和使用 DLL，请考虑以下方案：  
  
-   `MathLibrary.DLL`：包含要在运行时调用的方法的库文件。 在此示例中，DLL 包含两个方法，即 `Add` 和 `Multiply`。  
  
-   `Add`：包含方法 `Add` 的源文件。 它返回其参数的总和。 包含方法 `Add` 的类 `AddClass` 是命名空间 `UtilityMethods` 的成员。  
  
-   `Mult`：包含方法 `Multiply` 的源代码。 它返回其参数的乘积。 包含方法 `Multiply` 的类 `MultiplyClass` 也是命名空间 `UtilityMethods` 的成员。  
  
-   `TestCode`：包含 `Main` 方法的文件。 它使用 DLL 文件中的方法计算运行时参数的总和与乘积。  
  
## <a name="example"></a>示例  
  
```vb  
' File: Add.vb   
Namespace UtilityMethods  
    Public Class AddClass  
        Public Shared Function Add(ByVal i As Long, ByVal j As Long) As Long  
            Return i + j  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: Mult.vb  
Namespace UtilityMethods  
    Public Class MultiplyClass  
        Public Shared Function Multiply(ByVal x As Long, ByVal y As Long) As Long  
            Return x * y  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: TestCode.vb  
  
Imports UtilityMethods  
  
Module Test  
  
    Sub Main(ByVal args As String())  
  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:")  
  
        If args.Length <> 2 Then  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>")  
            Return  
        End If  
  
        Dim num1 As Long = Long.Parse(args(0))  
        Dim num2 As Long = Long.Parse(args(1))  
  
        Dim sum As Long = AddClass.Add(num1, num2)  
        Dim product As Long = MultiplyClass.Multiply(num1, num2)  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum)  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product)  
  
    End Sub  
  
End Module  
  
' Output (assuming 1234 and 5678 are entered as command-line arguments):  
' Calling methods from MathLibrary.DLL:  
' 1234 + 5678 = 6912  
' 1234 * 5678 = 7006652  
```  
  
 此文件包含使用 DLL 方法 `Add` 和 `Multiply` 的算法。 它首先分析从命令行输入的参数 `num1` 和 `num2`。 然后通过对 `AddClass` 类使用 `Add` 方法来计算总和，并通过对 `MultiplyClass` 类使用 `Multiply` 方法来计算乘积。  
  
 请注意，`Imports`语句开头的文件使您能够使用非限定的类名来引用 DLL 方法在编译时，如下所示：  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 否则，你必须使用完全限定的名称，如下所示：  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a>执行  
 若要运行程序，请输入 EXE 文件的名称，后跟两个数字，如下所示：  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a>编译代码  
 若要生成文件 `MathLibrary.DLL`，请使用以下命令行编译两个文件 `Add` 和 `Mult`。  
  
```console  
vbc -target:library -out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 [-目标 (Visual Basic 中)](../../../../visual-basic/reference/command-line-compiler/target.md)编译器选项告知编译器输出而不是 EXE 文件的 DLL。 [-Out (Visual Basic 中)](../../../../visual-basic/reference/command-line-compiler/out.md)跟文件名称的编译器选项用于指定 DLL 文件的名称。 否则，编译器使用第一个文件 (`Add.vb`) 作为 DLL 的名称。  
  
 若要生成可执行文件 `TestCode.exe`，请使用以下命令行：  
  
```console  
vbc -out:TestCode.exe -reference:MathLibrary.DLL TestCode.vb  
```  
  
 **-出**编译器选项告知编译器输出的 EXE 文件，并指定输出文件的名称 (`TestCode.exe`)。 此编译器选项是可选的。 [-参考 (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md)编译器选项指定的 DLL 文件或此程序使用的文件。  
  
 有关从命令行生成的详细信息，请参阅和[从命令行生成](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)。  
  
## <a name="see-also"></a>另请参阅  
 [编程概念](../../../../visual-basic/programming-guide/concepts/index.md)  
 [程序集和全局程序集缓存 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [创建用于容纳 DLL 函数的类](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
