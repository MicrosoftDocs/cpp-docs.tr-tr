---
title: Dize ve G/Ç Biçimlendirme (Modern C++)
description: Modern C++'da biçimlendirilmiş string I/O seçenekleri mevcuttur.
ms.date: 05/30/2019
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: a3fc93b0baf414759eb50c787c4057fb85dcb370
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375780"
---
# <a name="string-and-io-formatting-modern-c"></a>Dize ve G/Ç Biçimlendirme (Modern C++)

C++ [ \<iostream>](../standard-library/iostream.md) sınıfları, işlevleri ve işleçleri biçimlendirilmiş string I/O'yı destekler. Örneğin, aşağıdaki kod, bir `cout` tamsediyi hexadecimal çıktısına biçimlendirecek şekilde nasıl ayarlanır. İlk olarak, biçim durumu geçirildiği için, daha sonra sıfırlamak `cout`için geçerli durumu kaydeder, çünkü biçim durumu geçirildiği nde, değiştirilene kadar bu şekilde kalır. Sadece tek kod satırı için geçerli değildir.

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

Bu yaklaşım tür güvenli ve genişletilebilir, ama aynı zamanda karmaşık ve ayrıntılı.

## <a name="alternative-format-options"></a>Alternatif biçim seçenekleri

Alternatif olarak, standart `Boost.Format` olmayan olsa da Boost C++ kitaplıklarından kullanabilirsiniz. Herhangi bir Boost kitaplığını [Boost](https://www.boost.org/) web sitesinden indirebilirsiniz.

Bazı avantajları `Boost.Format` şunlardır:

- Güvenli: Tür güvenli ve hatalar için bir özel durum atar, örneğin, çok az veya çok fazla öğe belirtimi.

- Genişletilebilir: Akış yapılabilen herhangi bir tür için çalışır.

- Uygun: Standart POSIX ve benzeri biçim dizeleri.

Güvenli `Boost.Format` ve genişletilebilir C++ [ \<iostream>](../standard-library/iostream-programming.md) tesisleri üzerine inşa edilmiş olsa da, performans açısından optimize edilmezler. Performans optimizasyonu gerektirdiğinde, hızlı ve kullanımı kolay C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) ve [sprintf'i](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)göz önünde bulundurun. Ancak, bunlar genişletilebilir veya güvenlik açıklarından güvenli değildir. (Güvenli sürümleri var, ancak hafif bir performans cezası tabi. Daha fazla bilgi için [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) ve [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l)](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)bakın.

Aşağıdaki kod, Bazı Artır biçimlendirme özelliklerini gösterir.

```cpp
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );
    // s contains "hello hello world"

    for( auto i = 0; i < names.size(); ++i )
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321
```

## <a name="see-also"></a>Ayrıca bkz.

[C++'a tekrar hoş geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Referansı](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplık](../standard-library/cpp-standard-library-reference.md)<br/>
[\<iostream>](../standard-library/iostream.md)<br/>
[\<sınırlar>](../standard-library/limits.md)<br/>
[\<iomanip>](../standard-library/iomanip.md)
