---
title: Dize ve g-Ç biçimlendirme (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: 0cc0c84a6e4ffac3e6a80425039bfcc1db567911
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631851"
---
# <a name="string-and-io-formatting-modern-c"></a>Dize ve G/Ç Biçimlendirme (Modern C++)

C++ [iostreams](../standard-library/iostream.md) biçimlendirilmiş dize g/ç yeteneğine sahiptir. Örneğin, aşağıdaki kod önce geçerli durumun kaydedilmesi ve daha sonra bir kez cout için durum biçimlendirme geçirilir, bu, yalnızca bir satır için değiştirilene kadar bu şekilde kalacağından yeniden ayarlama onaltılı çıkış için bir tamsayı biçimlendirmek için cout ayarlama işlemini gösterir kodu.

```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main() 
{
    ios state(nullptr);

    cout << "The answer in decimal is: " << 42 << endl;

    state.copyfmt(cout); // save current formatting
    cout << "In hex: 0x" // now load up a bunch of formatting modifiers
        << hex 
        << uppercase 
        << setw(8) 
        << setfill('0') 
        << 42            // the actual value we wanted to print out
        << endl;
    cout.copyfmt(state); // restore previous formatting
}
```

Bu tamamen, çoğu durumda çok kullanışsız. Alternatif olarak, standart dışı olsa bile Boost C++ kitaplıklarından Boost.Format kullanabilirsiniz. Boost kitaplıklarını indirebileceğiniz [Boost](http://www.boost.org/) Web sitesi.

Boost.Format avantajlarından bazıları şunlardır:

- Güvenli: Tür açısından güvenlidir ve hatalar için bir özel durum oluşturur; Örneğin, çok az veya çok fazla öğe belirtimi.

- Genişletilebilir: Yapılabilen herhangi bir türü çalışır.

- Kullanışlı: Standart Posix ve benzer biçim dizeleri.

Boost.Format C++ üzerinde kurulmuş olmasına rağmen [iostreams](../standard-library/iostream-programming.md), güvenli ve Genişletilebilir olan, bunlar performans iyileştirme yapılmamıştır. Performansı en iyi, C göz önünde bulundurun [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) ve [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md), hızlı ve kullanımı kolaydır. Ancak, bunlar genişletilebilir veya güvenlik açıklarına karşı güvenli değildir. (Güvenli sürümler var ancak bunlara küçük bir performans cezası uygulanmaz. Daha fazla bilgi için [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) ve [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)).

Aşağıdaki kod Boost biçimlendirme özelliklerinin bazılarını gösterir.

```cpp
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );
    // s contains "hello hello world"  

    for( auto i = 0; i < names.size(); ++i )
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)<br/>
[\<iostream >](../standard-library/iostream.md)<br/>
[\<sınırları >](../standard-library/limits.md)<br/>
[\<iomanip >](../standard-library/iomanip.md)