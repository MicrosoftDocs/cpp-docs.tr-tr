---
title: Dize ve G/Ç Biçimlendirme (Modern C++)
description: Modern, biçimlendirilmiş dize g/ç kullanılabilir seçenekleri C++.
ms.date: 05/30/2019
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: e22c745798109a2dbef82297c45256593823f806
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450507"
---
# <a name="string-and-io-formatting-modern-c"></a>Dize ve G/Ç Biçimlendirme (Modern C++)

C++[ \<iostream >](../standard-library/iostream.md) biçimlendirilmiş dize g/ç sınıfları, İşlevler ve işleçler destekler. Örneğin, aşağıdaki kod nasıl ayarlanacağını gösterir `cout` tamsayının onaltılık çıkış biçimlendirmek için. İlk olarak, çünkü biçim durum için bir kez geçirilir daha sonra sıfırlamak için geçerli durumunu kaydeder `cout`, değiştirilene kadar bu şekilde kalır. Yalnızca bir kod satırı için geçerli değildir.

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

Bu yaklaşım, tür kullanımı uyumlu ve genişletilebilir, ancak aynı zamanda karmaşık ve ayrıntılı.

## <a name="alternative-format-options"></a>Diğer biçimlendirme seçenekleri

Alternatif olarak, kullandığınız `Boost.Format` Boost gelen C++ kitaplıklarını, standart dışı olsa bile. Boost kitaplıklarını indirebileceğiniz [Boost](https://www.boost.org/) Web sitesi.

Bazı avantajları `Boost.Format` şunlardır:

- Güvenli: Tür kullanımı uyumlu ve bir özel durum için hataları, örneğin, çok az veya çok fazla öğe belirtimi oluşturur.

- Genişletilebilir: Yapılabilen herhangi bir tür için çalışır.

- Kullanışlı: Standart Posix ve benzer biçim dizeleri.

Ancak `Boost.Format` üzerine kurulmuştur C++ [ \<iostream >](../standard-library/iostream-programming.md) güvenli ve genişletilebilir, özellikleri, bunlar olmayan performans için iyileştirilmiş. Performansı en iyi, C göz önünde bulundurun [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) ve [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md), hızlı ve kullanımı kolaydır. Ancak, bunlar genişletilebilir veya güvenlik açıklarına karşı güvenli değildir. (Güvenli sürümler var ancak bunlara küçük bir performans cezası uygulanmaz. Daha fazla bilgi için [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) ve [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)).

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

[C++'a (Modern C++) Tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)<br/>
[\<iostream >](../standard-library/iostream.md)<br/>
[\<sınırları >](../standard-library/limits.md)<br/>
[\<iomanip >](../standard-library/iomanip.md)
