---
title: 'Nasıl yapılır: arama ve değiştirme için normal ifadeleri kullanma (C + +/ CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- search and replace
- Replace method
- regular expressions [C++], search and replace
ms.assetid: 12fe3e18-fe10-4b25-a221-19dc5eab3821
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: feb64670accef1cdcc5eedf9aa2b081dc41615b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132420"
---
# <a name="how-to-use-regular-expressions-to-search-and-replace-ccli"></a>Nasıl yapılır: Arama ve Değiştirme için Normal İfadeleri Kullanma (C++/CLI)
Aşağıdaki kod örneğinde gösterilmektedir nasıl normal ifade sınıfının <xref:System.Text.RegularExpressions.Regex> arama ve değiştirme yapmak için kullanılabilir. Bu gerçekleştirilir <xref:System.Text.RegularExpressions.Regex.Replace%2A> yöntemi. Kullanılan sürüm iki dizeyi giriş olarak alır: değiştirilecek dize ve (varsa) yerine bölümleri eklenecek dize verilen desenle eşleşen <xref:System.Text.RegularExpressions.Regex> nesnesi.  
  
 Bu kod bir dizedeki tüm basamağını alt çizgiler (_) ile değiştirir ve etkili bir şekilde bunları kaldırma, boş bir dize olanlar değiştirir. Aynı etkiye tek bir adımda gerçekleştirilebilir, ancak iki adımlar burada tanıtım amacıyla kullanılır.  
  
## <a name="example"></a>Örnek  
  
```  
// regex_replace.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System::Text::RegularExpressions;  
using namespace System;  
  
int main()  
{  
   String^ before = "The q43uick bro254wn f0ox ju4mped";  
   Console::WriteLine("original  : {0}", before);  
  
   Regex^ digitRegex = gcnew Regex("(?<digit>[0-9])");  
   String^ after = digitRegex->Replace(before, "_");  
   Console::WriteLine("1st regex : {0}", after);  
  
   Regex^ underbarRegex = gcnew Regex("_");  
   String^ after2 = underbarRegex->Replace(after, "");  
   Console::WriteLine("2nd regex : {0}", after2);  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET framework normal ifadeleri](/dotnet/standard/base-types/regular-expressions)   
 [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)