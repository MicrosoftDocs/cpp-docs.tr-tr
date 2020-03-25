---
title: 'Bit Düzeyinde Özel OR İşleci: ^'
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], bitwise
- exclusive OR operator
- XOR operator
- bitwise operators [C++], OR operator
- ^ operator
- OR operator [C++], bitwise exclusive
- operators [C++], logical
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
ms.openlocfilehash: 9a44dc60a985729aae79ed0e2e48c44adace647b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190722"
---
# <a name="bitwise-exclusive-or-operator-"></a>Bit Düzeyinde Özel OR İşleci: ^

## <a name="syntax"></a>Sözdizimi

```
expression ^ expression
```

## <a name="remarks"></a>Açıklamalar

Bit düzeyinde dışlamalı OR işleci ( **^** ), ilk işleneninin her bir bitini ikinci işleneninin karşılık gelen bitine karşılaştırır. Bir bit 0 ise ve diğer bit 1 ise, karşılık gelen sonuç biti 1 olarak ayarlanır. Aksi takdirde, karşılık gelen sonuç biti 0 olarak ayarlanır.

Bit düzeyinde dışlamalı veya işlecin her iki işleneni de İntegral türünde olmalıdır. [Standart dönüştürmelerde](standard-conversions.md) ele alınan Olağan aritmetik dönüştürmeler işlenenlere uygulanır.

## <a name="operator-keyword-for-"></a>^ İçin işleç anahtar sözcüğü

**Xor** işleci **^** metin eşdeğeridir. Programlarınızda **Xor** işlecine erişmenin iki yolu vardır: `iso646.h`üst bilgi dosyasını dahil edin veya [/za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırak) derleyici seçeneğiyle derleyin.

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

[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
