---
title: 'Nasıl yapılır: veri alanlarını ayıklamak için normal ifadeleri kullanma (C + +/ CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], extracting data from
- formatted strings [C++]
- regular expressions [C++], extracting data fields
- data [C++], extracting from strings
ms.assetid: b581d9b6-630e-48fa-94fe-20b0f7b89b06
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 20e1139ccee0c3cc1533f42fb1b9e1eafaca3afd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129674"
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
 [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)