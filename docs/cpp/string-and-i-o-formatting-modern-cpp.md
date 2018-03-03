---
title: "Dize ve t-O biçimlendirme (Modern C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a13861fe03547e37c4de72c21a528e297a217511
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="string-and-io-formatting-modern-c"></a>Dize ve G/Ç Biçimlendirme (Modern C++)
C++ [iostreams](../standard-library/iostream.md) biçimlendirilmiş dizesini g/ç yeteneğine sahiptir. Örneğin, aşağıdaki kod bir tamsayı önce geçerli durumunu kapatmak kaydetme ve daha sonra durumu biçimlendirme cout için geçirilen sonra yalnızca bir satır için değişiklik kadar bu şekilde kalır olduğundan yeniden ayarlama onaltılık çıkış biçimine cout ayarlamak nasıl gösterir kodu.  
  
```cpp  
#include <iostream>  
#include <iomanip>  
  
using namespace std;  
  
int main()   
{  
    ios state(nullptr);  
  
    cout << "The answer in decimal is: " << 42 << endl;  
  
    state.copyfmt(cout); // save current formatting  
    cout << "In hex: 0x" // now load up a bunch of formatting modifiers  
        << hex   
        << uppercase   
        << setw(8)   
        << setfill('0')   
        << 42            // the actual value we wanted to print out  
        << endl;  
    cout.copyfmt(state); // restore previous formatting  
}  
  
```  
  
 Bu tamamen olabilir çok sıkıcı birçok durumda. Alternatif olarak, standart dışı olsa da artırma C++ kitaplıklarından Boost.Format kullanabilirsiniz. Tüm artırma Kitaplığı'ndan yükleyebilirsiniz [artırma](http://www.boost.org/) Web sitesi.  
  
 Boost.Format avantajlarından bazıları şunlardır:  
  
-   Güvenli: Tür kullanımı uyumlu ve hatalar için bir özel durum oluşturur — Örneğin, çok az veya çok fazla sayıda öğe belirtimi.  
  
-   Genişletilebilir: Gönderilebilen herhangi bir türü çalışır.  
  
-   Kullanışlı: Standart POSIX ve benzer biçim dizeleri.  
  
 C++ Boost.Format oluşturulmakla birlikte [iostreams](../standard-library/iostream-programming.md), güvenli ve Genişletilebilir olduğu, bunlar performansı iyileştirilmiş değil. Performans iyileştirmesi gerektirmediğinden, C göz önünde [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) ve [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md), hızlı ve kolaydır. Ancak, bunlar genişletilebilir veya güvenlik açıklarına karşı güvenli değildir. (Güvenli sürümleri var, ancak bunlar küçük performans cezasına sebep. Daha fazla bilgi için bkz: [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) ve [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)).  
  
 Aşağıdaki kod biçimlendirme özellikleri artırma bazılarını göstermektedir.  
  
```cpp  
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );  
    // s contains "hello hello world"    
  
    for( auto i = 0; i < names.size(); ++i )  
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];  
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789  
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ için yeniden Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)   
 [\<iostream >](../standard-library/iostream.md)   
 [\<sınırları >](../standard-library/limits.md)   
 [\<iomanip >](../standard-library/iomanip.md)
