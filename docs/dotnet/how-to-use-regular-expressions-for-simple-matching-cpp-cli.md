---
title: "Nasıl yapılır: Basit Eşleştirme için normal ifadeleri kullanma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- substrings, simple matches
- searching, exact substring matches
- strings [C++], exact substring matching
- regular expressions [C++], simple matching
- IsMatch method
ms.assetid: 4661f6f3-0f6d-48f2-abe4-cb4770bf9bd5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 46a9301904d3293c242ca631c161b7e71304f283
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-regular-expressions-for-simple-matching-ccli"></a>Nasıl yapılır: Basit Eşleştirme için Normal İfadeler Kullanma (C++/CLI)
Aşağıdaki kod örneği için tam altdizgi eşleşme aramak için normal ifadeler kullanır. Arama statik tarafından gerçekleştirilen <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> yöntemi iki dizeyi giriş olarak alır. Aranacak düzeni saniyedir ve ilk aranacak dizedir.  
  
## <a name="example"></a>Örnek  
  
```  
// regex_simple.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ sentence =   
   {  
      "cow over the moon",  
      "Betsy the Cow",  
      "cowering in the corner",  
      "no match here"  
   };  
  
   String^ matchStr = "cow";  
   for (int i=0; i<sentence->Length; i++)  
   {  
      Console::Write( "{0,24}", sentence[i] );  
      if ( Regex::IsMatch( sentence[i], matchStr,  
                     RegexOptions::IgnoreCase ) )  
         Console::WriteLine("  (match for '{0}' found)", matchStr);  
      else  
         Console::WriteLine("");  
   }  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET framework normal ifadeleri](/dotnet/standard/base-types/regular-expressions)   
 [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)