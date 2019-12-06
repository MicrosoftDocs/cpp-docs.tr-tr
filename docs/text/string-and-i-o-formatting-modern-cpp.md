---
title: Dize ve G/Ç Biçimlendirme (Modern C++)
description: Modern C++olarak bulunan, biçimlendirilen dize g/ç için seçimler.
ms.date: 05/30/2019
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: 7ea858a8a8126d3754783edee0dd3ea5409e5f73
ms.sourcegitcommit: 6ddfb8be5e5923a4d90a2c0f93f76a27ce7ac299
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2019
ms.locfileid: "74898823"
---
# <a name="string-and-io-formatting-modern-c"></a>Dize ve G/Ç Biçimlendirme (Modern C++)

C++[\<iostream >](../standard-library/iostream.md) sınıfları, işlevleri ve işleçleri, biçimlendirilen dize g/ç 'sini destekler. Örneğin, aşağıdaki kod, onaltılı düzende çıkış yapmak için bir tamsayıyı biçimlendirmek üzere `cout` ayarlamayı gösterir. İlk olarak, daha sonra sıfırlamak için geçerli durumu kaydeder, çünkü biçim durumu `cout`geçirildiğinde, bu şekilde değiştirilene kadar kalır. Yalnızca tek bir kod satırı için geçerlidir.

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

Bu yaklaşım tür açısından güvenlidir ve genişletilebilir, ancak karmaşık ve ayrıntılıdır.

## <a name="alternative-format-options"></a>Alternatif biçim seçenekleri

Alternatif olarak, standart dışı olsa da, yükseltme C++ kitaplıklarından `Boost.Format` kullanabilirsiniz. [Boost Web sitesinden](https://www.boost.org/) herhangi bir artırma kitaplığı indirebilirsiniz.

`Boost.Format` avantajlarından bazıları şunlardır:

- Güvenli: tür kullanımı güvenli ve hatalar için bir özel durum oluşturur. Örneğin, çok az sayıda veya çok fazla öğe belirtimi.

- Genişletilebilir: Akışı yapılabilen herhangi bir tür için çalışır.

- Uygun: Standart POSIX ve benzer biçim dizeleri.

`Boost.Format`, güvenli ve Genişletilebilir C++ olan [\<iostream >](../standard-library/iostream-programming.md) tesislerinde oluşturulmuş olsa da, performans için iyileştirilmez. Performans iyileştirmesi gerektirdiğinde, hızlı ve kullanımı kolay olan C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) ve [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)' i değerlendirin. Ancak, güvenlik açıklarına göre Genişletilebilir veya güvenli değildir. (Güvenli sürümler var ancak performansta küçük bir düşüş oluşturabilir. Daha fazla bilgi için bkz. [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) ve [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)).

Aşağıdaki kod Boost biçimlendirme özelliklerinin bazılarını gösterir.

```cpp
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );
    // s contains "hello hello world"

    for( auto i = 0; i < names.size(); ++i )
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321
```

## <a name="see-also"></a>Ayrıca bkz.

[Uygulamasına geri hoş geldinizC++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)<br/>
[\<iostream >](../standard-library/iostream.md)<br/>
[\<sınırları >](../standard-library/limits.md)<br/>
[iomanıp > \<](../standard-library/iomanip.md)
