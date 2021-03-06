---
title: "如何：在 Visual Basic 中创建 XML 文档"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 63b6485de5aba2ca49d54a057045bec2062d12dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>如何：在 Visual Basic 中创建 XML 文档
此示例演示如何将 XML 文档注释添加到你的代码。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>若要创建一个类型或成员的 XML 文档  
  
1.  在**代码编辑器**，放置在你想要创建文档的类型或成员上方的行的光标。  
  
2.  类型`'''`（三个单引号引起来）。  
  
     在中添加该类型或成员的 XML 主干**代码编辑器**。  
  
3.  添加到相应的标记之间的描述性信息。  
  
    > [!NOTE]
    >  如果你添加的 XML 文档块中的其他行，每行必须以开头`'''`。  
  
4.  添加新的 XML 文档注释中使用该类型或成员的其他代码。  
  
     IntelliSense 会在显示中的文本\<摘要 > 标记的类型或成员。  
  
5.  编译代码，以生成包含文档注释的 XML 文件。 有关详细信息，请参阅 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使用 XML 记录代码](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
