---
title: 'Bit düzeyinde özel OR işleci: ^'
description: C++ standart dil özel veya işleç sözdizimi ve kullanımı.
ms.date: 09/21/2020
f1_keywords:
- xor_cpp
- ^
helpviewer_keywords:
- operators [C++], bitwise
- exclusive OR operator
- XOR operator
- bitwise operators [C++], OR operator
- ^ operator
- OR operator [C++], bitwise exclusive
- operators [C++], logical
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
ms.openlocfilehash: 4823c245ffca7032347e37c0c25c2963407733a7
ms.sourcegitcommit: f656092eebbcb148ca4d3b7a6a8508eff8f7e85f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836634"
---
# <a name="bitwise-exclusive-or-operator-"></a>Bit düzeyinde özel OR işleci: ^

## <a name="syntax"></a>Syntax

> *ifade* **`^`** *ifade*

## <a name="remarks"></a>Açıklamalar

Bit düzeyinde dışlamalı OR işleci ( **`^`** ), ilk işleneninin her bir bitini ikinci işleneninin karşılık gelen bitine karşılaştırır. İşlenenden birindeki bit 0 ise ve diğer işlenenin bit 1 ise, karşılık gelen sonuç biti 1 olarak ayarlanır. Aksi takdirde, karşılık gelen sonuç biti 0 olarak ayarlanır.

İşlecin her iki işleneni de İntegral türlerine sahip olmalıdır. [Standart dönüştürmelerde](standard-conversions.md) ele alınan Olağan aritmetik dönüştürmeler işlenenlere uygulanır.

**`^`** C++/CLI ve c++/cx içindeki karakterin diğer kullanımı hakkında daha fazla bilgi için bkz. [Handle to Object işleci (^) (c++/CLI ve c++/cx)](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md).

## <a name="operator-keyword-for-"></a>^ İçin işleç anahtar sözcüğü

C++, **`xor`** için alternatif bir yazım biçimi belirler **`^`** . C 'de alternatif yazım, üst bilgide bir makro olarak sağlanır \<iso646.h> . C++ ' da, alternatif yazım bir anahtar sözcüktür; \<iso646.h> C++ eşdeğeri veya kullanımı \<ciso646> kullanım dışıdır. Microsoft C++ ' da, [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) alternatif yazımı etkinleştirmek için veya derleyici seçeneği gereklidir.

## <a name="example"></a>Örnek

```cpp
// expre_Bitwise_Exclusive_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise exclusive OR
#include <iostream>
using namespace std;
int main() {
   unsigned short a = 0x5555;      // pattern 0101 ...
   unsigned short b = 0xFFFF;      // pattern 1111 ...

   cout  << hex << ( a ^ b ) << endl;   // prints "aaaa" pattern 1010 ...
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ yerleşik işleçleri, önceliği ve ilişkilendirilebilirlik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
