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
ms.openlocfilehash: fed9fd05ed9916e4d285c64a398b48b82d99f884
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)