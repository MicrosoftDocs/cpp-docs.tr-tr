---
title: 'Bit düzeyinde kapsamlı OR işleci: &#124;'
description: C++ standart dil bit düzeyinde kapsamlı veya işleç sözdizimi ve kullanımı.
ms.date: 07/23/2020
f1_keywords:
- '|'
- bitor_cpp
helpviewer_keywords:
- OR operator [C++], bitwise inclusive
- bitwise operators [C++], OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
ms.openlocfilehash: 76f80c2101b3acfac71dc4d8ad1be4a999f69aa5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229096"
---
# <a name="bitwise-inclusive-or-operator-124"></a>Bit düzeyinde kapsamlı OR işleci: &#124;

## <a name="syntax"></a>Sözdizimi

> *İfade1* **`|`** *İfade2*

## <a name="remarks"></a>Açıklamalar

Bit düzeyinde kapsamlı OR işleci ( **`|`** ), ilk işleneninin her bir bitini ikinci işleneninin karşılık gelen bitine karşılaştırır. Her iki bit de 1 ise, karşılık gelen sonuç biti 1 olarak ayarlanır. Aksi takdirde, karşılık gelen sonuç biti 0 olarak ayarlanır.

İşlecin her iki işleneni de İntegral türlerine sahip olmalıdır. [Standart dönüştürmelerde](standard-conversions.md) ele alınan Olağan aritmetik dönüştürmeler işlenenlere uygulanır.

## <a name="operator-keyword-for-124"></a>&#124; için işleç anahtar sözcüğü

C++, **`bitor`** için alternatif bir yazım biçimi belirler **`|`** . C 'de alternatif yazım, üst bilgide bir makro olarak sağlanır \<iso646.h> . C++ ' da, alternatif yazım bir anahtar sözcüktür; \<iso646.h>C++ eşdeğeri veya kullanımı \<ciso646> kullanım dışıdır. Microsoft C++ ' da, [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) alternatif yazımı etkinleştirmek için veya derleyici seçeneği gereklidir.

## <a name="example"></a>Örnek

```cpp
// expre_Bitwise_Inclusive_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise inclusive OR
#include <iostream>
using namespace std;

int main() {
   unsigned short a = 0x5555;      // pattern 0101 ...
   unsigned short b = 0xAAAA;      // pattern 1010 ...

   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ yerleşik işleçleri, önceliği ve ilişkilendirilebilirlik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C bit düzeyinde işleçler](../c-language/c-bitwise-operators.md)
