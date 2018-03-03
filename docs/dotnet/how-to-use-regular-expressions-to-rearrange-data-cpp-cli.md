---
title: "Nasıl yapılır: veriyi yeniden düzenlemek için normal ifadeleri kullanma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- regular expressions [C++], rearranging data
- data [C++], rearranging
ms.assetid: 5f91e777-9471-424e-ba75-dca3d1b49e42
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bf60fff6c15313a6f7df1104f67c1f043f885eac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-regular-expressions-to-rearrange-data-ccli"></a>Nasıl yapılır: Veriyi Yeniden Düzenlemek İçin Normal İfadeleri Kullanma (C++/CLI)
Aşağıdaki kod örneği, .NET Framework normal ifade destek yeniden düzenleyin veya verileri yeniden biçimlendirmek için nasıl kullanılabileceğini gösterir. Aşağıdaki kod örneğinde <xref:System.Text.RegularExpressions.Regex> ve <xref:System.Text.RegularExpressions.Match> adları ve soyadları çıkartmak ve bu adı öğeleri ters sırada görüntülemek için sınıflar.  
  
 <xref:System.Text.RegularExpressions.Regex> Sınıfı verilerin geçerli biçimini tanımlayan bir normal ifade oluşturmak için kullanılır. İki ad virgülle ayrılmış kabul edilir ve herhangi bir sayıdaki beyaz-boşluk, virgül kullanabilirsiniz. <xref:System.Text.RegularExpressions.Match> Yöntemi her dize çözümlemek için daha sonra kullanılır. Başarılı olursa, ad ve Soyadı alınır <xref:System.Text.RegularExpressions.Match> nesne ve görüntülenir.  
  
## <a name="example"></a>Örnek  
  
```  
// regex_reorder.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ name =   
   {  
      "Abolrous, Sam",   
      "Berg,Matt",   
      "Berry , Jo",  
      "www.contoso.com"  
   };  
  
   Regex^ reg = gcnew Regex("(?<last>\\w*)\\s*,\\s*(?<first>\\w*)");  
  
   for ( int i=0; i < name->Length; i++ )  
   {  
      Console::Write( "{0,-20}", name[i] );  
      Match^ m = reg->Match( name[i] );  
      if ( m->Success )  
      {  
         String^ first = m->Groups["first"]->Value;  
         String^ last = m->Groups["last"]->Value;  
         Console::WriteLine("{0} {1}", first, last);  
      }  
      else  
         Console::WriteLine("(invalid)");  
   }  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET framework normal ifadeleri](/dotnet/standard/base-types/regular-expressions)   
 [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)