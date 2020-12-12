---
description: 'Daha fazla bilgi edinin: sola kaydırma ve sağ kaydırma Işleçleri ( &gt; &gt; ve &lt; &lt; )'
title: Sol kaydırma ve sağ kaydırma Işleçleri ( &gt; &gt; ve &lt; &lt; )
ms.date: 08/13/2018
f1_keywords:
- <<
- '>>'
helpviewer_keywords:
- << operator [C++], with specific objects
- left shift operators [C++]
- right shift operators [C++]
- bitwise-shift operators [C++]
- '>> operator'
- shift operators [C++]
- operators [C++], shift
ms.assetid: 25fa0cbb-5fdd-4657-8745-b35f7d8f1606
ms.openlocfilehash: e13333d178fdfbb44631b9a2aced9ed2a48ad871
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321024"
---
# <a name="left-shift-and-right-shift-operators-gtgt-and-ltlt"></a>Sol kaydırma ve sağ kaydırma Işleçleri ( &gt; &gt; ve &lt; &lt; )

Bit düzeyinde kaydırma işleçleri sağ SHIFT işleçtir (), bu, Shift-ifadesinin bitlerini **&gt;&gt;** sağa  ve sola kaydırma işleci ( **&lt;&lt;** ) ile sola kayar.  <sup>1</sup>

## <a name="syntax"></a>Syntax

> *SHIFT ifadesi* `<<` *Toplamsal ifadesi*\
> *SHIFT ifadesi* `>>` *Toplamsal ifadesi*

## <a name="remarks"></a>Açıklamalar

> [!IMPORTANT]
> Aşağıdaki açıklamalar ve örnekler, Windows için x86 ve x64 mimarileri için geçerlidir. Sol SHIFT ve sağ kaydırma işleçlerinin uygulanması, ARM cihazlarda Windows için önemli ölçüde farklıdır. Daha fazla bilgi için [Merhaba ARM](https://devblogs.microsoft.com/cppblog/hello-arm-exploring-undefined-unspecified-and-implementation-defined-behavior-in-c/) blog gönderisinin "kaydırma işleçleri" bölümüne bakın.

## <a name="left-shifts"></a>Sola Kaydırmalar

Sol SHIFT işleci, *SHIFT ifadesindeki* bitlerin, *DITIVE ifadesi* tarafından belirtilen konum sayısına göre sola kaydırmasına neden olur. Kaydırma işleci tarafından boşaltılmış bit konumları sıfır dolguludur. Sola kaydırma mantıksal bir kaydırmadır (imza biti dahil, sona kaydırılan bitler atılır). Bit düzeyinde vardiyaların türleri hakkında daha fazla bilgi için bkz. [bit düzeyinde vardiyalar](https://en.wikipedia.org/wiki/Bitwise_shift).

Aşağıdaki örnek, işaretsiz sayıların kullanıldığı sola kaydırma işleçlerini gösterir. Bu örnek değeri bir bit kümesi olarak temsil eden bitlere ne olduğunu göstermektedir. Daha fazla bilgi için bkz. [bitset Class](../standard-library/bitset-class.md).

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    unsigned short short1 = 4;
    bitset<16> bitset1{short1};   // the bitset representation of 4
    cout << bitset1 << endl;  // 0b00000000'00000100

    unsigned short short2 = short1 << 1;     // 4 left-shifted by 1 = 8
    bitset<16> bitset2{short2};
    cout << bitset2 << endl;  // 0b00000000'00001000

    unsigned short short3 = short1 << 2;     // 4 left-shifted by 2 = 16
    bitset<16> bitset3{short3};
    cout << bitset3 << endl;  // 0b00000000'00010000
}
```

İşaretli bir sayıyı sola kaydırırsanız, imza biti etkilenir ve sonuç tanımsız olur. Aşağıdaki örnek, bir 1 bit, işaret biti konumuna sola kaydırdığınızda ne olacağını gösterir.

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    short short1 = 16384;
    bitset<16> bitset1(short1);
    cout << bitset1 << endl;  // 0b01000000'00000000

    short short3 = short1 << 1;
    bitset<16> bitset3(short3);  // 16384 left-shifted by 1 = -32768
    cout << bitset3 << endl;  // 0b10000000'00000000

    short short4 = short1 << 14;
    bitset<16> bitset4(short4);  // 4 left-shifted by 14 = 0
    cout << bitset4 << endl;  // 0b00000000'00000000
}
```

## <a name="right-shifts"></a>Sağa Kaydırmalar

Sağ SHIFT işleci, *SHIFT ifadesindeki* bit deseninin, *eklenebilir ifade* tarafından belirtilen konum sayısına göre sağa kaydırmasına neden olur. İşaretsiz sayılar için, kaydırma işleci tarafından boşaltılmış bit konumları sıfır dolguludur. İşaretli sayılar için, imza biti boşaltılmış bit konumlarını doldurmak için kullanılır. Başka bir deyişle, sayı pozitif ise 0 kullanılır ve sayı negatif ise 1 kullanılır.

> [!IMPORTANT]
> İmzalı bir negatif sayının sağ kaydırmasının sonucu uygulama bağımlıdır. Microsoft C++ derleyicisi, karıştırılmış bit konumlarını doldurmaları için işaret bitini kullansa da, diğer uygulamaların da bunu yapacağının garantisi yoktur.

Bu örnek, işaretsiz sayıların kullanıldığı sağa kaydırma işleçlerini gösterir:

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    unsigned short short11 = 1024;
    bitset<16> bitset11{short11};
    cout << bitset11 << endl;     // 0b00000100'00000000

    unsigned short short12 = short11 >> 1;  // 512
    bitset<16> bitset12{short12};
    cout << bitset12 << endl;     // 0b00000010'00000000

    unsigned short short13 = short11 >> 10;  // 1
    bitset<16> bitset13{short13};
    cout << bitset13 << endl;     // 0b00000000'00000001

    unsigned short short14 = short11 >> 11;  // 0
    bitset<16> bitset14{short14};
    cout << bitset14 << endl;     // 0b00000000'00000000
}
```

Sonraki örnek, pozitif işaretli sayılara sahip sağa kaydırma işleçlerini gösterir.

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    short short1 = 1024;
    bitset<16> bitset1(short1);
    cout << bitset1 << endl;     // 0b00000100'00000000

    short short2 = short1 >> 1;  // 512
    bitset<16> bitset2(short2);
    cout << bitset2 << endl;     // 0b00000010'00000000

    short short3 = short1 >> 11;  // 0
    bitset<16> bitset3(short3);
    cout << bitset3 << endl;     // 0b00000000'00000000
}
```

Sonraki örnek, negatif işaretli tamsayılara sahip sağa kaydırma işleçlerini gösterir.

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    short neg1 = -16;
    bitset<16> bn1(neg1);
    cout << bn1 << endl;  // 0b11111111'11110000

    short neg2 = neg1 >> 1; // -8
    bitset<16> bn2(neg2);
    cout << bn2 << endl;  // 0b11111111'11111000

    short neg3 = neg1 >> 2; // -4
    bitset<16> bn3(neg3);
    cout << bn3 << endl;  // 0b11111111'11111100

    short neg4 = neg1 >> 4; // -1
    bitset<16> bn4(neg4);
    cout << bn4 << endl;  // 0b11111111'11111111

    short neg5 = neg1 >> 5; // -1
    bitset<16> bn5(neg5);
    cout << bn5 << endl;  // 0b11111111'11111111
}
```

## <a name="shifts-and-promotions"></a>Kaydırmalar ve Yükseltmeler

Bir kaydırma işlecinin her iki tarafındaki ifadelerin de tamsayı türünde olması gerekir. Integral yükseltmeler, [Standart dönüşümlerde](standard-conversions.md)açıklanan kurallara göre gerçekleştirilir. Sonucun türü, yükseltilen *kaydırma ifadesinin* türüyle aynı olur.

Aşağıdaki örnekte, türünde bir değişken **`char`** bir sürümüne yükseltilir **`int`** .

```cpp
#include <iostream>
#include <typeinfo>

using namespace std;

int main() {
    char char1 = 'a';

    auto promoted1 = char1 << 1;   // 194
    cout << typeid(promoted1).name() << endl;  // int

    auto promoted2 = char1 << 10;  // 99328
    cout << typeid(promoted2).name() << endl;  // int
}
```

## <a name="additional-details"></a>Ek ayrıntılar

Ek *ifade* negatifse veya (yükseltilen) *SHIFT ifadesinde* bit sayısından büyük veya buna *eşitse, bir* vardiya işleminin sonucu tanımsız olur. *Toplamsal ifade* 0 ise hiçbir vardiya işlemi gerçekleştirilmez.

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    unsigned int int1 = 4;
    bitset<32> b1{int1};
    cout << b1 << endl;    // 0b00000000'00000000'00000000'00000100

    unsigned int int2 = int1 << -3;  // C4293: '<<' : shift count negative or too big, undefined behavior
    unsigned int int3 = int1 >> -3;  // C4293: '>>' : shift count negative or too big, undefined behavior
    unsigned int int4 = int1 << 32;  // C4293: '<<' : shift count negative or too big, undefined behavior
    unsigned int int5 = int1 >> 32;  // C4293: '>>' : shift count negative or too big, undefined behavior
    unsigned int int6 = int1 << 0;
    bitset<32> b6{int6};
    cout << b6 << endl;    // 0b00000000'00000000'00000000'00000100 (no change)
}
```

## <a name="footnotes"></a>Dipnotlar

<sup>1</sup> C++ 11 ISO belirtiminde (INCITS/ISO/IEC 14882-2011 [2012]), 5.8.2 ve 5.8.3 bölümlerine kaydırma işleçleri açıklaması aşağıda verilmiştir.

Değeri `E1 << E2` `E1` sola kaydırılan `E2` bit konumlardır; karıştırılmış bitler sıfır doldurulur. `E1`İmzasız bir tür varsa, sonucun değeri **E1 × 2**<sup>**E2**</sup>, en az mod ise sonuç türündeki maksimum değer gösterilebilir tablosundan bir daha fazla. Aksi halde, `E1` imzalı bir tür ve negatif olmayan bir değer varsa ve **E1 × 2**<sup>**E2**</sup> , sonuç türünün karşılık gelen imzasız türünde gösterilebilir ise, bu değer sonuç türüne dönüştürülür, sonuçta elde edilen değerdir; Aksi takdirde, davranış tanımsızdır.

Değeri, `E1 >> E2` `E1` sağa kaydırılan `E2` bit konumlara sahiptir. `E1`İmzasız bir tür varsa veya imzalı bir `E1` türe ve negatif olmayan bir değere sahipse, sonucun değeri **E1/2**<sup>**E2**</sup>bölümünün integral kısmıdır. `E1`İmzalı bir tür ve negatif bir değer varsa, elde edilen değer uygulama tanımlı olur.

## <a name="see-also"></a>Ayrıca bkz.

[Ikili Işleçlere sahip ifadeler](../cpp/expressions-with-binary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
