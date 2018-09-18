---
title: 'Bit düzeyinde AND işleci: &amp; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bitand
dev_langs:
- C++
helpviewer_keywords:
- AND operator
- bitwise operators [C++], AND operator
- '& operator [C++], bitwise operators'
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8967861ab6ac4e6b6fafd11eea22e67de339ea8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111387"
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