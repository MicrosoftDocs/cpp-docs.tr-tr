---
title: 'Nasıl yapılır: Split yöntemini kullanarak dizeleri ayrıştırma (C + +/ CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- parsing strings [C++]
- examples [C++], strings
- regular expressions [C++], parsing strings
- Split method, parsing strings
- strings [C++], parsing
ms.assetid: d52d2539-5ebb-4716-86b3-07314dd7e4bd
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7494a615d1a253c6617601f38e5d01755c718b80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-parse-strings-using-the-split-method-ccli"></a>Nasıl yapılır: Split Yöntemini Kullanarak Dizeleri Ayrıştırma (C++/CLI)
Aşağıdaki kod örneğinde kullanımı gösterilir <xref:System.String.Split%2A?displayProperty=fullName> her sözcüğün çıkartmak yöntemi. Birden çok sözcük ayırıcı türü içeren bir dize oluşturulur ve çağrılarak ayrıştırılır <xref:System.String.Split%2A> ayırıcıların listesiyle. Ardından, her sözcüğün tümcedeki ayrı olarak görüntülenir.  
  
## <a name="example"></a>Örnek  
  
```  
// regex_split.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String^ delimStr = " ,.:\t";  
   Console::WriteLine( "delimiter : '{0}'", delimStr );  
   array<Char>^ delimiter = delimStr->ToCharArray( );  
   array<String^>^ words;  
   String^ line = "one\ttwo three:four,five six seven";  
  
   Console::WriteLine( "text : '{0}'", line );  
   words = line->Split( delimiter );  
   Console::WriteLine( "Number of Words : {0}", words->Length );  
   for (int word=0; word<words->Length; word++)  
      Console::WriteLine( "{0}", words[word] );  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET framework normal ifadeleri](/dotnet/standard/base-types/regular-expressions)   
 [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)