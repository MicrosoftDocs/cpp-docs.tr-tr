---
title: Sol kaydırma ve sağ kaydırma işleçleri (&gt; &gt; ve &lt; &lt;) | Microsoft Docs
ms.custom: ''
ms.date: 08/13/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- <<
- '>>'
dev_langs:
- C++
helpviewer_keywords:
- << operator [C++], with specific objects
- left shift operators [C++]
- right shift operators [C++]
- bitwise-shift operators [C++]
- '>> operator'
- shift operators [C++]
- operators [C++], shift
ms.assetid: 25fa0cbb-5fdd-4657-8745-b35f7d8f1606
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a6c89e2550c01db695aa513a98d6d1cc8f116ca0
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2018
ms.locfileid: "42465274"
---
# <a name="left-shift-and-right-shift-operators-gtgt-and-ltlt"></a>Sol kaydırma ve sağ kaydırma işleçleri (&gt; &gt; ve &lt; &lt;)

Bit düzeyinde kaydırma işleçleri olan sağa kaydırma işleci (>>), bitlerini shift_expression *shift-expression* sağa ve sola kaydırma işleci (<<), bitlerini shift_expression *shift-expression* sol. <sup>1</sup>

## <a name="syntax"></a>Sözdizimi

> *Shift-expression* `<<` *additive-expression*  
> *Shift-expression* `>>` *additive-expression*

## <a name="remarks"></a>Açıklamalar

> [!IMPORTANT]
> Windows üzerinde aşağıdaki açıklamalar ve örnekler x86 ve x64 mimarileri için geçerlidir. Sola kaydırma ve sağa kaydırma işleçleri uygulaması üzerinde Windows ARM cihazları için önemli ölçüde farklıdır. Daha fazla bilgi için "Kaydırma işleçleri" bölümüne bakın. [Hello ARM](https://blogs.msdn.com/b/vcblog/archive/2012/10/25/hello-arm-exploring-undefined-unspecified-and-implementation-defined-behavior-in-c.aspx) blog gönderisi.

## <a name="left-shifts"></a>Sola Kaydırmalar

Sola kaydırma işleci neden olan bitler *shift-expression* sola tarafından belirtilen konum sayısına göre kaydırılmasına *additive-expression*. Kaydırma işleci tarafından boşaltılmış bit konumları sıfır dolguludur. Sola kaydırma mantıksal bir kaydırmadır (imza biti dahil, sona kaydırılan bitler atılır). Bit düzeyinde kaydırma türleri hakkında daha fazla bilgi için bkz: [bit düzeyinde kaydırmalar](https://en.wikipedia.org/wiki/Bitwise_shift).

Aşağıdaki örnek, işaretsiz sayıların kullanıldığı sola kaydırma işleçlerini gösterir. Bu örnek değeri bir bit kümesi olarak temsil eden bitlere ne olduğunu göstermektedir. Daha fazla bilgi için [bitset sınıfı](../standard-library/bitset-class.md).

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

İşaretli bir sayıyı sola kaydırırsanız, imza biti etkilenir ve sonuç tanımsız olur. Aşağıdaki örnek, bir 1 bit imza biti konumuna sola kaydırıldığında, Visual C++'ta ne olduğunu gösterir.

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

Sağa kaydırma işleci bit deseninde neden *shift-expression* sağ tarafından belirtilen konum sayısına göre kaydırılmasına *additive-expression*. İşaretsiz sayılar için, kaydırma işleci tarafından boşaltılmış bit konumları sıfır dolguludur. İşaretli sayılar için, imza biti boşaltılmış bit konumlarını doldurmak için kullanılır. Başka bir deyişle, sayı pozitif ise 0 kullanılır ve sayı negatif ise 1 kullanılır.

> [!IMPORTANT]
> İmzalı bir negatif sayının sağ kaydırmasının sonucu uygulama bağımlıdır. Visual C++ bitleri boşaltılmış konumları dolduracak şekilde kullansa da, başka bir uygulamanın da bunu yapacağının garantisi yoktur.

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

Bir kaydırma işlecinin her iki tarafındaki ifadelerin de tamsayı türünde olması gerekir. İntegral yükseltmeler açıklanan kurallara göre gerçekleştirilir [standart dönüştürmeler](standard-conversions.md). Sonucun türü yükseltilen tür ile aynıdır *shift-expression*.

Aşağıdaki örnekte, türünde bir değişken **char** için yükseltilmiş bir **int**.

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

## <a name="additional-details"></a>Ek Ayrıntılar

Bir kaydırma işleminin sonucu tanımsızdır *additive-expression* negatif veya *additive-expression* büyüktür veya eşittir bit sayısı kadar additive  *Shift-expression*. Hiçbir kaydırma işlemi gerçekleştirilmez *additive-expression* 0'dır.

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

<sup>1</sup> C ++ 11 ISO belirtimindeki (INCITS/ISO/IEC 14882-2011[2012]), bölüm 5.8.2 ve 5.8.3.kaydırma. kaydırma işleçlerinin açıklaması aşağıdadır

Değerini `E1 << E2` olduğu `E1` sola kaydırılacak `E2` bit konumlarıdır; Boşaltılan bitler sıfır dolguludur. Varsa `E1` bir işaretsiz türe sahipse sonuç değeri **E1 × 2**<sup>**E2**</sup>, indirgenmiş değerden en fazla sonuç türü içinde gösterilebilir. Aksi takdirde `E1` işaretli bir türe ve negatif olmayan değer vardır ve **E1 × 2**<sup>**E2** </sup> sonuç türü, karşılık gelen işaretsiz türünde temsil edilebilir ise Sonuç türüne dönüştürülür, bu değer sonuç değeri olan; Aksi durumda davranış tanımsız olur.

Değerini `E1 >> E2` olduğu `E1` sağa kaydırılacak `E2` bit konumlarıdır. Varsa `E1` bir işaretsiz türe sahipse veya `E1` işaretli bir türe ve negatif olmayan değere sahip, sonucun değeri sayının tamsayı kısmını **E1/2**<sup>**E2** </sup>. Varsa `E1` işaretli bir türe ve negatif bir değere sahipse, sonuç değeri uygulama tanımlanır.

## <a name="see-also"></a>Ayrıca bkz.

[İkili İşleçli İfadeler](../cpp/expressions-with-binary-operators.md)  
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)  
