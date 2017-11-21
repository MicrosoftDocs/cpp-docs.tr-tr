---
title: "Biçimlendirmesini doğrulamak için normal ifadeleri kullanma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- strings [C++], formatting
- data [C++], formatting
- regular expressions [C++], validating data formatting
ms.assetid: 225775c3-3efc-4734-bde2-1fdf73e3d397
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: db15abf9aca532b8c0fb712733c4e87350b58747
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-regular-expressions-to-validate-data-formatting-ccli"></a>Nasıl yapılır: Veri Biçimlendirmesini Doğrulamak için Normal İfadeleri Kullanma (C++/CLI)
Aşağıdaki kod örneğinde biçimlendirme dizesi doğrulamak için normal ifadeler kullanımını göstermektedir. Aşağıdaki kod örneğinde, geçerli bir telefon numarası dize içermelidir. Aşağıdaki kod örneğinde "\d{3}-\d{3}-\d{4}" dizesi her bir alan geçerli bir telefon numarası temsil ettiğini göstermek için kullanır. Bir basamak dizesindeki "d" gösterir ve sonra her "d" bağımsız değişkeni bulunmalıdır basamak sayısını belirtir. Bu durumda, numara çizgilerle ayrılmış olması zorunlu değildir.  
  
## <a name="example"></a>Örnek  
  
```  
// regex_validate.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ number =   
   {  
      "123-456-7890",   
      "444-234-22450",   
      "690-203-6578",   
      "146-893-232",  
      "146-839-2322",  
      "4007-295-1111",   
      "407-295-1111",   
      "407-2-5555",   
   };  
  
   String^ regStr = "^\\d{3}-\\d{3}-\\d{4}$";  
  
   for ( int i = 0; i < number->Length; i++ )  
   {  
      Console::Write( "{0,14}", number[i] );  
  
      if ( Regex::IsMatch( number[i], regStr ) )  
         Console::WriteLine(" - valid");  
      else  
         Console::WriteLine(" - invalid");  
   }  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET framework normal ifadeleri](/dotnet/standard/base-types/regular-expressions)   
 [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)