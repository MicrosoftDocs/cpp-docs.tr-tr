---
title: "Nasıl yapılır: normal ifadeler kullanarak dizeleri ayrıştırma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- parsing strings [C++]
- examples [C++], strings
- regular expressions [C++], parsing strings
- strings [C++], parsing
ms.assetid: 5b0c7ca3-9bba-4389-a45c-6d373cff91b0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 629486c98888fd8012d616c9e845e7d70a90fdcf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-parse-strings-using-regular-expressions-ccli"></a>Nasıl yapılır: Normal İfadeler Kullanarak Dizeleri Ayrıştırma (C++/CLI)
Aşağıdaki kod örneği kullanarak basit bir dize ayrıştırmayı göstermektedir <xref:System.Text.RegularExpressions.Regex> sınıfını <xref:System.Text.RegularExpressions?displayProperty=fullName> ad alanı. Birden çok sözcük ayırıcı türü içeren bir dize oluşturulur. Dize, ardından kullanılarak ayrıştırılır <xref:System.Text.RegularExpressions.Regex> sınıfı ile birlikte <xref:System.Text.RegularExpressions.Match> sınıfı. Ardından, her sözcüğün tümcedeki ayrı olarak görüntülenir.  
  
## <a name="example"></a>Örnek  
  
```  
// regex_parse.cpp  
// compile with: /clr  
#using <system.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main( )  
{  
   int words = 0;  
   String^ pattern = "[a-zA-Z]*";  
   Console::WriteLine( "pattern : '{0}'", pattern );  
   Regex^ regex = gcnew Regex( pattern );  
  
   String^ line = "one\ttwo three:four,five six  seven";     
   Console::WriteLine( "text : '{0}'", line );  
   for( Match^ match = regex->Match( line );   
        match->Success; match = match->NextMatch( ) )   
   {  
      if( match->Value->Length > 0 )  
      {  
         words++;  
         Console::WriteLine( "{0}", match->Value );  
      }  
   }  
   Console::WriteLine( "Number of Words : {0}", words );  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET framework normal ifadeleri](/dotnet/standard/base-types/regular-expressions)   
 [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)