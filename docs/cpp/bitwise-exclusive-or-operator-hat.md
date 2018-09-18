---
title: 'Bit düzeyinde özel OR işleci: ^ | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], bitwise
- exclusive OR operator
- XOR operator
- bitwise operators [C++], OR operator
- ^ operator
- OR operator [C++], bitwise exclusive
- operators [C++], logical
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76c1863b9e27c1ec28206a5734f7301f077df678
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064830"
---
# <a name="bitwise-exclusive-or-operator-"></a>Bit Düzeyinde Özel OR İşleci: ^

## <a name="syntax"></a>Sözdizimi

```
expression ^ expression
```

## <a name="remarks"></a>Açıklamalar

Bit düzeyinde özel OR işleci (**^**) karşılık gelen bit ikinci işlenenin ilk işlenenin her bitini karşılaştırır. Bir bit 0'dır ve 1 diğer bit ise, karşılık gelen sonuç bit 1 olarak ayarlanır. Aksi takdirde, karşılık gelen sonuç bit 0 olarak ayarlanır.

Bit düzeyinde dışlamalı OR işlecinin her iki işlenen, integral türde olmalıdır. Olağan aritmetik dönüştürmeler ele [standart dönüştürmeler](standard-conversions.md) işlenenlere uygulanır.

## <a name="operator-keyword-for-"></a>İçin işleç anahtar sözcüğü ^

**Xor** işlecidir öğesinin metin eşdeğeridir **^**. Erişmenin iki yöntemi vardır **xor** programlarınızda işleci: üstbilgi dosyasını dahil `iso646.h`, ya da derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırakma) derleyici seçeneği.

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