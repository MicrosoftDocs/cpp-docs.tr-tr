---
title: "Nasıl yapılır: veri alanlarını ayıklamak için normal ifadeleri kullanma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- strings [C++], extracting data from
- formatted strings [C++]
- regular expressions [C++], extracting data fields
- data [C++], extracting from strings
ms.assetid: b581d9b6-630e-48fa-94fe-20b0f7b89b06
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a297ee1676fb3ffbff45d46334d20280beeab078
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-regular-expressions-to-extract-data-fields-ccli"></a>Nasıl yapılır: Veri Alanlarını Ayıklamak için Normal İfadeleri Kullanma (C++/CLI)
Aşağıdaki kod örneğinde biçimlendirilmiş bir dizeden veri ayıklamak için normal ifadeler kullanımını göstermektedir. Aşağıdaki kod örneğinde <xref:System.Text.RegularExpressions.Regex> sınıfı bir e-posta adresine karşılık gelen bir desen belirtin. Bu desen kullanıcı ve her bir e-posta adresinin ana bilgisayar adı bölümünü almak için kullanılan alan tanımlayıcıları içerir. <xref:System.Text.RegularExpressions.Match> Sınıfı gerçek desen eşleştirme işlemi yapmak için kullanılır. Belirtilen e-posta adresi geçerli ise, kullanıcı adı ve ana bilgisayar adları ayıklanır ve görüntülenir.  
  
## <a name="example"></a>Örnek  
  
```  
// Regex_extract.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main()  
{  
    array<String^>^ address=  
    {  
        "jay@southridgevideo.com",  
        "barry@adatum.com",  
        "treyresearch.net",  
        "karen@proseware.com"  
    };  
  
    Regex^ emailregex = gcnew Regex("(?<user>[^@]+)@(?<host>.+)");  
  
    for (int i=0; i<address->Length; i++)  
    {  
        Match^ m = emailregex->Match( address[i] );  
        Console::Write("\n{0,25}", address[i]);  
  
        if ( m->Success )   
        {  
            Console::Write("   User='{0}'",   
            m->Groups["user"]->Value);  
            Console::Write("   Host='{0}'",   
            m->Groups["host"]->Value);  
        }  
        else   
            Console::Write("   (invalid email address)");  
        }  
  
    Console::WriteLine("");  
    return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET framework normal ifadeleri](/dotnet/standard/base-types/regular-expressions)   
 [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)