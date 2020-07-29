---
title: Bit düzeyinde AND işleci:&amp;
description: C++ standart dil bit düzeyinde ve işleç sözdizimi ve kullanımı.
ms.date: 07/23/2020
f1_keywords:
- bitand_cpp
helpviewer_keywords:
- AND operator
- bitwise operators [C++], AND operator
- '& operator [C++], bitwise operators'
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
ms.openlocfilehash: 7e78e4003a31ee59ebd974275df784b7a76e73ce
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229122"
---
# <a name="bitwise-and-operator-amp"></a>Bit düzeyinde AND işleci:&amp;

## <a name="syntax"></a>Sözdizimi

> *ifade* **`&`** *ifade*

## <a name="remarks"></a>Açıklamalar

Bit düzeyinde AND işleci ( **`&`** ), birinci işlenenin her bir bitini ikinci işlenenin karşılık gelen bitine göre karşılaştırır. Her iki bit de 1 ise, karşılık gelen sonuç biti 1 olarak ayarlanır. Aksi takdirde, karşılık gelen sonuç biti 0 olarak ayarlanır.

Bit düzeyinde AND işlecinin her iki işleneni de İntegral türlerine sahip olmalıdır. [Standart dönüştürmelerde](standard-conversions.md) ele alınan Olağan aritmetik dönüştürmeler işlenenlere uygulanır.

## <a name="operator-keyword-for-"></a>& için işleç anahtar sözcüğü

C++, **`bitand`** için alternatif bir yazım biçimi belirler **`&`** . C 'de alternatif yazım, üst bilgide bir makro olarak sağlanır \<iso646.h> . C++ ' da, alternatif yazım bir anahtar sözcüktür; \<iso646.h>C++ eşdeğeri veya kullanımı \<ciso646> kullanım dışıdır. Microsoft C++ ' da, [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) alternatif yazımı etkinleştirmek için veya derleyici seçeneği gereklidir.

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

[C++ yerleşik işleçleri, önceliği ve ilişkilendirilebilirlik](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C bit düzeyinde işleçler](../c-language/c-bitwise-operators.md)
