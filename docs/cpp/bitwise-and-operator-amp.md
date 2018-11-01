---
title: 'Bit düzeyinde AND işleci: &amp;'
ms.date: 11/04/2016
f1_keywords:
- bitand
helpviewer_keywords:
- AND operator
- bitwise operators [C++], AND operator
- '& operator [C++], bitwise operators'
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
ms.openlocfilehash: b7d0d73802a5af7ab71e980d73eaff5c5b3c4bb8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575363"
---
# <a name="bitwise-and-operator-amp"></a>Bit düzeyinde AND işleci: &amp;

## <a name="syntax"></a>Sözdizimi

```
expression & expression
```

## <a name="remarks"></a>Açıklamalar

İfadeler diğer ve ifadeleri, veya olabilir (aşağıda belirtilen türü kısıtlamalarına tabidir) eşitlik ifadeleridir, ilişkisel ifadeleri, ek ifadeleri, çarpma ifadeler, üye ifadeleri, cast ifadeleri birli işaretçisi deyimler, ifadeler veya birincil ifadeler sonek.

Bit düzeyinde AND işleci (**&**) karşılık gelen bit ikinci işlenenin ilk işlenenin her bitini karşılaştırır. Her iki bit 1 ise, karşılık gelen sonuç bit 1 olarak ayarlanır. Aksi takdirde, karşılık gelen sonuç bit 0 olarak ayarlanır.

Bit düzeyinde AND işleci iki işleneni de integral türünde olmalıdır. Olağan aritmetik dönüştürmeler ele [standart dönüştürmeler](standard-conversions.md), işlenenlere uygulanır.

## <a name="operator-keyword-for-"></a>İçin işleç anahtar sözcüğü &

**Bitand** işlecidir öğesinin metin eşdeğeridir **&**. Erişmenin iki yöntemi vardır **bitand** programlarınızda işleci: üstbilgi dosyasını dahil `iso646.h`, ya da derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırakma) derleyici seçeneği.

## <a name="example"></a>Örnek

```cpp
// expre_Bitwise_AND_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise AND
#include <iostream>
using namespace std;
int main() {
   unsigned short a = 0xFFFF;      // pattern 1111 ...
   unsigned short b = 0xAAAA;      // pattern 1010 ...

   cout  << hex << ( a & b ) << endl;   // prints "aaaa", pattern 1010 ...
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C Bit Düzeyinde İşleçler](../c-language/c-bitwise-operators.md)