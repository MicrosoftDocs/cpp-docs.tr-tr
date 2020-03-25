---
title: 'Bit düzeyinde AND Işleci: &amp;'
ms.date: 11/04/2016
helpviewer_keywords:
- AND operator
- bitwise operators [C++], AND operator
- '& operator [C++], bitwise operators'
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
ms.openlocfilehash: b5c99d19be3461b10a1126dea3a45d308c0fc558
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181297"
---
# <a name="bitwise-and-operator-amp"></a>Bit düzeyinde AND Işleci: &amp;

## <a name="syntax"></a>Sözdizimi

```
expression & expression
```

## <a name="remarks"></a>Açıklamalar

İfadeler diğer ve ifadeleri ya da (aşağıda bahsedilen tür kısıtlamalarına tabidir) eşitlik ifadeleri, ilişkisel ifadeler, eklenebilir ifadeler, çarpma ifadeleri, üye ifadeleri işaretçisi, atama ifadeleri, Birli ifadeler, sonek ifadeleri veya birincil ifadeler.

Bit düzeyinde AND işleci ( **&** ), birinci işlenenin her bir bitini ikinci işlenenin karşılık gelen bitine göre karşılaştırır. Her iki bit de 1 ise, karşılık gelen sonuç biti 1 olarak ayarlanır. Aksi takdirde, karşılık gelen sonuç biti 0 olarak ayarlanır.

Bit düzeyinde AND işlecinin her iki işleneni de İntegral türünde olmalıdır. [Standart dönüşümlerde](standard-conversions.md)ele alınan Olağan aritmetik dönüştürmeler işlenenlere uygulanır.

## <a name="operator-keyword-for-"></a>& İçin işleç anahtar sözcüğü

**Bitand** işleci **&** metin eşdeğeridir. Programlarınızda **bitand** işlecine erişmenin iki yolu vardır: `iso646.h`üst bilgi dosyasını dahil edin veya [/za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırak) derleyici seçeneğiyle derleyin.

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
